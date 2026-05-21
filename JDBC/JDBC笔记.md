

## 概念

**JDBC（Java Database Connectivity，Java数据库连接）** 是 Java 语言中用来规范客户端程序如何访问数据库的**应用程序接口（API）**。它是 Java 标准库（Java SE）的一部分，由一系列用 Java 语言编写的类和接口组成。

用最通俗的话来解释：**JDBC 就是 Java 世界里连接数据库的“万能适配器”或“标准插座”。**


### 1. 为什么需要 JDBC？（解决什么痛点）


![[JDBC笔记.png]]



在没有 JDBC 之前，如果世界上有十种数据库（如 MySQL、Oracle、SQL Server 等），它们各自的连接方式、底层协议和 API 都是完全不同的。如果你用 Java 写了一个程序，原本连的是 MySQL，后来公司决定换成 Oracle，你就必须把所有涉及数据库连接和交互的代码全部推翻重写。

为了解决这种混乱，Sun 公司（现为 Oracle）制定了 JDBC 规范。JDBC 规定了 Java 操纵数据库的统一标准。

- **对 Java 开发者而言**：你只需要学习 JDBC 这一套标准接口（比如怎么建立连接、怎么发送 SQL、怎么接收结果），不需要关心底层是什么数据库。
    
- **对数据库厂商而言**：MySQL、Oracle 等厂商必须按照 JDBC 的规范，自己编写一个“翻译器”（这个翻译器就叫 **数据库驱动，Database Driver**）。驱动负责把标准的 JDBC 请求翻译成它们自家数据库能听懂的私有协议。
    

### 2. JDBC 的核心工作原理

JDBC 的架构采用的是“面向接口编程”的思想，主要分为两层：

- **接口层（JDBC API）**：这是面向开发者的。比如 `Connection`（连接）、`Statement`（执行 SQL）、`ResultSet`（结果集）。这些全都是 Java 官方定义好的**接口**，没有具体实现。
    
- **驱动层（Driver）**：这是面向厂商的。厂商的驱动程序实现了上述接口。当你的 Java 程序调用 `Connection.createStatement()` 时，实际上运行的是厂商驱动里的具体实现代码。
    

当你的程序运行时，JDBC 内部的 **DriverManager（驱动管理器）** 会像一个调度中心一样，根据你提供的数据库 URL（例如 `jdbc:mysql://...`），自动找到对应的厂商驱动，从而拉起一条通往数据库的管道。

### 3. 经典的操作流程

虽然现在有很多高级框架，但原生 JDBC 的核心操作雷打不动就这几步：

1. **建立连接**：通过账号、密码和数据库地址（URL），让 `DriverManager` 给你分配一个 `Connection` 对象。
    
2. **创建执行对象**：通过连接对象创建一个“送信官”（`Statement` 或 `PreparedStatement`），用来存放你要执行的 SQL 语句。
    
3. **执行 SQL**：让“送信官”带着 SQL 语句去数据库执行。如果是查询，数据库会返回一行行的数据。
    
4. **处理结果**：Java 用一个叫 `ResultSet`（结果集）的对象来接收返回的数据，你可以通过循环一行行地读取字段。
    
5. **关闭资源**：数据库连接是非常宝贵的服务器资源，用完之后必须把结果集、执行对象和连接按顺序关闭。
    

### 4. 现代开发中 JDBC 的地位

**JDBC 是所有 Java 数据库操作的基石。**

虽然现在我们在实际开发中很少直接手写原生的 JDBC 代码（因为它的模板代码太冗长，每次都要手动捕获异常、手动关闭连接、手动把结果集转换成 Java 对象），而是使用诸如 **MyBatis**、**Hibernate** 或 **Spring Data JPA** 这样的高级持久层框架。

但是，**这些框架的底层无一例外全都是基于 JDBC 封装的**。它们只是帮你把那些枯燥的、重复的 JDBC 代码给自动化了。理解了 JDBC 的原理，你才能真正明白这些高级框架底层是如何与数据库通信的。



---
---


## 入门代码


这是一个最基础、最标准的 MySQL JDBC 连接示例。

在运行这段代码之前，请确保你的项目中已经引入了 **MySQL 驱动 Jar 包**（例如 `mysql-connector-j`）。

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.sql.SQLException;

public class JdbcQuickStart {
    public static void main(String[] args) {
        // 1. 配置数据库连接信息
        // 注意：jdbc:mysql://localhost:3306/ 后面跟的是你的数据库名称
        String url = "jdbc:mysql://localhost:3306/test_db?useSSL=false&serverTimezone=UTC";
        String username = "root";
        String password = "your_password"; // 替换为你的数据库密码

        // 要执行的 SQL 语句
        String sql = "SELECT id, name, age FROM users WHERE id = ?";

        // 2. 使用 try-with-resources 自动关闭资源 (Java 7 后的推荐写法)
        // 把需要关闭的资源定义在 try() 中，代码执行完毕后会自动释放，省去了复杂的 close() 和 try-catch
        try (
            // A. 建立与数据库的连接
            Connection conn = DriverManager.getConnection(url, username, password);
            
            // B. 创建预编译的 SQL 执行对象（比普通的 Statement 更安全，能防止 SQL 注入）
            PreparedStatement pstmt = conn.prepareStatement(sql)
        ) {
            System.out.println("数据库连接成功！");

            // 3. 设置 SQL 语句中的参数（用实际值替换 SQL 中的第一个问号 `?`）
            pstmt.setInt(1, 1); // 假设我们要查询 id 为 1 的用户

            // 4. 执行查询，并用 ResultSet (结果集) 接收数据库返回的表格数据
            try (ResultSet rs = pstmt.executeQuery()) {
                
                // 5. 循环遍历结果集（rs.next() 判断是否还有下一行数据，有则指针下移一行）
                while (rs.next()) {
                    // 通过列名获取当前行的字段值
                    int id = rs.getInt("id");
                    String name = rs.getString("name");
                    int age = rs.getInt("age");

                    // 打印输出结果
                    System.out.println("查询结果 -> ID: " + id + ", 姓名: " + name + ", 年龄: " + age);
                }
            }

        } catch (SQLException e) {
            System.err.println("数据库操作发生异常！");
            e.printStackTrace();
        }
        // 6. 运行到这里，ResultSet、PreparedStatement、Connection 已经按顺序自动关闭了
    }
}
```

### 两个新手必须注意的细节：


![[JDBC笔记-1.png]]


1. **不再需要 `Class.forName()`**：你可能在很多老教程里看到第一步必须写 `Class.forName("com.mysql.cj.jdbc.Driver")`。其实从 **JDBC 4.0 (Java 6)** 开始，Java 引入了 SPI 机制，只要你的项目中放了 MySQL 驱动的 Jar 包，`DriverManager` 就会**自动加载驱动**，这行代码现在可以完全不写。
    
2. **时区与加密问题**：如果连接报错，通常是 URL 的参数问题。上面代码 URL 里的 `serverTimezone=UTC` 是指定时区，`useSSL=false` 是关闭安全证书警告，这两个参数在连接本地 MySQL 5.7 或 8.0+ 时非常实用。


---
---


## API详解——DriverManager



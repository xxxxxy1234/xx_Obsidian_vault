

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


在 JDBC 的整个世界里，`DriverManager`（驱动管理器）扮演着“大总管”或“调度中心”的角色。它是你编写的 Java 程序与底层各种数据库驱动之间的桥梁。

下面为你详细拆解这个核心类的主要职责、常用 API、内部机制以及现代开发中的变化。

### 1. DriverManager 的核心职责

`DriverManager` 的工作非常纯粹，主要就两件事：

1. **管理驱动**：把各种数据库厂商提供的驱动（Driver）登记注册在自己这里。
    
2. **建立连接**：当你给它一个数据库地址（URL）时，它负责在注册表里挑选出合适的驱动，帮你打通一条通往数据库的物理管道（返回 `Connection` 对象）。
    

![[JDBC笔记-2.png]]


![[JDBC笔记-3.png]]

### 2. 常用 API 详解

`DriverManager` 的所有方法都是**静态方法（static）**，你不需要实例化它，直接调用即可。最常用的有以下几个：

#### ① `getConnection(String url, String user, String password)`

这是最核心的方法，用来获取数据库连接。

- **参数**：
    
    - `url`：数据库连接字符串（不同数据库格式不同，如 `jdbc:mysql://...` 或 `jdbc:oracle:thin:...`）。
        
    - `user`：数据库用户名。
        
    - `password`：数据库密码。
        
- **返回值**：一个实现了 `Connection` 接口的数据库连接对象。
    
- **异常**：如果连接失败（用户名密码错、网络不通、未找到驱动等），会抛出 `SQLException`。
    

_(注：它还有一个重载版本 `getConnection(String url, java.util.Properties info)`，可以把用户名、密码和其他配置参数封装在 `Properties` 对象里传入。)_

#### ② `registerDriver(Driver driver)`

- **作用**：向 `DriverManager` 注册一个新的数据库驱动。
    
- **现实情况**：开发中**几乎不需要我们手动调用这个方法**。因为厂商的驱动类（比如 MySQL 的 `com.mysql.cj.jdbc.Driver`）在它自己的静态代码块里已经默认调用了 `DriverManager.registerDriver(this)`。也就是说，只要该驱动类被加载，它就会自己把自己注册上去。
    

#### ③ `setLoginTimeout(int seconds)` / `getLoginTimeout()`

- **作用**：设置或获取等待数据库连接建立的**超时时间**（单位：秒）。
    
- **场景**：如果数据库服务器挂了，或者网络极慢，程序不能无限期死等。通过这个方法可以限制最长等待时间，超时则直接抛出异常。
    

### 3. 深入底层：它是如何找到对应驱动的？

当你调用 `DriverManager.getConnection("jdbc:mysql://localhost:3306/db", "root", "123")` 时，`DriverManager` 内部是如何知道该用 MySQL 驱动，而不是 Oracle 驱动的呢？

其内部有一个有趣的“毛遂自荐”机制：

```
+---------------------------------------------------------+
|                  DriverManager 内部                     |
|                                                         |
|  [ 驱动列表 (Registered Drivers) ]                      |
|  - OracleDriver                                         |
|  - PostgreSQLDriver                                     |
|  - MySqlDriver  <-- 只有它认识 "jdbc:mysql://"           |
+---------------------------------------------------------+
       |
       | 1. 遍历列表，逐个询问：
       |    "这条 URL 'jdbc:mysql://...' 你们谁认识？"
       |
       v
  OracleDriver   --> "我不认识，不归我管。" (返回 null)
  MySqlDriver    --> "我认识！这是我的地盘，我来连！" (返回 Connection)
```

1. `DriverManager` 内部维护了一个已经注册的驱动列表。
    
2. 当你传入一条 URL 时，它会调用 `for` 循环，**遍历**列表中的每一个驱动对象。
    
3. 它会调用驱动自带的 `acceptsURL(url)` 方法询问：“你认识这个 URL 吗？”
    
4. 比如 Oracle 驱动一看开头是 `jdbc:mysql`，就会拒绝；轮到 MySQL 驱动时，它识别出这是自己的协议，就会主动接单，并负责创建真实的连接返回给 `DriverManager`。
    

### 4. 时代变迁：现代 Java 中的自动加载机制 (SPI)

这涉及到一个经典的面试题或技术演进：**“为什么现在不需要写 `Class.forName()` 了？”**

#### 过去（JDBC 4.0 之前，Java 5 及以前）：

我们必须在代码第一行硬编码写上：

```java
Class.forName("com.mysql.cj.jdbc.Driver"); // 强行加载驱动类
```

**原理**：这行代码的作用是让 JVM 去寻找并加载这个类。前面说到，驱动类内部有静态代码块，一旦被加载就会自动向 `DriverManager` 注册。如果不写这行，`DriverManager` 内部的驱动列表就是空的，就会报错 `No suitable driver found`。

#### 现在（JDBC 4.0 之后，Java 6 及以后）：

你直接写 `DriverManager.getConnection()` 就能成功，上面那行不写也完全没事。

**原理**：Java 引入了 **SPI (Service Provider Interface) 机制**。

当你引入了 MySQL 的 Jar 包后，你可以解压它，在 `META-INF/services/` 目录下会发现一个名为 `java.sql.Driver` 的配置文件，里面的内容只有一行，就是该驱动类的全限定名：`com.mysql.cj.jdbc.Driver`。

当你的程序第一次调用 `DriverManager` 时，它会利用 `ServiceLoader` **自动去扫描**你项目所有 Jar 包里的这个指定配置文件，把里面写好的驱动类全部自动加载并注册掉。

### 总结

你可以把 `DriverManager` 理解为一个“无知但严谨的接线员”。它自己不知道怎么连 MySQL 还是 Oracle，但它手里有一本各大厂商主动登记的通讯录。你把连接需求（URL）报给它，它就挨个翻通讯录问谁能接这个活，确认后把电话线递到你手里（返回 `Connection`），它的任务就圆满完成了。


---
---


## API详解——Connection



如果说 `DriverManager` 的角色是帮你打通电话的“接线员”，那么 **`Connection`（数据库连接接口）** 就是那条**已经建立好的“电话线”**。

在 JDBC 中，`Connection` 对象代表了 Java 程序与特定数据库之间的一个**物理会话（Session）**。所有的 SQL 语句执行、事务管理，都必须依赖这个连接对象才能进行。

下面为你深度拆解 `Connection` 接口的核心职责、常用 API、最重要的事务管理机制，以及生产环境中的最佳实践。

### 1. Connection 的核心职责

`Connection` 接口主要承担三大核心任务：

1. **控制会话状态**：管理连接的开启、关闭、超时以及只读状态。
    
2. **创建执行对象**：它是 `Statement`、`PreparedStatement` 和 `CallableStatement` 的**工厂**，没有连接就无法创建这些执行 SQL 的对象。
    
3. **管理事务（Transaction）**：这是 `Connection` 最灵魂的功能，Java 层的事务提交、回滚完全由它控制。
    


![[JDBC笔记-4.png]]


![[JDBC笔记-5.png]]

### 2. 常用 API 详解

`Connection` 是一个接口，具体的实现类由数据库厂商（如 MySQL 的 `ConnectionImpl`）提供。我们日常开发中最常用的方法可以分为三类：

#### ① 创建 SQL 执行对象（工厂方法）

- **`prepareStatement(String sql)`** _(最常用)_
    
    - **作用**：创建一个 `PreparedStatement` 对象，用于向数据库发送**预编译**的 SQL 语句。
        
    - **优势**：支持占位符 `?`，能防止 SQL 注入，且效率更高。
        
- **`createStatement()`**
    
    - **作用**：创建一个基本的 `Statement` 对象，用于发送普通的、无参数的静态 SQL 语句。目前生产中已极少使用。
        
- **`prepareCall(String sql)`**
    
    - **作用**：创建一个 `CallableStatement` 对象，用于调用数据库的**存储过程（Stored Procedures）**。
        

#### ② 事务管理方法（核心）

- **`setAutoCommit(boolean autoCommit)`**
    
    - **作用**：开启或关闭**自动提交模式**。
        
    - **注意**：JDBC **默认是开启（true）自动提交的**，意味着你每执行一条 `executeUpdate()`，数据库就会立刻把它持久化。如果你要开启一个包含多条 SQL 的事务，必须先调用 `setAutoCommit(false)`。
        
- **`commit()`**
    
    - **作用**：提交当前事务，让上一次提交后的所有修改在数据库中永久生效。
        
- **`rollback()`**
    
    - **作用**：回滚当前事务，撤销当前事务中所有未提交的修改。通常写在 `catch` 块中。
        

#### ③ 连接状态与元数据

- **`close()`**
    
    - **作用**：立即释放此 `Connection` 对象的数据库和 JDBC 资源，而不是等待它们被垃圾回收（GC）。
        
- **`isClosed()`**
    
    - **作用**：判断当前连接是否已经被关闭。
        
- **`getMetaData()`**
    
    - **作用**：返回一个 `DatabaseMetaData` 对象，通过它可以获取非常底层的数据库信息（如：数据库版本、支持哪些特性、当前用户权限等）。
        

### 3. 核心机制：如何在 JDBC 中控制事务？

在实际业务（如银行转账：A 扣钱，B 加钱）中，多条 SQL 必须作为一个整体，要么全成功，要么全失败。JDBC 通过 `Connection` 实现这一机制的标准模板如下：


```java
Connection conn = null;
try {
    conn = DriverManager.getConnection(url, user, pass);
    
    // 1. 【核心】关闭自动提交，正式开启事务
    conn.setAutoCommit(false); 
    
    // 执行业务 SQL 1：给 A 扣钱 100 元
    // 执行业务 SQL 2：给 B 加钱 100 元
    
    // 2. 如果一切顺利，手动提交事务
    conn.commit(); 
    System.out.println("转账成功，事务已提交！");
    
} catch (Exception e) {
    // 3. 一旦中间任何一步发生异常，立刻回滚整个事务
    if (conn != null) {
        try {
            conn.rollback();
            System.err.println("发生异常，事务已回滚，数据未受影响。");
        } catch (SQLException ex) {
            ex.printStackTrace();
        }
    }
    e.printStackTrace();
} finally {
    // 4. 无论成功失败，恢复默认的自动提交状态（在使用连接池时这很重要），并关闭连接
    if (conn != null) {
        try {
            conn.setAutoCommit(true); 
            conn.close();
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}
```

### 4. 生产环境下的重要认知：不要频繁开关 Connection

在新手阶段，我们习惯了“用时拿连接，用完立马 `.close()`”。但在真实的生产环境中，**绝对不能这样做**。

#### 为什么建立 Connection 很慢？

因为 `Connection` 代表的是一次真实的**网络物理连接**（通常基于 TCP/IP 协议）。每当你调用一次 `DriverManager.getConnection()`，底层都要经历：

1. 三次握手建立 TCP 连接。
    
2. 数据库服务器的身份验证（校验用户名、密码）。
    
3. 数据库为该会话分配内存、初始化资源。
    

这个过程非常耗时（通常需要几十毫秒甚至更久）。在高并发的网站中，如果一秒有 1000 个请求，每个请求都去新建、销毁连接，数据库服务器的 CPU 会瞬间被拉满，系统直接卡死。

#### 解决方案：引入数据库连接池（Connection Pool）

为了解决这个问题，现代工业界普遍使用**连接池**技术（如 **HikariCP**（Spring Boot 默认）、Druid 等）。

```
+--------------------------------------------------------+
|                      连接池 (Pool)                      |
|                                                        |
|  [ 空闲连接管道 ] [ 空闲连接管道 ] [ 空闲连接管道 ]   |
+--------------------------------------------------------+
       ^                                          |
       | 2. 用完归还 (调用 close())               | 1. 借出连接
       |                                          v
+--------------------------------------------------------+
|                   你的业务代码 (Thread)                 |
+--------------------------------------------------------+
```

- **工作原理**：程序启动时，连接池会预先向数据库申请一批 `Connection`（比如 10 个）放在池子里。
    
- **获取连接**：你需要用连接时，不再找 `DriverManager`，而是向连接池“借”一个已经建好的空闲连接。
    
- **关闭连接（核心骗局）**：当你调用 `connection.close()` 时，连接池在底层做了解析拦截——**它并没有真正断开与数据库的物理连接，而是悄悄把这个连接标记为空闲，放回池子里供下一个请求复用。**
    

### 总结

- `Connection` 是 Java 代码和数据库通信的**生命线**。
    
- 它是创建 `PreparedStatement` 对象的**工厂**。
    
- 控制事务的秘诀在于：`setAutoCommit(false)` 开启 -> 顺利则 `commit()` -> 失败则 `rollback()`。
    
- 生产环境严禁频繁建立物理连接，必须通过**连接池**来管理和复用 `Connection` 对象。

---
---



## API详解——Statement



在 JDBC 的世界里，虽然现代开发中我们更倾向于使用它的子接口，但 **`Statement`（基本语句执行接口）** 是所有 SQL 执行对象的鼻祖与基石。

它扮演的角色是连接之上的“直通车”或“基础送信官”。它的核心职责非常简单：**接收你拼接好的完整 SQL 字符串，直接发送到数据库中执行，并将结果原封不动地带回来。**


### 1. Statement 的核心职责

`Statement` 接口的设计初衷是为了处理**静态的、不需要传递参数的 SQL 语句**。它的工作流程是纯线性的：

1. **打包发送**：将 Java 层的纯文本 SQL 字符串直接打包，通过 `Connection` 管道扔给数据库。
    
2. **静待结果**：等待数据库完成 `解析 -> 编译 -> 执行` 的全套动作。
    
3. **带回数据**：根据 SQL 的类型，将执行结果（受影响行数或数据表）封装并带回给 Java 程序。
    

### 2. 常用 API 详解

`Statement` 的核心方法主要围绕“执行 SQL”和“管理执行状态”展开，全部为实例方法，通过 `connection.createStatement()` 创建。

#### ① 核心执行方法

- **`executeQuery(String sql)`**
    
    - **作用**：专门用于执行**查询**语句（`SELECT`）。
        
    - **返回值**：一个 `ResultSet`（结果集）对象，包含符合查询条件的数据。
        
    - **限制**：如果传入增删改语句（如 `UPDATE`），会抛出 `SQLException`。
        
- **`executeUpdate(String sql)`**
    
    - **作用**：专门用于执行**数据更新**或**结构定义**语句（`INSERT`、`UPDATE`、`DELETE`、`CREATE TABLE`、`DROP TABLE` 等）。
        
    - **返回值**：一个 `int` 整数，代表**受影响的行数**（Row Count）。如果是 DDL 语句（如建表），则返回 0。
        
- **`execute(String sql)`**
    
    - **作用**：万能执行方法，可以执行任何 SQL 语句。通常在编写通用数据库工具或不确定 SQL 类型时使用。
        
    - **返回值**：`boolean` 类型。
        
        - 返回 `true`：说明执行的是查询，后面需要调用 `getResultSet()` 提取数据。
            
        - 返回 `false`：说明执行的是增删改，后面需要调用 `getUpdateCount()` 查看受影响行数。
            

#### ② 最大返回限制与超时控制

- **`setMaxRows(int max)`** / `getMaxRows()`
    
    - **作用**：限制 `ResultSet` 对象可以包含的**最大行数**。
        
    - **场景**：防止意外执行了无条件的大表查询（如 `SELECT * FROM big_table`）导致 Java 内存溢出（OOM）。超出限制的数据会被直接丢弃。
        
- **`setQueryTimeout(int seconds)`** / `getQueryTimeout()`
    
    - **作用**：设置数据库执行该语句的**超时等待时间**（单位：秒）。
        
    - **场景**：如果某条 SQL 因为数据库死锁或索引缺失导致执行极慢，通过此方法可以强行中断该操作并抛出异常，防止阻塞 Java 业务线程。
        

#### ③ 批处理操作

- **`addBatch(String sql)`**：将一条完整的 SQL 语句加入到当前 `Statement` 的批处理命令列表中。
    
- **`executeBatch()`**：一次性将批处理列表中的所有 SQL 发送给数据库执行，返回一个 `int[]` 数组，记录每条 SQL 受影响的行数。
    
- **`clearBatch()`**：清空当前批处理列表。
    

### 3. 致命局限性：为什么它在现代开发中被冷落？

理解 `Statement` 的缺陷，是理解整个 JDBC 演进史的关键。它在处理“带参数的动态 SQL”时存在两个无法调和的矛盾：

#### ❌ 痛点一：极度痛苦的“字符串拼接”

当 SQL 语句需要引入 Java 变量时，你必须使用 `+` 号进行硬拼接。这会导致代码中充斥着大量的单引号、双引号和加号：

```java
// 假设要插入一个用户，代码会变成极其混乱的“套娃”：
String sql = "INSERT INTO users (name, age, city) VALUES ('" + name + "', " + age + ", '" + city + "')";
stmt.executeUpdate(sql);
```

这种代码不仅可读性极差，而且极其容易漏掉单引号而导致语法错误。

#### ❌ 痛点二：致命的“SQL 注入攻击”

因为 `Statement` 只是机械地将你拼好的字符串送给数据库解析，它无法分辨什么是“执行命令”，什么是“用户数据”。

假设有一段登录验证代码：

```java
String sql = "SELECT * FROM users WHERE username = '" + inputName + "' AND password = '" + inputPass + "'";
```

如果恶意攻击者在前端输入框输入：

- 用户名：`admin' OR '1'='1`
    
- 密码：随便输
    

经过 `Statement` 拼接后的 SQL 会变成：

```sql
SELECT * FROM users WHERE username = 'admin' OR '1'='1' AND password = '123'
```

由于 `OR '1'='1'` 永远成立，数据库的逻辑被直接攻破，攻击者无需密码就能以管理员身份登录。

### 4. Statement 的现代剩余价值

既然它缺点明显，为什么 JDBC 还没有把它删掉？因为在某些**特定场景**下，它依然是最简单、最高效的选择：

1. **执行纯静态、无参数的 SQL**：例如程序启动时初始化数据库，执行一个固定的建表脚本、创建索引脚本，或者清空某张临时表（`TRUNCATE TABLE temp_data`）。
    
2. **多条不同结构的 SQL 批处理**：它的子接口通常只能对同一个 SQL 骨架进行数据批处理。如果你想在一个批次里**同时执行不同的操作**（比如先执行一条 `INSERT`，再执行一条 `UPDATE`，最后执行一条 `DELETE`），只有原生的 `Statement.addBatch(String sql)` 能够做到。
    

### 总结

- `Statement` 是 JDBC 最基础的 SQL 发送器，专为**无参数的静态 SQL** 而生。
    
- 它通过 `executeQuery` 搞定查询，通过 `executeUpdate` 搞定增删改。
    
- 它的致命软肋在于**动态拼串麻烦**且**无法防范 SQL 注入攻击**。
    
- 在现代 Java 体系中，除了一些不带参数的 DDL 脚本执行或异构 SQL 批处理，它基本已经退居幕后。


---
---


## 补充：什么是SQL注入


**SQL 注入（SQL Injection，简称 SQLi）** 是一种非常经典且危害极大的网络安全漏洞。

简单来说，它的本质是：**恶意的攻击者利用了程序逻辑的漏洞，把“带有特殊含义的数据库命令”伪装成“普通的输入数据”，欺骗服务器去执行，从而非法控制、窃取或破坏后端的数据库。**

它的核心根源在于：**后端程序没有做到“数据与命令分离”，错把恶意用户输入的数据当成了 SQL 命令的一部分来解析执行。**

### 一个经典的 SQL 注入演练

为了让你秒懂，我们来看一个最常见的“登录验证”场景。

#### 1. 正常的后台代码逻辑

假设后台程序员写了一条基于字符串拼接的 SQL 语句来验证用户登录：


```sql
SELECT * FROM users WHERE username = '用户输入的用户名' AND password = '用户输入的密码'
```

- **正常情况**：用户输入用户名 `jack`，密码 `123456`。
    
- **拼出的 SQL**：
    
    
    
    ```sql
    SELECT * FROM users WHERE username = 'jack' AND password = '123456'
    ```
    
    数据库一查，账号密码对得上，允许登录。这没任何问题。
    

#### 2. 遭受攻击的情况

如果一个懂安全的黑客来到登录页面，他故意在用户名输入框里输入了这一段看似奇怪的文本：

- **用户名输入**：`admin' OR '1'='1`
    
- **密码输入**：随便填（比如 `abc`）
    

当后台傻乎乎地再次进行字符串拼接时，神奇的事情发生了，最终生成的 SQL 变成了：

仔细看这条 SQL 的后半部分：


```sql
... WHERE username = 'admin' OR '1'='1' AND password = 'abc'
```

在数据库的逻辑运算符优先级中，`AND` 的优先级高于 `OR`。所以这条语句被拆解为两个判断条件：

1. 条件一：`username = 'admin'`
    
2. 条件二：`'1'='1' AND password = 'abc'` （因为 `'1'='1'` 永远为真，所以只要密码对不上，这部分就是假）
    

但是！因为中间有一个 **`OR`** 连着，整个 `WHERE` 子句的最终逻辑变成了：

> **(条件一 成立)** 或者 **(条件二 成立)**

由于 `'1'='1'` 这个恒等式永远为真，导致整个条件判定直接被永久判定为 **`true`**！数据库根本不再关心密码对不对，直接把用户名为 `admin` 的那一行数据通过验证并返回给了前端，黑客在没有密码的情况下，成功绕过验证，直接登录了管理员账号。

### SQL 注入的巨大危害

如果仅仅是绕过登录，那还只是冰山一角。攻击者一旦在你的输入框内拿到了自由构建 SQL 语句的权力，他们还可以做这些事：

- **拖库（窃取数据）**：使用 `UNION` 操作符，强行把整张用户表（包含身份证、银行卡、密码明文或哈希）的数据跟当前查询拼接在一起，一次性全部打包带走。
    
- **删库/破坏数据**：在输入框末尾加一个分号 `;` 截断前一句，紧接着加上 `DROP TABLE users;` 顺手把你的整个数据表彻底抹去。
    
- **远程控制服务器**：某些数据库（如 SQL Server、MySQL）如果配置了高权限，黑客可以通过注入命令直接调用操作系统的 shell，在你的服务器上植入木马，把你的整台服务器变成他的肉鸡。
    

### 如何彻底防御 SQL 注入？

既然危害这么大，怎么防范？其实经过这么多年的发展，防御 SQL 注入的技术已经非常成熟，核心思想只有一句话：**绝对不要相信用户的任何输入！**

#### 1. 参数化查询 / 预编译（最核心、最完美的解法）

这也是我们在学习 JDBC 时，**强调必须使用 `PreparedStatement` 而不是 `Statement`** 的核心原因。

- **原理**：在执行前，先把 SQL 的骨架发给数据库进行编译固定。此时数据库已经明确了哪里是“命令”，哪里是“参数占位符 `?`”。
    
- **结果**：当黑客再次输入 `admin' OR '1'='1` 时，数据库**只会把它当成一个长长的、奇形怪状的字符串用户名**去比对，绝对不会把它里面的 `OR` 当成命令来执行。
    

#### 2. 使用现代的 ORM 框架

现代开发使用的 **MyBatis**（使用 `#{}` 占位符）、**Hibernate**、**Spring Data JPA** 等框架，其底层默认全部都采用了参数化查询的预编译机制，天然免疫大部分 SQL 注入。

_(注：在 MyBatis 中如果错误使用了 `${}` 符号，它依然会变成原始的字符串拼接，从而引发注入风险。)_

#### 3. 输入验证与过滤

对用户输入的数据进行严格的校验。比如限制年龄输入框只能输入数字，注册用户名不能包含单引号 `'`、分号 `;`、双减号 `--` 等 SQL 关键字。

#### 4. 最小权限原则

不要让你的 Java 程序用 `root` 或 `sa` 等数据库超级管理员账号去连接数据库。给 Web 应用分配一个只具备 `SELECT`、`INSERT`、`UPDATE` 核心权限的低权限账号。这样哪怕不幸被注入，黑客也无法执行删库或控制服务器等高危操作。




---
---

## API详解——ResultSet



在 JDBC 的工作流中，`DriverManager` 帮我们打通了电话（`Connection`），`Statement` 帮我们把请求传了过去，而 **`ResultSet`（结果集接口）** 就是数据库给你回信时，寄过来的那个“数据包裹”。

当执行查询语句（`SELECT`）后，数据库会返回一张虚拟的表格，`ResultSet` 就是在 Java 语言中封装并操纵这张表格的**核心接口**。它扮演着“数据指针与翻译官”的角色。

下面为你详细拆解 `ResultSet` 的工作机制、核心 API、数据类型转换以及注意事项。

### 1. ResultSet 的核心职责

`ResultSet` 的结构非常像一张数据库表，有行（Row）和列（Column）。但它并不是把数据库里的几万条数据一次性全部加载到 Java 内存中，它的底层工作极其克制：

1. **控制光标（Cursor）**：内部维护了一个“行光标”（或叫指针）。刚拿到对象时，光标指向**第一行数据的前面（Before First Row）**。
    
2. **数据解析与翻译**：提供了一系列的 `get` 方法，负责将数据库底层的二进制数据，翻译转换成 Java 里的 `String`、`int`、`Date` 等具体的对象类型。
    

![[JDBC笔记-6.png]]


### 2. 常用 API 详解

`ResultSet` 的方法主要分为两类：**光标移动方法** 和 **获取列数据方法**。

#### ① 光标移动方法（控制看哪一行）

- **`next()`** _(最核心、最常用)_
    
    - **作用**：将光标从当前行向前移动一行。
        
    - **返回值**：`boolean` 类型。如果新的一行有数据，返回 `true`；如果已经到了表格末尾没有数据了，返回 `false`。
        
    - **经典用法**：配合 `while` 循环遍历整张表。
        
- **高级光标控制（需连接配置支持）**
    
    - `previous()`：光标向后退一行。
        
    - `absolute(int row)`：光标直接跳到指定的第几行（1 代表第一行，-1 代表最后一行）。
        
    - `first()` / `last()`：光标直接跳到第一行或最后一行。
        
    - _(注意：默认情况下 ResultSet 是“只读且只能向前滚动”的，调用这些高级方法需要创建 Statement 时进行特殊配置。)_
        

#### ② 获取列数据方法（控制拿哪个字段）

`ResultSet` 提供了极其丰富的 `getXxx()` 方法，其中 `Xxx` 代表你希望转换成的 Java 数据类型：

- **常用数据类型获取**：
    
    - `getString(int columnIndex / String columnLabel)`：获取字符串（可对应 MySQL 的 `varchar`、`text`）。
        
    - `getInt(int columnIndex / String columnLabel)`：获取整数（对应 `int`、`tinyint`）。
        
    - `getDouble(int columnIndex / String columnLabel)`：获取浮点数（对应 `double`、`decimal`）。
        
    - `getTimestamp(int columnIndex / String columnLabel)`：获取时间戳（对应 `datetime`、`timestamp`）。
        
- **传参的两种方式（索引 vs 列名）**：
    
    每个 `get` 方法都有两种重载形式，比如拿名字：
    
    1. **根据列名（推荐）**：`rs.getString("username")`。可读性极高，即便 SQL 调整了字段查询顺序，代码也不会垮。
        
    2. **根据索引（从 1 开始）**：`rs.getString(2)`。代表获取当前行的第 2 列。执行效率略高一点点，但极其容易数错，不便于维护。
        

### 3. 经典遍历模版

当你从 `Statement` 拿到 `ResultSet` 后，标准的处理代码如下：


```java
// 执行查询
ResultSet rs = stmt.executeQuery("SELECT id, username, create_time FROM users");

// 遍历结果集
while (rs.next()) { 
    // 每次进入循环，光标都精准停留在某一行
    
    // 提取当前行的各个字段数据
    int id = rs.getInt("id");
    String name = rs.getString("username");
    java.sql.Timestamp createTime = rs.getTimestamp("create_time");
    
    // 将其打印或者封装成 Java Bean 对象
    System.out.println("用户: " + id + " | 名字: " + name + " | 注册时间: " + createTime);
}

// 用完记得关闭它
rs.close();
```

### 4. 两个高频踩坑点与底层认知

#### ❌ 坑点一：在没有调用 `next()` 之前直接取数据

很多新手拿到 `ResultSet` 后非常兴奋，直接调用：

```java
ResultSet rs = stmt.executeQuery("SELECT name FROM users WHERE id = 1");
String name = rs.getString("name"); // 💥 直接报错：Before start of result set
```

**原因**：正如前面所说，刚拿到的 `ResultSet` 光标停在第一行**之前**（第 0 行），这里没有任何数据。哪怕你的结果集里只有 1 条数据，你也必须先调用一次 `rs.next()` 让光标走到第一行，才能正常取值。单条数据通常配合 `if (rs.next()) { ... }` 使用。

#### ❌ 坑点二：数据库的 NULL 值被包装成了 Java 的 0

在数据库中，一个 `age` 字段（`int` 类型）如果是 `NULL`（代表用户没填）。

当你调用 `int age = rs.getInt("age");` 时，Java 没办法让基础数据类型 `int` 变成 `null`，于是 **JDBC 驱动会自动帮你把它转换成 `0`**。

这在业务上会引发灾难（没填年龄变成了 0 岁）。

**解决方案**：

1. **方法一（使用包装类 + `wasNull()`）**：

    ```java
    int age = rs.getInt("age");
    Integer realAge = null;
    if (!rs.wasNull()) { // wasNull() 检查上一次 get 的字段在数据库里是不是 NULL
        realAge = age;
    }
    ```

2. **方法二（直接 getObject）**：

```java
Integer realAge = rs.getObject("age", Integer.class); // 直接拿到包装类，可为 null
```


---

### 总结

*   `ResultSet` 是 Java 里的**虚拟数据表**，它依赖**行光标**单向向下移动来读取数据。
*   每次取数据前，**必须先通过 `next()` 移动光标**。
*   通过 `getXxx("列名")` 的方式将数据库字段类型翻译为 Java 对象。
*   对于数据库中的 `NULL` 值要格外小心，基础类型（如 `int`）接收会变成 `0`，建议使用 `getObject()` 或包装类处理。


---
---



## API详解——PreparedStatement



在 JDBC 的世界里，如果说 `Statement` 是一个只管送信、不管安全的“初级邮差”，那么 **`PreparedStatement`（预编译语句执行接口）** 就是配备了装甲、能够完美防弹的“特级镖师”。

它是 `Statement` 的子接口。在现代 Java 开发中，**无论是出于安全考虑还是性能考虑，它都是执行 SQL 的绝对核心与唯一标准。**


### 1. PreparedStatement 的核心职责

`PreparedStatement` 专为动态 SQL（带参数的 SQL）**而生。它的工作流程采用了**“参数占位符”机制，主要承担两大职责：

1. **结构与数据分离**：在创建时，先将不带参数的 SQL 骨架发给数据库进行“预编译”，锁定语法结构。
    
2. **安全填装参数**：编译完成后，再将具体的 Java 变量强行解释为纯数据（不参与语法解析）填入占位符，安全地发给数据库执行。
    

### 2. 常用 API 详解

`PreparedStatement` 的方法主要集中在 **“为占位符 `?` 设值”** 以及 **“高效执行”** 上。

#### ① 参数设置方法（Setters）

针对不同的数据类型，它提供了极度丰富的 `setXxx(int parameterIndex, Xxx x)` 方法。

- **参数规律**：
    
    - 第一个参数 `parameterIndex`：代表 SQL 语句中**第几个问号 `?`**，**索引从 1 开始**。
        
    - 第二个参数 `x`：要填入的具体 Java 变量值。
        
- **常用设值方法**：
    
    - `setInt(int index, int x)`：设置整数。
        
    - `setString(int index, String x)`：设置字符串。自动处理单引号转义，防止 SQL 注入。
        
    - `setDouble(int index, double x)`：设置浮点数。
        
    - `setTimestamp(int index, java.sql.Timestamp x)`：设置日期和精准时间。
        
    - `setObject(int index, Object x)`：万能设值方法。会自动根据 Java 对象的类型映射到对应的数据库类型。如果变量可能为 `null`，这个方法非常实用。
        

#### ② 执行方法（无参版本）

由于在创建 `PreparedStatement` 时已经把 SQL 语句传给 `Connection` 了，因此它的执行方法**全部不需要传入 SQL 字符串**：

- `executeQuery()`：执行查询，返回 `ResultSet`。
    
- `executeUpdate()`：执行增删改，返回受影响行数。
    

### 3. 核心机制：什么是“预编译”？为什么它能防注入？

理解“预编译”是掌握 JDBC 的分水岭。我们用一个登录验证的例子来看看它在底层做了什么：

```java
// 1. 【预编译阶段】将带占位符的骨架发给数据库
String sql = "SELECT * FROM users WHERE username = ? AND password = ?";
PreparedStatement pstmt = conn.prepareStatement(sql);
```

此时，数据库拿到这个骨架，立刻执行词法分析、语法解析。数据库在底层已经做了一个决定：**“这条 SQL 的语法结构已经死锁，`username` 和 `password` 后面对应的两个问号，只能是纯字符串数据，绝对不可能是执行命令。”**


```java
// 2. 【设值阶段】黑客试图输入带有 SQL 注入命令的字符串
pstmt.setString(1, "admin' OR '1'='1");
pstmt.setString(2, "123");

// 3. 【执行阶段】发送纯参数
ResultSet rs = pstmt.executeQuery();
```

当黑客输入的 `admin' OR '1'='1` 被传入时，由于数据库的语法树已经生成完毕，`PreparedStatement` 驱动层会对单引号 `'` 等敏感字符进行彻底转义（解释为纯文本）。

数据库**只会机械地去用户表中寻找一个“名字长成 `admin' OR '1'='1` 的怪异用户”**。因为根本找不到这个用户，所以查询失败，SQL 注入攻击宣告彻底失效。

### 4. 性能双飞翼：性能缓存与批处理优化

除了安全性，`PreparedStatement` 在性能上也对 `Statement` 形成了降维打击。

#### ① 性能缓存 (Server-side Prepare)

如果你要循环执行 10,000 次插入操作：

- **使用 `Statement`**：数据库必须痛苦地重复执行 10,000 次语法解析、编译优化，CPU 直接飙升。
    
- **使用 `PreparedStatement`**：数据库只在第 1 次时编译了 SQL 骨架，并将其缓存起来。接下来的 9,999 次，数据库只需要接收纯参数，然后直接套用缓存的编译结果去执行。这使得性能得到了质的提升。
    

#### ② 批处理模版 (Batch Processing)

结合事务关闭与批处理，`PreparedStatement` 可以在大批量数据导入时发挥出极佳的性能：

```java
String sql = "INSERT INTO orders (user_id, amount) VALUES (?, ?)";
try (PreparedStatement pstmt = conn.prepareStatement(sql)) {
    // 1. 关闭自动提交，开启事务，这是批处理提速的关键
    conn.setAutoCommit(false); 

    for (int i = 1; i <= 5000; i++) {
        pstmt.setInt(1, i);
        pstmt.setDouble(2, 99.9 * i);
        
        // 2. 将当前参数包攒到批处理缓存中，不和数据库交互
        pstmt.addBatch(); 

        // 每 1000 条打包向数据库发送一次，防止 Java 内存溢出
        if (i % 1000 == 0) {
            pstmt.executeBatch(); // 3. 集中发送执行
            pstmt.clearBatch();   // 4. 清空缓存，迎接下一批
        }
    }
    conn.commit(); // 5. 最终手动提交事务
}
```

### 总结

- **工作方式**：先发骨架编译（`conn.prepareStatement(sql)`），再填入参数（`pstmt.setXxx()`），最后无参执行（`pstmt.executeQuery()`）。
    
- **核心优势**：
    
    1. **无解的安全性**：利用**预编译语法树锁死**的技术，让一切 SQL 注入攻击沦为纯字符串文本，彻底杜绝注入。
        
    2. **极高的可读性**：告别恶心的单双引号拼接，代码像填空题一样整洁。
        
    3. **恐怖的执行性能**：支持数据库端编译缓存，配合 `addBatch()` 批处理，是海量数据操作的唯一选择。

[阿里巴巴Java开发手册](https://developer.aliyun.com/ebook/386/read?spm=a2c6h.26392459.ebook-detail.2.63392867CQCErU)
# 命名

① 变量 / 方法：**小驼峰 camelCase**
	String userName;
	 int userAge; 
	 void getUserInfo() {}

② 类 / 接口：**大驼峰 PascalCase**
	class UserInfo {} 
	interface UserService {}

③ 常量：**小写或大写蛇形**
	user_name;
	db_connection;
	MAX_COUNT;
	

④**串式 (kebab-case)**
	单词全小写，用连字符连接。因连字符`-`会与减号冲突，不能用于大多数编程语言的变量名，但常用于URL或HTML属性
	<div user-profile>
	 ....
	 </div>

---
---





# 快捷键

按F2可以快速对文件重命名

命令行里按上下键可以快速使用刚刚的命令

psvm或main快速输出public static void main

sout快速输出System.out.println


“数组名.fori ” 可以快速打出for循环遍历数组元素
“数组名.forr ” 可以快速打出for循环反向遍历数组元素
“数字.fori ”可以快速打出for循环遍历从0到这个数
字符串要用“名字.length().fori”，“名字.charAT(i)”*i表示索引*可获取字符串的内容

shift+F6统一修改变量名
ctrl+/行注释
ctrl+shift+/块注释
ctrl+d快速复制一行
ctrl+p光标置于方法参数括号中，可浏览到需要哪些参数
ctrl+alt+m自动抽取方法（将一段代码总结成方法）
Home光标快速移动到行首
End光标快速移动到行尾
ctrl+Home移动到文件开头
ctrl+End移动到文件末尾
ctrl+ait+L格式化代码
ctrl+ait+V光标放在这一行，快速给方法返回值赋值（自动命名）
按住alt加上鼠标左键向下拖动可批量修改（比如统一修改变量名）

---
---





# IDEA项目结构


### 一、核心逻辑层级（Project / Module / Package）

IDEA 里最关键的三层关系：

1. **Project（项目 / 工程）**
    
    - 整个项目的根容器，对应一个文件夹。
    - 管理全局配置、SDK、项目级库、模块列表JetBrains。
    
2. **Module（模块）**
    
    - 项目下的独立功能单元，可单独编译、运行、测试。
    - 一个 Project 可以包含多个 Module（多模块项目），也可以只有一个默认 Module。
    - 每个 Module 有自己的 `.iml` 配置文件。
    
3. **Package（包）**
    
    - 代码的逻辑分组，对应磁盘上的目录结构（如 `com.example.demo`）。
    
4. **Class（类 / 文件）**
    
    - 具体的 `.java`、`.kt`、`.properties` 等文件。
    

---

### 二、标准目录结构（Java/Maven/Gradle 通用）

一个典型的 IDEA 项目目录如下：

your-project/                # 项目根目录（Project）
├── .idea/                   # IDEA 自动生成的配置目录（勿手动改）
│   ├── modules.xml          # 模块列表与配置
│   ├── workspace.xml        # 工作区布局、运行配置
│   ├── libraries/           # 项目级库配置
│   └── misc.xml             # 杂项设置（编码、代码风格等）
├── module-name/             # 模块目录（多模块项目会有多个）
│   ├── .iml                 # 模块专属配置文件
│   ├── src/                 # 源代码根目录
│   │   ├── main/            # 生产代码（业务逻辑）
│   │   │   ├── java/        # Java/Kotlin 源码（按包结构存放）
│   │   │   ├── resources/   # 配置文件、静态资源（properties、XML、图片等）
│   │   │   └── webapp/      # Web 项目专用（WEB-INF、html、js 等）
│   │   └── test/            # 测试代码（JUnit、单元测试）
│   │       ├── java/        # 测试源码
│   │       └── resources/   # 测试专用资源
│   ├── lib/                 # 手动引入的第三方 Jar 包（非 Maven/Gradle 时）
│   ├── out/                 # IDEA 默认编译输出目录（.class 文件）
│   │   ├── production/      # 生产代码编译结果
│   │   └── test/            # 测试代码编译结果
│   └── target/              # Maven/Gradle 构建输出目录（替代 out）
├── pom.xml                   # Maven 项目配置文件（依赖、构建脚本）
├── build.gradle              # Gradle 项目配置文件
├── settings.gradle           # Gradle 多模块配置
├── .gitignore                # Git 忽略文件（通常忽略 .idea、out、target）
└── README.md                 # 项目说明文档

---

### 三、关键目录 / 文件详解

#### 1. 配置类（IDE 自动维护）

- **`.idea/`**：项目级配置，包含 SDK、模块、代码风格、运行配置等，**建议加入版本控制**（方便团队共享）JetBrains。
- **`*.iml`**：模块级配置，每个 Module 一个，记录该模块的源码路径、依赖、输出目录等。

#### 2. 源码与资源（核心开发目录）

- **`src/main/java`**：业务代码入口，按包名创建子目录（如 `com/company/project`）。
- **`src/main/resources`**：非代码资源，Spring Boot 的 `application.properties`、MyBatis 的 mapper.xml 都放这里JetBrains。
- **`src/test/java`**：单元测试代码，与 main 目录结构一一对应。

#### 3. 编译输出（自动生成，可忽略）

- **`out/`**：IDEA 原生编译输出，存放 `.class` 文件。
- **`target/`**：Maven/Gradle 构建输出，包含编译结果、打包后的 Jar/War 等。
- **`build/`**：Gradle 专用输出目录，功能类似 target。

#### 4. 构建与依赖

- **`pom.xml` / `build.gradle`**：构建脚本，管理项目依赖、插件、打包规则。
- **`lib/`**：手动管理 Jar 包时使用，Maven/Gradle 项目一般不用。

---

### 四、多模块项目结构（进阶）

大型项目通常拆分为多个 Module，结构示例：

plaintext

```
my-project/
├── .idea/
├── pom.xml                # 父项目（管理公共依赖、版本）
├── module-common/         # 公共工具模块（工具类、枚举、配置）
├── module-api/            # API 接口模块（Controller、对外接口）
├── module-service/        # 业务逻辑模块（Service、DAO）
└── module-web/            # Web 启动模块（含 main 方法、启动类）
```

每个 Module 都有自己的 `src`、`.iml`，可独立编译、依赖其他 Module。

---

### 五、快速查看与修改项目结构

- 打开：`File → Project Structure`（快捷键 `Ctrl+Alt+Shift+S`）
- 可配置：
    
    - **Project SDK**：指定 JDK 版本。
    - **Modules**：添加 / 删除模块、设置源码 / 资源 / 输出路径。
    - **Libraries**：管理项目 / 模块 / 全局依赖库。
    - **Artifacts**：配置打包方式（Jar/War）。
    

---

### 六、常见规范与建议

1. **源码分离**：`main` 放业务代码，`test` 放测试代码，不混放。
2. **资源分类**：配置文件放 `resources`，静态资源（图片、JS）Web 项目放 `webapp`。
3. **忽略文件**：`.gitignore` 必须包含 `.idea`、`out`、`target`、`build`、`*.iml`（可选）。
4. **多模块拆分**：按业务域 / 功能拆分 Module，降低耦合、便于复用。

---
---


# 逻辑运算符

```java
&：与
|：或
！：非
^:异或


#1. 按位与（位运算，最常考计算机基础）

  `&` 会把两个数字按二进制位一位一位做运算：

  - 对应位 **都为 1 → 结果是 1**
  - 否则 → 结果是 0

   例子：

  3 的二进制：011

  5 的二进制：101

  3 & 5 = 001 → 1


#2. 逻辑与（不短路）

  `&` 也可以当逻辑与用，和 `&&` 很像，但关键区别：

  - `&&`：左边为 false，右边不执行（短路）
  - `&`：左边为 false，右边照样执行（不短路）
  
  
  
  
byte a=200;  //1100 1000
byte b=10;   //0000 1010
System.out.println(a&b);  //0000 1000，十进制为8

  
  
  
----------------------------------------  

#1. 按位或（位运算）

  规则：对应位只要有一个是 1，结果就是 1**

  0 | 0 = 0

  0 | 1 = 1

  1 | 0 = 1

  1 | 1 = 1

  例子：

  3 二进制：011

  5 二进制：101

  3 | 5 = 111 → 7


#2. 逻辑或（不短路）

  `|` 两边都是布尔时：只要一个 true，结果就是 true**

  但重点：

  - `||`：左边 true → **右边不执行**（短路）
  - `|`：左边 true → **右边照样执行**（不短路）



-----------------------------------------





&&：短路与（和&结果一样）
||：短路非（和|结果一样）
额外具有短路功能，表示当左边的表达式能确定最终结果，右边便不会再进行

int a=10;
int b=10;
bollean result= ++a<10 && ++b<10;
System.out.println(result);//false
System.out.println(a);//11
System.out.println(b);//10




-----------------------------------------



<<：向左移动，低位补0，每移动一位相当于乘2
>>：向右移动，高位补0或1（数值位补0，但符号位要看之前是0还是1），每移动一位相当于除以2
>>>：无符号向右移动，高位只补0




```

---
---





# 关于随机数

生成随机数范围的秘诀：*比如7~15*    **注意随机数的范围首位默认从0开始，我们填的参数是控制末尾的**
	1、让这个范围首尾都减去一个值，使得范围从0开始  *减去7，即0~8*
	2、尾巴加1   *8+1=9*
	3、最终的结果再加上第一步减去的值   *9+7=16，即参数填16*



> 以后如果我们要在一堆没有什么规律的数据中随机抽取，可以先把这些数据放在数组当中，在随机抽取一个索引



---
---





# Java有无指针


1、Java没有指针

Java **不能**：

- 写 `int *p = &a;`
- 做指针运算 `p++`、`p+1`
- 直接操作内存地址


**Java 没有指针。**


 2、 但 Java 到处都是 “指针思想”

比如：

```
int[] arr = new int[5];
```

- `arr` 存的**不是数组本身**，是**数组对象的地址**
- 这就是**引用（reference）**，本质是**受控制的指针**

再比如对象：

```
Student stu = new Student();
```

- `stu` 也是指向堆内存的**指针（引用）**


 3、 和 C 指针的区别

- C 指针：可以加减、乱指、越界、操作任意地址 → **危险但自由**
- Java 引用：只能指向对象 / 数组，不能算地址、不能改地址 → **安全但不自由**

4、最简记忆

- **C：有指针，能玩地址，能出事**
- **Java：没有指针语法，但有引用（安全指针），不能玩地址**



---
---






# 键盘录入

在 Java 中，最常用的键盘录入方式是使用 `java.util.Scanner` 类。它就像是一个“翻译官”，负责把用户从键盘敲下的字符转换成程序能理解的数字、字符串等数据。

---

### 1. 键盘录入的标准步骤

实现键盘录入只需要简单的“三部曲”：

1. **导包**：在类定义之前引入 Scanner 类。
    
2. **创建对象**：实例化一个扫描器对象。
    
3. **接收数据**：调用对应的方法获取用户输入。
    


```java
// 1. 导包
import java.util.Scanner;

public class ScannerDemo {
    public static void main(String[] args) {
        // 2. 创建扫描器对象 (System.in 代表标准输入流，即键盘)
        Scanner sc = new Scanner(System.in);

        System.out.println("请输入您的年龄：");

        // 3. 接收数据
        int age = sc.nextInt(); 

        System.out.println("您的年龄是：" + age);
    }
}
```

---

### 2. 常用接收方法一览

根据你想获取的数据类型，`Scanner` 提供了不同的“捕捉”工具：

|**方法**|**说明**|
|---|---|
|`nextInt()`|接收一个**整数**（遇到空格、回车、制表符就停止）|
|`nextDouble()`|接收一个**小数**（遇到空格、回车、制表符就停止））|
|`next()`|接收一个**字符串**（遇到空格、回车、制表符就停止）|
|`nextLine()`|接收**整行字符串**（可以包含空格，直到按回车为止）|

---

### 3. 内存与原理简析

当你运行 `Scanner` 时，程序会在 **栈内存** 中创建一个 `sc` 引用，指向 **堆内存** 中的 Scanner 对象。这个对象会监听 `System.in`（系统输入流）。

- **阻塞效果**：当程序执行到 `sc.nextInt()` 时，它会“卡”在那里，等待用户在控制台输入内容并按下回车。
    
- **缓冲区**：用户输入的内容其实先进入了一个“缓冲区”。Scanner 会根据你调用的方法，从缓冲区中取走它想要的数据。
    

---

### 4. 两个容易踩的“坑”

#### ① `nextInt()` 后面接 `nextLine()` 的“跳过”现象

这是初学者最容易崩溃的地方。

- **现象**：如果你先输入一个数字（按回车），再想输入一行字符串，你会发现程序直接结束了，没让你写字符串。
    
- **原因**：`nextInt()` 只取走了数字，把那个“回车换行符”留在了缓冲区。`nextLine()` 看到回车以为你已经输完了，直接带走了一个空字符串。
    
- **解决**：要么全部用 `next()`，要么在 `nextInt()` 之后多写一行 `sc.nextLine()` 把多余的回车“吃掉”。
    

#### ② 记得“关门”

虽然小程序不关也没事，但在规范的项目中，Scanner 使用完毕后建议调用 `sc.close()` 释放资源，防止内存泄漏。

---
---






# 数据类型


基本数据类型：数据值存储在自己空间中  *栈内存*
		特点：赋值给其他变量，也是赋的真实的值
```java
int a=10;
int b=a;
```


引用数据类型：数据值存储在其他空间中，自己空间中存储的是地址值  *堆内存*
		特点：赋值给其他变量，赋的地址值
```java
int[] arr1={1,2,3};
int[] arr2=arr1;
```

---
---






# 数据的默认值

### 数组元素

不管在哪，只要 `new` 出来，元素就有默认值：


```java
int[] arr = new int[5]; // 全部 0
boolean[] b = new boolean[3]; // 全部 false
String[] str = new String[2]; // 全部 null
```



### 类的成员变量（字段）

直接写在类里、不在方法里的变量：




```java
public class Test {
    int a;         // 默认 0
    double d;      // 默认 0.0
    boolean flag;  // 默认 false
    String s;      // 默认 null
}
```

*与C语言不同，这些不用赋值就能直接用、直接比较。*



---
---



# 面向对象

## 一、类和对象
- 类（设计图）：是对象共同特征的描述
- 对象：真实存在的具体东西

*如何定义类*
```java
public class 类名{
	1.成员变量（代表属性，一般是名词）
	2.成员方法（代表行为，一般是动词）
	3.构造器
	4.代码块
	5.内部类
}
```
*如何得到类的对象*
```java
类名 对象名=new 类名（）;
```
*如何得到类的对象*
- 访问属性：对象名.成员变量
- 访问行为：对象名.方法名（...）

> [!tip]
> 用来描述一类事物的类，专业叫做：Javabean类，不写main方法
> - *三点要求*
>- **类是 public**
>- **有无参构造器**
>- **字段 private，提供 public 的 getXxx () /setXxx ()**


## 二、封装
### 1. 核心定义

封装是指将对象的**属性（状态）和行为（方法）结合成一个独立的单位（类），并尽可能地隐藏**对象的内部细节，只保留有限的对外接口与外部进行交互。

---

### 2. 为什么要封装？（痛点分析）

想象一下，如果一个人的 `age` 属性是公开的，任何人都可以直接把它改成 `-500` 岁，这显然不符合逻辑。

- **安全性：** 防止外部成员随意修改内部数据。
    
- **解耦：** 外部不需要知道内部逻辑。只要接口不变，内部逻辑怎么改都行。
    
- **简单化：** 调用者只需要知道方法的作用，不需要研究它是怎么实现的。
    

---

### 3. 如何实现封装？

在 Java 中，实现封装通常遵循“三部曲”：

#### 第一步：私有化属性

使用 `private` 关键字修饰成员变量，使其在类外部不可直接访问。

#### 第二步：提供公共的 Getter/Setter 方法

通过 `public` 方法来控制属性的读取和修改，并在 Setter 中加入**逻辑判断**。

#### 第三步：隐藏实现逻辑

将复杂的计算或校验逻辑写在私有方法中，只暴露一个简单的公共方法给用户。


### 4. 封装的四个访问修饰符

封装的程度由访问权限控制符决定，我们可以根据需要选择“围墙”的高度：

|**修饰符**|**同类**|**同包**|**子类**|**整个项目**|
|---|---|---|---|---|
|**private**|✅|❌|❌|❌|
|**default** (默认)|✅|✅|❌|❌|
|**protected**|✅|✅|✅|❌|
|**public**|✅|✅|✅|✅|

## 三、this关键字

既然提到了封装，那 **`this`** 关键字就是那个在暗中穿针引线的“指路人”。

在 Java 中，`this` 是一个**引用变量**，它指向**当前对象本身**。简单来说，谁调用了这个方法，`this` 就代表谁。（*本质：当前对象的地址*）

---

### 1. `this` 的三大核心用法

#### ① 区分同名的成员变量与局部变量（最常用）

当你的方法参数名和类属性名“撞衫”时，Java 会优先采用就近原则（局部变量）。此时必须用 `this` 来点名成员变量。


```java
public class User {
    private String name;

    public void setName(String name) {
        // name = name;      // 这里的两个 name 都是参数，赋值无效
        this.name = name;    // this.name 指向类里的属性，右边的 name 是参数
    }
}
```

#### ② 调用本类中的其他构造器

如果你有多个构造方法，想让一个构造器去“搭便车”调用另一个，可以用 `this()`。

> **注意：** `this()` 必须写在构造方法的第一行。


```java
public class Student {
    private String name;
    private int age;

    public Student() {
        this("无名氏", 18); // 调用下面那个带两个参数的构造器
    }

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```

#### ③ 代表当前对象进行传递

你可以把 `this` 当作参数传递给其他方法，或者在方法中返回 `this`（这常用于**链式编程**，比如 StringBuilder）。

---

### 2. 形象化理解

我们可以把类（Class）想象成一张**建筑图纸**，而对象（Object）是根据图纸盖出来的**多栋房子**。

- 当你在图纸上写“把这栋房子的墙刷红”时，程序并不知道具体是哪一栋。
    
- **`this`** 就像是房子的**内部定位系统**。当你在 1 号房里操作时，`this` 就指向 1 号房；在 2 号房里，它就指向 2 号房。
    

---

### 3. 使用注意点（避坑指南）

- **不能在 `static` 方法中使用：** 静态方法属于类，而不属于某个具体的对象。既然没有对象，自然也就没有 `this`。
    
- **不能在构造器中循环调用：** 比如 A 调用 B，B 又调用 A，这会导致编译错误。
    

---

### 4. 总结对比

|**特性**|**说明**|
|---|---|
|**本质**|指向当前实例的引用|
|**作用域**|只能在非静态方法、构造器中使用|
|**主要目的**|解决命名冲突、实现构造器复用、链式调用|

---
---
## 四、构造方法
### 作用：
- 创建对象的时候，由虚拟机自动调用，给成员变量进行初始化
### 分类
- 无参构造方法：初始化对象时，成员变量的数据均采用默认值
- 有参构造方法：初始化对象时，同时可以为对象赋值
### 注意事项：
- 任何类定义出来，默认自带无参构造器
- 一旦定义有参构造器。无参构造器便消失，此时需要手动写无参构造器
- 建议在任何时候都写上空参和带上全部参数的构造方法

## 五、标准Javabean类

在 Java 开发中，**JavaBean** 是一种特殊的类，它遵循特定的编写规范。你可以把它想象成一个“标准的数据集装箱”，专门用来封装数据并在层与层之间传递。

一个标准的 JavaBean（也常被称为 POJO - Plain Old Java Object）必须满足以下 **4 个核心条件**：

### 1. 编写规范

- **类修饰符：** 必须是 `public`。
    
- **成员变量：** 必须使用 `private` 私有化（体现封装思想）。
    
- **构造器：** 必须提供一个 **无参构造器**（很多框架如 Spring, MyBatis 反射时需要它）。
    
- **Getter/Setter：** 为每个私有属性提供公共的 `get` 和 `set` 方法。
    

---

### 2. 标准代码模板

这是一个符合标准的 `User` 类 JavaBean：

```java
public class User {
    // 1. 私有化成员变量
    private String username;
    private int age;

    // 2. 无参数构造器 (必须有)
    public User() {
    }

    // 3. 全参数构造器 (可选，但通常建议加上)
    public User(String username, int age) {
        this.username = username;
        this.age = age;
    }

    // 4. 公共的 Getter 和 Setter
    public String getUsername() {
        return username;
    }

    public void setUsername(String username) {
        this.username = username;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}
```

---

### 3. 为什么要遵守这个标准？

如果每个程序员都按自己的喜好写类，工具和框架就没法玩了。遵守标准的好处在于：

1. **框架兼容性：** 像 Hibernate、MyBatis、Spring 这种主流框架，都是通过反射调用**无参构造**和 **Setter/Getter** 来填充数据的。
    
2. **代码可维护性：** 任何开发者看到这样的类，就知道它是用来存数据的，直接调用 `get/set` 即可，不需要猜测逻辑。
    
3. **内省机制：** Java 语言自带的 `Introspector` 可以自动发现这些属性，方便在 GUI 或 Web 插件中展示。
    

---

### 4. 进阶技巧：效率神器

在实际开发中，手动写几十个 `get/set` 非常痛苦。我们通常有三种处理方式：

- **IDE 快捷键：** 在 IntelliJ IDEA 中，按 `Alt + Insert` 然后选择 `Getter and Setter` 即可一键生成。(*选择Constructor可以生成无参或有参构造函数*)
    
- **Lombok 插件：** 只需要在类名上加一个 `@Data` 注解，编译时会自动帮你写好所有构造器和方法。
    
- **Record (Java 14+)：** 如果你使用的是较新版本的 Java，可以用 `record` 关键字，它一行代码就能搞定类似 JavaBean 的功能（虽然它是不可变的）。
    

---

### 5. 常见误区

> **“JavaBean 必须实现 Serializable 接口吗？”**
> 
> 严格的 Sun 公司规范中建议实现 `Serializable`（序列化接口），以便对象能在网络上传输或保存到硬盘。但在现代开发中，如果你的对象只是在内存里跑，不涉及网络传输，不写也没问题。不过，为了保险起见，**建议养成实现该接口的习惯。**

---
---

## 7、对象内存图

理解对象内存图是掌握 Java 的底层逻辑、尤其是理解“引用”和“深浅拷贝”的关键。在 Java 中，内存主要分为三个核心区域：**栈（Stack）**、**堆（Heap）** 和 **方法区（Method Area）**。

我们通过一个简单的代码实例来拆解内存的变化过程。

---

### 1. 核心内存区域角色

|**区域**|**存储内容**|**特点**|
|---|---|---|
|**栈 (Stack)**|局部变量（如 `int a`, `User u`）|运行速度快，方法执行完自动释放。|
|**堆 (Heap)**|所有的**对象实例**（如 `new User()`）|存储实际数据，通过地址值访问，由 GC（垃圾回收）管理。|
|**方法区 (Method Area)**|类信息（.class文件）、常量、静态变量|整个程序共享，加载类时初始化。|

---

### 2. 对象创建的内存演变（案例）

假设我们有如下代码：


```java
public class Test {
    public static void main(String[] args) {
        Student s1 = new Student(); 
        s1.name = "张三";
        s1.age = 18;
        s1.study();
    }
}
```

#### 第一步：类加载（方法区）

JVM 启动，将 `Test.class` 和 `Student.class` 加载进**方法区**。此时方法区记录了 `Student` 类有哪些属性（name, age）和哪些方法（study）。

#### 第二步：声明变量（栈）

`main` 方法开始执行，在**栈**内存中为 `s1` 开辟空间。此时 `s1` 只是一个空的引用。

#### 第三步：创建对象（堆）

执行 `new Student()`：

1. 在**堆**内存中开辟一块空间。
    
2. 为该空间分配一个唯一的**十六进制地址值**（例如 `0x1122`）。
    
3. 初始化属性为默认值（String 为 `null`，int 为 `0`）。
    
4. 将地址值 `0x1122` 赋值给栈中的变量 `s1`。
    

#### 第四步：属性赋值（初始化）与方法调用

- `s1.name = "张三"`：程序通过 `s1` 存储的地址找到堆中的对象，修改其数据。
    
- `s1.study()`：通过对象内部持有的“方法区地址”，去方法区找到 `study` 方法的代码并执行。
    

---

### 3. 两个变量指向同一个对象


```java
Student s1 = new Student();
Student s2 = s1; // 关键一步：传递的是地址值
s2.name = "李四";
System.out.println(s1.name); // 输出：李四
```

在这种情况下，**栈**中会有两个引用 `s1` 和 `s2`，但它们存储的**地址值完全相同**，都指向**堆**中同一个对象。修改其中一个，另一个也会跟着变。

---

### 4. 关键结论

1. **栈管运行，堆管存储。**
    
2. **变量赋值本质是地址拷贝。** 如果你把一个对象赋值给另一个变量，你只是复制了一把“房门钥匙”，而不是盖了一栋新房子。
    
3. **垃圾回收：** 当栈中没有任何引用指向堆中的某个地址时，该对象就变成了“孤儿”，会被 JVM 的垃圾回收器择机清理。
    

---
---

# 字符串

## 一、API

在 Java 的世界里，**API（Application Programming Interface，应用程序编程接口）** 简单来说就是一套“规则说明书”或“功能字典”。

作为开发者，你不需要知道某个功能底层是怎么用 0 和 1 堆出来的，你只需要知道**调用哪个类、哪个方法、传什么参数**就能实现功能。

---

### 1. 广义与狭义的 API

- **广义的 API**：指的是软件系统之间的桥梁。比如你调用微信支付的接口、调用高德地图的定位，这些都是 API。
    
- **狭义的 Java API**：指的是 JDK 中内置的**类库**（Scanner, String, Math, ArrayList 等）。它们是 Oracle 已经写好的代码，你直接拿来用即可。
    

---

### 2. 如何使用 Java API？

使用 API 的核心逻辑就像查字典：

1. **确定需求**：比如我想生成一个随机数。
    
2. **查找类名**：搜索得知 `Random` 类可以实现。
    
3. **看包名**：在 `java.util` 包下，需要 `import`。
    
4. **看构造器**：怎么创建这个对象？`new Random()`。
    
5. **看方法名**：调用哪个方法？`nextInt(int bound)`。
    

---

### 3. Java 常用核心 API 概览

Java 拥有极其庞大的标准库，初学者最先接触的通常是以下几个包：

|**包名**|**功能描述**|**核心类举例**|
|---|---|---|
|**`java.lang`**|核心基础类（**自动导入**）|`String`, `Object`, `Math`, `System`|
|**`java.util`**|工具类、集合框架|`Scanner`, `ArrayList`, `Random`, `Arrays`|
|**`java.io`**|输入输出流，操作文件|`File`, `InputStream`, `OutputStream`|
|**`java.net`**|网络编程|`Socket`, `URL`|
|**`java.time`**|日期和时间（Java 8+）|`LocalDate`, `LocalDateTime`|

---

### 4. 学会看 API 文档（核心技能）

[Java API文档链接](https://docs.oracle.com/javase/8/docs/api/)

API 文档是每个 Java 程序员的“保命手册”。当你打开一个类的文档时，重点看这三块：

1. **类描述**：这个类是干嘛的？（比如 `String` 是不可变的字符序列）。
    
2. **构造方法摘要**：怎么把这个对象 `new` 出来？
    
3. **方法摘要**：
    
    - **方法名**：叫什么？
        
    - **参数列表**：要传什么？
        
    - **返回值类型**：执行完给我什么？
        

---

### 5. 举个例子：`Math` 类

`Math` 类的 API 设计非常特殊，它的方法全是 `static`（静态）的。



```java
// 不需要 new，直接类名点方法名调用
double result = Math.pow(2, 3); // 2的3次方
int randomNum = (int)(Math.random() * 100); // 0-100随机数
```

---

### 6. 给初学者的建议

不要试图**背诵** API。Java 的类多达几千个，没人能全部记住。

- **常用的**（如 String, ArrayList）写多了自然就熟了。
    
- **不常用的**（如正则表达式、复杂的文件操作）现用现查。

---
---



## 二、String

在 Java 中，**`String`** 是使用频率最高的类，没有之一。它虽然看起来像基本数据类型，但本质上是一个**引用数据类型**，而且藏着很多设计上的精妙之处。

---

### 1. `String` 的核心特性：不可变性 (Immutability)

这是 Java String 最重要的特性：**一旦创建，其内容就不可更改。**


```java
String s = "Hello";
s = "World"; 
```

当你执行上面的代码时，并不是把 "Hello" 变成了 "World"，而是在内存中**新建**了一个 "World" 对象，并将 `s` 指向了新的地址。原来的 "Hello" 依然静静地待在内存里（直到被回收）。

> **为什么要不可变？**
> 
> - **安全：** 字符串常作为参数传递（如数据库连接、网络地址），不可变保证了数据不会中途被恶意篡改。
>     
> - **缓存：** 因为不可变，多个变量可以共享同一个字符串常量，节省内存。
>     

---

### 2. 创建 String 对象的两种方式

创建 `String` 主要分为**直接赋值**和 **`new` 构造方法**两种途径：

#### ① 直接赋值（推荐）


```java
String name = "小明";
```

这是最常用的方式。它的特点是代码简洁，且能够高效利用内存。

#### ② 使用 `new` 关键字（多种构造方法）

通过 `new` 可以根据不同的数据源创建对象：

- **`public String()`**：创建一个空白字符串，不含任何内容。
    
- **`public String(String original)`**：根据传入的字符串再创建一个新的字符串对象。
    
- **`public String(char[] chs)`**：根据**字符数组**创建。常用于需要修改字符串内容的场景（因为 String 不可变，通常先转为数组修改后再转回 String）。
    
- **`public String(byte[] bytes)`**：根据**字节数组**创建。这是网络传输或读取文件时的核心方法，因为数据在网络中是以字节流传输的。
    

---



### 3. 字符串常量池 (String Constant Pool)



为了提高性能，JVM 在堆内存中专门开辟了一块区域叫**字符串常量池**。

这是理解 `String` 的难点。不同的创建方式，在内存中的表现完全不同：

#### 情况 A：直接赋值的复用机制

当使用双引号直接赋值时，系统会检查该字符串在串池是否存在

- **不存在**：在串池中创建新的字符串对象。
    
- **存在**：直接**复用**已有的地址。
    
- **结果**：`String s1 = "abc"; String s2 = "abc";` 此时 `s1 == s2` 为 `true`。
    

#### 情况 B：使用 `new` 的独立空间

每使用一次 `new` 关键字，都会在**堆内存**中开辟一块全新的空间：

- 即使内容相同，每一个通过 `new` 创建出来的对象都有自己独立的内存地址。
    
- **结果**：`String s1 = new String(chs); String s2 = new String(chs);` 此时 `s1 == s2` 为 `false`，因为它们的地址值分别是 `0x0022` 和 `0x0033`。




> [!tip] 这种设计的核心初衷是**性能优化**。
>- **串池**存在的意义是为了减少相同字符串频繁创建带来的内存开销。
>- **`char[]` 和 `byte[]` 构造器**存在的意义是为了灵活转换。比如你想修改一个字符串，String 本身改不了，你得先把它变成 `char[]`（如 `{'a','b','c'}` 改为 `{'Q','b','c'}`），再通过 `new String(chs)` 包装回去。



---

### 4. String的比较

在 Java 中，字符串的比较是一个经典的“陷阱”，我们可以将字符串比较分为**地址比较**和**内容比较**两种情况。

 核心区别：`==` vs `equals`

- **`==`（比较地址值）**：对于引用数据类型，它判断的是两个变量是否指向内存中的**同一个对象**。
    
- **`equals()`（比较内容）**：String 类重写了这个方法，它会逐个字符地比较字符串的**具体内容**是否完全相同。


---

#### ①不同创建方式下的比较结果

##### 情况 A：直接赋值（串池复用）


```java
String s1 = "abc";
String s2 = "abc";
```

- **内存表现**：当使用双引号直接赋值时，系统会检查串池。因为 `"abc"` 已存在，`s2` 会复用 `s1` 的地址。
    
- **比较结果**：`s1 == s2` 结果为 `true`，因为它们的地址完全一致。
    

##### 情况 B：使用 `new` 关键字（独立空间）

```java
char[] chs = {'a', 'b', 'c'};
String s1 = new String(chs);
String s2 = new String(chs);
```

- **内存表现**：每执行一次 `new`，都会在堆内存中开辟一个新的空间。即便内容都是 `"abc"`，它们的地址值（如 `0x0022` 和 `0x0033`）是不同的。
    
- **比较结果**：
    
    - `s1 == s2` 结果为 **`false`**（地址不同）。
        
    - `s1.equals(s2)` 结果为 **`true`**（内容相同）。
        

---

####  ②常见的比较方法 API

在实际开发中，除了基础的 `equals`，还有几个常用的比较接口：

- **`equals(Object anObject)`**：最常用。逐个字符比较**内容**，区分大小写。例如 `"Java".equals("java")` 结果为 `false`。
    
- **`equalsIgnoreCase(String s)`**：比较内容，但**忽略大小写**。例如 `"Java".equalsIgnoreCase("java")` 结果为 `true`。
    
- **`compareTo(String another)`**：按照字典顺序（Unicode码值）比较，返回两个字符串的差值，常用于**排序逻辑**。
---

####  ③ 最佳实践：避免空指针异常

在进行字符串比较时，为了防止 `null` 对象调用方法导致程序崩溃，建议将**确定不为 null 的常量**写在前面：

```java
String input = null;

// 不推荐：如果 input 为 null，会报 NullPointerException
if (input.equals("admin")) { ... } 

// 推荐：即使 input 为 null，代码也能正常运行并返回 false
if ("admin".equals(input)) { ... }
```

---


### 5.String类的常用方法



> **📌 核心提醒**：`String` 对象内容不可变。所有修改方法（如 `replace`, `toUpperCase`）都会返回一个**全新的字符串对象**，而不会改变原字符串。

####  获取信息类

用于提取字符串的状态或特定字符。

|**方法签名**|**作用**|**示例**|
|---|---|---|
|`int length()`|获取字符串长度（字符数）|`"abc".length()` → `3`|
|`char charAt(int i)`|获取指定索引处的字符|`"abc".charAt(1)` → `'b'`|
|`int indexOf(String s)`|返回子串第一次出现的索引，找不到返回 `-1`|`"abcabc".indexOf("bc")` → `1`|
|`int lastIndexOf(String s)`|返回子串最后一次出现的索引|`"abcabc".lastIndexOf("bc")` → `4`|
|`boolean isEmpty()`|判断是否为空串 `""`|`"".isEmpty()` → `true`|

---

####  判断与比较类

**注意**：内容比较务必使用 `equals` 系列方法，严禁使用 `==`（那是比地址）。

|**方法签名**|**作用**|**示例**|
|---|---|---|
|`boolean equals(Object o)`|比较内容是否完全相同（**区分大小写**）|`"abc".equals("Abc")` → `false`|
|`boolean equalsIgnoreCase(String s)`|比较内容（**忽略大小写**）|`"abc".equalsIgnoreCase("Abc")` → `true`|
|`boolean contains(CharSequence s)`|判断是否包含子串|`"abc".contains("bc")` → `true`|
|`boolean startsWith(String p)`|判断是否以指定前缀开头|`"abc".startsWith("ab")` → `true`|
|`boolean endsWith(String s)`|判断是否以指定后缀结尾|`"abc".endsWith("bc")` → `true`|

---

#### 截取与拼接类

**注意**：由于 `String` 的不可变性，这些方法本质上是在堆内存中创建新对象。*必须将所截取/修改的字符串（即调用方法后的返回值）赋值给新的String对象，否则输出原字符串不会变化*


|**方法签名**|**作用**|**示例**|
|---|---|---|
|`String substring(int begin)`|从 `beginIndex` 截取到末尾|`"abcde".substring(2)` → `"cde"`|
|`String substring(int b, int e)`|截取 `[begin, end)` 区间（**左闭右开**）|`"abcde".substring(1, 3)` → `"bc"`|
|`String concat(String s)`|拼接字符串（等价于 `+`）|`"a".concat("b")` → `"ab"`|
|`String replace(old, new)`|替换所有匹配的子串|`"abc".replace("b", "x")` → `"axc"`|

---

#### 转换与处理类

常用于数据清洗和格式转换。

|**方法签名**|**作用**|**示例**|
|---|---|---|
|`char[] toCharArray()`|转换为字符数组|`"abc".toCharArray()` → `{'a','b','c'}`|
|`byte[] getBytes()`|转换为字节数组（常用于网络传输）|`"abc".getBytes()` → `{97, 98, 99}`|
|`String toLowerCase()`|全转小写|`"AbC".toLowerCase()` → `"abc"`|
|`String toUpperCase()`|全转大写|`"AbC".toUpperCase()` → `"ABC"`|
|`String trim()`|去除首尾空白字符（空格、制表符等）|`" abc ".trim()` → `"abc"`|
|`String[] split(String reg)`|按正则表达式分割成数组|`"a,b,c".split(",")` → `{"a","b","c"}`|

---

#### 静态工具与正则

|**方法签名**|**作用**|**示例**|
|---|---|---|
|`static String valueOf(...)`|将基本类型或对象转为字符串|`String.valueOf(123)` → `"123"`|
|`boolean matches(String reg)`|用正则匹配整个字符串|`"123".matches("\\d+")` → `true`|


---
---



## 三、StringBuilder


`String` 对象具有**不可变性**，每次拼接（如 `s += "a"`）本质上都会在堆内存中创建新的对象并抛弃旧对象，这在循环中会导致极其严重的性能开销。

**`StringBuilder` 的优势：**

- **可变性**：它像一个可以自动扩容的容器，在原有内存空间上进行操作。
    
- **性能极高**：增删改操作不会产生多余的垃圾对象。
    
- **链式编程**：支持连续调用方法（如 `sb.append("A").append("B")`）。
    

---

### 1.构造方法

根据开发场景选择合适的初始化方式：

|**构造方法**|**说明**|
|---|---|
|`public StringBuilder()`|创建一个空白的可变字符串对象，默认初始容量为 16 个字符。|
|`public StringBuilder(String str)`|根据传入的字符串内容，创建一个可变字符串对象。|

---

### 2.常用核心方法

`StringBuilder` 的方法设计目标是高效地“增、删、改、查”。

|**方法签名**|**作用**|**示例**|
|---|---|---|
|`append(anyType val)`|**添加**任意类型数据到末尾，并返回自身|`sb.append("java").append(17)`|
|`reverse()`|**反转**容器内的内容|`sb.append("abc").reverse()` → `"cba"`|
|`length()`|返回字符序列的**长度**|`sb.length()`|
|`toString()`|将 `StringBuilder` **转换回 `String`**|`String s = sb.toString()`|

---

### 3.常见应用场景

#### 循环拼接字符串

这是 `StringBuilder` 最经典的使用场景。


```java
StringBuilder sb = new StringBuilder();
for (int i = 0; i < 1000; i++) {
    sb.append(i); // 始终在同一个对象上操作，速度极快
}
String result = sb.toString();
```

#### 字符串反转判断（如回文检查）


```java
String str = "上海自来水来自海上";
String result = new StringBuilder(str).reverse().toString();
System.out.println(str.equals(result)); // true
```



|**特性**|**String**|**StringBuilder**|
|---|---|---|
|**可变性**|**不可变**|**可变**|
|**性能**|频繁拼接时极低|频繁拼接时极高|
|**存储位置**|涉及字符串常量池|堆内存|
|**建议使用**|定义少量常量、作为参数传递|需要频繁增删改字符串内容时|

---
---

# 易错点
```java
Car[] arr = new Car[3]; 
Scanner sc=new Scanner(System.in);
for (int i = 0; i < arr.length; i++) {
Car c = new Car(); 
....
....
arr[i]=c;
}
```

### 为什么循环里重复写 `Car c = new Car();` 是合法的

在 Java 中，变量 `c` 的作用域只在当前这一次循环的 `{}` 内部。

- 每一次循环结束，`c` 这个变量就会被销毁。
- 下一次循环开始时，又会重新声明一个**全新的变量 `c`**，并指向一个**全新的 `Car` 对象**。


---
---


# 题目练习

```java
题目：实现一个5位验证码的输出，要求前四位是大写或小写字母，最后一位是数字


public class Main {  
    public static void main(String[] args) {  
       //1、将52个字母存放在数组中  
        char chs[]=new char[52];  
        for (int i = 0; i < chs.length; i++) {  
            if(i<26) chs[i]=(char)(97+i);   //利用ASCII码存储大小写字母  
            else chs[i]=(char)(65+i-26);  
  
        }  
  
        //2、利用循环获取数组的4个随机索引  
        String result="";      //定义字符串记录最终结果  
        int randomIndex;  
        Random r=new Random();  
        for (int i = 0; i < 4; i++) {  
            randomIndex=r.nextInt(chs.length);  
            result=result+chs[randomIndex];  
        }  
  
        //3、最后加上数字  
        result=result+r.nextInt(10);  
        System.out.println(result);  
  
    }  
}```

```

```java
题目：输入整型金额（如4321），最多七位数，转换成大写汉字金额，并补全高位（零佰零拾零万肆仟叁佰贰拾壹元）


import java.util.Scanner;

public class StringDemo9 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int money;
        while (true) {
            System.out.println("请录入一个金额");
            money = sc.nextInt();
            if (money >= 0 && money <= 9999999) {
                break;
            } else {
                System.out.println("金额无效");
            }
        }

        String moneyStr = "";
		//逐个获取整形金额个位数字
        while (true) {
            int ge = money % 10;
            String capitalNumber = getCapitalNumber(ge);
            moneyStr = capitalNumber + moneyStr; //capitalNumber要放在前面进行拼接
            money = money / 10;
            if (money == 0) {
                break;
            }
        }
		//高位补零
        int count = 7 - moneyStr.length();
        for (int i = 0; i < count; i++) {
            moneyStr = "零" + moneyStr;  //"零"要放在前面进行拼接
        }

        String[] arr = {"佰", "拾", "万", "仟", "佰", "拾", "元"};
        String result = "";
        for (int i = 0; i < moneyStr.length(); i++) {
            char c = moneyStr.charAt(i);
            result = result + c + arr[i]; //两个数组相互拼接
        }

        System.out.println(result);
    }
	
	//将大写金额放在数组中，通过索引获取
    public static String getCapitalNumber(int number) {
        String[] arr = {"零", "壹", "贰", "叁", "肆", "伍", "陆", "柒", "捌", "玖"};
        return arr[number];
    }
}


```

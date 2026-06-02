
[MDN的Web技术官方文档](https://developer.mozilla.org/zh-CN/docs/Web)
# 入门


如果说 Java SE 是让你学会如何编写一个个**独立的、在本地运行的**程序（比如控制台应用、小游戏），那么 **Java Web** 就是要带你进入“互联网时代”——让你的程序运行在服务器上，能够通过浏览器、手机 App 访问，处理成千上万用户的数据。

简单来说，Java Web 就是**用 Java 技术来构建网站、网页应用或者网络后台接口（API）的整套体系**。

---

## 什么是Web？


简单来说，**Web 就是我们天天都在用的“万维网”（World Wide Web）**，也就是我们常说的**网页世界**。

你平时用浏览器看新闻、刷 B 站、逛淘宝、查资料，这些通过浏览器就能打开的网页、系统、App 后台，全部都属于 Web 的范畴。

为了让你更透彻地理解，我们把它拆成**两个视角**来看：

### 视角一：技术本质（它是怎么组成的？）

在技术人员眼里，Web 的核心是由三驾马车组成的：

- **URL（统一资源定位符）：** 就是**网址**（比如 `[https://www.baidu.com](https://www.baidu.com)`）。网页世界很大，URL 就是每个网页的“家庭住址”，确保你不会走错门。
    
- **HTTP 协议（超文本传输协议）：** 它是网络世界里的**普通话**。浏览器和服务器之间传输数据，必须都遵守这套聊天规则。
    
- **HTML（超文本标记语言）：** 网页的**实体**。服务器传给浏览器的就是一堆 HTML 代码，浏览器把它“翻译”成你看到的图文并茂的精美网页。
    

### 视角二：工作原理（一进一出的双人舞）

Web 的运行极其依赖 **“请求-响应”** 模型。不管多复杂的网站，底层永远都在重复下面这两步：

```
[ 你的电脑/手机 (客户端) ]  --- 发送“请求” (Request) --->  [ 远方的机房 (服务器) ]
[ 你的电脑/手机 (客户端) ]  <--- 返回“响应” (Response) --  [ 远方的机房 (服务器) ]
```

1. **请求（Request）：** 你在浏览器里输入网址并敲下回车。这时，你的浏览器就向远在天边的服务器发送了一封信：“嘿，我想看这个页面，请把数据给我。”
    
2. **响应（Response）：** 服务器收到信后，把准备好的网页数据（HTML、图片、JSON数据等）打包寄回给你的浏览器。浏览器收到后，在屏幕上把它画出来。
    


> **去餐馆吃饭的例子：**
> 
> - **客户端（Browser/Client）：** 你（用户）。你打开浏览器，输入网址，就像服务员递给你一张菜单。
>     
> - **请求（Request）：** 你点了一份“宫保鸡丁”。浏览器把这个请求打包，通过网络发送给厨房。
>     
> - **服务器端（Server）：** 厨房（Java Web 程序运行的地方）。厨房收到订单，厨师（Java 代码）去冰箱（数据库）拿食材，炒好菜，打包好。
>     
> - **响应 (Response)：** 服务员把做好的“宫保鸡丁”端到你面前。浏览器收到后台传过来的数据，渲染成漂亮的网页展示给你。
>     



### 作为 Java 开发者，在 Web 中扮演什么角色？

Web 开发分为**前端**和**后端**。你正在努力成为的 Java 开发者，属于**后端（Server-side）**。

- **前端（Visual）：** 负责网页“长什么样”。用 HTML/CSS/JS 写出按钮、动画、排版，运行在用户的浏览器里。
    
- **后端（Logic & Data）：** 负责网页“怎么工作”。**这就是你的战场。**
    
    当用户点击“登录”或“下单”时，前端会发一个 HTTP 请求到后台。你的 Java 代码（运行在服务器上）就要去数据库里校验密码对不对、库存够不够，算好结果后再丢给前端。
    

> **一句话总结：** Web 就像一家餐馆。前端是前厅漂亮的装潢和迎宾的服务员；而你学的 **Java Web，则是负责在后厨掌勺的厨师**，虽然客人看不见你，但整个餐馆最核心的“核心科技”（业务逻辑、数据处理）全都在你手里。



---


## Java Web 学习路线图

从 Java SE 跨入 Web，你会遇到很多新名词。别慌，我们可以把它们拆解为三个必经阶段：

### 1. 基础基石：Web 前端基础 & 网络常识

虽然你是走 Java 后端，但后台最终要和前端交互，所以你必须看得懂前端的“语言”，并理解它们是怎么传输的。

- **HTML/CSS/JavaScript：** 网页的骨架、皮囊和灵魂（了解即可，能看懂、会微调就行）。
    
- **HTTP 协议：** 极其重要！这是浏览器和服务器聊天的“语言规范”，你需要搞懂什么是 `GET`、`POST` 请求，什么是状态码（比如 `404 Not Found`, `500 Server Error`）。
    

### 2. 底层内功：Java Web 三驾马车 (经典技术)

这是 Java Web 的底层基石。虽然现在开发很少直接手写这些，但**几乎所有高级框架（如 Spring Boot）的底层都是它们**，面试必考：

- **Servlet：** Java Web 的核心。它是一个运行在服务器端的 Java 程序，专门用来接收浏览器的请求并做出响应。
    
- **Tomcat（Web 服务器）：** 你的 Java 代码不能直接在网络上飞，Tomcat 就像一个“容器”或者“港口”，它负责监听网络端口，把过来的网络请求变成 Servlet 能看懂的 Java 对象。
    
- **Cookie & Session：** HTTP 协议是“健忘”的（无状态）。这两个技术用来让服务器记住用户（比如保持登录状态）。
    

### 3. 现代兵器：主流主流框架 (企业级开发)

学完底层，你就会发现纯手写 Servlet 太痛苦了。这时候就要上现代化的“全自动武器”：

- **Maven / Gradle：** 项目构建和依赖管理工具（帮你自动下载和管理各种 Jar 包，告别手动拷贝）。
    
- **SSM 框架组合：**
    
    - **Spring：** 管理对象的“大管家”（核心思想是 IoC 和 AOP）。
        
    - **Spring MVC：** 帮你在 Servlet 之上封装了一层，让处理网络请求变得极其简单。
        
    - **MyBatis：** 让你用极其优雅的方式去操作 MySQL 数据库，告别繁琐的 JDBC 代码。
        
- **Spring Boot（终极目标）：** 现在的绝对主流。它把上面那些复杂的框架全部“一键打包”并自动化配置，让你能用最快的速度搭建起一个商业级的后台系统。
    

---

## 给你的学习建议

1. **不要在前端死磕：** 很多 Java 初学者在学 HTML/CSS 时花了大把时间去研究怎么画一个好看的按钮，这是走偏了。你的核心是**后端逻辑**，前端只要达到“能看懂、能用表单传数据”的程度即可。
    
2. **重视数据库（SQL）：** 进入 Web 阶段后，几乎所有的业务都离不开数据存储。MySQL 的增删改查（CRUD）要练得像本能一样熟练。
    
3. **多抓包看数据：** 推荐在浏览器里按 `F12` 打开开发者工具，切换到 `Network`（网络）选项卡。随便刷新一个网页，看看请求头（Request Headers）和响应体（Response Body），这能帮你快速建立起网络通信的底层的直观认知。
    


---
---



# Web前端开发初识


既然你要走 Java 后端，那么对于 Web 前端，你的目标不是去当一个“像素级还原设计图”的艺术家，而是要当一个**能听懂前端说话、能跟前端顺利交接**的合格队友。

我们可以把 Web 前端开发，比作**盖一栋写字楼**。前端的核心就是以下这三门基础技术，它们各司其职：

## 1. HTML：建筑的“钢筋水泥” (骨架)

**HTML (HyperText Markup Language，超文本标记语言)** 决定了网页上有什么东西。它用各种“标签”把文本、图片、输入框、按钮等元素堆砌起来。

- **它的角色：** 纯骨架。如果没有别的技术修饰，纯 HTML 网页看起来就像 90 年代的黑白文档。
    
- **Java 开发者需要掌握的：**
    
    - 看懂常见的标签：`<div>`（区块）、`<p>`（段落）、`<a>`（超链接）、`<img>`（图片）。
        
    - **重点理解 `<form>`（表单）和 `<input>`（输入框）：** 因为用户在网页上输入的账号、密码、订单信息，都是通过表单传给你后端的 Java 程序的。
        

## 2. CSS：大楼的“精装修” (皮囊)

**CSS (Cascading Style Sheets，层叠样式表)** 负责网页“长得好不好看”。它用来控制元素的颜色、大小、字体、间距以及页面排版布局。

- **它的角色：** 皮肤与衣服。让按钮变圆角、让导航栏浮动在最上面、让背景变成渐变色。
    
- **Java 开发者需要掌握的：**
    
    - **了解即可：** 你不需要去死记硬背怎么画复杂的动画或做高阶的特效。
        
    - **基本概念：** 知道什么是**盒模型**（Box Model，元素的边距和大小）、什么是 **Flex 布局**（现在主流的排版方式）。遇到前端页面样式错位时，能通过浏览器按 `F12` 简单定位一下原因就行。
        

## 3. JavaScript：大楼的“智能系统” (灵魂)

**JavaScript (JS)** 是一门真正的编程语言（注意：它跟 Java 没有任何血缘关系，就像雷锋和雷峰塔一样）。它让网页“动”起来，具备交互能力。

- **它的角色：** 网页的肌肉与神经。点击按钮弹出一个提示框、滑动轮播图、或者在不刷新整个页面的情况下更新局部数据。
    
- **Java 开发者需要掌握的：**
    
    - **非常重要：** 因为你以后要经常和 JS 打交道。
        
    - **Ajax / Fetch 技术：** 这是前后端交互的桥梁！前端写一段 JS 代码，通过 Ajax 向你的 Java 后端发送一个请求，拿到数据后再偷偷更新到网页上（比如你刷 B 站时，滚动到页面底部会自动加载更多视频，而不需要重新刷新整个网页）。
        

## 总结：三者的配合流程

我们可以用一段极其简化的伪代码，来看看这三者是怎么在浏览器里协同工作的：

```HTML
<!-- HTML 定义：这里有一个按钮 -->
<button id="myBtn">点我点我</button>

<style>
/* CSS 定义：这个按钮必须是蓝色的，字是白色的 */
#myBtn {
    background-color: blue;
    color: white;
}
</style>

<script>
// JS 定义：当用户真的点击这个按钮时，要做什么事
document.getElementById("myBtn").onclick = function() {
    alert("你点了我一下！");
};
</script>
```

## 现代前端在干嘛？(了解一下)

你可能在网上听过 **Vue、React、Angular**。别被它们吓到，它们是**现代前端框架**。

以前的前端是一页一页写 HTML；现在的现代化前端（比如目前国内最火的 **Vue**）更像是在玩乐高积木——把网页拆成一个个“组件”（比如一个导航栏组件、一个评论区组件），然后用 JS 来驱动整个页面的数据变化。

作为 Java 后端，未来前端会向你发起请求，你只需要给他们返回干净的 **JSON 数据**（一种轻量级的数据交换格式，像键值对一样），剩下的页面渲染全部交由前端框架去处理。这就是现在主流的**前后端分离开发模式**。



---
---



# HTML-CSS 



## 央视新闻—标题—排版


![[Java Web笔记.png]]


看来你已经正式进入实战阶段了！黑马程序员的这个央视新闻案例非常经典，它用一个极其直观的“新闻标题页”把 HTML 的**标题标签**和**超链接标签**讲得清清楚楚。

既然是“初识加实战”，我们不搞死记硬背。结合你发的这张图片，我帮你把这里面的核心考点和后端开发者必须知道的“潜规则”梳理一下：

### 1. 标题标签：`<h1>` 到 `<h6>`

图片中，新闻的主标题“推进长江十年禁渔...”被包裹在了 `<h1>` 标签里。

- **技术本质：** `h` 代表 **Heading（标题）**。从 `<h1>` 到 `<h6>`，数字越小，字号越大，权重越高。`<h1>` 通常一个网页里**只出现一次**，用来放最核心的标题。
    
- **后端/全栈视角：** 标题标签自带加粗和换行效果。但更重要的是，它是 **SEO（搜索引擎优化）** 的关键。百度或谷歌的爬虫来到你的网站时，会优先抓取 `<h1>` 里面的文字。所以，核心业务数据（比如商品名称、新闻标题）在前端渲染时必须用好标题标签。
    

### 2. 超链接标签：`<a>` (Anchor)

图片中点击“央视网”能跳转到官网，靠的就是 `<a>` 标签。这是前后端交互中**极其高频**的一个标签。

我们来拆解一下图片里它的两个核心属性：

#### ① `href` 属性（Hypertext Reference）

- **作用：** 指定你要跳转到哪里去（资源的 URL）。
    
- **后端视角：** 这里的地址不仅可以写死一个像 `https://www.cctv.com/` 这样的外部网站，未来你在写后端路由时，这里往往会写你自己的 Java 后端接口地址。
    
    - 例如：`<a href="/download?fileId=123">下载文件</a>`。当用户点击这个链接时，就会向你的 Java 后台发送一个请求，你的 Servlet/Spring Boot 代码就会收到 `fileId=123`，然后从数据库查出文件流返回给浏览器。
        

#### ② `target` 属性

决定点击这个链接后，新网页在哪里打开：

- `_self`（默认值）：在**当前标签页**直接刷新打开。用户想回来的话得点浏览器的“返回”箭头。
    
- `_blank`：默默地在浏览器**新建一个空白标签页**打开。
    
    - _避坑指南：_ 像新闻、商品详情这种“看完了还想回列表页”的场景，用户体验上几乎**100% 都要用 `target="_blank"`**，不然用户好不容易滑到地下的列表，一点击详情原页面就没了，体验会很糟糕。
        

### 顺手写个小练习

既然在看视频，强烈建议你在电脑上打开 VS Code，新建一个 `index.html`，把下面这段最简单的代码复制进去，然后右键用浏览器打开，亲手点一下那个链接：

```HTML
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>我的第一个新闻排版</title>
</head>
<body>

    <h1>【新思想引领新征程】推进长江十年禁渔 谱写长江大保护新篇章</h1>
    
    <a href="https://www.cctv.com/" target="_blank">央视网</a> 2024年05月15日 20:07

</body>
</html>
```

感受一下：**代码里的标签，是如何变成浏览器上的网页的。** 这对你接下来理解后端如何向前端“吐”出这些 HTML 字符串至关重要！

---
---


## 央视新闻—标题—样式


![[Java Web笔记-1.png]]



这两张图直接切入了 CSS 的核心：**样式怎么引入** 以及 **颜色怎么控制**。在图里，黑马程序员用 `<span>` 标签把“2024年05月15日 20:07”包裹起来，并把它改成了灰色。

我们依然用**后端开发者的视角**，快速提炼这里的核心技术点：

### 核心点一：CSS 的三种引入方式

这决定了你的样式代码写在哪里。从上到下，它们的解耦（分工）程度越来越高：

|**引入方式**|**代码写在哪里**|**优缺点 / 使用场景**|
|---|---|---|
|**1. 行内样式**|直接写在 HTML 标签的 `style="..."` 属性里|**缺点：** 代码极其臃肿，不能复用。<br><br>  <br><br>**场景：** 配合 JavaScript 动态修改某个标签的颜色/大小（后端了解即可）。|
|**2. 内部样式**|写在 HTML 文件的 `<style>` 标签中|**优点：** 在当前页面内可以复用样式。<br><br>  <br><br>**场景：** 做一些单页面的小练习或写个小 Demo 时最方便。|
|**3. 外部样式**|写在独立的 `.css` 文件里，HTML 通过 `<link>` 标签引入|**绝对的主流！** 实现了“结构（HTML）”与“皮肤（CSS）”的完全分离，多个网页可以共享同一个 CSS 文件。|

> **💡 潜规则：** 未来不管是你自己写项目，还是看前端同学的代码，**绝大多数情况都是用“外部样式”**。

### 核心点二：CSS 颜色的四种表示法

在 CSS 里想表达“灰色”或者“央视红”，有四种写法（参见第二张图）：

1. **关键字：** 直接写英文单词，如 `color: gray;`、`red`、`blue`。简单直观，但颜色种类有限。
    
2. **十六进制表示法（最常用）：** 以 `#` 开头，后面跟 6 位数字/字母（每两位分别代表红、绿、蓝）。
    
    - 例如：`#000000` 是纯黑（简写 `#000`），`#ffffff` 是纯白（简写 `#fff`），`#ff0000` 是纯红（简写 `#f00`）。
        
3. **rgb 表示法：** `rgb(红, 绿, 蓝)`，取值范围都是 `0 - 255`。
    
4. **rgba 表示法（控制透明度）：** 比 rgb 多了一个 `a`（Alpha），取值 `0 - 1`。比如 `rgba(0, 0, 0, 0.5)` 就是 **50% 透明度的半透明黑色**，常用来做网页的遮罩层或弹窗背景。
    

### 实战演练：完整代码实现

为了让你更好地理解**外部样式**和**内部样式**，我为你准备了对应的代码。你可以直接用电脑实操：

#### 方法 A：内部样式版（单文件，最适合现在练手）

你可以新建一个 `news.html` 文件，将以下代码贴进去并用浏览器打开：


```HTML
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>央视新闻-标题样式（内部样式版）</title>
    
    <style>
        /* 让新闻大标题使用 h1，默认自带样式 */
        h1 {
            color: #333333; /* 靠近黑色的深灰，比纯黑更高级 */
            font-size: 24px;
        }

        /* 选中页面中所有的 a 标签（超链接） */
        a {
            color: #1a0dab; /* 经典的超链接蓝色 */
            text-decoration: none; /* 去掉超链接默认的下划线 */
        }

        /* 选中页面中所有的 span 标签（这里用来包裹时间） */
        span {
            color: gray; /* 第二张图里的颜色控制：灰色 */
            font-size: 14px; /* 字号稍微缩小一点 */
        }
    </style>
</head>
<body>

    <h1>【新思想引领新征程】推进长江十年禁渔 谱写长江大保护新篇章</h1>
    
    <a href="https://www.cctv.com/" target="_blank">央视网</a> 
    
    <span>2024年05月15日 20:07</span>

</body>
</html>
```

#### 方法 B：外部样式版（企业标准，规范写法）

如果你想体验真实的开发规范，可以创建两个文件：

1. 新建一个文件夹名为 `css`，在里面建一个文件叫 `news.css`，代码如下：
    
    ```css
    /* css/news.css */
    h1 {
        color: #333;
    }
    a {
        color: #1a0dab;
        text-decoration: none;
    }
    span {
        color: gray;
    }
    ```
    
2. 在外面新建 `news_outer.html`，通过 `<link>` 标签引入它：
    
    ```HTML
    <!DOCTYPE html>
    <html lang="zh-CN">
    <head>
        <meta charset="UTF-8">
        <title>央视新闻-标题样式（外部样式版）</title>
        <link rel="stylesheet" href="css/news.css">
    </head>
    <body>
        <h1>【新思想引领新征程】推进长江十年禁渔 谱写长江大保护新篇章</h1>
        <a href="https://www.cctv.com/" target="_blank">央视网</a> 
        <span>2024年05月15日 20:07</span>
    </body>
    </html>
    ```
    

---
---


## 央视新闻—标题—样式（选择器）


![[Java Web笔记-2.png]]


这一课非常关键！**CSS 选择器（Selector）** 是 CSS 的灵魂。

简单来说，选择器就是一具“瞄准镜”。你在 `<style>` 里写了一堆漂亮的皮肤（样式），但浏览器怎么知道这些皮肤该套在哪个 HTML 标签上呢？就得靠选择器去**精准定位**。

图片中黑马程序员列出了 6 种选择器，作为 Java 后端开发者，我帮你梳理一下哪些是**高频必会**，哪些是**未来跟后端交互息息相关**的。


### 1. 元素选择器（标签选择器）

- **写法：** 直接写标签名，如 `h1 { ... }` 或 `span { ... }`。
    
- **效果：** 宁可错杀一千，绝不放过一个。页面上**所有**该标签都会被套用样式。
    
- **使用场景：** 通常用来做通用的初始化设置（比如让页面上所有的超链接 `a` 默认都不带下划线）。
    

### 2. 类选择器（Class Selector）🌟【最高频】

- **写法：** 前面加一个点 `.`，后面跟自定义的名字。例如 `.cls { ... }`。在 HTML 中通过 `class="cls"` 引入。
    
- **效果：** 精准打击，谁带了这个 `class` 属性，谁就变样。一个页面里可以有很多标签共用同一个 `class`。
    
- **后端视角：** 以后用动态模板技术（比如 Thymeleaf）或者前端框架循环输出数据（比如循环输出商品列表）时，每个商品卡片的标签上都会套上同一个 `class`。
    

### 3. id 选择器 🌟【与后端/JS交互核心】

- **写法：** 前面加个井号 `#`，后面跟自定义名字。例如 `#hid { ... }`。在 HTML 中通过 `id="hid"` 引入。
    
- **效果：** 独一无二。在一个 HTML 页面里，**同一个 id 名称只能出现一次**。
    
- **后端视角：** **极其重要！** 虽然它能控制 CSS，但它更重要的舞台是在 **JavaScript 和自动化测试** 中。当后端传过来数据，前端 JS 想要精准修改某一个特定的标签（比如订单状态的那个小方块）时，通常会通过 `document.getElementById("order-status")` 来锁死它。
    

### 4. 属性选择器 🌟【表单处理核心】

- **写法：** 标签名加上中括号，里面写属性。例如 `input[type="text"] { ... }`。
    
- **效果：** 筛选出带有特定属性的标签。
    
- **后端视角：** 后端接触最多的 HTML 标签就是 `<input>`（输入框）。输入框有很多种（文本框 `type="text"`、密码框 `type="password"`、提交按钮 `type="submit"`）。通过属性选择器，前端可以单独给密码框加一个“小眼睛”图标，而不影响普通的文本框。
    

### 5. 后代选择器

- **写法：** 两个选择器中间**用空格隔开**。例如 `form input { ... }`。
    
- **效果：** 选中祖先元素里面的后代元素。图里的例子意思是：只选中 `<form>` 标签内部的 `<input>` 标签，外面单独存在的 `<input>` 不受影响。
    

### 实战演练：完整结合代码

我们把这些选择器融入到之前的央视新闻案例中。通过下面的代码，你能清晰地看到**元素、类、id、后代选择器**是如何同台竞技的：


```HTML
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>央视新闻-选择器实战</title>
    <style>
        /* 1. 元素选择器：让页面上所有 h1 基础字体都变大 */
        h1 {
            font-size: 24px;
        }

        /* 2. 类选择器（以 . 开头）：定义一个灰色的样式 */
        .text-muted {
            color: #b2b2b2; /* 对应图中的灰色 #b2b2b2 */
            font-size: 14px;
        }

        /* 3. id 选择器（以 # 开头）：专门用来高亮显示特定的核心链接 */
        #main-link {
            color: #ff0000; /* 央视红 */
            font-weight: bold; /* 加粗 */
            text-decoration: none;
        }

        /* 4. 后代选择器（空格隔开）：只有在新闻盒子(news-box)内部的 a 标签才会变成深蓝色 */
        .news-box a {
            color: #1a0dab;
        }
    </style>
</head>
<body>

    <div class="news-box">
        
        <h1>【新思想引领新征程】推进长江十年禁渔 谱写长江大保护新篇章</h1>
        
        <a id="main-link" href="https://www.cctv.com/" target="_blank">央视网</a> 
        
        <span class="text-muted">2024年05月15日 20:07</span>

    </div>

    <hr>
    <a href="https://www.baidu.com">我是外面的普通链接</a>

</body>
</html>
```

### 额外赠送一个面试高频考点：选择器的优先级

当一个标签同时被多个选择器盯上时（比如上面代码里的央视网标签），谁说了算？

CSS 有一套权重计算规则，简单来说：

> **`id 选择器 (#)` > `类选择器 (.)` > `元素选择器 (标签名)`**

这也是为什么上面的“央视网”链接最终听了 `#main-link` 的话变成了红色，而不是后代选择器的蓝色。把这段代码跑一下，感受一下选择器的威力吧！


---
---


## 央视新闻—正文—排版


![[Java Web笔记-3.png]]



你已经从“标题”顺利推进到“正文排版”了！这一节黑马程序员带你解锁了网页最核心的内容载体：**视频、图片和段落**，并且引入了一个全栈开发（尤其是后端）**每天都要打交道、极容易踩坑**的概念——**资源路径**。

让我们用后端的逻辑，把这一课的精华彻底榨干。


### 1. `<p>` 段落标签 (Paragraph)

- **作用：** 把正文文字包裹起来。它最显著的特点是：**自带换行**，并且段落与段落之间会默认留有一点空白间距。
    
- **后端视角：** 以后做博客系统、新闻系统或者商品详情，后端从数据库里查出来的“长文本”（Java 中的 `String`），前端通常会通过高级文本编辑器（如富文本编辑器）在段落两端自动加上 `<p>` 和 `</p>`，再展示在网页上。
    

### 2. `<img>` 图片标签 (Image) 与 `<video>` 视频标签

这两个多媒体标签有共同的灵魂属性：

- **`src` (Source)：** 资源的路径。告诉浏览器去哪里把图片或视频抓过来显示。
    
- **`width` 和 `height`：** 控制尺寸。一般在实际开发中，我们**只设置其中一个（比如只设 width）**，另一个让浏览器等比例自动缩放，否则图片会变形（被拉长或压扁）。
    
- **`<video>` 的 `controls` 属性：** 极其重要。如果不写这个属性，视频在网页上就像一张静态图，没有任何播放、暂停、进度条和音量按钮。写上了它，浏览器才会调出播放控件。
    
- `alt`**（alternate text）：** 图片加载失败时，显示的文字描述；也是给特殊用户、搜索引擎看的图片说明


### 重中之重：资源路径写法（后端高频踩坑点）

图片下方重点讲解了路径，这是后端开发者的“重灾区”（不仅前端写路径，后端读写文件、引包也天天用）。

#### ① 绝对路径

不管你当前代码文件在哪，直接一步到位的死地址。

- **绝对磁盘路径（如 `D:/xxx.jpg`）：** ❌ **在 Web 开发中绝对不要用！** * _后端避坑提示：_ 如果你在代码里写了磁盘路径，代码在你的 Windows 电脑上跑得好好的。一旦部署到 Linux 服务器上，Linux 根本没有 `D盘` 概念，网页上的图片瞬间全部变成打叉的碎图。
    
- **绝对网络路径（如 `https://xxx.com/img.jpg`）：** 主流写法。把图片上传到专门的图片服务器（如阿里云 OSS、腾讯云 COS）后拿到的网络 URL。
    

#### ② 相对路径（最推荐的本地测试写法）

以**当前编写的 HTML 文件所在的位置**为参考起点去寻宝。

- `./`：当前目录下。如果图片和 HTML 在同一个文件夹，可以写 `./pic.jpg`（`./` 也可以省略不写）。
    
- `../`：**跳出当前文件夹，去上一级目录**找。
    

### 实战演练：正文排版完整代码

为了完美还原图片中的央视新闻正文排版（视频 + 文字段落 + 鱼的图片），我们需要把这些标签和路径知识组合起来。

你可以找一个本地的视频和图片（或者直接用我代码里提供的网络绝对路径），新建一个 `article.html` 运行体验：


```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>央视新闻-正文排版实战</title>
    <style>
        /* 简单用 CSS 让内容居中好看点，限制一下最大宽度 */
        .container {
            width: 700px;
            margin: 0 auto; /* 页面居中 */
            font-family: "Microsoft YaHei", sans-serif;
        }
        
        /* 控制正文字体样式 */
        p {
            font-size: 16px;
            color: #333333;
            line-height: 1.8; /* 设置行高，让密密麻麻的字看起来不挤 */
            text-indent: 2em; /* 赠送小技巧：每个段落开头自动空两格 */
        }
    </style>
</head>
<body>

<div class="container">

    <video src="https://vjs.zencdn.net/v/oceans.mp4" controls width="100%"></video>

    <p>
        <b>央视网消息</b>（新闻联播）：作为共抓长江大保护的标志性工程，长江十年禁渔今年进入第四年。
        习近平总书记指出，长江禁渔是为全局计、为子孙谋的重要决策。牢记总书记嘱托，沿江省市持续推
        进长江水生生物多样性恢复，努力保障退捕渔民就业生活。这段时间，记者深入长江两岸，记录下禁
        渔工作取得的重要阶段性成效和广大干部群众坚定不移推进长江十年禁渔的扎实行动。
    </p>
    
    <p>
        行走在长江沿线，科研人员发现很多喜人现象。
    </p>

    <img src="https://img-s-msn-com.akamaized.net/tenant/amp/entityid/BB1m9T8S.img" alt="长江禁渔成果" width="100%">

</div>

</body>
</html>
```

### 思考一个后端场景：

当你未来写完 Java 后端，用户在管理后台上传了一张新的新闻图片。你的 Java 代码会把图片存到服务器的某个文件夹里，然后把这张图片的**路径**（通常是相对路径或网络绝对路径）存入 MySQL 数据库。当前端请求这条新闻时，你的 Java 后端就把这个路径字符串传给前端，前端拿到后直接塞进 `<img>` 的 `src` 属性里。

这就是 Web 前后端打配合的完整闭环！代码跑起来试试看吧！


---
---



## 央视新闻—正文—样式


![[Java Web笔记-4.png|697]]


这一节课的信息量非常实用，提到了**文本格式化标签**、**字符实体（转义字符）** 以及**文本排版专属的 CSS 属性**。

在这里，黑马程序员特别强调了“强调语义”这个词。作为后端和未来的全栈开发者，我们需要从“底层逻辑”来理解为什么同样的视觉效果，会有两套不同的标签。

### 核心点一：文本格式化标签（视觉 vs 语义）

图中展示了四组标签，每一组在浏览器里看效果几乎一模一样，但底层含义完全不同：

|**纯视觉标签 (旧写法)**|**具有强调语义的标签 (现代标准)**|**网页上的视觉效果**|
|---|---|---|
|`<b>` (Bold)|**`<strong>`**|**文字加粗**|
|`<u>` (Underline)|**`<ins>`** (Insert)|文字下划线|
|`<i>` (Italic)|**`<em>`** (Emphasized)|_文字倾斜_|
|`<s>` (Strikethrough)|**`<del>`** (Delete)|~~文字删除线~~（常用于电商原价）|

#### 为什么现代开发一定要用右边的“语义化标签”？

1. **盲人读屏软件：** 视障人士使用读屏软件听网页时，遇到 `<strong>` 或 `<em>`，软件会**加重语气**读出来，而遇到 `<b>` 则不会。
    
2. **SEO（搜索引擎优化）：** 百度、谷歌的爬虫能看懂语义。它们看到 `<strong>` 会知道这是本篇文章的**关键字**，从而给这篇网页更高的搜索排名。
    

### 核心点二：字符实体 (HTML 转义字符)

这是**后端安全和防踩坑**的必考点。

在 HTML 中，如果你直接在正文里敲一串空格，或者写大于号小于号，浏览器会**非常困惑**。因为 `<` 和 `>` 是用来定义 HTML 标签的（比如 `<a>`）。为了避免冲突，必须使用“密码”来代替它们：

- **`&nbsp;`（Non-Breaking Space）：** 空格。在 HTML 代码里，不管你连着敲 10 个空格键，浏览器最终也只认一个。如果你想在网页上连续空几个格，就必须连着写 `&nbsp;&nbsp;&nbsp;`。
    
- **`&lt;`（Less Than）：** 小于号 `<`。
    
- **`&gt;`（Greater Than）：** 大于号 `>`。
    

#### 后端核心关联：防止 XSS 攻击

未来你写 Java Web 项目，如果用户在评论框里恶意输入：`<script>alert('你被黑了')</script>`，如果你的 Java 后端原封不动地把这串字符串存入数据库并展示给其他用户，其他用户的浏览器就会执行这段恶意 JS 代码！

**解决办法：** 后端在接收或输出数据时，要把 `<` 和 `>` 转义成 `&lt;` 和 `&gt;`。这样浏览器就只会把它当成普通的文本显示出来，而不会当成代码执行。

### 核心点三：文本专属 CSS 属性

图片最下方给出了两个调整文章阅读体验的极佳属性：

- **`line-height`（行高）：** 用来控制行与行之间的垂直间距。纯文本默认挤在一起很难看，一般我们会设为 `1.5` 或 `1.8`（即字号的 1.5 到 1.8 倍），或者 `24px`。
    
- **`text-indent`（首行缩进）：** 按照中国人的阅读习惯，文章段落开头要空两格。我们在 CSS 里写 `text-indent: 2em;`。
    
    - _名词解释：_ `em` 是一个相对单位，**`1em` 等于当前 1 个字的宽度**。`2em` 就是雷打不动地刚好空出两个字的位置。
        

### 实战演练：完整结合代码

我们把上面的**语义化标签、转义字符、以及行高缩进 CSS** 完美融入到央视新闻的正文中。

你可以创建一个 `news_detail.html` 文件来跑这段代码：


```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>央视新闻-正文样式高级版</title>
    <style>
        .news-content {
            width: 600px;
            margin: 20px auto;
            font-family: "Microsoft YaHei", sans-serif;
        }

        /* 控制正文段落的 CSS 属性 */
        p {
            font-size: 16px;
            color: #333333;
            
            /* 1. 设置行高，让排版更疏朗呼吸感 */
            line-height: 1.8; 
            
            /* 2. 首行缩进 2 个字的宽度（无需手动敲空格） */
            text-indent: 2em; 
        }

        /* 专门给电商促销或者特殊标记价格用的删除线样式 */
        .old-price {
            color: #999;
            font-size: 12px;
        }
    </style>
</head>
<body>

<div class="news-content">

    <p>
        <strong>央视网消息</strong>（新闻联播）：长江十年禁渔今年进入第四年。
        沿江省市持续推进长江水生生物多样性恢复。科研人员在检测时发现，
        长江某流域的鱼类密度 <strong>&gt;</strong> 过去五年的平均值（此处用了转义大于号）。
    </p>
    
    <p>
        我们在写代码时，如果要表达 <em>a &lt; b</em>（这里用了转义倾斜和小于号），
        必须使用字符实体，否则浏览器会产生解析错误。
    </p>

    <p>
        相关周边纪念品原价：<del class="old-price">￥99.00</del> 现价：￥19.90
    </p>

</div>

</body>
</html>
```

点击运行，你会发现即使我们没有在代码正文里手敲空格，每一个 `<p>` 段落的开头也都整整齐齐地空出了两个字的位置，而且大于号、小于号也都能完美且安全地显示出来了！

---
---

## 央视新闻—整体布局


![[Java Web笔记-5.png]]


高能预警！你现在进入到了 Web 前端开发**最核心、最经典、同时也是初学者最容易懵圈**的领域——**盒子模型（Box Model）与页面布局**。

在网页世界里，其实根本没有“文本”或“图片”，**所有看到的元素，底层全部都是一个一个矩形的“盒子”**。网页排版，就是在大盒子里面套小盒子，然后把它们像积木一样拼起来。

下面我们结合这张图，彻底搞懂网页布局的底层秘籍。

### 核心点一：两个万能的布局“塑料袋” (`div` 与 `span`)

以前学的 `<h1>`、`<p>` 都有自己的长相和含义，而 `<div>` 和 `<span>` 是两个**完全没有语义**的标签。它们生来就是为了**装载其他内容、方便用 CSS 调整结构和样式**的。

它们代表了 HTML 中最基础的两种元素类型：

#### 1. `<div>` 标签 —— 块级元素 (Block-level)

- **霸道总裁：** 它非常霸道，**必须独占一行**。即便你给它设置了很窄的宽度，右边的空间它也空着，不让别人跟它并排。
    
- **特点：** 宽度默认和父元素一样宽，高度由里面的内容撑开。**可以自由设置宽度 (`width`) 和高度 (`height`)**。
    
- **用途：** 网页的“大结构框架”（比如头部、侧边栏、正文大盒子）。
    

#### 2. `<span>` 标签 —— 行内元素 (Inline)

- **随和路人：** 它很温柔，**一行可以显示多个**。直到这一行挤不下了，才会自动折行。
    
- **特点：** 宽和高完全由里面的内容撑开，**不可以直接设置宽高**（写了 `width: 200px` 也会被浏览器直接忽略）。
    
- **用途：** 用来包裹文章里的“个别词汇”或者小图标，方便单独给它们变个颜色或加粗（就像之前包围新闻时间的写法）。
    

### 核心点二：揭秘“盒子模型”的四大组成部分

看图片右上角的那个绿色示意图，任何一个盒子，从内到外都由四个部分组成：

1. **Content (内容)：** 盒子里装的真正东西（文字、图片、或者嵌套的小盒子）。通过 `width` 和 `height` 设置。
    
2. **Padding (内边距/内衬)：** **内容**到**边框**之间的距离。就像买手机时，手机（内容）和包装盒边框之间的泡沫塑料填充层。
    
3. **Border (边框)：** 盒子的壳。可以设置粗细、样式（实线、虚线）和颜色。
    
4. **Margin (外边距)：** **盒子**与**另外一个盒子**之间的距离。它是完全透明的，用来防止两个盒子挨得太近。
    

### 核心点三：CSS 边距缩写“顺时针口诀”

图片下方展示了 `padding` 和 `margin` 的三种经典写法。参数变少时，浏览器有一套固定的“补齐”规则：

- **写满 4 个值（图左）：** `margin: 30px 20px 10px 40px;`
    
    - **口诀：顺时针方向。** 依次代表 **[ 上、右、下、左 ]**。
        
- **写 2 个值（图中）：** `margin: 30px 20px;`
    
    - **口诀：前控上下，后控左右。** 依次代表 **[ 上下是30px，左右是20px ]**。
        
- **只写 1 个值（图右）：** `margin: 30px;`
    
    - **全员统一：** 代表 **[ 上、下、左、右 全部都是30px ]**。
        

### 实战演练：完整还原央视新闻大盒子布局

我们把之前所有的案例（标题、来源、时间、视频、正文）用一个高大上的 `div` 大盒子**包裹**起来，并利用盒子模型让整个新闻页在浏览器里变得精致、居中、有呼吸感。

新建 `news_layout.html` 体验完整布局：


```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>央视新闻-整体布局实战</title>
    <style>
        /* 1. 外层最大的盒子布局 */
        .news-container {
            width: 650px;             /* 设置内容宽度 */
            background-color: #fff;  /* 盒子背景为纯白 */
            
            /* 核心应用： border (边框) */
            border: 1px solid #e5e5e5; /* 给大盒子加一个淡淡的灰色边框 */
            
            /* 核心应用： padding (内边距) */
            /* 2个值写法：上下留出 30px 空间，左右留出 40px 空间，防止文字死贴着边框 */
            padding: 30px 40px;       
            
            /* 核心应用： margin (外边距) */
            /* 炫酷技巧：上下留 40px，左右设为 auto 表示由浏览器自动平分。大盒子瞬间在屏幕居中！ */
            margin: 40px auto;        
            
            box-shadow: 0 4px 12px rgba(0,0,0,0.05); /* 加一点点现代感的阴影 */
        }

        /* 2. 新闻发布信息盒子的布局 */
        .info-box {
            /* 这是一个 span，它默认不能设置 margin-bottom。 */
            /* 所以黑马程序员用一个 div 把来源和时间包起来，利用 div 的独占一行和外边距把下面的视频推开 */
            margin: 15px 0 25px 0; /* 顺时针：上15px，右0，下25px，左0 */
            font-size: 14px;
        }

        .source {
            color: #1a0dab;
            text-decoration: none;
            margin-right: 15px; /* 让“央视网”和后面的时间拉开 15px 的距离 */
        }

        .time {
            color: #b2b2b2; /* 对应图上的灰色 */
        }

        /* 3. 正文段落布局 */
        p {
            font-size: 16px;
            color: #333;
            line-height: 1.8;
            text-indent: 2em;
            margin-bottom: 20px; /* 段落与下面的元素保持 20px 距离 */
        }
    </style>
</head>
<body style="background-color: #f5f5f5;"> <div class="news-container">
    
        <h1 style="font-size: 26px; line-height: 1.4; color: #000;">
            【新思想引领新征程】推进长江十年禁渔 谱写长江大保护新篇章
        </h1>
        
        <div class="info-box">
            <a class="source" href="https://www.cctv.com/" target="_blank">央视网</a>
            <span class="time">2024年05月15日 20:07</span>
        </div>

        <video src="https://vjs.zencdn.net/v/oceans.mp4" controls width="100%" style="margin-bottom: 20px;"></video>

        <p>
            <strong>央视网消息</strong>（新闻联播）：作为共抓长江大保护的标志性工程，长江十年禁渔今年进入第四年。
            沿江省市持续推进长江水生生物多样性恢复，努力保障退捕渔民就业生活。
        </p>
        
        <p>
            行走在长江沿线，科研人员发现很多喜人现象。
        </p>

        <img src="https://img-s-msn-com.akamaized.net/tenant/amp/entityid/BB1m9T8S.img" alt="成果" width="100%">

    </div>

</body>
</html>
```

这段代码跑起来，在浏览器里看，就已经是一个**完全可以上线商用的、极其规范的高级新闻网页**了。当你通过写盒子的边距和宽高把它们安排得整整齐齐时，恭喜你，你的前端基础已经过关了！

---
---


## 表单标签


![[Java Web笔记-8.png]]



之前学的排版（文字、视频、布局）都是后端往前端“发数据”（只读）；而表单，是**前端往后端“收数据”**（交互）。用户注册、登录、修改密码、发布评论，全部都要走表单。

我们直接用纯正的 **Java 后端视角**，把这三个核心标签和两个致命属性彻底剥离出来：

### 一、 后端管家：`<form>` 表单大容器

`<form>` 标签在网页上默认是看不见的，它像一个“快递打包盒”，把盒子里所有用户填的数据打包，然后寄给后台。它有两个决定命运的属性（见图属性栏）：

#### 1. `action` 属性

- **干嘛的：** 规定当用户点击提交时，数据要发给远方的**哪个接口 URL**。
    
- **后端视角：** 这里写的就是你未来写的 Java 控制器（Controller/Servlet）的路由地址。
    
    - 比如：`action="/login"`。
        

#### 2. `method` 属性 🌟【面试必问】

规定用什么方式发送数据，最核心的就是 `GET` 和 `POST`：

- **`GET`：** 顺风车。数据会**直接暴露在浏览器的网址栏后面**（形如 `/search?username=admin&pwd=123`）。
    
    - _致命缺点：_ 极不安全（密码全看见了）、传输数据量很小。一般只用于**搜索、查询**数据。
        
- **`POST`：** 押运车。数据会被包裹在 **HTTP 请求体（Request Body）** 里面。
    
    - _巨大优势：_ 网址栏干净，相对安全；能传输海量数据（比如上传头像、发长博文）。所以**登录、注册、提交敏感数据必须用 `POST`**。
        

### 二、 核心表单项组件

#### 1. `<input>` 标签（全能百变怪）

它通过修改 `type` 属性的值，能瞬间变成完全不同的长相：

- `type="text"`：普通文本框。
    
- `type="password"`：密码框（输入的字会自动变成小黑点 ）。
    
- `type="radio"`：单选框（比如选性别 男/女，需要设置相同的 `name` 属性才能实现互斥）。
    
- `type="checkbox"`：多选框（比如选兴趣爱好 篮球/足球/编程）。
    
- `type="submit"`：**提交按钮**。点击它就会立刻触发 `<form>` 的打包寄件。
    

#### 2. `<select>` 标签（下拉列表）

用于省市区选择、职位选择等，配合内部的 `<option>` 标签使用。

#### 3. `<textarea>` 标签（文本域）

可以拉伸的多行文本框，用于发评论、填备注等长文字。

### 后端开发天条：没有 `name` 属性，后端直接“抓瞎”

这是初学者 99% 都会踩的惊天巨坑。

在表单项（如 `<input>`）中，**必须写 `name` 属性**！

- **为什么：** 假设用户在文本框里输入了 `admin`。如果你的标签只写了 `<input type="text">`，点击提交后，你的 Java 后端确实收到了一个 `admin`。但 Java 会崩溃：“这 `admin` 到底是个啥？是用户名？还是密码？还是邮箱？”浏览器提交表单时，只会把**有 name 属性**的控件按 `name=值` 发给服务器
    
- **正确做法：** 必须写上 `<input type="text" name="username">`。这样打包发送时，数据就会变成键值对：`username=admin`发给服务器。你的 Java 代码就能通过 `request.getParameter("username")` 极其优雅地把数据拿出来了！
    

| 属性     | 是否需要唯一                   | 核心用途                             |
| ------ | ------------------------ | -------------------------------- |
| `id`   | **整个html页面必须全局唯一**       | 配合 label 的`for`、CSS 定位、JS 精准查找元素 |
| `name` | html页面可重复，**仅表单提交时分组生效** | 后端接收表单参数、单选 / 复选互斥分组             |


### 实战演练：完整还原“账号/短信登录”表单结构

我们参考“账号登录”弹窗原型，亲手写一个标准的、符合后端接收规范的表单页面。

新建 `login_form.html` 体验：

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>tlias系统-用户登录表单</title>
    <style>
        .login-box {
            width: 380px;
            margin: 100px auto;
            padding: 30px;
            background-color: #ffffff;
            border: 1px solid #e5e5e5;
            box-shadow: 0 4px 15px rgba(0,0,0,0.08);
            font-family: "Microsoft YaHei", sans-serif;
        }
        .form-item {
            margin-bottom: 20px;
        }
        .form-item label {
            display: block;
            margin-bottom: 8px;
            font-size: 14px;
            color: #666;
        }
        /* 批量美化所有的输入框和下拉框 */
        .form-item input[type="text"], 
        .form-item input[type="password"],
        .form-item select,
        .form-item textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
            outline: none;
        }
        /* 美化提交按钮 */
        .submit-btn {
            width: 100%;
            padding: 12px;
            background-color: #7bc3a1; /* tlias 经典绿 */
            color: white;
            border: none;
            border-radius: 4px;
            font-size: 16px;
            cursor: pointer;
        }
        .submit-btn:hover {
            background-color: #69b390;
        }
    </style>
</head>
<body style="background-color: #f4f4f4;">

    <div class="login-box">
        <h2 style="margin-bottom: 25px; text-align: center; color: #333;">tlias 账号登录</h2>
        
        <form action="/login" method="POST">
            
            <div class="form-item">
                <label>用户名 / 手机号 / 邮箱：</label>
                <input type="text" name="username" placeholder="请输入您的账号" required>
            //placeholder代表输入框里面没有东西时的提示词
            </div>
            
            <div class="form-item">
                <label>登录密码：</label>
                <input type="password" name="password" placeholder="请输入密码" required>
            </div>

            <div class="form-item">
                <label>登录角色：</label>
                <select name="role">
                    <option value="admin">系统管理员</option>
                    <option value="teacher">授课讲师</option>
                    <option value="student">学员</option>
                </select>
            </div>
            
            <button type="submit" class="submit-btn">登 录</button>
            
        </form>
    </div>

</body>
</html>
```



>[!tip]
>`<label>` 就是**给表单元素（输入框、单选框、复选框等）加文字标签**的标签，核心作用是**让文字和表单控件绑定在一起**，必须配合 `input`、`select` 等表单控件使用。
>- **点击文字也能选中 / 激活表单**
 >   不用精准点小圆圈 / 小方框，点旁边的文字就能操作，用起来更方便。
 >- **提升无障碍性**
 >  屏幕阅读器能识别文字和表单的对应关系，方便视障用户使用
 >
 >```html
 ><!-- 绑定方式1：for 属性对应 input 的 id -->
 > <input type="radio" id="male" name="gender"> 
 > <label for="male">男</label> 
 > <!-- 绑定方式2：直接把 input 包在 label 里 --> 
 > <label> <input type="checkbox"> 同意协议 </label>
 >```
 >==注意上面的代码例子中没有使用这两种绑定，那么label只是纯普通文字==
 >```html
 >//写法一：
 ><label for="pwd">登录密码：</label>
 > <input type="password" id="pwd" name="password">
 >```
 >```html
 >//写法二：
 ><label> 登录密码： <input type="password" name="password"> </label>
 >```
 >```html
 >//下拉列表同理
 ><label for="role">登录角色：</label> 
 ><select name="role" id="role"> 
 ><option value="admin">系统管理员</option> 
 >...
 > </select>
 >```



当你把这个表单跑起来，尝试在框里输入一些内容并点击“登录”按钮，虽然因为还没有写 Java 后端会报一个 `404` 错误，但你会发现浏览器的地址栏依然非常干净。因为我们使用了 `method="POST"`！





---
---

## tlias练习案例—顶部导航栏



![[Java Web笔记-6.png]]



![[Java Web笔记-7.png]]



绝了！你已经肝到现代前端排版的超级大招——**Flex 布局（弹性盒子布局）**，并且开始做后台管理系统（tlias 智能学习辅助系统）的实战案例了。

对于 Java 后端开发者来说，**Flex 布局是全栈路上性价比最高的技术**。过去用 `float`（浮动）做对齐能让人抓狂到头秃，而现代开发的导航栏、工具栏，基本全靠 Flex **一键对齐**。

根据你发的两张新图，我们直接来攻克这个“顶部导航栏”。

### 核心武器：Flex 布局的三板斧

Flex 布局的核心逻辑是：**给父容器发号施令，控制里面所有子元素的排布。** 要搞定顶部导航栏，你只需要掌握这三个属性：

1. **`display: flex;`**
    
    - **大招激活：** 只要给父盒子（比如导航栏的大 `div`）加上这句话，里面原本要“独占一行”的子元素们，瞬间就会像听话的士兵一样，**全都在同一行并排站好**。
        
2. **`flex-direction`（决定主轴方向）**
    
    - 默认是 `row`（水平从左到右）。导航栏里的 Logo 和文字需要横着排，所以用默认的就行。
        
3. **`justify-content`（子元素在主轴上的对齐/分发方式）** 🌟【核心】
    
    - 看管理系统的原型图：左边是系统名字 “tlias 智能学习辅助系统”，右边是 “退出登录”。它们一个死贴着最左，一个死贴着最右。
        
    - 这正是图里对应的 **`space-between`（先两边贴边，再平分剩余空间）** 的完美使用场景！
        

### 实战演练：完整还原 tlias 顶部导航栏

为了让你彻底吃透，我们把“盒子模型”和“Flex 布局”结合起来。下面是纯正的 **tlias 顶部导航栏** 还原代码：


```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>tlias智能学习辅助系统-顶部导航栏</title>
    <style>
        /* 全局初始化，清除浏览器自带的边距 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box; /* 让 border 和 padding 不撑大盒子，后端开发极力推荐 */
        }

        body {
            font-family: "Microsoft YaHei", sans-serif;
            background-color: #f4f4f4;
        }

        /* 1. 顶部导航栏父容器 */
        .header {
            /* 激活 Flex 弹性布局 */
            display: flex;
            /* 核心对齐：让左边的标题和右边的退出登录分别贴紧两头 */
            justify-content: space-between;
            /* 辅助属性：让子元素在垂直方向上居中对齐 */
            align-items: center; 

            /* 导航栏的尺寸与皮肤样式 */
            height: 60px;
            background-color: #7bc3a1; /* 对应原型图上的标志性青绿色 */
            padding: 0 20px;           /* 左右留出 20px 边距，防止内容死贴屏幕边缘 */
            color: white;
        }

        /* 2. 左侧系统名称样式 */
        .header .logo-title {
            font-size: 22px;
            font-weight: bold;
            letter-spacing: 1px; /* 字间距拉开一点显得更专业 */
        }

        /* 3. 右侧用户信息与操作区 */
        .header .user-actions {
            display: flex;
            align-items: center;
            font-size: 14px;
        }

        /* 退出登录按钮样式 */
        .logout-btn {
            color: rgba(255, 255, 255, 0.8);
            text-decoration: none;
            margin-left: 20px; /* 与前面的用户名拉开距离 */
            padding: 4px 8px;
            border: 1px solid rgba(255, 255, 255, 0.5);
            border-radius: 4px; /* 微微圆角 */
            transition: all 0.3s; /* 鼠标悬停动画 */
        }

        /* 鼠标悬停在退出登录上的视觉反馈 */
        .logout-btn:hover {
            color: white;
            background-color: rgba(255, 255, 255, 0.2);
        }
    </style>
</head>
<body>

    <div class="header">
        
        <div class="logo-title">
            tlias 智能学习辅助系统
        </div>
        
        <div class="user-actions">
            <span>欢迎你，管理员</span>
            <a href="/logout" class="logout-btn">退出登录</a>
        </div>

    </div>

</body>
</html>
```

### 后端大局观提示：

注意看右侧“退出登录”的超链接我写的是 `href="/logout"`。

以后当你学到 Java Web 的高级框架（如 Spring Security 或 Shiro）时，当用户点击这个按钮，前端就会向后端发送一个 `/logout` 请求。你的 Java 后端会立刻销毁当前用户的 `Session`（清空登录状态），然后让页面重定向（跳转）回 `login.html` 登录页。

把代码跑起来，拉伸一下浏览器的宽度，你会发现不管屏幕多宽，左边的标题和右边的退出按钮都会雷打不动地贴在两边。这就是 Flex 布局的魅力！


---
---



## tlias练习案例—搜索表单区域


这个“搜索表单区域”在企业后台管理系统中属于**骨灰级高频场景**。不管去哪家公司做 Java 后端，你逃不掉的第一个任务，往往就是给这种列表页写**多条件组合查询**的接口。

从图片上看，这一块（搜索表单区域）包含了：

1. 文本输入框（姓名）
    
2. 下拉选择框（性别）
    
3. 下拉选择框（职位）
    
4. 两个按钮（查询、清空）
    

我们继续带着**后端的大局观**，把这一块的前端布局和它对应的**核心 Java 后端逻辑**一次性打通！

### 核心技术拆解

#### 1. 结构与语义（HTML）

为了让这一排输入框老老实实呆在同一行，且具备表单的属性，我们需要：

- 最外层用 `<form>` 包裹。
    
- 内部表单项使用 `display: flex;` 让它们横向排列。
    
- 姓名框：`<input type="text" name="name">`
    
- 性别与职位：使用 `<select name="gender">` 和 `<select name="job">`。
    

#### 2. 后端核心：为什么多条件查询接口必须对空值进行处理？

当用户在前端点击“查询”按钮时，浏览器会将表单数据打包。这里有个细节：如果用户**只输入了姓名，没有选择性别和职位**，前端发过来的请求参数会类似于：

`name=张三&gender=&job=` （性别和职位是空字符串）。

你在写后台 Java 代码（比如 MyBatis 的 SQL 语句）时，必须使用**动态 SQL (`<if>` 标签)**。否则，如果你直接去数据库查 `gender = ''`，就会导致明明有这个人，却因为性别条件被过滤掉而查不出任何数据！

> **MyBatis 动态 SQL 伪代码示意：**

```XML
select * from emp
<where>
    <if test="name != null and name != ''"> name like concat('%', #{name}, '%') </if>
    <if test="gender != null"> and gender = #{gender} </if>
    <if test="job != null"> and job = #{job} </if>
</where>
```

### 实战演练：完整还原 tlias 搜索表单区域

我们将刚才学到的 **Flex 布局**、**盒子模型属性** 和 **表单项标签** 融会贯通，写出符合原型图样式的干净代码。

你可以直接在之前的导航栏代码下面，接着追加下面这个搜索区域的 `div`：

```HTML
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>tlias-搜索表单区域</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: "Microsoft YaHei", sans-serif;
            background-color: #f4f4f4;
            padding: 20px; /* 让整个页面离边缘有点间距 */
        }

        /* 搜索表单区域大盒子 */
        .search-area {
            background-color: #fcf0e7; /* 对应原型图上的淡淡橙粉色背景 */
            padding: 15px 20px;
            border-radius: 4px;
            margin-bottom: 20px;
        }

        /* 激活 Flex 布局，让表单内的元素全部横向一字排开 */
        .search-form {
            display: flex;
            align-items: center; /* 垂直居中对齐 */
            flex-wrap: wrap;     /* 如果屏幕太窄，允许自动换行 */
        }

        /* 每个表单项（文字+输入框）的包裹盒子 */
        .form-group {
            display: flex;
            align-items: center;
            margin-right: 25px; /* 每个输入组件之间拉开 25px 距离 */
        }

        /* 表单前面的小标题提示（如“姓名：”） */
        .form-group label {
            font-size: 14px;
            color: #333;
            margin-right: 10px; /* 提示文字和输入框挨得别太紧 */
            font-weight: bold;
        }

        /* 统一控制文本框和下拉框的精细样式 */
        .form-group input, .form-group select {
            height: 32px;
            padding: 0 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
            outline: none;
            background-color: #fff;
        }
        
        /* 稍微控制一下姓名框的宽度 */
        .form-group input[type="text"] {
            width: 160px;
        }

        /* 按钮公共样式 */
        .btn {
            height: 32px;
            padding: 0 15px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 14px;
            margin-right: 10px;
        }

        /* 查询按钮：亮蓝色 */
        .btn-query {
            background-color: #00a0e9;
            color: white;
        }
        .btn-query:hover {
            background-color: #008cd1;
        }

        /* 清空按钮：灰色 */
        .btn-clear {
            background-color: #999;
            color: white;
        }
        .btn-clear:hover {
            background-color: #888;
        }
    </style>
</head>
<body>

    <div class="search-area">
        <form class="search-form" action="" method="GET">
            
            <div class="form-group">
                <label>姓名</label>
                <input type="text" name="name" placeholder="请输入员工姓名">
            </div>

            <div class="form-group">
                <label>性别</label>
                <select name="gender">
                    <option value="">请选择</option>
                    <option value="1">男</option>
                    <option value="2">女</option>
                </select>
            </div>

            <div class="form-group">
                <label>职位</label>
                <select name="job">
                    <option value="">请选择</option>
                    <option value="1">班主任</option>
                    <option value="2">讲师</option>
                    <option value="3">学工主管</option>
                </select>
            </div>

            <button type="submit" class="btn btn-query">查询</button>
            <button type="reset" class="btn btn-clear">清空</button>

        </form>
    </div>

</body>
</html>
```

### 绝妙设计解析：

注意看我的性别和职位下拉框里的 `<option>`：

文字显示的是“男”、“女”，但给后端传的 `value` 值我写的是 **`1` 和 `2`**。

这也是开发中的黄金标准！因为在 MySQL 数据库里，为了节省空间和提高索引效率，我们通常会用数字 `tinyint` 来存储状态（比如 `1` 代表男，`2` 代表女，`1` 代表班主任...）。前端通过 `value` 属性，把文字直接翻译成了后端数据库最喜欢的数字，前后端的默契就在这里！

把代码跑起来，在里面随便填几个条件点击查询，观察一下浏览器地址栏上的参数变化吧！


---
---


## tlias练习案例—表格数据展示区域


![[Java Web笔记-9.png]]



作为 Java 后端开发者，如果你去翻看你的商业项目或者大厂代码，你会发现数据库里通过 `SELECT * FROM emp` 查出来的 `List<Emp>` 集合数据，到了前端**100% 都是通过这个 `<table >` 标签（或者基于它封装的组件）渲染出来的**。

结合图片，我们用后端视角来解构表格的核心骨架和“潜规则”。

### 1. 表格标签的“四层嵌套”骨架

表格的结构非常严密，就像是一个多维数组。它的嵌套层级是这样的：

- **`<table>`：** 整个表格的最外层大壳子。
    
- **`<thead>`（表头）：** 用来放第一行（姓名、性别、职位等列名）。
    
    - **`<tr>` (Table Row)：** 代表**一行**。
        
    - **`<th>` (Table Header Cell)：** 代表表头里的**加粗单元格**。
        
- **`<tbody>`（表体）：** 用来放真正的业务数据。
    
    - **`<tr>` (Table Row)：** 每一条员工记录就是一行。
        
    - **`<td>` (Table Data Cell)：** 这一行里的**普通数据单元格**。
        

### 2. 后端开发者的“循环渲染”视角

为什么后端必须要懂 `<tbody>` 里的 `<tr>` 和 `<td>`？

因为在实际开发中，这些员工数据（如风清扬、赵敏）绝对不是在 HTML 里死记硬背硬写出来的。

未来你会用前端模板（如 Thymeleaf）或者主流前端框架（如 Vue/React），你的前端代码会通过 **`v-for` 或 `th:each` 标签**，对着后端传过来的 `List` 集合进行**循环遍历**。

> **后端动态渲染伪代码：**

```HTML
<tr v-for="emp in employees">
    <td>{{ emp.name }}</td>
    <td>{{ emp.gender == 1 ? '男' : '女' }}</td>
    <td><img :src="emp.avatar"></td>
    <td>{{ emp.job }}</td>
    <td>{{ emp.entryDate }}</td>
</tr>
```

所以，掌握了基础的 `<tr>` 和 `<td>` 结构，你才能一眼看懂前端框架到底是怎么把你的 Java 对象变成网页表格的。

### 实战演练：完整还原 tlias 员工表格数据区

我们来写一段干净的、符合原型图样式的原生 HTML 表格代码。这里融入了**隔行变色**、**边框合并**等企业后台常用的美化 CSS。

你可以直接新建一个 `employee_list.html` 文件运行体验：


<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>tlias-员工表格数据展示区域</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: "Microsoft YaHei", sans-serif;
            background-color: #f4f4f4;
            padding: 20px;
        }

        /* 1. 表格整体美化 */
        .emp-table {
            width: 100%;
            /* 核心技巧：合并传统的双线边框为单线边框 */
            border-collapse: collapse; 
            background-color: #ffffff;
            font-size: 14px;
            text-align: center; /* 让表格内的文字和图片全部居中对齐 */
        }

        /* 2. 表头样式管理 */
        .emp-table thead {
            background-color: #e2f0d9; /* 对应原型图上的淡绿色表头背景 */
        }
        
        .emp-table th {
            padding: 12px 10px;
            border: 1px solid #d9d9d9; /* 淡淡的灰色边框 */
            color: #333333;
            font-weight: bold;
        }

        /* 3. 表体单元格样式 */
        .emp-table td {
            padding: 10px;
            border: 1px solid #d9d9d9;
            color: #666666;
            vertical-align: middle; /* 让单元格里的图片和文字垂直居中 */
        }

        /* 头像图片微调 */
        .avatar {
            width: 40px;
            height: 40px;
            border-radius: 4px;
            object-fit: cover;
        }

        /* 4. 高级小技巧：隔行变色（让奇数行背景变成浅灰，提高表格阅读体验） */
        .emp-table tbody tr:nth-child(odd) {
            background-color: #fafafa;
        }

        /* 鼠标悬停在某一行时，整行变色提示（Hover反馈） */
        .emp-table tbody tr:hover {
            background-color: #f1f8e9;
        }

        /* 5. 操作按钮样式 */
        .action-link {
            text-decoration: none;
            font-size: 13px;
            margin: 0 5px;
        }
        .edit-btn { color: #ff9900; } /* 编辑按钮橙色 */
        .del-btn { color: #ff3300; }  /* 删除按钮红色 */
    </style>
</head>
<body>

    <table class="emp-table">
        <thead>
            <tr>
                <th>姓名</th>
                <th>性别</th>
                <th>头像</th>
                <th>所属部门</th>
                <th>职位</th>
                <th>入职日期</th>
                <th>最后操作时间</th>
                <th>操作</th>
            </tr>
        </thead>
        
        <tbody>
            <tr>
                <td>赵敏</td>
                <td>女</td>
                <td><img class="avatar" src="https://img.icons8.com/illustrations/lex/112/user-female-circle.png" alt="头像"></td>
                <td>学工部</td>
                <td>班主任</td>
                <td>2008-12-18</td>
                <td>2023-07-22 12:05:20</td>
                <td>
                    <a href="#" class="action-link edit-btn">编辑</a>
                    <a href="#" class="action-link del-btn">删除</a>
                </td>
            </tr>

            <tr>
                <td>风清扬</td>
                <td>男</td>
                <td><img class="avatar" src="https://img.icons8.com/illustrations/lex/112/user-male-circle.png" alt="头像"></td>
                <td>教研部</td>
                <td>讲师</td>
                <td>2015-07-22</td>
                <td>2022-07-22 15:00:00</td>
                <td>
                    <a href="#" class="action-link edit-btn">编辑</a>
                    <a href="#" class="action-link del-btn">删除</a>
                </td>
            </tr>

            <tr>
                <td>风清扬</td>
                <td>男</td>
                <td><img class="avatar" src="https://img.icons8.com/illustrations/lex/112/user-male-circle.png" alt="头像"></td>
                <td>教研部</td>
                <td>讲师</td>
                <td>2015-07-22</td>
                <td>2022-07-22 15:00:00</td>
                <td>
                    <a href="#" class="action-link edit-btn">编辑</a>
                    <a href="#" class="action-link del-btn">删除</a>
                </td>
            </tr>
        </tbody>
    </table>

</body>
</html>


```HTML
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>tlias-员工表格数据展示区域</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: "Microsoft YaHei", sans-serif;
            background-color: #f4f4f4;
            padding: 20px;
        }

        /* 1. 表格整体美化 */
        .emp-table {
            width: 100%;
            /* 核心技巧：合并传统的双线边框为单线边框 */
            border-collapse: collapse; 
            background-color: #ffffff;
            font-size: 14px;
            text-align: center; /* 让表格内的文字和图片全部居中对齐 */
        }

        /* 2. 表头样式管理 */
        .emp-table thead {
            background-color: #e2f0d9; /* 对应原型图上的淡绿色表头背景 */
        }
        
        .emp-table th {
            padding: 12px 10px;
            border: 1px solid #d9d9d9; /* 淡淡的灰色边框 */
            color: #333333;
            font-weight: bold;
        }

        /* 3. 表体单元格样式 */
        .emp-table td {
            padding: 10px;
            border: 1px solid #d9d9d9;
            color: #666666;
            vertical-align: middle; /* 让单元格里的图片和文字垂直居中 */
        }

        /* 头像图片微调 */
        .avatar {
            width: 40px;
            height: 40px;
            border-radius: 4px;
            object-fit: cover;
        }

        /* 4. 高级小技巧：隔行变色（让奇数行背景变成浅灰，提高表格阅读体验） */
        .emp-table tbody tr:nth-child(odd) {
            background-color: #fafafa;
        }

        /* 鼠标悬停在某一行时，整行变色提示（Hover反馈） */
        .emp-table tbody tr:hover {
            background-color: #f1f8e9;
        }

        /* 5. 操作按钮样式 */
        .action-link {
            text-decoration: none;
            font-size: 13px;
            margin: 0 5px;
        }
        .edit-btn { color: #ff9900; } /* 编辑按钮橙色 */
        .del-btn { color: #ff3300; }  /* 删除按钮红色 */
    </style>
</head>
<body>

    <table class="emp-table">
        <thead>
            <tr>
                <th>姓名</th>
                <th>性别</th>
                <th>头像</th>
                <th>所属部门</th>
                <th>职位</th>
                <th>入职日期</th>
                <th>最后操作时间</th>
                <th>操作</th>
            </tr>
        </thead>
        
        <tbody>
            <tr>
                <td>赵敏</td>
                <td>女</td>
                <td><img class="avatar" src="https://img.icons8.com/illustrations/lex/112/user-female-circle.png" alt="头像"></td>
                <td>学工部</td>
                <td>班主任</td>
                <td>2008-12-18</td>
                <td>2023-07-22 12:05:20</td>
                <td>
                    <a href="#" class="action-link edit-btn">编辑</a>
                    <a href="#" class="action-link del-btn">删除</a>
                </td>
            </tr>

            <tr>
                <td>风清扬</td>
                <td>男</td>
                <td><img class="avatar" src="https://img.icons8.com/illustrations/lex/112/user-male-circle.png" alt="头像"></td>
                <td>教研部</td>
                <td>讲师</td>
                <td>2015-07-22</td>
                <td>2022-07-22 15:00:00</td>
                <td>
                    <a href="#" class="action-link edit-btn">编辑</a>
                    <a href="#" class="action-link del-btn">删除</a>
                </td>
            </tr>

            <tr>
                <td>风清扬</td>
                <td>男</td>
                <td><img class="avatar" src="https://img.icons8.com/illustrations/lex/112/user-male-circle.png" alt="头像"></td>
                <td>教研部</td>
                <td>讲师</td>
                <td>2015-07-22</td>
                <td>2022-07-22 15:00:00</td>
                <td>
                    <a href="#" class="action-link edit-btn">编辑</a>
                    <a href="#" class="action-link del-btn">删除</a>
                </td>
            </tr>
        </tbody>
    </table>

</body>
</html>
```

跑起来之后，你会看到一个带高亮响应、隔行交替背景色、完美还原黑马原型的企业级员工数据表。拿下这一课，整个 tlias 系统的核心展示层你就彻底啃下来了！


---
---


## tlias练习案例—底部导航区域


拿下这最后一个“底部版权区域（底部导航区域）”，整个 tlias 员工管理系统的页面大骨架就彻底宣告通关了！

在各类管理系统或企业官网上，底部区域通常用来展示**版权信息（Copyright）、公司名称、备案号以及一些辅助链接**。虽然它的内容通常不多，但在排版上却有特定的“潜规则”和细节。

结合前面的布局逻辑，我们来把最后一块拼图完美补齐。

### 核心技术点与排版规范

#### 1. 结构与文本设计（HTML）

- **标签选择：** 通常使用无语义的 `<div>` 作为大容器，或者使用 HTML5 语义化标签 `<footer>`（表示页脚）。
    
- **字符实体应用：** 看到原型图上的 **`©`**（版权符号）了吗？在 HTML 中，我们不能直接打出这个标准的版权标，必须使用它的转义字符：**`&copy;`**。
    
- **换行控制：** 原型图上有两行淡淡的文字。我们可以用两个 `<p>` 标签来分行，或者在一个盒子内使用 `<br>` 进行强制换行。
    

#### 2. 视觉与对齐（CSS）

- **文本水平居中：** 底部版权通常都是居中对齐的，直接一行 CSS 搞定：`text-align: center;`。
    
- **字体微调：** 作为页脚，它的地位是辅助性的，所以字号一般会设得比较小（如 `12px` 或 `13px`），颜色通常使用淡淡的灰色（如 `#999` 或 `#888`），不能抢了主体表格的风头。
    
- **间距控制：** 利用 `padding`（内边距）把上下撑开一定的距离，让页面看起来更加透气、不紧绷。
    

### 实战演练：完整还原 tlias 底部版权区域

我们严格参照原型图的浅绿色样式，编写一段干净的标准代码。

你可以将以下代码作为一个独立的模块，或者直接拼接到你之前写的 `header`（顶部导航）、`search-area`（搜索表单）和 `table`（表格展示） 的最下方：


<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>tlias-底部版权区域</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: "Microsoft YaHei", sans-serif;
            background-color: #f4f4f4;
            /* 模拟页面主体内容，把底部推到屏幕下方 */
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        /* 主体内容占位（实际开发中这里放搜索区域和表格） */
        .main-content {
            flex: 1; 
            padding: 20px;
            text-align: center;
            color: #ccc;
            font-size: 24px;
        }

        /* ================= 底部版权区域核心 CSS ================= */
        .footer {
            background-color: #7bc3a1; /* 对应原型图底部的标志性青绿色 */
            padding: 15px 0;           /* 上下留出 15px 的内边距 */
            text-align: center;        /* 全局文字水平居中 */
        }

        /* 页脚内的段落文字样式 */
        .footer p {
            font-size: 13px;           /* 辅助信息字号偏小 */
            color: rgba(255, 255, 255, 0.85); /* 柔和的白色，看久了不刺眼 */
            line-height: 1.6;          /* 设置行高，防止两行字挤在一起 */
        }
    </style>
</head>
<body>

    <div class="main-content">
        （页面主体内容区）
    </div>

    <footer class="footer">
        <p>江苏传智播客教育科技股份有限公司</p>
        <p>版权所有&copy;Copyright 2006-2024. All Rights Reserved</p>
    </footer>

</body>
</html>


```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>tlias-底部版权区域</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: "Microsoft YaHei", sans-serif;
            background-color: #f4f4f4;
            /* 模拟页面主体内容，把底部推到屏幕下方 */
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        /* 主体内容占位（实际开发中这里放搜索区域和表格） */
        .main-content {
            flex: 1; 
            padding: 20px;
            text-align: center;
            color: #ccc;
            font-size: 24px;
        }

        /* ================= 底部版权区域核心 CSS ================= */
        .footer {
            background-color: #7bc3a1; /* 对应原型图底部的标志性青绿色 */
            padding: 15px 0;           /* 上下留出 15px 的内边距 */
            text-align: center;        /* 全局文字水平居中 */
        }

        /* 页脚内的段落文字样式 */
        .footer p {
            font-size: 13px;           /* 辅助信息字号偏小 */
            color: rgba(255, 255, 255, 0.85); /* 柔和的白色，看久了不刺眼 */
            line-height: 1.6;          /* 设置行高，防止两行字挤在一起 */
        }
    </style>
</head>
<body>

    <div class="main-content">
        （页面主体内容区）
    </div>

    <footer class="footer">
        <p>江苏传智播客教育科技股份有限公司</p>
        <p>版权所有&copy;Copyright 2006-2024. All Rights Reserved</p>
    </footer>

</body>
</html>
```

### 全栈大局观提示：

注意看上面的代码中，我给 `body` 加上了 `min-height: 100vh; display: flex; flex-direction: column;`。

- **为什么：** 在实际的企业项目里，有时候数据库查出来的员工数据是空的（表格只有一行）。如果不用这个布局技巧，底部版权大盒子就会因为上面没有内容支撑，**死死地贴在屏幕正中间**，下面留出一大片死白，非常难看。
    
- **效果：** 加上这三行 Flex 属性后，即使表格里一条数据都没有，底部版权也会**雷打不动地乖乖呆在浏览器最底部**；而当表格数据成百上千条时，它又会自然地被推到网页的最下方，随着滚动条滚动才出现。
    

---
---



## 总结


太棒了！从央视新闻的单页排版到 tlias 完整的后台管理系统，你已经在不知不觉中啃下了前端最核心的“四大金刚”：**语义化、样式控制、盒子模型、Flex 布局**。

为了让你建立起更高维度的全栈知识大地图，我们把这部分的 HTML 和 CSS 核心知识点做个硬核大复盘，并顺便把那些**后端天天看得到、但目前没提到的“漏网之鱼”标签**一次性补齐。

### 第一部分：HTML 核心知识大通关

HTML 的本质就是**给内容穿上代表身份的“马甲”（标签）**。

#### 1. 已学核心标签分类复盘

- **文本与标题：** `<h1>`-`<h6>`（标题）、`<p>`（段落）。
    
- **多媒体载体：** `<img>`（图片）、`<video>`（视频，别忘了写 `controls`）。
    
- **超链接：** `<a>`（`href` 填跳转路径，`target="_blank"` 开启新窗口）。
    
- **布局双子星：** `<div>`（霸道总裁，独占一行）、`<span>`（随和路人，一行多个）。
    
- **表单收据（前后端交接）：** `<form>`、`<input>`、`<select>`、`<textarea>`。**必须写 `name` 属性，后端才能拿到值！**
    
- **表格阵列（数据展示）：** `<table>` ➡️ `<thead>`/`<tbody>` ➡️ `<tr>` ➡️ `<th>`/`<td>`。
    

#### 2. 后端必须知道的“漏网之鱼”标签

在商业项目中，你还会频繁遇到以下三个目前没提到、但极其常用的标签：

##### ① `<ul>`、`<ol>`、`<li>` —— 列表标签

- **直白解释：** 用来展示一连串并列的数据。
    
- **分工：** `<ul>` 是无序列表（前面默认是个小圆点），`<ol>` 是有序列表（前面默认是 1, 2, 3）。里面每一行内容都必须用 `<li>` 包裹。
    
- **全栈场景：** 后台系统的“左侧菜单栏”或者前台的“热搜文章列表”，底层全是用 `<ul>` + `<li>` 渲染出来的。
    

##### ② `<iframe>` —— 内嵌网页标签

- **直白解释：** 网页里的“画中画”。可以在你当前的网页里，硬生生抠出一个洞，用来显示另一个完全独立的网页。
    
- **全栈场景：** 很多老旧的后台管理系统，左侧点击菜单，右侧区域不跳转，而是让 `<iframe src="员工列表.html">` 动态切换。此外，接入第三方报表、或者是嵌入腾讯视频播放器时天天用它。
    

### 第二部分：CSS 样式大地图

CSS 的本质就是**通过“选择器”抓到 HTML 标签，然后给它“涂颜色、摆位置”**。

#### 1. 样式引入与选择器复盘

- **引入方式：** 行内样式（不推荐）、内部样式（`<style>`）、外部样式（`<link>`，企业规范）。
    
- **选择器优先度：** id 选择器 (`#id`) > 类选择器 (`.class`) > 元素选择器 (`div`)。
    
- **后代选择器：** `form input`，精准抓取某个大盒子内部的特定小组件。
    

#### 2. 盒子模型（Box Model）—— 网页排版的底层逻辑

任何标签在网页上都是一个矩形盒子：

- **`width / height`：** 盒子的核心肚量（内容区）。
    
- **`padding`（内边距）：** 衣服加厚。内容到边框的距离，会把盒子撑大。
    
- **`border`（边框）：** 盒子的外壳线条。
    
- **`margin`（外边距）：** 社交距离。盒子和盒子之间的空白，`margin: 0 auto;` 能让块级大盒子直接在页面水平居中！
    
- **顺时针口诀：** 无论是 padding 还是 margin，写 4 个值时代表 `[上、右、下、左]`。
    

#### 3. Flex 弹性布局 —— 现代对齐神器

再也不用传统的 `float`（浮动）了，一句话激活高级弹性：

- **`display: flex;`**：给父盒子加，让子盒子全部乖乖横着并排站。
    
- **`justify-content: space-between;`**：tlias 导航栏两侧贴边对齐的精髓。左右两头顶死，中间平分空隙。
    
- **`align-items: center;`**：子盒子在垂直方向上完美居中对齐。
    

### 总结：前后端打配合的完整闭环

恭喜你！学完这些，你已经完全具备了去理解 Java Web 后端的核心底盘。

未来你写完 Java 后端，用户在管理后台点击查询，流程是这样的：

1. 前端表单（`<form>`）打包搜索条件（根据 `name` 属性），通过 `POST` 或 `GET` 寄给你的 Java 后端。
    
2. 你的 Java 拿到参数，通过 MyBatis 的动态 SQL 去 MySQL 里查出数据（`List<User>`）。
    
3. Java 把 `List` 转成 JSON 发回给前端。
    
4. 前端拿到数据，通过循环，把数据一条条塞进表格（`<table>`）的 `<tr><td>` 单元格中，最后塞进 Flex 布局的大框架里展示给用户。
    


---
---


# JS


## 概述


如果说 **HTML 是网页的“骨架”**（结构），**CSS 是网页的“衣服”**（样式），那么 **JavaScript（简称 JS）就是网页的“灵魂和大脑”**（行为交互）。

作为后端开发者，你未来在商业项目里不仅要写 Java 接口，还要经常和 JS 打交道。因为网页上所有**活过来的交互**——比如点击按钮弹出一个登录框、手机验证码倒计时、局部刷新表格数据、折叠左侧菜单栏，底层全部都是由 JavaScript 控制的。

JavaScript 是一种运行在**浏览器端**的脚本编程语言。它和 Java 虽然名字很像，但其实**没有任何血缘关系**（就像雷锋和雷峰塔、老婆和老婆饼的关系）。

对于 Java 程序员来说，JS 的语法上手极其简单，因为它们都借鉴了 C 语言的风格。你在 Java 里熟悉的 `if-else`、`for` 循环、`switch` 分支，在 JS 里几乎一模一样。

- **Java：** 运行在服务器端（JVM），负责算数据、读写数据库、保证系统安全。
    
- **JS：** 运行在用户浏览器端，负责监听用户的鼠标键盘动作，动态修改 HTML 和 CSS，给用户爽快的交互体验。
    

## 引入方式


和 CSS 类似，JavaScript 也有三种经典的引入方式。我们直接通过具体的代码例子来逐一拆解：

### 1. 行内脚本（Inline JS）

- **直白解释：** 直接把 JS 代码写在 HTML 标签的事件属性里面（例如 `onclick` 点击事件）。
    
- **特点：** 极其不推荐！代码和 HTML 严重混杂，后期根本没法维护。
    

```HTML
<button onclick="alert('恭喜你，点击成功！')">点我一下</button>
```

### 2. 内部脚本（Internal JS）

- **直白解释：** 把 JS 代码集中写在 HTML 页面的 `<script>` 标签对内部。
    
- **规范约定：** 理论上 `<script>` 标签可以写在页面的任何地方，但业界通常约定**写在 `<body>` 标签的最底部**。这样可以确保网页的 HTML 骨架和 CSS 样式先加载出来，避免因为 JS 脚本太大而导致网页“卡死”在空白状态。
    

**具体例子：**
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>内部脚本示例</title>
</head>
<body>

    <h1 id="title">tlias 智能学习辅助系统</h1>
    <button id="btn">切换标题颜色</button>

    <script>
        // 1. 通过 id 拿到 HTML 中的按钮和标题标签
        var myBtn = document.getElementById("btn");
        var myTitle = document.getElementById("title");

        // 2. 给按钮绑定点击事件
        myBtn.onclick = function() {
            // 3. 点击时，动态修改 CSS 样式
            myTitle.style.color = "red";
            alert("标题颜色已成功修改为红色！");
        };
    </script>
    
</body>
</html>

```HTML
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>内部脚本示例</title>
</head>
<body>

    <h1 id="title">tlias 智能学习辅助系统</h1>
    <button id="btn">切换标题颜色</button>

    <script>
        // 1. 通过 id 拿到 HTML 中的按钮和标题标签
        var myBtn = document.getElementById("btn");
        var myTitle = document.getElementById("title");

        // 2. 给按钮绑定点击事件
        myBtn.onclick = function() {
            // 3. 点击时，动态修改 CSS 样式
            myTitle.style.color = "red";
            alert("标题颜色已成功修改为红色！");//在浏览器顶部会出现一个弹窗
        };
    </script>
    
</body>
</html>
```


>[!tip]
>一般来说，使用JS的内部脚本引入时，`<script>`标签都放在`<body>`最底部，因为JS代码的解析执行时间比较长，放在最下面可以改善页面的显示速度；此外，JS代码中可以操作html的标签，如果html标签还没渲染出来，JS代码可能报错

### 3. 外部脚本（External JS）—— 企业开发黄金标准

- **直白解释：** 把 JS 代码单独写在一个以 `.js` 结尾的文件里，然后通过 HTML 的 `<script src="路径"></script>` 标签引入进来。
    
- **巨大优势：** 实现了“结构与行为完全分离”。同一个 JS 文件可以被多个 HTML 页面复用，而且浏览器可以缓存 JS 文件，极大地提高了网页的加载速度。
    
- **注意：** 负责引入外部 JS 的 `<script>` 标签**内部绝对不能写任何 JS 代码**，写了也会被浏览器直接无视！
    

**具体例子：**

**第一步：** 创建一个独立的纯 JS 文件，取名为 `main.js`（里面不需要写 `<script>` 标签）：


```JavaScript
// main.js 文件内容
window.onload = function() {
    console.log("外部 JS 文件已成功加载并执行！");
    
    var btn = document.getElementById("logout-btn");
    if(btn) {
        btn.onclick = function() {
            // 弹出确认框
            var result = confirm("您确定要退出 tlias 系统吗？");
            if(result) {
                // 如果点确定，跳转到登录页
                window.location.href = "login.html";
            }
        };
    }
};
```

**第二步：** 在你的 HTML 页面（比如 `index.html`）中，通过 `src` 属性把它引入进来：

<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>外部脚本示例</title>
</head>
<body>

    <button id="logout-btn">退出登录</button>

    <script src="js/main.js"></script>
    
</body>
</html>

```HTML
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>外部脚本示例</title>
</head>
<body>

    <button id="logout-btn">退出登录</button>

    <script src="js/main.js"></script>
    
</body>
</html>
```


---
---


## 基础语法——变量、数据类型


在 Java SE 里，你已经习惯了强类型语言的严谨：定义一个数字得用 `int`，定义一段文字得用 `String`，而且一旦定义，类型雷打不动。

当你来到 JavaScript 的世界，你会发现这里的变量和数据类型变得**极其自由、甚至有点“放飞自我”**。作为 Java 开发者，我们用**对比映射**的方式来学 JS 语法，效率最高。

### 一、 JS 变量：解脱的“万能口袋”

在 JS 中，声明变量不需要写具体的类型，而是统一使用关键字。最核心、最现代的声明方式有以下几种：

#### 1. `let` —— 现代变量声明（对应 Java 的普通变量）

- **特点：** 它是**块级作用域**（只在最近的大括号 `{}` 内有效），且不能重复声明。
    
- **直白解释：** 这就是你在 JS 里最常用的万能口袋，什么都能装。
    


```JavaScript
let age = 18;       // 装一个整数
let name = "张三";   // 装一个字符串
age = 19;           // 自由修改值
```

#### 2. `const` —— 常量声明（对应 Java 的 `final`）

- **特点：** 一旦赋值，**绝对不能修改**。如果是对象或数组，里面的内容能改，但不能重新指向新对象。
    
- **开发规范：** 实际开发中，如果一个值不需要改变（比如引入的模块、配置项），**优先全部使用 `const`**。
    


```JavaScript
const PI = 3.1415926;
// PI = 3.14; // ❌ 报错：不能给常量重新赋值
```

#### 3. `var` —— 时代的眼泪（❌ 尽量别用）

- 你在看一些老旧视频或老代码时会经常看到 `var`。
    
- **为什么淘汰：** 它没有块级作用域，且存在“变量提升”等莫名其妙的隐患，现在属于过时语法。**新代码一律用 `let` 和 `const`**。
    

### 二、 JS 数据类型：动态变脸

JS 是一门**动态类型语言**。这意味着一个变量的类型不是固定死的，而是**取决于你往里塞了什么值**。

在 JS 中，数据类型主要分为两大类：**原始类型**和**对象类型**。

#### 1. 原始类型（Primitive Types）

| **数据类型**        | **直白解释 / 对应 Java** | **代码示例**                                           | **后端防坑提示**                                    |
| --------------- | ------------------ | -------------------------------------------------- | --------------------------------------------- |
| **`number`**    | 数字型（**不分整数和小数**）   | `let a = 10;`<br><br>  <br><br>`let b = 3.14;`     | 无论是 `int` 还是 `double`，在 JS 里统统都是 `number`。    |
| **`string`**    | 字符串型               | `let s = "tlias";`<br><br>  <br><br>`let c = 'A';` | 单引号、双引号都能用。还支持反引号 (`` ` ``) 拼字符。              |
| **`boolean`**   | 布尔型                | `let isOk = true;`                                 | 和 Java 一样，只有 `true` 和 `false`。                |
| **`null`**      | 空值                 | `let user = null;`                                 | 类似 Java 的 `null`，表示这个口袋现在故意空着，用来占位。           |
| **`undefined`** | 未定义 ⚠️             | `let score;`                                       | **JS 特产！** 声明了一个变量但没给它赋值，它的默认值就是 `undefined`。 |

#### 2. 对象类型（Object Types）

当原始类型不够用时，就需要用到组合复杂的对象类型。

##### ① `Object`（对象 —— 对应 Java 的 Map 或实体类对象）

JS 的对象非常牛，不需要先写一个 `Class` 类。直接用大括号 `{}` 就能手写一个“键值对”对象。

```JavaScript
let employee = {
    name: "风清扬",
    gender: "男",
    age: 58,
    // 甚至可以在里面塞一个函数（方法）
    sayHello: function() {
        console.log("独孤九剑！");
    }
};

// 调用的写法和 Java 一样，用点 . 语法
console.log(employee.name); // 输出到浏览器控制台: 风清扬
employee.sayHello();        // 调用方法
```

##### ② `Array`（数组 —— 对应 Java 的 `ArrayList`）

JS 的数组底层类似 Java 的集合，**长度是可变的**，而且一个数组里**可以同时塞入不同类型的数据**（虽然实际开发不建议这么干）。

```JavaScript
let arr = ["班主任", "讲师", 100, true];
console.log(arr[1]); // 通过索引取值，输出: 讲师
console.log(arr.length); // 获取长度，输出: 4
arr.push("学工主管"); // 末尾追加元素（类似 Java 的 list.add()）
```

### 三、 终极对比：两门语言的灵魂碰撞

我们来看一段真实的后端数据拼接场景，感受一下 JS 变量与数据类型的灵活：

```JavaScript
// 假设这是后端通过 Ajax 传给前端的三个零散数据
let empName = "赵敏";     // string
let empJob = "班主任";     // string
let empStatus = 1;        // number (1代表在职，0代表离职)

// 1. 动态类型：JS 的变量可以随时变脸
let info = "员工名字叫："; // 此时 info 是个 string
info = 666;              // 瞬间变成 number，浏览器完全不报错

// 2. 现代 JS 的高级黑科技：模板字符串（反引号 ``）
// 告别痛苦的 "+" 号拼接。在反引号里，直接用 ${变量名} 就能把变量完美嵌入文本！
let htmlTemplate = `
    <tr>
        <td>${empName}</td>
        <td>${empJob}</td>
        <td>${empStatus === 1 ? '在职' : '离职'}</td>
    </tr>
`;

console.log(htmlTemplate);
```

#### 一个判断类型的黑科技：`typeof`

如果你在调试代码时不知道当前变量是什么类型，可以在前面加一个 `typeof`：

```JavaScript
console.log(typeof age); // 输出: "number"
console.log(typeof name); // 输出: "string"

//特别地
console.log(typeof null); // 输出: "object"

```



---
---



## 基础语法——函数


在 Java 里，方法（Method）必须依附于类（Class），你得先 `public class`，才能在里面写方法。

但在 JavaScript 的世界里，**函数（Function）是一等公民（First-class Citizens）**。它不需要依附于任何类，自己就能独立存在，甚至可以像普通变量一样**作为参数传给另一个函数**，或者**作为返回值返回**。

对于 Java 程序员来说，JS 函数的写法非常多变。我们今天用最直白的方式，把日常开发（包括以后写 Ajax 交互）最常用的三种函数写法一次性搞懂。


### 1. 经典宣告式（最像 Java 的写法）

使用 `function` 关键字直接定义。这种方式最符合 Java 程序员的直觉，而且它支持**函数提升**（也就是说，你可以在定义函数之前就调用它）。

- **语法：** `function 函数名(参数1, 参数2) { ... }`
    
- **⚠️ 注意：** 参数不需要写类型，函数返回值也不需要写声明类型，直接 `return` 即可。
    


```JavaScript
// 调用函数（可以在定义前调用）
let result = add(5, 3);
console.log(result); // 输出: 8

// 定义函数
function add(a, b) {
    return a + b;
}
```

### 2. 函数表达式（把函数当变量用）

在 JS 中，函数可以是一个匿名（没有名字）的实体，我们可以直接把它塞进一个变量里。

- **语法：** `const 变量名 = function(参数) { ... }`
    
- **注意：** 这种方式定义的函数**不支持**在定义前调用。
    


```JavaScript
// 定义一个计算员工年薪的函数，并存入常量 salaryCal 中
const salaryCal = function(monthSalary, bonus) {
    return monthSalary * 12 + bonus;
};

// 通过变量名来调用这个函数
let total = salaryCal(10000, 20000); // 10k底薪 + 2万年终奖
console.log(total); // 输出: 140000
```

### 3. 箭头函数（Arrow Function）🌟【现代全栈绝对主力】

这是 ES6 引入的高级黑科技，对应 Java 8 里的 **Lambda 表达式**。它的目的就是**极简、优雅**。以后你用前端框架（如 Vue）或者写动态数据请求时，**90% 的场景都是它**。

- **演变过程：** 去掉 `function` 关键字，在参数和冒号之间加一个胖箭头 `=>`。
    
- **极简口诀：** * 如果参数只有**一个**，小括号 `()` 可以省略。
    
    - 如果函数体只有**一行代码**，大括号 `{}` 和 `return` 可以同时省略！
        

```JavaScript
// 写法 A：标准的箭头函数
const multiply = (x, y) => {
    return x * y;
};

// 写法 B：只有一行代码，直接连大括号和 return 都省了！一气呵成！
const square = x => x * x; 

console.log(square(4)); // 输出: 16
```

### JS 函数的两个“特异功能”

作为 Java 开发者，初学 JS 函数时一定要注意以下两点，它们和 Java 的规则完全不同：

#### 1. 参数极其“佛系”（没有重载概念）

在 Java 里，方法名相同但参数不同叫重载。而在 JS 里，**后面定义的同名函数会直接覆盖前面的函数**。

而且，JS 允许你传“不守规矩”的参数：

- 函数要两个参数，你只传一个，没传的那个参数会自动变成 `undefined`，不会报错！
    
- 函数要两个参数，你传了三个，多出来的那个浏览器默默忽略，依旧不报错！
    

```JavaScript
function greet(name, msg) {
    console.log(`你好 ${name}，${msg}`);
}

greet("张三"); // 只传一个参数。输出: "你好 张三，undefined"
```

_提示：为了防止这种尴尬，现代 JS 支持**给参数设置默认值**，如 `function greet(name, msg = "吃了吗")`。_

#### 2. 回调函数（Callback Function）🌟【Ajax的核心】

这是 Java 程序员最开始觉得别扭、但又是前端精髓的地方：**把函数当成参数传给另一个函数**。

> **餐馆通知的例子：**
> 
> 你去餐馆排队，你把你的“手机号”（回调函数）留给服务员。服务员（主函数）等到有位子了，就会打你的电话通知你（调用回调函数）。


```JavaScript
// 主函数：模拟发送网络请求
function fetchDataFromServer(callback) {
    console.log("1. 正在拼命向 Java 后端请求 tlias 系统的员工数据...");
    
    // 模拟网络延迟 2 秒
    setTimeout(() => {
        let data = ["赵敏", "风清扬"]; // 拿到数据了
        console.log("2. 成功拿到数据！准备执行回调...");
        
        callback(data); // 拨通你的电话，把数据交给你
    }, 2000);
}

// 调用主函数，直接把一个“箭头函数”当做快递员（参数）传进去
fetchDataFromServer(result => {
    console.log("3. 最终在网页表格里渲染出来的员工是: " + result);
});
```

未来你写 Ajax/Axios 请求你写的 Spring Boot 接口时，代码结构和上面这个例子一模一样：**你发一个请求，并传一个函数过去，当后端 Java 把数据返回给浏览器时，传过去的那个函数就会被自动执行。**

---
---


## 基础语法——自定义对象



在 Java 里，如果你想创建一个对象，必须先老老实实写一个 `class` 类，定义好成员变量、构造方法、Getter/Setter，然后才能用 `new` 关键字去实例化一个对象。

但在 JavaScript 的世界里，**自定义对象不需要依赖任何类**。你可以把它想象成一个**动态的豪华版“键值对（Key-Value）容器”**，类似于 Java 里的 `HashMap<String, Object>`。它生来就极其轻量和自由。

### 一、 最主流的创建方式：对象字面量（Object Literal）

不需要 `new`，直接用**大括号 `{}`** 就能当场生出一个对象。

- **属性（Property）：** 键值对里的“数据”，对应 Java 的成员变量。
    
- **方法（Method）：** 键值对里的“函数”，对应 Java 的成员方法。
    

#### 规范语法示例

我们直接以之前做过的 **tlias 员工系统** 为例，用 JS 表达一个员工对象：


```JavaScript

// 1. 当场创建一个自定义对象
const emp = {
    name: "赵敏",          // 属性，注意用逗号(,)隔开
    gender: "女",
    age: 26,
    dept: "学工部",
    skills: ["管理", "Java", "Python"], // 属性的值也可以是数组
    
    // 2. 在对象里定义方法（经典写法）
    work: function() {
        console.log("正在处理 tlias 系统的学员考勤...");
    },
    
    // 3. 现代 ES6 极简写法（省去 : 和 function 关键字，推荐！）
    sayHello() {
        // ⚠️ 核心考点：必须用 this 才能访问对象自己的属性，否则会报 undefined
        console.log(`大家好，我是 ${this.name}，来自 ${this.dept}。`);
    }
};
```

### 二、 如何操作这个对象（点语法 vs 括号语法）

拿到对象后，对属性和方法的读写有两套完全不同的武器：

#### 1. 点语法（`.`）—— 最常用、最符合 Java 直觉


```JavaScript
// 读取属性
console.log(emp.name); // 输出: 赵敏

// 调用方法
emp.sayHello(); // 输出: 大家好，我是 赵敏，来自 学工部。

// 动态修改属性
emp.age = 27;

// 甚至能动态追加新属性！（Java的类绝对做不到，Map可以）
emp.salary = 15000; 
console.log(emp.salary); // 输出: 15000
```

#### 2. 括号语法（`[]`）—— 动态的高级黑科技

如果属性名是一个存放在变量里的字符串，点语法就抓瞎了（比如 `emp.variable` 会去盒子里找名字叫 variable 的属性）。这时候必须用方括号：

```JavaScript
let keyName = "dept";

// console.log(emp.keyName); // ❌ 报错或 undefined！
console.log(emp[keyName]);   //  正确！等价于 emp["dept"]，输出: 学工部
```


---
---


## JSON


既然你要走 Java 后端开发这条路，那么 **JSON** 就是你未来职业生涯中逃不掉的“空气和水”。不管你是用 Spring Boot 写 RESTful API 接口，还是用 MyBatis 把配置以 JSON 格式存在 MySQL 数据库里，它都会如影随形。


![[Java Web笔记-10.png]]


### 1. 什么是 JSON？（它的诞生背景）

**JSON (JavaScript Object Notation，JS 对象简记法)**，说白了，它就是一种**轻量级的、纯文本的数据交换格式**。

#### 历史小八卦

在 JSON 诞生之前（2000 年代初），网页和服务器之间传输数据主要靠 **XML**。XML 长这样：


```XML
<user>
    <name>赵敏</name>
    <age>26</age>
</user>
```

XML 臃肿、难看，里面有大量重复的标签（光是 `<name>` 就出现了两次）。后来前端大佬们发现，JavaScript 声明对象的方式（就是我们上一节学的自定义对象 `{name: "赵敏", age: 26}`）简直太干净、太漂亮了！

于是，大家一合计，直接把 JS 的这种对象格式抽离出来，变成了一种独立的文本标准，这就是 JSON。

### 2. JSON 的三大铁律（语法规范）

虽然 JSON 借鉴了 JavaScript 的对象写法，但作为跨语言的标准，它的语法比 JS 对象要**严格 100 倍**。在写 JSON 文件或者传输 JSON 时，必须死守以下三大铁律：

1. **键（Key）必须用双引号 `""` 包裹**
    
    - 在 JS 对象里，你可以写 `name: "张三"`。
        
    - 但在 JSON 里，必须写 **`"name": "张三"`**。写单引号或者不写引号，Java 和前端解析时直接报错崩掉。
        
2. **值（Value）只能是指定的基础类型**
    
    - 允许的值：**字符串**（必须用双引号）、**数字**、**布尔值（true/false）**、**null**、**另一个 JSON 对象**、或者 **数组**。
        
    - **绝对不允许出现任何 JavaScript 函数方法！**（纯文本传输，Java 拿到了也无法执行）。
        
3. **末尾绝对不能有多余的逗号 `,`**
    
    - JS 允许你在对象的最后一个属性后面留一个尾随逗号。
        
    - 但 JSON 里，最后一条数据的末尾如果加了逗号，直接判定为非法 JSON。
        

### 3. JSON 的两大骨架结构

在标准 JSON 文本中，数据只可能以以下两种形态（或者它们互相嵌套）出现：

#### ① 对象（Object）—— 用大括号 `{}` 包裹

代表一个独立的实体。对应 Java 中的一个实体类对象（POJO）或者 **`Map<String, Object>`**。

```JSON
{
  "id": 1001,
  "name": "风清扬",
  "isLeader": true,
  "avatar": null
}
```

#### ② 数组（Array） —— 用中括号 `[]` 包裹

代表一组并列的相同结构数据。对应 Java 中的 **`List<T>`** 或者 **`Object[]` 数组**。

```JSON
[
  {"name": "张三", "age": 18},
  {"name": "李四", "age": 20}
]
```

### 4. 深度穿透：复杂的 JSON 嵌套长什么样？

在实际的企业项目（比如你的 tlias 员工管理系统）中，后端返回给前端的数据往往非常复杂。

我们来手写一个**企业级规范的后台响应 JSON**。请注意观察大括号和中括号是如何完美套娃的：

```JSON
{
  "code": 200,
  "message": "查询员工列表成功",
  "data": {
    "total": 35,
    "rows": [
      {
        "empId": 1,
        "name": "赵敏",
        "job": "班主任",
        "skills": ["管理", "沟通", "心理学"]
      },
      {
        "empId": 2,
        "name": "风清扬",
        "job": "讲师",
        "skills": ["Java", "算法", "独孤九剑"]
      }
    ]
  }
}
```

#### 后端大局观解析：

- 最外层的 `{}` 代表这是一个统一的响应结果对象（在 Java 里我们通常封装为一个 `Result` 类）。
    
- `code: 200` 告诉前端状态正常。
    
- `data` 里面又嵌套了一个对象，用来放具体的分页数据（总条数 `total` 和当页数据 `rows`）。
    
- `rows` 是一个中括号 `[]`，里面塞了多条员工对象，每条对象内部的 `skills` 居然又是一个数组！
    


### 5. JSON和自定义对象相互转换


在前两节中，我们已经分别解锁了“JS自定义对象”（内存中的豪华键值对容器）和“JSON”（跨语言传输的纯文本规范）。

在实际的企业级 Web 开发中，**“自定义对象”与“JSON字符串”的相互转换**，是前后端数据交互的必经之路。JavaScript 内部提供了一个极其强大的内置对象 **`JSON`**，它就像一台完美的“翻译机”，专门负责在两兄弟之间进行高频的翻译工作。


|**转换方向**|**核心方法**|**直白花名**|**适用场景（后端大局观）**|
|---|---|---|---|
|**JSON 字符串 ➡️ JS 自定义对象**|**`JSON.parse(str)`**|**复活 / 反序列化**|**接收数据：** 当你的前端通过 Ajax 收到 Java 后端发来的一串冰冷纯文本 JSON 时，需要立刻用它“复活”成前端能直接操作的对象，然后把数据塞进 HTML 表格里。|
|**JS 自定义对象 ➡️ JSON 字符串**|**`JSON.stringify(obj)`**|**打包 / 脱水 / 序列化**|**发送数据：** 当用户在前端表单（例如 tlias 系统的搜索区或添加员工弹窗）填完数据后，前端把数据收集成一个 JS 对象，需要先给它“脱水”打包成通用的 JSON 纯文本，才能安全地跨网线 POST 提交给 Java 后端。|

#### 具体代码演练

我们直接通过一段完整的控制台测试代码，看看它们在两端转换时的语法和底层变化：

##### 1. 【反序列化】从 JSON 到 JS 对象（后端发给前端）

```JavaScript
// 模拟从 Java 后端接口（Spring Boot）接收到的一串员工数据（注意：最外层是单引号包着的纯文本字符串）
const jsonFromServer = '{"name":"赵敏","age":26,"job":"班主任","skills":["管理","Java"]}';

console.log(typeof jsonFromServer); // 输出: "string" (此时只是普通的文本，不能用 .name 拿数据)

// 🌟 开始“复活”转换：
const empObj = JSON.parse(jsonFromServer);

console.log(typeof empObj);        // 输出: "object" (复活成功，变成了内存中的 JS 对象)
console.log(empObj.name);          // 优雅地通过点语法取值，输出: 赵敏
console.log(empObj.skills[0]);     // 优雅地读取内部数组，输出: 管理
```

##### 2. 【序列化】从 JS 对象到 JSON（前端发给后端）

```JavaScript
// 前端在内存中自己创建（或修改）了一个员工数据对象
const newEmp = {
    name: "风清扬",
    job: "讲师",
    status: 1,
    // 对象里可以写函数，但注意看转换后的变化
    teach() {
        console.log("独孤九剑！");
    }
};

console.log(typeof newEmp); // 输出: "object"

// 🌟 开始“脱水打包”转换：
const jsonToSend = JSON.stringify(newEmp);

console.log(typeof jsonToSend); // 输出: "string" (变成了纯文本)
console.log(jsonToSend); 
// 打印结果：'{"name":"风清扬","job":"讲师","status":1}'
```

##### 避坑指南：转换时的“降维打击”

在转换过程中，有一个关于 **函数方法（Function）** 的致命细节，这是全栈开发中极容易产生误解的地方：

1. **函数是无法被“脱水”的：**
    
    仔细观察上面第 2 步的打印结果，你会惊讶地发现：原本在 `newEmp` 对象里的 `teach()` 方法，在经过 `JSON.stringify()` 转换成 JSON 字符串后，**彻底蒸发（消失）了**！
    
    - **为什么：** 因为 JSON 是一种跨语言、通用的文本协议。Java、Python、PHP 都要读这段 JSON。如果 JSON 里面保留了一段前端 JavaScript 的函数代码，后台的 Java 虚拟机（JVM）拿到后根本无法理解，更无法执行。因此，JSON 规范强制规定：**传输时只传纯粹的数据，丢弃所有方法。**
        
2. **键名双引号的“自动纠正”：**
    
    你在定义 JS 对象时，可以写不带引号的 `name: "风清扬"`；但经过 `JSON.stringify()` 包装后，生成的文本会自动规范化，变成带有双引号的标准格式：`"name": "风清扬"`。
    


### 6. Java 与前端是如何隔空传输并翻译 JSON 的？

这也是前后端分离开发的**核心闭环**。数据在网络中传输时，**100% 都是纯文本字符串**

#### 🔄 第一步：Java 后端（序列化）

当你在 Spring Boot 的 Controller 里写完业务逻辑，直接 `return list;` 返回一个 Java 的 `ArrayList` 集合时。

- Spring Boot 内部自带的 **Jackson 框架** 会自动启动。
    
- 它会像一个翻译官一样，把你的 Java `List<Emp>` 对象活生生给拍扁，脱水成一段**纯文本的 JSON 字符串**，然后通过网络发送出去。
    

#### 🔄 第二步：网络传输中

在网线上跑的，只是一串冰冷的字符串：`'[{"name":"赵敏","age":26}]'`。

#### 🔄 第三步：浏览器前端（反序列化）

前端 JavaScript 收到这串字符串后，没法直接用点语法 `.name` 读出来。

- 前端需要调用 **`JSON.parse()`**，瞬间把这段纯文本丢进内存，复活成一个原生的 **JS 自定义对象**。
    
- 接着，前端通过 Vue 的 `v-for` 循环，把数据整整齐齐地塞进你在 HTML 里写好的表格 `<tr><td>` 里。
    

### 硬核复习表

|**维度**|**Java 语言 (后端)**|**JSON 标准 (网络中介)**|**JavaScript 语言 (前端)**|
|---|---|---|---|
|**存在形态**|编译后的 JVM 内存对象|**纯文本字符串 (String)**|浏览器内存对象|
|**数据容器**|`User` 实体类 / `HashMap`|键值对大括号 `{}`|自定义对象 `{}`|
|**列表容器**|`ArrayList<User>`|中括号数组 `[]`|数组 `[]`|
|**语法严格度**|极高（强类型，丢个分号都报错）|**极高（键必须双引号，不能有尾随逗号）**|极低（弱类型，极为自由）|

现在，你已经掌握了前后端数据交互最核心的语议载体 JSON。

---
---


## DOM


在学 DOM 之前，很多后端同学最困惑的问题就是：“我在 JS 里定义了一个对象或者函数，浏览器怎么知道去改网页上的哪一行字？怎么知道哪个按钮被点击了？”

答案全在 **DOM** 身上。

### 一、 什么是 DOM？（网页的“提线木偶”）

**DOM（Document Object Model，文档对象模型）**，直白点说，就是**浏览器专门为 JavaScript 准备的一套“网页操作说明书和控制手柄”**。

当浏览器加载一个 HTML 页面时，它会在后台默默地做一件大事：**把干巴巴的 HTML 标签，全部翻译成内存中的 JavaScript 对象**。

![[Java Web笔记-11.png]]

#### 核心概念：DOM 树（Tree）

在浏览器的内存里，网页不是一堆文本，而是一棵倒过来的“大树”：

- **`document` 对象：** 树的**根部**。它是整个网页的“大老板”，在 JS 里只要输入 `document`，你就抓住了整个世界。
    
- **节点（Node）：** 树上的分支和树叶。网页里的每一个标签（`<div>`、`<h1>`、`<input>`）、每一个属性（`class`、`id`）、甚至标签里的每一段文字，在内存里都是一个独立的**节点对象**。
    

**后端大局观：** 所谓的“动态网页交互”，底层逻辑非常简单：**JS 代码 ➡️ 调用 DOM API ➡️ 修改内存中的 DOM 树 ➡️ 浏览器实时刷新 ➡️ 用户看到网页变了。**

### 二、 DOM 操作的核心三部曲

在开发 tlias 系统的搜索表单或者按钮交互时，JS 的操作永远逃不开这三个固定步骤：

```
1. 抓取对象 (找人) ➡️ 2. 绑定事件 (盯着他) ➡️ 3. 修改属性/内容 (揍他)
```


![[Java Web笔记-12.png]]

[DOM对象的属性方法参考文档](https://www.w3school.com.cn/js/js_intro.asp)

#### 1. 第一步：抓取对象（选择器 API）

你想让哪个标签动，就必须先在内存里把它捞出来。现代 JS 淘汰了以前臃肿的方法，统一使用这两个神器（跟 CSS 选择器无缝衔接）：

- **`document.querySelector('CSS选择器')`**
    
    - **效果：** 极其精准，根据你写的 CSS 选择器，返回**第一个**匹配到的 HTML 标签对象。
        
    - `let btn = document.querySelector('#query-btn');`（抓取 id 为 query-btn 的查询按钮）
        
    - `let input = document.querySelector('.search-box input');`（后代选择器，抓取搜索框里的输入框）
        
- **`document.querySelectorAll('CSS选择器')`**
    
    - **效果：** 广撒网，返回一个**包含所有匹配标签的数组（伪数组）**。常用于批量控制（比如抓住表格里的所有 `<tr>` 行）。
        

#### 2. 第二步：绑定事件（监听用户动作）

抓到人之后，要告诉浏览器：当用户对这个标签做什么动作时，去执行哪段 JS 函数。

- **常用事件类型：** `click`（点击）、`focus`（获得焦点）、`blur`（失去焦点/表单验证常用）、`keydown`（键盘按下）。
    
- **企业级绑定规范：** 使用 `addEventListener('事件名', 回调函数)`。
    

```JavaScript
let queryBtn = document.querySelector('#query-btn');

// 监听“点击”动作，当被点击时，后面的箭头函数立刻爆发执行
queryBtn.addEventListener('click', () => {
    console.log("报告老板，用户点击了查询按钮！");
});
```

#### 3. 第三步：修改属性和内容（真正的交互变脸）

一旦事件触发，我们就可以在函数体里对标签对象“为所欲为”了。最常用的修改手段有三种：

- **修改表单的值（`.value`）🌟【后端最关心】**
    
    - 获取或修改用户在输入框里敲的代码。
        
    - `let name = document.querySelector('#username').value;`（拿到用户输入的姓名）
        
- **修改标签中间的文字/HTML（`.innerText` / `.innerHTML`）**
    
    - `title.innerText = "数据加载中...";`（单纯改文字）
        
    - `tableBody.innerHTML = "<tr><td>新员工</td></tr>";`（直接往盒子里灌入新的 HTML 骨架）
        
- **修改 CSS 样式（`.style.属性名` 或 `.classList`）**
    
    - `box.style.backgroundColor = "red";`（直接改行内样式）
        
    - `box.classList.add("active");`（优雅写法：给标签追加一个写好样式的 class 类名）
        

### 实战连通：让 tlias 搜索区域真正活起来

我们直接拿之前做过的 **tlias 搜索表单区域** 弹窗作为舞台。现在我们写一段纯正的 DOM 操作 JS 代码，实现：**点击“查询”拿到输入框的值，点击“清空”让样式变红复位。**

```HTML
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>tlias-DOM操作实战</title>
    <style>
        .search-area { background-color: #fcf0e7; padding: 20px; border-radius: 4px; }
        .error-style { border: 2px solid red !important; background-color: #fce4e4; }
    </style>
</head>
<body>

    <div class="search-area">
        <label>姓名：</label>
        <input type="text" id="emp-name" placeholder="请输入员工姓名">
        
        <button id="btn-query">查询</button>
        <button id="btn-clear">清空</button>
    </div>

    <script>
        // 【第一步：找人】精确抓取网页上的输入框和两个按钮
        const nameInput = document.querySelector('#emp-name');
        const queryBtn = document.querySelector('#btn-query');
        const clearBtn = document.querySelector('#btn-clear');

        // 【第二步：盯着他】给“查询”按钮绑定点击事件
        queryBtn.addEventListener('click', () => {
            // 【第三步：拿值】获取用户到底在框里填了什么
            let inputValue = nameInput.value;
            
            if (inputValue.trim() === "") {
                alert("请输入姓名后再查询！");
                // 动态修改 CSS：让输入框瞬间变成警告红
                nameInput.classList.add('error-style');
            } else {
                alert(`正在为您向 Java 后端检索员工：${inputValue}`);
                // 以后这里就是写 Ajax 把 inputValue 发给 Spring Boot 控制器
            }
        });

        // 给“清空”按钮绑定事件
        clearBtn.addEventListener('click', () => {
            // 清空输入框里的文本
            nameInput.value = "";
            // 移除警告红色样式
            nameInput.classList.remove('error-style');
        });
    </script>
</body>
</html>
```

---
---


## 事件监听


在上一节认识 DOM 的时候，我们提到了交互的“核心三部曲”：**找人 ➡️ 盯着他 ➡️ 揍他**。这中间的第二步——“盯着他”，就是我们今天要深度解密的**事件监听（Event Listening）**。

如果把 DOM 元素比作硬件（比如一个实体按钮），那么事件监听就是**驱动程序**。它让浏览器知道，当用户的鼠标、键盘或者屏幕发生变化时，后台该执行哪段 JS 代码。

### 一、 事件监听的标准语法

在现代 JavaScript（ES6 标准）中，我们统一使用 **`addEventListener`** 方法来绑定事件。

#### 规范语法骨架

```JavaScript
target.addEventListener('type', listener);
```

- **`target`（元素对象）：** 绑定的主体。也就是你用 `document.querySelector` 抓出来的那个 HTML 标签。
    
- **`'type'`（事件类型）：** 字符串格式。比如点击事件 `'click'`、鼠标移入 `'mouseenter'`（**注意：前面千万不要加 "on"**）。
    
- **`listener`（监听器/回调函数）：** 当事件发生时要触发执行的函数。实际开发中，**100% 推荐使用箭头函数**。
    

#### 基础代码演练

我们让 tlias 系统顶部的“退出登录”按钮具有点击反馈：

```JavaScript
// 1. 抓取按钮
const logoutBtn = document.querySelector('.logout-btn');

// 2. 绑定点击事件
logoutBtn.addEventListener('click', () => {
    // 3. 事件触发后的业务逻辑
    alert("正在安全退出 tlias 系统...");
});
```

### 二、 核心考点：事件对象 `e` 是个啥？

在写事件监听时，你经常会看到别人在箭头函数的括号里写一个 **`e`**（或者 `event`）：


```JavaScript
btn.addEventListener('click', (e) => { ... });
```

#### 直白解释

**`e` 就是“案发现场的记录仪”**。当事件被触发的瞬间，浏览器会自动产生一个名为 `e` 的对象，塞进你的函数参数里。这个对象里装满了**当时发生这个动作时的所有细节数据**。

#### 两个最常用的爆款属性：

1. **`e.target`：** 告诉你是**谁**触发了这个事件（在复杂页面里极其有用）。
    
2. **`e.preventDefault()` 🌟【后端高频防御】**
    
    - **作用：** 拦截（阻止）标签的默认行为。
        
    - **全栈场景：** 原型图上的 `<a href="/logout">` 标签点击后默认会刷新跳转网页，或者表单 `<button type="submit">` 会默认刷新页面提交。如果我们想在跳转前先做个表单格式验证，或者改用 Ajax 异步发数据，就必须在函数第一行写上 `e.preventDefault()`，死死拦住浏览器的默认刷新！
        

### 三、 企业级 Web 开发常见事件大沙盘

在写管理系统或者前端组件时，以下这四类事件是日常搬砖的绝对主力：

#### 1. 鼠标事件（Mouse Events）

- **`'click'`（点击）：** 触发频次之王。查询、清空、删除、编辑按钮全部走它。
    
- **`'mouseenter'`（鼠标移入）/ `'mouseleave'`（鼠标移出）：**
    
    - **开发场景：** 鼠标悬停在表格某一行时，整行变色提示（Hover 反馈），或者鼠标放到头像上时弹出一个下拉菜单。
        

#### 2. 键盘事件（Keyboard Events）

- **`'keydown'`（键盘按下）：**
    
    - **全栈场景：** 极佳的用户体验优化。当用户在 tlias 系统的“姓名”输入框里敲完名字后，**懒得去点“查询”按钮**，直接在键盘上敲了个 **回车键（Enter）**。你的 JS 就可以通过监听 `keydown` 并判断 `e.key === 'Enter'`，直接自动触发查询接口！
        

#### 3. 表单事件（Form Events）—— 校验主力 🌟

- **`'focus'`（获得焦点）：** 鼠标点进输入框内部，框子变蓝。
    
- **`'blur'`（失去焦点）：** 鼠标从输入框里移出来，点到了别的地方。
    
    - **后端安全前哨：** **前端表单异步校验的黄金时机**。当用户刚输完“手机号”，鼠标移出输入框的瞬间触发 `blur`。JS 立刻去校验手机号是不是 11 位数字。如果不合法，直接在框子下面弹红字报错，把垃圾数据直接拦截在前端，**根本不需要去麻烦后端的 Java 接口**，极大地节省了服务器的带宽和算力！
        

#### 4. 页面加载事件（Layout/Load Events）

- **`'DOMContentLoaded'`：**
    
    - **直白解释：** 当 HTML 纯骨架加载完毕后立刻执行。
        
    - **用途：** 如果你的 `<script>` 脚本不小心写在了 HTML 的顶部，这时候 DOM 树还没生成，直接 `querySelector` 会抓到 `null` 导致报错。把代码包裹在 `DOMContentLoaded` 事件里，就能确保代码在安全的时机执行。
        

### 综合实战：打造智能键盘提交与失去焦点验证

我们直接把上面的**事件对象拦截、键盘监听、失去焦点（blur）验证**融会贯通，应用到 tlias 的登录/搜索场景中：


```HTML

<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>tlias-高级事件监听实战</title>
    <style>
        .input-box { padding: 8px; border: 1px solid #ccc; outline: none; }
        .error-border { border: 2px solid #ff4d4f; background-color: #fff2f0; }
        .error-tip { color: #ff4d4f; font-size: 12px; margin-top: 5px; }
    </style>
</head>
<body>

    <div style="padding: 40px;">
        <h3>员工账号注册（前端防御验证）</h3>
        <br>
        <input type="text" id="username" class="input-box" placeholder="请输入用户名（少于4位报错）">
        <div id="tip-area" class="error-tip"></div>
        <br><br>
        <button id="reg-btn" style="padding: 8px 16px;">提交注册</button>
    </div>

    <script>
        const usernameInput = document.querySelector('#username');
        const tipArea = document.querySelector('#tip-area');
        const regBtn = document.querySelector('#reg-btn');

        // 🔥 实战场景一：失去焦点（blur）时自动触发格式检查（不打扰用户输入）
        usernameInput.addEventListener('blur', () => {
            let val = usernameInput.value.trim();
            if (val.length < 4 && val.length > 0) {
                usernameInput.classList.add('error-border');
                tipArea.innerText = "❌ 警告：用户名长度不能少于 4 位！";
            } else {
                usernameInput.classList.remove('error-border');
                tipArea.innerText = ""; // 清空报错
            }
        });

        // 🔥 实战场景二：监听键盘（keydown），按下回车键直接触发注册按钮的逻辑
        usernameInput.addEventListener('keydown', (e) => {
            // 通过事件对象 e 的 key 属性，精准锁定是不是回车键
            if (e.key === 'Enter') {
                alert("检测到您按下了回车键，正在为您自动提交...");
                regBtn.click(); // 用代码去模拟点击提交按钮
            }
        });

        // 🔥 实战场景三：点击事件与拦截默认行为
        regBtn.addEventListener('click', (e) => {
            let val = usernameInput.value.trim();
            if (val === "") {
                alert("表单不能为空！");
                // 假设这在一个 form 表单里，这行可以阻止表单往 Java 后端发空数据刷新页面
                e.preventDefault(); 
            } else {
                alert(`恭喜！数据验证合格，成功将 "${val}" 打包为 JSON 发往 Java 后端！`);
            }
        });
    </script>
</body>
</html>
```

把这段代码跑起来，在里面输入 1 个字然后把鼠标点到空白处，或者在框里直接敲回车，感受一下事件监听带来的细腻交互体验。

---
---


## JS的模块化


![[Java Web笔记-13.png]]


在写 Java 的时候，你对“模块化”一定深有体会：我们不可能把所有的业务代码都写在 `Main.class` 里。我们会用 `package` 把代码分层，需要用别处的类时，直接在文件顶部来一句 `import java.util.ArrayList;` 就可以了。

但在 JavaScript 的早期历史中，**它根本没有“模块”的概念**。如果一个网页引入了 5 个不同的 JS 文件，它们全部都会暴露在同一个“全局作用域”下。这就导致如果小明和小红在各自的 JS 文件里都定义了一个 `let name = 'abc'`，页面运行时就会直接因为命名冲突而崩溃。

为了解决这个痛点，JS 经历了几代演变，最终确立了现代的模块化规范。今天我们用**后端视角**，把最核心的现代模块化（ES6 Module）和一些常见的概念彻底理清。

### 一、 现代 JS 模块化：ES6 Module (ESM) 

这是自 2015 年（ES6）起，官方正式确立的模块化标准，也是现在全栈开发（尤其是 Vue / React 项目）中的**绝对主力**。它的思想和 Java 非常接近：**每个 JS 文件都是一个独立的保险箱（模块），外部无法直接访问；除非你主动“导出（export）”，别人才能“导入（import）”。**

它的玩法主要分为两种：

#### 1. 玩法 A：命名导出与导入（可以导出多个）

适合一个模块里有很多独立的工具函数。

- **导出端（`utils.js`）：** 谁想公开，就在谁前面加 `export`。
    

```JavaScript
// 导出变量
export const baseUrl = "http://localhost:8080/tlias";

// 导出功能函数
export function formatDate(date) {
    return `2026年-${date.getMonth() + 1}月`;
}
```

- **导入端（`main.js`）：** 使用 **大括号 `{}`** 挑选你需要的零件，名字必须对得上。
    

```JavaScript
// 类似 Java 的 import
import { baseUrl, formatDate } from './utils.js';

console.log(baseUrl); // 输出接口基地址
console.log(formatDate(new Date()));
```

#### 2. 玩法 B：默认导出与导入（每个文件只能有一个）

当你的 JS 文件只负责干一件大事（比如定义一个完整的员工业务对象，或者一个核心类）时，用默认导出最合适。

- **导出端（`empService.js`）：** 使用 `export default`。
    

```JavaScript
const empService = {
    // 模拟向 Java 后端查询员工列表
    queryAllEmps() {
        console.log("正在通过 Ajax 访问 tlias 系统的查询接口...");
    },
    deleteEmp(id) {
        console.log(`正在删除 id 为 ${id} 的员工...`);
    }
};

// 默认导出这个核心对象
export default empService;
```

- **导入端（`index.js`）：** 导入时 **不需要加大括号**，而且你可以随便给它起名字（非常自由）！
    
```JavaScript
// 导入默认模块，顺便起名叫 service
import service from './empService.js';

// 直接调用
service.queryAllEmps();
```

### 二、 浏览器运行 ESM 的“致命天条”

如果你想在原生的 HTML 页面里直接测试上面的 `import` 和 `export` 代码，你必须在引入 JS 时做一件至关重要的事：**在 `<script>` 标签上加上 `type="module"` 属性。**

```HTML
<script type="module" src="./index.js"></script>
```

- **后端提示：** 一旦加了 `type="module"`，浏览器就会把这个 JS 文件当成独立的模块运行。另外，出于网络安全考虑，带有模块化的 HTML 页面**不能直接双击用本地路径（File://）打开**，未来必须跑在本地服务器（比如用 VS Code 的 Live Server 插件，或者由你的 Tomcat/Spring Boot 托管）上。
    

### 三、 漏网之鱼：CommonJS (CJS) 规范是什么？

在复习资料或者阅读一些老旧的 Node.js 后端代码时，你可能还会频繁看到另一种长相的模块化写法：

```JavaScript
// 它是用 require 导入，用 module.exports 导出的！
const fs = require('fs'); 
module.exports = { name: '张三' };
```

#### 别慌，一句话理清它们的区别：

- **CommonJS：** 是在官方标准出台前，**Node.js 服务端（也就是用 JS 写后端服务器）** 自己搞出来的一套规范。它是同步加载的，非常适合服务器读取本地硬盘的文件。
    
- **ES6 Module：** 是 **ECMAScript 官方出品的现代标准**。它是异步加载的，专门针对网络传输进行了优化，是现代浏览器端（网页端、Vue/React 项目）的绝对标准。
    

### JS 模块化与 Java 模块化

|**概念**|**Java 语言**|**JavaScript 语言 (ESM)**|
|---|---|---|
|**隔离基本单元**|`.class` 文件 / `package`|独立的 `.js` 文件|
|**公开功能**|`public` 关键字|**`export`** 或 **`export default`**|
|**引入功能**|`import java.util.List;`|**`import { List } from './module.js';`**|
|**重命名防冲突**|只能写全限定名 `com.a.User`|极度优雅：`import { User as AUser } from './a.js';`|

掌握了模块化，你就正式拿到了进入现代前端工程化（如 Vue 3、Vite、Webpack）的入场券。在以后的 Vue 实战里，你写的每一个组件、每一个 API 请求文件，底层全都是基于这个模块化标准来拼装的！

---
---



# Vue




既然你已经解锁了 **JS 的模块化（ES6 Module）**，看到你在新上传的截图里引入了官方提供的 Vue 模块，这标志着你正式从“传统原生 JS 搬砖时代”**跨入了**“现代全栈工程化时代”！

作为 Java 后端开发者，学 Vue 会让你有一种极其强烈的亲切感，因为它的核心设计思想，几乎就是后端玩得最转的 **MVC / MVVM 架构**。

## 什么是 Vue？（为什么要淘汰原生 DOM 操作）

**Vue.js** 是一款用于构建用户界面的 **渐进式 JavaScript 框架**。

### 核心痛点：原生 DOM 操作太累了

在传统原生开发里，我们要实现“修改用户名”的功能，代码是这样的：

1. 用 `document.querySelector` 抓取输入框。
    
2. 监听输入事件拿到新值。
    
3. 再抓取展示名字的 `<h1>` 标签。
    
4. 修改 `innerText`。
    

这种“手动提线木偶”式的写法（DOM操作）在面对 tlias 系统这种复杂的表格和表单时，会导致代码极度臃肿且难以维护。

### Vue 的终极魔法：数据驱动视图（MVVM）

如你截图中所示，Vue 带来了解放全栈开发者的核心武器——**数据驱动视图**。

- **你不需要再手动去抓标签、改内容了。**
    
- 你只需要在 JavaScript 里声明一个普通的变量（数据 Model）。
    
- Vue 会在后台帮你盯着这个变量，只要你在代码里修改了这个变量的值，**网页上所有绑定了该变量的标签会自动眨眼变脸（视图 View 自动刷新）**。
    

## 拆解 Vue 3 快速入门案例



![[Java Web笔记-14.png]]


我们直接对照你提供的截图中的官方模块化引入方式，写一个最纯正的 Vue 3 极简代码例子。

### 完整示例代码：

```HTML
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>Vue3 快速入门——数据驱动视图</title>
</head>
<body>

    <div id="app">
        <h1>系统提示：{{ message }}</h1>
        <p>当前登录账号：{{ loginUser.name }} (职位：{{ loginUser.job }})</p>
        
        <button @click="changeUser">切换体验账号</button>
    </div>

    <script type="module">
        // 从官方提供的 CDN 加地址导入 createApp 核心函数
        import { createApp } from 'https://unpkg.com/vue@3/dist/vue.esm-browser.js';

        // 3. 创建 Vue 应用程序实例
        createApp({
            // data 方法：专门用来放你这页面的“活数据”（Model）
            data() {
                return {
                    message: "Hello Vue",
                    loginUser: {
                        name: "赵敏",
                        job: "班主任"
                    }
                }
            },
            // methods 属性：专门用来放页面上的交互函数（类似旧的JS函数）
            methods: {
                changeUser() {
                    // ⚠️ 注意：在 Vue 内部访问 data 里的变量，必须加 this
                    this.message = "欢迎进入 tlias 员工管理系统！";
                    this.loginUser.name = "风清扬";
                    this.loginUser.job = "教研主管";
                    // 看到了吗？这里完全没有写任何 document.querySelector，网页自己就会变！
                }
            }
        }).mount("#app"); // 4. 将这个 Vue 实例死死地挂载（绑定）到 id 为 app 的大盒子上
    </script>
    
</body>
</html>
```

## 核心代码深度解密

### 1. `import { createApp } from '...'`

利用了我们刚学过的 **ES6 模块化命名导入**。`createApp` 是 Vue 3 的总入口、总指挥官，负责创建一整台帮你管理网页的自动机器。

### 2. 插值表达式 `{{ }}`（Mustache 语法）

- **直白解释：** 在 HTML 标签中间，只要写上双大括号 `{{ 变量名 }}`，Vue 就会把 `data()` 里面返回的同名变量值**死死地钉在那个位置**。
    
- 它是前端动态渲染的核心。后续你从 Java 后端拿到一条员工姓名 JSON `"name": "赵敏"`，在前端只需要写 `<td>{{ emp.name }}</td>` 就能直接展现在表格里。
    

### 3. `.mount("#app")`

- **直白解释：** 划定地盘。这句话告诉 Vue：你的超能力**只在 id 为 app 的这个 `<div>` 标签内部有效**。在这个大盒子外面的 HTML 标签，Vue 是管不到的。
    

---
---


## 常用指令——v-for


### 什么是 Vue 指令？

**指令（Directives）是带有 `v-` 前缀的特殊属性**。它们被写在 HTML 标签上，不同的指令能赋予标签不同的神秘力量（比如控制显示隐藏、绑定事件等）。


![[Java Web笔记-15.png]]



在传统原生 JS 里，如果我们从 Java 后端拿到一个包含 10 个员工的数组，想要渲染到表格里，得痛苦地写 `for` 循环、用字符串拼接 `<tr><td>`，再疯狂操作 DOM 塞进去。

而 Vue 提供的 `v-for` 的专属力量就是：**列表渲染（遍历容器的元素或者对象的属性）**，为了干碎这种重复劳动力而生的。它能让你在 HTML 标签上**直接写循环**，一句话就能把整个表格动态渲染出来！


![[Java Web笔记-16.png]]


### 标准语法骨架

```HTML
<tr v-for="(item, index) in items" :key="item.id">
    <td>{{ item }}</td>
</tr>
```

### 参数逐字拆解：

- **`items`**：你在 `data()` 中定义好、从后端查出来的**源数据数组**。
    
- **`item`**：从数组里**当前遍历出来的单个元素实例**（类似于 Java 增强 for 循环 `for(Object item : items)` 里的元素名）。
    
- **`index`**：当前循环的**索引/下标**，从 `0` 开始。
    
    - _提示：如果开发中你不需要用到下标，括号和 index 都可以直接省略，直接写成 `v-for="item in items"`_。
        

### `:key` 的作用是什么？

`:key` 是给循环出来的每一个 HTML 元素添加的**唯一身份证标识**。有了这个唯一标识，Vue 底层的虚拟 DOM 在进行页面数据更新排序时，就能**准确、高效地复用和提升渲染性能**。

### 核心避坑铁律：

- 🌟 **推荐使用数据的 id 作为 key**：因为数据库里每条记录的 id 是绝对唯一的，不会随着前端翻页或删除而改变。
    
- ❌ **极其不推荐使用 index 作为 key**：因为 index（0, 1, 2）是会随着你删除某一行而动态变化的。一旦混淆，Vue 底层在复用输入框等组件时就会产生莫名其妙的样式和数据错位 Bug。
    

### 实战演练：一句话渲染出整个 tlias 员工表格

我们直接以“表格数据展示区”作为舞台。假设我们已经通过 Ajax 从 Java 后端拿到了员工的 List 集合，现在用 Vue 3 的 `v-for` 完美渲染它：


```HTML
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>tlias 员工表格——v-for 实战</title>
    <style>
        table { width: 100%; border-collapse: collapse; text-align: center; }
        th, td { border: 1px solid #e8e8e8; padding: 12px; }
        th { background-color: #fafafa; }
        .gender-tag { padding: 3px 8px; border-radius: 4px; font-size: 12px; }
    </style>
</head>
<body>

    <div id="app">
        <h2>tlias 智能学习辅助系统 - 员工管理</h2>
        <br>

        <table>
            <thead>
                <tr>
                    <th>姓名</th>
                    <th>性别</th>
                    <th>职位</th>
                    <th>入职日期</th>
                    <th>操作</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(emp, index) in empList" :key="emp.id">
                    
                    <td>{{ emp.name }}</td>
                    
                    <td>{{ emp.gender }}</td>
                    
                    <td>{{ emp.job }}</td>
                    
                    <td>{{ emp.entryDate }}</td>
                    
                    <td>
                        <button @click="editEmp(emp.id)">编辑</button>
                        <button @click="deleteEmp(emp.id, index)">删除</button>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>

    <script type="module">
        import { createApp } from 'https://unpkg.com/vue@3/dist/vue.esm-browser.js';

        createApp({
            data() {
                return {
                    // 🚨 注意警告：遍历的数组，必须提前在 data 中定义好！
                    empList: [
                        { id: 1, name: "赵敏", gender: "女", job: "班主任", entryDate: "2008-12-18" },
                        { id: 2, name: "风清扬", gender: "男", job: "讲师", entryDate: "2015-07-22" },
                        { id: 3, name: "张无忌", gender: "男", job: "讲师", entryDate: "2018-09-01" }
                    ]
                }
            },
            methods: {
                editEmp(id) {
                    alert(`准备编辑 id 为 ${id} 的员工数据...`);
                },
                deleteEmp(id, index) {
                    // 模拟前端点击删除后，同步更新视图
                    if(confirm(`确定要删除此员工吗？`)) {
                        // 利用 JS 数组方法删除当前行，Vue 会自动感知并刷新表格！
                        this.empList.splice(index, 1);
                        alert(`成功通知 Java 后端将数据库中 id 为 ${id} 的员工抹去！`);
                    }
                }
            }
        }).mount("#app");
    </script>
</body>
</html>
```

### 核心全栈思维提示：

**遍历的数组，必须提前在 `data` 中定义！**

在未来真实项目里，页面刚打开时，`empList` 往往初始化是一个**空数组 `[]`**。紧接着 Vue 的 `mounted()` 生命周期钩子会自动触发，向你的 Spring Boot 发送一个 Ajax 网络请求。Java 接口从 MySQL 里将 List 查出来并转成 JSON 传回给前端，前端直接一句 `this.empList = response.data;` 赋值，表格瞬间就会唰地一下全部展示出来。

这就是现代前后端分离项目里，**数据动态列表渲染** 的无缝全闭环流程！

---
---



## 常用指令——v-if和v-show


在开发 **tlias 智能学习辅助系统** 的表格数据展示区时，你一定遇到过这种后端传回的“黑话”数据：性别字段传过来的是 `1` 或 `2`（1代表男，2代表女）；或者员工的头像图片地址，有的有值，有的直接返回了 `null`。

如何让网页根据这些数据条件，智能地显示对应的文字、标签或者隐藏不需要的组件？

这就需要用到你新上传的截图中介绍的两大经典“条件控制”指令：**`v-if`** 和 **`v-show`**。虽然它们最终呈现给用户的视觉效果都是“让一个东西显示或隐藏”，但作为后端开发者，我们必须死死抠住它们的**底层执行原理**，因为它们的性能开销完全不同。

![[Java Web笔记-18.png]]

### 1. `v-if` 家族 —— 条件渲染（对应 Java 的 `if-else`）


![[Java Web笔记-17.png]]

- **语法**：`v-if="表达式"`，可以配合 `v-else-if` 和 `v-else` 进行链式条件判断。
    
- **底层原理（硬核）**：**基于条件判断，来控制创建或移除元素节点**。如果表达式的值为 `false`，Vue 会直接残忍地**把整个 HTML 标签从 DOM 树上切掉、彻底销毁**；只有变为 `true` 时，才会重新动态创建这个标签。
    
- **警告**：`v-else-if` 必须紧跟在 `v-if` 之后，`v-else` 必须紧跟在 `v-if` 或 `v-else-if` 之后，否则浏览器直接报错罢工！
    

### 2. `v-show` —— 样式显示隐藏

- **语法**：`v-show="表达式"`。
    
- **底层原理（硬核）**：**基于 CSS 样式 `display` 来控制显示与隐藏**。不管表达式是 `true` 还是 `false`，这个 HTML 标签**永远完好无损地躺在 DOM 树里**。当值为 `false` 时，Vue 只是自动给它加上了行内样式 `display: none;` 把它藏起来而已。
    

### 3. 两者对比

|**维度**|**v-if / v-else-if / v-else**|**v-show**|
|---|---|---|
|**隐藏时的底层动作**|**销毁 / 移除 DOM 节点**|**仅修改 CSS 样式 `display: none;`**|
|**初始渲染开销**|如果初始值为 `false`，则完全不渲染，初次加载极快|不管初始是什么，都会把节点造出来，初次加载稍慢|
|**频繁切换开销**|**极高**（频繁地在内存里创建、销毁 DOM 节点非常消耗 CPU）|**极低**（仅仅改个 CSS 属性，浏览器毫无压力）|
|**企业级应用场景**|**要么显示，要么不显示，不频繁切换的场景**。<br><br>  <br><br>例如：根据当前登录员工的权限，控制“删除按钮”是否渲染（非管理员直接不生出这个按钮）。|**频繁切换显示隐藏的场景**。<br><br>  <br><br>例如：点击搜索栏的“高级筛选”展开/收起菜单，或者各种弹窗、Tooltip 提示框。|

### 4. 代码实战

我们直接结合员工管理表格，以及 `v-bind` 图片属性绑定，来写一段最纯正的条件控制实战：

```HTML
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>tlias 员工表格——v-if 与 v-show 实战</title>
    <style>
        table { width: 100%; border-collapse: collapse; text-align: center; }
        th, td { border: 1px solid #e8e8e8; padding: 12px; }
        .avatar-img { width: 40px; height: 40px; border-radius: 50%; }
        .no-avatar { color: #aaa; font-style: italic; }
    </style>
</head>
<body>

    <div id="app">
        <h3>员工列表展示（条件控制区域）</h3>
        
        <table>
            <thead>
                <tr>
                    <th>姓名</th>
                    <th>性别（数据翻译）</th>
                    <th>头像状态（动态控制）</th>
                    <th>在线状态</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="emp in empList" :key="emp.id">
                    <td>{{ emp.name }}</td>

                    <td>
                        <span v-if="emp.gender === 1" style="color: blue;">♂ 男</span>
                        <span v-else-if="emp.gender === 2" style="color: pink;">♀ 女</span>
                        <span v-else style="color: gray;">未知</span>
                    </td>

                    <td>
                        <img v-if="emp.avatar" :src="emp.avatar" class="avatar-img">
                        <span v-else class="no-avatar">暂无头像</span>
                    </td>

                    <td>
                        <span style="color: green;">● </span>
                        <span v-show="emp.isOnline">工作在线</span>
                        <span v-show="!emp.isOnline" style="color: #999;">离线</span>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>

    <script type="module">
        import { createApp } from 'https://unpkg.com/vue@3/dist/vue.esm-browser.js';

        createApp({
            data() {
                return {
                    empList: [
                        { id: 1, name: "赵敏", gender: 2, avatar: "https://randomuser.me/api/portraits/women/1.jpg", isOnline: true },
                        { id: 2, name: "风清扬", gender: 1, avatar: null, isOnline: false },
                        { id: 3, name: "东方不败", gender: 3, avatar: "https://randomuser.me/api/portraits/legends/3.jpg", isOnline: true }
                    ]
                }
            }
        }).mount("#app");
    </script>
</body>
</html>
```

### 总结 

1. **`v-if` 是真正的“生死判官”**：当条件为假时，对应的标签和里面的子标签在页面 HTML 源码里是**彻底消失、找不到的**。
    
2. **`v-show` 是“隐身斗篷”**：不管真假，标签永远都在，只是加了 `display: none`。
    
---
---



## 常用指令——v-bind



我们在第一节学过，如果要动态改变 HTML 标签**中间的文字**，我们直接用双大括号 **插值表达式 `{{ }}`** 就能轻松搞定：

```HTML
<p>当前登录账号：{{ loginUser.name }}</p>
```

### 致命痛点：插值表达式不能写在属性里

但是，如果你想动态改变 HTML 标签的**属性值**（比如图片的 `src` 路径、超链接的 `href` 地址、或者盒子的 `style/class` 样式），你绝对**不能**这样写：

```HTML
<img src="{{ emp.avatar }}"> 
```

### 救场英雄：`v-bind`

**`v-bind` 的作用，就是动态为 HTML 标签绑定属性值**。 一旦你在某个属性前面加上了 `v-bind:`，你就等于开启了一个“魔法通道”：**属性值里面的双引号就不再是普通的字符串了，而是变成了可以执行 JS 表达式、读取 `data` 变量的“高能区域”**！

### 写法

它的写法分为标准版和企业开发 100% 会用的极简版：

- **标准语法**：`v-bind:属性名="data中的变量名"`
    
- **简化语法（语法糖）🌟**：**直接把 `v-bind` 蒸发掉，只留一个冒号 `:`**


### 属性绑定对比演练：

```HTML
<img v-bind:src="item.image" width="30px"> 
<img :src="item.image" width="30px">       

<a :href="baseUrl + '/download'">下载附件</a>

<button :disabled="!emp.isOnline">发送消息</button>
```

### 实战演练

我们把 `v-for`、`v-if` 以及刚学的 `:`（`v-bind` 简化版）融会贯通，做一个高级的名片渲染中心。在这个案例中，我们会动态绑定**图片地址**、**超链接**，甚至根据员工的在职状态**动态绑定不同的 CSS 颜色样式**！

```HTML
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>tlias 员工名片——v-bind 终极实战</title>
    <style>
        .card { width: 220px; padding: 20px; border: 1px solid #ccc; text-align: center; display: inline-block; margin: 10px; border-radius: 8px; }
        .avatar { width: 80px; height: 80px; border-radius: 50%; }
        /* 两个不同的控制样式的 class 类名 */
        .active-style { border: 2px solid #52c41a; background-color: #f6ffed; }
        .leave-style { border: 2px solid #ff4d4f; background-color: #fff2f0; filter: grayscale(100%); }
    </style>
</head>
<body>

    <div id="app">
        <h2>tlias 系统 - 讲师风采墙</h2>
        <br>

        <div v-for="emp in empList" :key="emp.id" :class="emp.status === 1 ? 'card active-style' : 'card leave-style'">
            
            <img :src="emp.avatar" class="avatar" alt="员工头像">
            
            <h3>{{ emp.name }}</h3>
            <p>职位：{{ emp.job }}</p>

            <a :href="'http://localhost:8080/tlias/emp/detail/' + emp.id" target="_blank">查看详情介绍</a>
            <br><br>

            <span v-if="emp.status === 1" style="color: green;">● 在职</span>
            <span v-else style="color: red;">● 已离职</span>
        </div>
    </div>

    <script type="module">
        import { createApp } from 'https://unpkg.com/vue@3/dist/vue.esm-browser.js';

        createApp({
            data() {
                return {
                    empList: [
                        { id: 10, name: "风清扬", job: "教研主管", avatar: "https://randomuser.me/api/portraits/men/10.jpg", status: 1 },
                        { id: 11, name: "任统领", job: "普通讲师", avatar: "https://randomuser.me/api/portraits/men/11.jpg", status: 1 },
                        { id: 12, name: "左盟主", job: "高级讲师", avatar: "https://randomuser.me/api/portraits/men/12.jpg", status: 0 } // 已离职，名片会自动变灰变红
                    ]
                }
            }
        }).mount("#app");
    </script>
</body>
</html>
```

---
---

## 常用指令——v-model和v-on



在开发 tlias 系统的**搜索表单区域**时，这两个指令是绝对的黄金搭档：一个负责在输入框和下拉列表里**实时采集用户输入的数据**（`v-model`）；另一个负责在点击“查询”或“清空”按钮时**触发后台逻辑**（`v-on`）。


### 1.  `v-model`（表单数据的“数据传送门”）

`v-model` 的核心作用是：**在表单元素上使用，创建双向数据绑定**。它可以让我们极其方便地 **获取 或 设置 表单项数据**。


![[Java Web笔记-19.png]]


#### 什么是“双向绑定”？

- **方向一（内存 ➡️ 页面）**：你在 `data()` 里把变量改了，网页输入框里的文本会自动跟着变。
    
- **方向二（页面 ➡️ 内存）🌟后端最爱**：用户在网页输入框里敲了字，**你不需要写任何 DOM 操作去抓取，`data()` 里对应的变量已经瞬间自动同步拿到了新值**！
    

#### 语法与规范要求

```HTML
v-model="变量名"
```

- **警告**：**`v-model` 中绑定的变量，必须提前在 `data` 中定义好**！
    
- **后端优雅写法律感**：在采集表单时，不要把变量散着写。强烈推荐像截图里一样，在 `data` 里封装一个 `searchForm` 或 `pojo` 对象，把所有的输入项收拢进去：

    ```HTML
    <input type="text" v-model="searchForm.name">
    ```


### 2. `v-on`（网页动作的“神经末梢”）

`v-on` 的作用是：**为 HTML 标签绑定事件（添加事件监听）**。它彻底取代了我们之前学过的原生 `addEventListener` 这种臃肿的写法。


![[Java Web笔记-20.png]]

#### 语法与极简“语法糖”

- **标准语法**：`v-on:事件名="methods中的方法名"`
    
- **简化语法（语法糖）🌟**：**直接把 `v-on:` 缩写为一个艾特符号 `@`**！
    

```HTML
<button v-on:click="handle">点我</button>
<button @click="handle">再点我</button>
```

- **方法栖息地**：绑定的方法，必须规规矩矩地写在 Vue 实例的 **`methods`** 属性里。
    

### 终极联手实战：全面还原 tlias 条件搜索区域

现在，我们把 `v-model` 数据采集和 `@click` 事件触发完美结合，直接在前端还原你朝思暮想的 **tlias 员工搜索表单区域功能**！


```HTML
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>tlias 搜索栏——v-model与v-on实战</title>
    <style>
        .search-container { background-color: #fcf0e7; padding: 20px; border-radius: 4px; display: flex; gap: 15px; align-items: center; }
        .input-item { padding: 5px; border: 1px solid #ccc; border-radius: 4px; }
        .btn-query { background-color: #00bcd4; color: white; border: none; padding: 6px 15px; cursor: pointer; border-radius: 4px; }
        .btn-clear { background-color: #9e9e9e; color: white; border: none; padding: 6px 15px; cursor: pointer; border-radius: 4px; }
    </style>
</head>
<body>

    <div id="app" style="padding: 30px;">
        <h2>tlias 智能学习辅助系统</h2>
        <br>

        <div class="search-container">
            <label>姓名：</label>
            <input type="text" class="input-item" placeholder="请输入员工姓名" v-model="searchForm.name">

            <label>性别：</label>
            <select class="input-item" v-model="searchForm.gender">
                <option value="">请选择</option>
                <option value="1">男</option>
                <option value="2">女</option>
            </select>

            <label>职位：</label>
            <select class="input-item" v-model="searchForm.job">
                <option value="">请选择</option>
                <option value="1">班主任</option>
                <option value="2">讲师</option>
                <option value="3">学工主管</option>
            </select>

            <button class="btn-query" @click="handleQuery">查询</button>
            <button class="btn-clear" @click="handleClear">清空</button>
        </div>

        <p style="margin-top: 20px; color: #888;">
            【后端调试视窗】当前 searchForm 里面的实时 JSON 数据：{{ searchForm }}
        </p>
    </div>

    <script type="module">
        import { createApp } from 'https://unpkg.com/vue@3/dist/vue.esm-browser.js';

        createApp({
            data() {
                return {
                    // 🚨 天条：v-model中绑定的变量，必须在data中提前定义
                    searchForm: {
                        name: '',
                        gender: '',
                        job: ''
                    }
                }
            },
            methods: {
                // 点击查询按钮触发
                handleQuery() {
                    // 校验一下拿到的数据
                    if (this.searchForm.name === '' && this.searchForm.gender === '' && this.searchForm.job === '') {
                        alert("请至少选择一个条件再进行检索！");
                        return;
                    }
                    
                    // 震撼全栈的一刻：直接打印数据，用户填的所有值全在里面！
                    console.log("准备打包发送给 Spring Boot 的条件参数：", this.searchForm);
                    alert(`正在向 Java 接口发送异步请求... \n条件：姓名=${this.searchForm.name}, 性别=${this.searchForm.gender}, 职位=${this.searchForm.job}`);
                    // 以后这里直接写 axios.get('/emp/page', { params: this.searchForm })
                },
                
                // 点击清空按钮触发
                handleClear() {
                    // 利用数据驱动视图思想，直接重置 data 里的对象，页面上的表单框会自动清空！
                    this.searchForm.name = '';
                    this.searchForm.gender = '';
                    this.searchForm.job = '';
                    console.log("表单已重置复位");
                }
            }
        }).mount("#app");
    </script>
</body>
</html>
```



当你把上面这段代码跑起来，在输入框里敲字、切换下拉框时，盯着那个“后端调试视窗”里的 JSON 字符串跟着实时缩放变动，你会由衷地发现：**DOM 操作的时代彻底过去了**。利用 `v-model` + `v-on`，你只用关注数据的状态，繁琐的底层交互全部被框架接管了。

---
---


## 补充：Vue的生命周期


![[Java Web笔记-26.png]]



很多全栈初学者写代码非常随意：想发 Ajax 请求，结果写错地方导致拿到数据页面死活不刷新；或者想操作 DOM 节点，结果代码执行时标签根本还没造出来，直接报 `undefined` 错误。

作为后端开发者，你可以把 Vue 生命周期完美类比为 **Servlet的 `init/service/destroy`**，或者是 **Spring 容器中 Bean 的生命周期管理**。一个 Vue 实例从**在内存中被创建**，到**编译模板**、**挂载到浏览器页面上**，再到**数据变动导致重新渲染**，最后**被销毁**，整个过程就像人类的一生一样，会经历不同的“关键节点”。

Vue 在这些节点上为你预留了**生命周期钩子函数（Lifecycle Hooks）**，允许你在特定的时刻自动塞入你的 Java/Axios 逻辑。

### 一、 四大核心阶段与 8 个主要钩子

我们将生命周期的全程拆解为四大核心阶段（每个阶段都有一个“准备前”和“完成交接后”的钩子）：

#### 1. 初始化阶段（Creation）—— 内存中胚胎发育

Vue 实例正在内存里初始化，此时**页面上什么都看不到**。

- **`beforeCreate`**：实例刚在内存里创建，此时 Vue 最核心的 `data` 数据和 `methods` 方法**都还没初始化**，什么也干不了。
    
- **`created`**：极度重要！此时内存中的 `data` 和 `methods` 已经大功告成，可以正常读写变量了。
    
    - _全栈开发场景_：如果你不需要对 DOM 标签做调整，这时候已经可以在后台默默启动 `axios` 异步向 Java 后端发送请求拉取数据了。
        

#### 2. 挂载阶段（Mounting）—— 破土而出见浏览器

Vue 准备把内存里编译好的 HTML 骨架，真正地“强行塞入”到浏览器的 DOM 树中。

- **`beforeMount`**：模板已经在内存里编译好了，但是还没正式装进网页里。此时页面上你写的 `{{ message }}` 还没被翻译，还是串死文本。
    
- **`mounted` 🌟🌟🌟（企业全栈绝对的王牌之魂）**：**整个生命周期里使用率达 90% 的钩子。**此时，Vue 已经把写好数据的真实 HTML 节点**成功挂载、渲染到了网页上**。
    
    - _全栈开发场景_：正如我们前两节写的一样，**发 Ajax 请求、拿后端真实员工列表、初始化各种第三方图表插件，100% 必须写在 `mounted()` 里！** 因为只有到了这一刻，页面上的 HTML 标签才真实存在。
        

#### 3. 更新阶段（Updating）—— 数据变动，页面“变脸”

只要你网页上的数据（`data` 里的变量）发生了修改，这个阶段就会被循环反复触发。

- **`beforeUpdate`**：`data` 里的变量已经变成新值了，但网页上的老标签还没来得及换，两者处于脱节状态。
    
- **`updated`**：Vue 内部利用虚拟 DOM 算法比对完毕，网页上的 HTML 标签已经唰地一下**完成了重新渲染，变成最新的视觉效果**。
    

#### 4. 销毁阶段（Unmounting）—— 功成身退，内存释放

当页面切换、或者组件利用 `v-if` 被隐藏销毁时触发。

- **`beforeUnmount`**（老版本叫 `beforeDestroy`）：组件从页面移除前的一瞬间。
    
    - _全栈开发场景_：用来做收尾工作。比如你在页面上开了一个每隔 1 秒请求一次 Java 接口的“大屏定时器”，必须在这里手动把定时器关掉，否则组件没了定时器还在后台裸奔，会导致严重的内存泄漏。
        
- **`unmounted`**（老版本叫 `destroyed`）：实例彻底瓦解，所有事件监听被移除。
    

### 二、 代码实战：肉眼捕捉生命周期的“心跳”

我们直接写一段好玩的监控代码，把你截图里最核心的 `created` 和 `mounted` 抓到控制台里，并看清楚它们和 Axios 数据的执行先后顺序：

```HTML
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>Vue 生命周期钩子全捕捉</title>
</head>
<body>

    <div id="app">
        <h3 id="title">当前系统状态：{{ statusMessage }}</h3>
        <button @click="statusMessage = '数据已更新！'">修改状态触发 Update</button>
    </div>

    <script type="module">
        import { createApp } from 'https://unpkg.com/vue@3/dist/vue.esm-browser.js';

        createApp({
            data() {
                return {
                    statusMessage: "正在初始化..."
                }
            },
            
            // 1. 内存初始化完毕
            created() {
                console.log("【1. 执行了 created() 钩子】:");
                console.log("-> 内存中的数据可以读取到了:", this.statusMessage);
                
                // 🚨 后端思维测试：此时去抓网页上的 h3 标签
                let dom = document.getElementById("title");
                console.log("-> 此时抓取网页上的h3元素结果是:", dom); // 结果会是 null！因为还没挂载呢！
                console.log("-----------------------------------------");
            },

            // 2. 网页挂载完毕（全栈最常用的高架桥）
            mounted() {
                console.log("【2. 执行了 mounted() 钩子】:");
                console.log("-> 此时抓取网页上的h3元素结果是:", document.getElementById("title")); // 完美抓到对象！
                
                // 模拟在这个时刻，自动执行异步 Axios 业务
                this.statusMessage = "tlias 系统就绪，已成功连接 Spring Boot 服务端！";
                console.log("-----------------------------------------");
            },

            // 3. 当你点击按钮改变 statusMessage 时，会自动触发以下两个钩子
            beforeUpdate() {
                console.log("【3. 触发 beforeUpdate】数据变了，但页面还没变");
            },
            updated() {
                console.log("【4. 触发 updated】页面已经完成了重绘渲染！");
            }

        }).mount("#app");
    </script>
</body>
</html>
```

#### 运行后的控制台打印真相：

1. `【1. 执行了 created() 钩子】` 触发 ➡️ 证明内存数据好了，但 DOM 节点是 `null`。
    
2. `【2. 执行了 mounted() 钩子】` 触发 ➡️ 成功抓到真正的网页 DOM 节点，数据渲染成功。
    
3. 点击按钮 ➡️ 依次打印 `beforeUpdate` 和 `updated`。
    

### 面试与开发核心死理（一句话总结）

> **“在 `created` 里有数据无 DOM，在 `mounted` 里有数据有 DOM。”**
> 
> 作为全栈开发，记住一个铁律：**凡是涉及到调用后端接口（Axios）并需要渲染到页面上的初始化动作，不要犹豫，统统塞进 `mounted()` 里！**




---
---
# Ajax




如果说前面的 HTML/CSS 是皮肉，JavaScript 是筋骨，Vue 是高效的器官，那么 **Ajax 就是血液**。没有 Ajax，前端只是一个单机版、孤芳自赏的精美壳子；**有了 Ajax，前端才能跨越千山万水，连接上你的 Spring Boot 后端、Tomcat 服务器和 MySQL 数据库**

今天我们顺着你的课程脉络，用纯正的后端视角，把 **Ajax 的本质、同步与异步的死穴、以及企业级标配 Axios 框架** 彻底扒得清清楚楚。

## 什么是 Ajax？（解决什么核心痛点）


![[Java Web笔记-21.png]]

如图所示，**Ajax** 全称是 **A**synchronous **J**avaScript **A**nd **X**ML（异步的 JavaScript 和 XML）。

### 核心作用：

1. **数据交换**：通过 Ajax 可以给服务器发送请求，并获取服务器响应的数据。
    
2. **异步交互**：可以**在不重新加载（刷新）整个页面的情况下，与服务器交换数据并更新部分网页**的技术。
    

### 场景暴击：如果没有 Ajax 会怎样？

在遥远的 2005 年之前，网页没有 Ajax。用户在注册网易邮箱时，输入完用户名（比如 `java666`），必须点击“提交”按钮，**导致整个网页大白屏刷新一次**，把数据传给后端 Java，Java 去 MySQL 查完发现重名了，再渲染一个新网页返回给浏览器，提示“该邮箱已被占用”。用户之前填写的密码、密保全没了，体验差到让人想砸电脑。

有了 Ajax 之后，就像截图里的网易邮箱注册一样：用户输入完鼠标一失焦，前端在后台默默发一个极其轻量级的请求给 Java，**整个网页完全不动，只有输入框下面唰地弹出一行红字**。这就是 Ajax 的恐怖威力。


## 核心硬核：同步与异步的区别

![[Java Web笔记-22.png]]

看懂图中的那两条“时间轴”，是决定一个程序员能不能写好并发代码的关键。

### 1. 同步（Synchronous）模式

- **执行逻辑**：客户端向服务器发送请求后，**必须死死停在原地，什么也干不了，等待服务器的响应**。
    
- **后端类比**：就像 Java 里单线程调用一个阻塞方法 `Thread.sleep(3000)`，代码必须卡在那一行，等它执行完才能走下一步。
    

### 2. 异步（Asynchronous）模式 🌟（Ajax的灵魂）

- **执行逻辑**：客户端向服务器发送请求。在服务器处理的这 3 秒钟里，**客户端（浏览器）完全不需要等待，用户可以继续在网页上愉快地打字、滚动、点击其他按钮**。当服务器处理完把数据送回来时，浏览器会自动触发一个“回调函数”来渲染数据。
    
- **全栈白话**：你去饭店点完单，拿了个会亮灯的排队号簿（发起了异步请求），然后你就回座位上刷手机、和朋友聊天去了（客户端执行其他操作）。等到号簿开始震动闪烁（服务器响应），你再去取餐（执行成功回调）。
    

## 从原生到企业级王牌：Axios 的降维打击

原生 JS 提供的 Ajax 核心对象叫 `XMLHttpRequest`（简称 XHR），但它的语法设计得极其反人类，需要手写十几行代码，还要处理复杂的跨域状态判断。

所以，在实际的企业项目开发中，**没人会去写原生的 Ajax，100% 会使用对原生 Ajax 进行优雅封装的第三方库——Axios**！

### 1. 标准经典写法（配置对象模式）

![[Java Web笔记-23.png]]


如你图所示，引入 Axios 的 JS 文件后，标准写法如下：

```JavaScript
axios({
    method: 'GET',                                // 请求方式，GET/POST/PUT/DELETE
    url: 'https://web-server.itheima.net/emps/list' // 请求路径（未来换成你的Spring Boot接口）
}).then((result) => {
    // 🌟 成功回调函数：当后端Java成功返回JSON数据时，自动触发
    console.log("拿到后端数据了：", result.data);    // 真正的后端数据藏在 result.data 里！
}).catch((err) => {
    // ❌ 失败回调函数：网络断了、或者后端报500服务器炸了时触发
    alert("网络请求失败：" + err);
});
```

### 2. 企业开发最推荐：请求方式别名


![[Java Web笔记-24.png]]

如图所展示的带有大绿色“**推荐**”戳的花样写法。因为天天写 `method` 太烦了，Axios 为所有常用请求方式提供了别名函数：

```JavaScript
// 格式：axios.请求方式(url [, data [, config]])
```

- **GET 请求别名（常用于查询 List/Page）**：

    ```JavaScript
    axios.get('http://localhost:8080/tlias/emps/list')
         .then(res => console.log(res.data))
         .catch(err => console.error(err));
    ```
    
- **POST 请求别名（常用于新增、修改、携带复杂JSON体）**：

    ```JavaScript
    // 第二个参数直接塞你要传给 Java 的参数体
    axios.post('http://localhost:8080/tlias/emps/save', { name: '张三', gender: 1 })
         .then(res => alert("保存成功！"))
         .catch(err => alert("保存失败"));
    ```


## 代码实战：Vue 3 + Axios 异步数据渲染

现在，我们把前几节学到的 Vue 3 数据驱动、`v-for` 表格渲染、以及今天的 Axios 别名异步请求全部拧成一股绳，为你还原一个大三做毕业设计、去企业实习时 **100% 一模一样的真实表格开发闭环代码**！

```HTML
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>tlias 终极闭环——Vue+Axios 异步动态渲染</title>
    <style>
        table { width: 100%; border-collapse: collapse; text-align: center; margin-top: 15px; }
        th, td { border: 1px solid #e2e2e2; padding: 10px; }
        th { background-color: #f7f7f7; }
        .loading { font-size: 18px; color: #666; font-weight: bold; }
    </style>
</head>
<body>

    <div id="app" style="padding: 30px;">
        <h2>tlias 智能学习辅助系统 - 异步数据联动中心</h2>

        <div class="loading" v-show="isLoading">🔄 正在连接远程 Java 接口，拼命读取 MySQL 中，请稍候...</div>

        <table v-show="!isLoading">
            <thead>
                <tr>
                    <th>员工ID</th>
                    <th>姓名</th>
                    <th>职位</th>
                    <th>入职时间</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="emp in empList" :key="emp.id">
                    <td>{{ emp.id }}</td>
                    <td>{{ emp.name }}</td>
                    <td>{{ emp.job }}</td>
                    <td>{{ emp.entryDate }}</td>
                </tr>
            </tbody>
        </table>
    </div>

    <script src="https://unpkg.com/axios/dist/axios.min.js"></script>

    <script type="module">
        import { createApp } from 'https://unpkg.com/vue@3/dist/vue.esm-browser.js';

        createApp({
            data() {
                return {
                    // 天条：遍历的源数组，必须初始化定义好！开始时是空的
                    empList: [],
                    isLoading: true // 初始状态为正在加载
                }
            },
            // 🌟 震撼全栈的生命周期钩子：mounted()
            // 它的意思是：当网页刚刚在浏览器里渲染、挂载完毕的一瞬间，会自动执行这里的代码！
            mounted() {
                console.log("【生命周期钩子触发】网页已就绪，立即启动 Ajax 向后端拉取真实数据！");
                
                // 执行异步网络请求（这里使用的是黑马程序员官方提供的线上模拟 Mock 接口）
                axios.get('https://mock.apifox.cn/m1/3083103-0-default/emps/list')
                    .then((result) => {
                        // 1. 把后端返回的真实 JSON 数组，死死地喂给 data 里的 empList 变量
                        this.empList = result.data.data; 
                        
                        // 2. 关闭加载动画
                        this.isLoading = false;
                        console.log("【数据交付成功】Vue 感知到 empList 发生变量，已自动帮你触发重新变脸渲染！");
                    })
                    .catch((error) => {
                        this.isLoading = false;
                        alert("连接服务端失败，请检查你的后端 Spring Boot 端口是否正常开启！");
                    });
            }
        }).mount("#app");
    </script>
</body>
</html>
```

---
---


## 补充：async和await


![[Java Web笔记-25.png]]



作为 Java 开发者，你看到这一幕绝对会狂喜。因为上一节我们写的 `axios.get().then().catch()` 这种一环扣一环的回调函数（俗称**回调地狱**），在习惯了“从上到下按顺序执行”的 Java 程序员眼里，看多了总觉得别扭。

而 `async` 和 `await` 的出现，就是为了让我们**用写同步代码的爽快感，去写底层的异步网络请求**！

### 一、 核心概念：它们到底是什么？

这两个关键字通常是**成双成对、密不可分**的亲兄弟：

1. **`async`（异步声明）**：
    
    - **作用**：用来修饰一个方法。只要方法前面加了 `async`，就代表告诉浏览器：“这是一个异步方法，我里面准备整点网络请求等耗时操作了！”
        
2. **`await`（异步等待）**：
    
    - **作用**：只能写在被 `async` 声明的方法内部。它放在一个异步请求（比如 Axios）前面，意思是：“后面的网络请求你给我卡住，等后端 Java 把数据安全送回来了，我拿到结果再往下走下一行。”
        

### 二、 维打击：传统 `.then()` 与 `async/await` 代码对比

为了让你一眼看出为什么官方疯狂推荐它，我们把上一节的 Axios 请求拿出来做个肉眼可见的对比：

#### 1. 传统的 `.then()` 写法（配置回调）

```JavaScript
methods: {
    search() {
        axios.get('https://web-server.itheima.net/emps/list').then((result) => {
            // 嵌套在里面的回调函数，层级一旦变多，代码就会疯狂往右边缩进
            this.employees = result.data.data;
            console.log("成功拿到数据");
        });
    }
}
```

#### 2. 完美的 `async / await` 写法（如同写 Java 顺序代码）

```JavaScript
methods: {
    // 1. 在方法名前面加上 async 声明
    async search() {
        // 2. 在 axios 前面加上 await，直接用一个普通的变量接收返回结果！
        // 此时，代码会在这里“等”网络请求成功，完全取代了传统的 .then() 函数
        let result = await axios.get('https://web-server.itheima.net/emps/list');
        
        // 3. 拿到结果直接用，完全是在写同步代码！从上到下一目了然
        this.employees = result.data.data;
    }
}
```

### 三、 绝对高频的注意警告（避坑死理）


1. **`await` 关键字只能在 `async` 函数内部有效**。如果你在一个普通的方法里写 `await axios.get(...)`，浏览器会无情地给你抛出一个大红色的语法错误。
    
2. **`await` 关键字直接取代了 `.then()` 函数**，用来等待并直接获取请求成功的返回值。
    

### 后端思维小 Tips：那如果网络请求报错（比如404/500）了，怎么替代原先的 `.catch()`？

在 `async/await` 写法里，捕获异常的方式回归到了最纯正的 **Java 传统老手艺——`try-catch` 代码块**：

```JavaScript
async search() {
    try {
        let result = await axios.get('/emps/list');
        this.employees = result.data.data;
    } catch (error) {
        // 如果后端接口炸了，直接进到这里，完美取代 .catch()
        console.error("请求 Java 后端失败：", error);
    }
}
```

### 终极实战演练：用最高级的姿势重构 tlias 查询

我们将上一节的 Vue 3 表格查询，用今天学到的 `async/await` 进行黄金重构。让你的前端代码看起来就像是由拥有 3 年开发经验的老鸟写出来的一样优雅：


```HTML
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>tlias 高级重构——async/await 极简实战</title>
</head>
<body>

    <div id="app" style="padding: 20px;">
        <h3>员工管理（async / await 异步拉取版本）</h3>
        
        <button @click="getEmployeeData">🔍 异步刷新员工列表</button>
        
        <ul>
            <li v-for="emp in employees" :key="emp.id">
                【ID: {{emp.id}}】 姓名: {{ emp.name }} —— 职位: {{ emp.job }}
            </li>
        </ul>
    </div>

    <script src="https://unpkg.com/axios/dist/axios.min.js"></script>

    <script type="module">
        import { createApp } from 'https://unpkg.com/vue@3/dist/vue.esm-browser.js';

        createApp({
            data() {
                return {
                    employees: []
                }
            },
            methods: {
                // 🌟 用 async 关键字包装你的核心点击事件
                async getEmployeeData() {
                    console.log("【1】开始发起异步请求...");
                    
                    try {
                        // 🌟 用 await 静静等待网络畅通，数据直接被赋值给 response
                        let response = await axios.get('https://mock.apifox.cn/m1/3083103-0-default/emps/list');
                        
                        // 【2】这一行代码，绝对会等到上面接口返回后才会执行！
                        console.log("【2】成功抓取到响应体，开始解析赋值！");
                        this.employees = response.data.data;
                        
                    } catch (err) {
                        alert("捕获到服务端异常！");
                    }
                    
                    console.log("【3】方法执行完毕");
                }
            },
            // 顺便在生命周期里也用 async/await，页面一加载就自动顺序执行！
            async mounted() {
                await this.getEmployeeData();
            }
        }).mount("#app");
    </script>
</body>
</html>
```

掌握了 `async` 和 `await`，你在 JavaScript 异步网络通信这一块的内功已经彻底圆满。

---
---


# Web后端开发初识


要开发一个像 tlias 这样的现代化企业级管理系统，后端的武器库绝对不止一个软件，而是分为**核心框架、数据存储、项目管理、中间件、安全防御**五大阵营。

## 一、 核心骨架：Spring 生态帝国

在 Java 后端领域，Spring 就是绝对的统治者。你听到的各种“弹簧”，其实分工明确：

- **Spring Framework（基础内核）**：
    
    - **核心超能力**：**IOC（控制反转）与 DI（依赖注入）**。简单来说，以前在 Java 里用一个对象得自己手动 `new`，现在不需要了，Spring 变成了一个巨大的“对象托管中心”（Spring 容器）。你需要什么，它直接给你注入进去，实现了代码之间的极度解耦。
        
    - **切面编程（AOP）**：把记录日志、事务控制这些重复的脏活累活从核心业务里抽离出来，像“切面包”一样动态贴在方法上。
        
- **Spring Boot（效率革命）**：
    
    - **核心痛点**：传统的 Spring 配置极其繁琐，被称为“配置地狱”，光是 XML 配置文件就能写几百行。
        
    - **降维打击**：Spring Boot 提出了 **“约定大于配置”** 的核心思想。它把常用的第三方 Jar 包打包成了各种 **Starter（启动器）**，并且内置了 Tomcat 服务器。你只要引入它，它就会自动帮你把底层环境配好，真正实现“开箱即用”。
        
- **Spring MVC（交通警察）**：
    
    - 专门负责处理 HTTP 网络请求的框架。当前端通过 Axios 发送请求过来时，是 Spring MVC 在底层负责拦截路由、解析参数，并把 Java 对象自动转成 JSON 响应回去。
        

## 二、 数据存储与持久层：后端的“记忆中枢”

后端的一切业务，本质上都是对数据的“增删改查”。这一块的技术栈分为**持久层框架、关系型数据库、缓存**：

- **MyBatis / MyBatis-Plus（持久层桥梁）**：
    
    - **角色**：在 Java 代码和关系型数据库之间牵线搭桥的框架（ORM 框架）。
        
    - **痛点消除**：原生 Java 连接数据库（JDBC）要写大量的连接关闭代码，非常恶心。MyBatis 允许你把 SQL 语句写在 XML 里或者通过注解和 Java 方法绑定。
        
    - **升级版（MyBatis-Plus）**：企业开发标配。它在 MyBatis 的基础上做了进一步封装，普通的单表增删改查你甚至连一句 SQL 都不用写，直接调用 API 就能搞定。
        
- **MySQL（核心数据仓库）**：
    
    - 最流行的开源**关系型数据库**。采用表格结构，支持严谨的 SQL 语法和事务控制（ACID）。
        
    - **后端核心任务**：在实际开发中，后端的很大一部分内功，在于如何设计出高内聚、低耦合的数据库表结构（主外键关系、多对多连接），以及如何通过**优化索引、改写 SQL** 来让千万级数据的查询速度从 5 秒缩短到 0.05 秒。
        
- **Redis（高并发极速缓存）**：
    
    - 基于内存运行的**非关系型数据库（NoSQL）**。因为数据存在内存里，它的读写速度比机械硬盘上的 MySQL 快成百上千倍。
        
    - **场景暴击**：像系统里高频访问的“员工部门列表”、“字典数据”，如果每次都去查 MySQL，数据库迟早会被高并发冲垮。后端会把这些数据同步一份进 Redis，前端请求来时直接从内存里秒回，这就是**缓存策略**。
        

## 三、 基础设施与工程管理：后端的“后勤部”

写后端项目不是单兵作战，依赖管理和运行环境至关重要：

- **Maven（项目构建与依赖管理）**：
    
    - **角色**：后端的“应用商店”和“打包构建大师”。
        
    - **工作原理**：Java 项目需要海量的第三方依赖包。没有 Maven 之前，你需要去各个官网下载 Jar 包手动拷贝进项目，经常发生版本冲突。现在，你只需要在 Maven 的 `pom.xml` 文件里写几行标签（坐标），Maven 就会自动从中央仓库把 Jar 包下载到你的电脑上。它还负责把你的 Java 源码编译、打包成 `.jar` 或 `.war` 文件。
        
- **Tomcat（Web 服务器 / 核心容器）**：
    
    - 一个轻量级的开源应用服务器。Java 写的代码浏览器是无法直接访问的，必须把代码部署到 Tomcat 里面。Tomcat 负责在指定的端口（比如 8080）监听网络的 HTTP 请求，并把请求转交给我们的 Spring 业务代码。在 Spring Boot 项目中，Tomcat 已经被默默内置进去了。
        

## 四、 进阶拼图：企业级安全与微服务

当系统越做越大时，技术栈就会向深水区延伸：

- **Spring Security / Sa-Token（安全与权限认证）**：
    
    - **核心任务**：解决“你是谁”和“你能干什么”的问题。
        
    - 用来做用户登录加密拦截、JWT 令牌生成与校验、以及精确控制到按钮级别的权限管理（例如：普通讲师只能看数据，教研主管才能点击“删除”按钮）。
        
- **Spring Cloud（微服务架构体系）**：
    
    - 当系统的业务多到一台服务器装不下时，就需要把大系统拆分成几十个独立运行的小 Java 项目（微服务）。Spring Cloud 提供了注册中心（Nacos）、网关（Gateway）、远程调用（OpenFeign）等全套组件，是大型互联网公司的核心标配。
        

## 梳理：一条完整的全栈请求生命流向

了解完这些技术栈，我们把前后的知识串联起来。当用户在 tlias 页面上点击“查询”按钮时，幕后发生的完整技术生态流向是这样的：

1. **前端动作**：Vue 3 触发 `@click` 事件，通过 `v-model` 拿到搜索框里的条件。
    
2. **网络传输**：Axios 带着这些条件，发起一个异步的 HTTP 请求。
    
3. **后端拦截**：内置的 **Tomcat** 收到请求，**Spring Boot (Spring MVC)** 迅速接管，匹配到对应的 Controller 方法。
    
4. **业务处理**：Controller 调用 Service 层执行业务逻辑，如果安全框架（如 **Sa-Token**）检查发现该用户有权限，则放行。
    
5. **数据读取**：代码先去 **Redis** 缓存里碰碰运气，如果缓存没有，**MyBatis** 启动，带着 SQL 语句杀进 **MySQL** 数据库捞取真实数据。
    
6. **原路返回**：后端把拿到的 Java 数据对象转成 **JSON**，通过网络原路返回，Vue 3 的 `mounted()` 或者是 `async/await` 收到响应，页面唰地一下完成局部刷新！
    

后端的技术栈虽然庞大，但它的体系极其严密，层层递进。

---
---



# Maven


## 概述



在 Java 圈子里有一句名言：“**没有 Maven，你甚至很难优雅地跑通一个包含三个以上第三方功能的企业级项目。**”

下面我们完全脱离繁琐的代码，用最纯正的后端视角，把 Maven 的**三大核心作用**以及**三层仓库运作机制**彻彻底底盘点清楚。

### 一、 为什么必须有 Maven？（它解决什么核心痛点）

在没有 Maven 的蛮荒时代（大一写纯原生 Java 基础时），如果你想在项目里连接 MySQL 数据库，或者想用 JSON 解析工具，你得经历以下极其痛苦的四步：

1. 自己去网上海找 `mysql-connector-java-xxx.jar` 包。
    
2. 满怀希望地下载下来，一运行发现版本太新了，跟你的 MySQL 数据库不兼容，报错崩溃。
    
3. 重新找、重新下，手动建立一个 `lib` 文件夹，把 `.jar` 文件死死拷贝进去。
    
4. 手动在 IDE 里点击“Add as Library”（添加到类路径）。
    

更恶心的是，如果这个 A.jar 里面调用了 B.jar，B.jar 里面又调用了 C.jar（这叫**间接依赖**），你必须把 A、B、C 统统手工找齐下载下来。一旦团队里每个人下载的版本不一样，代码一合并直接就是“灾难现场”。

### 二、 Maven 的三大核心王牌功能


![[Java Web笔记-27.png]]


如你第一张截图所示，Maven 的核心价值被精准提炼为了三点：

#### 1. 依赖管理（Dependency Management） 

- **核心超能力**：方便快捷地管理项目依赖的资源（jar包）。
    
- **全栈白话**：它把你的 Java 项目变成了一个“手机 App”，把 `pom.xml` 变成了“App 配置文件”。你想用什么第三方工具，不需要再去网上到处下载 jar 包了，**只需要在 `pom.xml` 里写几行简单的文本坐标**（就像在应用商店搜索名字一样），Maven 会自动通过网络把这个 jar 包以及它所依赖的所有全家桶 jar 包，**全部完完整整、严丝合缝地自动下载并导入到你的项目里**。
    

#### 2. 项目构建（Project Build）

- **核心超能力**：标准化的跨平台（Linux、Windows、MacOS）的自动化项目构建方式。
    
- **全栈白话**：我们在 IDEA 里写的都是 `.java` 源代码，但服务器（如 Tomcat）和 JVM 根本不认源代码，它们只认编译后的 `.class` 字节码文件。Maven 内部自带了一套标准化的“流水线工具”，只需点一个按钮，它就能自动帮我们完成：**清理代码 ➡️ 编译源码 ➡️ 运行测试 ➡️ 把千百个类打包成一个 `.jar` 或 `.war` 压缩包**。这就让项目可以直接无缝部署到云端的 Linux 服务器上。
    

#### 3. 统一项目结构（Uniform Directory Structure）

- **核心超能力**：提供标准、统一的项目结构。
    
- **全栈白话**：以前用 Eclipse 写的项目，拿到 IntelliJ IDEA 里经常因为文件夹结构对不上而疯狂报错。Maven 直接在全世界强行推行了一套**铁律般的标准目录规范**：
    
    - `src/main/java`：雷打不动只能放 Java 业务源代码。
        
    - `src/main/resources`：只能放配置文件、静态资源（HTML/CSS/JS）。
        
    - `src/test/java`：放测试单元代码。
        
        这就是为什么现在不管任何大厂、任何开源项目，你只要用 IDEA 打开一个 Maven 项目，闭着眼睛都能瞬间找到代码在哪，极大地降低了团队协作的沟通成本。
        

### 三、 核心硬核：Maven 的“三层仓库”运作机制


![[Java Web笔记-28.png]]

你上传的第二张截图是一张非常完美的**数据流向图**。它揭示了当我们在 `pom.xml` 里声明了一个 jar 包后，Maven 究竟去哪里把它找出来。

在 Maven 的世界里，“**仓库**”就是用来存储资源、管理各种 jar 包的集中营。它被严密地划分为以下三层：

#### 1. 本地仓库（Local Repository） 

- **本质**：就是**你本地计算机上的一个普通磁盘文件夹**（默认在用户目录的 `.m2/repository` 路径下，通常我们会把它改配到非系统盘）。
    
- **运作流程**：只要你的 Java 项目要用某个 jar 包，Maven **首先绝对会去你的本地仓库文件夹里搜**。如果有，直接拿来用（0毫秒延迟）；如果没有，它才会启动网络去外面拉取。
    

#### 2. 远程仓库 / 私服（Remote Repository） 

- **本质**：一般由**公司团队、学校或组织内部搭建的私有局域网服务器仓库**。
    
- **企业应用场景**：在大厂或做创新创业团队项目时，你写了一个公共的 AI 识别工具包，想让组内其他同学也用上，但这个代码属于商业机密，不能发到互联网上。此时，你就可以把你写的 jar 包直接“上传（deploy）”到你们公司的私服上，你队友的 Maven 就会自动从私服把你的 jar 包拉取到他们的电脑里。
    

#### 3. 中央仓库（Central Repository） 

- **本质**：由 Maven 团队官方亲自出资、在全球范围内维护的、**全世界唯一的最高权力核心公共仓库**。
    
- **特点**：它里面包含了全世界所有开源的 Java jar 包（数以亿计）。只要本地仓库没有，私服也没有，Maven 就会一路向外求助，最终连接到中央仓库去下载。
    

> 🚨 **国内开发者的日常血泪经验（避坑重点）**：
> 
> 中央仓库的官方服务器远在海外，国内直接去下载的话，网速慢得令人抓狂，经常下到一半断线导致 jar 包损坏。因此，国内所有的 Java 程序员在装好 Maven 后，**第一件事绝对是修改 Maven 的 `settings.xml` 配置文件，把中央仓库的地址“镜像（Mirror）”替换为国内的阿里云镜像源（Aliyun Maven）**。这样，原本需要下载半小时的依赖，几秒钟就能全部飙速搞定！

### 思考：当你在项目里引入一个依赖时，幕后在发生什么？


1. 编写配置：你在 `pom.xml` 里写下了 MySQL 驱动的标签。
    
2. 第一步查找：Maven 跑去你电脑的 **本地仓库** 文件夹里看了一眼。
    
3. 发现本地没有 ➡️ Maven 顺着网线连上了你们公司的 **远程仓库（私服）**。
    
4. 发现私服也没有 ➡️ 私服作为代理，顺着互联网直接杀向海外的 **中央仓库**（或者我们配置的阿里云镜像），把最新的 jar 包一把揪下来。
    
5. 缓存原路返回 ➡️ jar 包被下载并缓存到你们公司的私服 ➡️ 再下载到你电脑的 **本地仓库** ➡️ 最终自动挂载到你的 Java 项目中。
    
6. 下次再用 ➡️ 因为本地仓库已经有了，瞬间秒开！
    
---
---


## Maven的安装

![[Java Web笔记-30.png]]


### 第一步：解压包（找准风水宝地）

- **截图步骤**：解压 `apache-maven-3.9.4-bin.zip`。
    
- **避坑大招**：解压路径**千万、绝对、永远不要包含中文或空格**（比如 `D:\软件安装\Java工具\` 是绝对禁止的）！因为后续很多后端底层脚本认不出中文路径，会疯狂报找不到文件的诡异错误。建议直接像截图里一样，解压在纯英文路径，如 `D:\develop\apache-maven-3.9.4`。
    

### 第二步：配置本地仓库（拯救 C 盘大作战） 

- **截图步骤**：修改 `conf/settings.xml` 中的 `<localRepository>` 为一个指定目录。
    
- **为什么要改**：如果不改，Maven 默认会把下载的所有 jar 包（未来可能会有几个G甚至十几G）通通塞进 `C:\Users\你的用户名\.m2\repository` 里面，C 盘会瞬间飘红。
    
- **实操动作**：
    
    1. 在你解压的 Maven 目录下，手动新建一个名为 `mvn_repo` 的空文件夹。
        
    2. 用文本编辑器（如 VS Code 或 Notepad++）打开 Maven 目录下的 `conf/settings.xml`。
        
    3. 找到大概第 50 行左右被 `` 注释掉的 `<localRepository>` 标签，在它外面单独写一行（千万别写进注释里）：
        
        
        
        ```XML
        <localRepository>D:\develop\apache-maven-3.9.4\mvn_repo</localRepository>
        ```
        
        _(这里的路径请完全对应你电脑上的真实创建路径)_
        

### 第三步：配置阿里云私服（开启飙速下载）

- **截图步骤**：修改 `conf/settings.xml` 中的 `<mirrors>` 标签，为其添加子标签。
    
- **为什么要改**：不改的话，Maven 默认连海外中央仓库，下载速度像几十KB的拨号上网，还总断线。
    
- **实操动作**：
    
    1. 依然在刚刚打开的 `settings.xml` 中，往下翻，找到一条大标签：`<mirrors>`。
        
    2. 把下面这段完美的阿里云镜像代码，死死**粘在 `<mirrors>` 和 `</mirrors>` 这两头大象的正中间**：
        
        
        
        ```XML
        <mirror>
            <id>alimaven</id>
            <name>aliyun maven</name>
            <url>http://maven.aliyun.com/nexus/content/groups/public/</url>
            <mirrorOf>central</mirrorOf>
        </mirror>
        ```
        

### 第四步：配置环境变量（让系统随时随地认识 mvn）

- **截图步骤**：`MAVEN_HOME` 为 maven 的解压目录，并将其 `bin` 目录加入 `PATH` 环境变量。
    
- **为什么要配**：不配的话，你只有进入到 maven 的 bin 目录下才能运行命令。配好后，你在电脑任意一个文件夹下打开终端，电脑都能秒懂你的指令。
    
- **实操动作**：
    
    1. 右键点击“此电脑” ➡️ 属性 ➡️ 高级系统设置 ➡️ 环境变量。
        
    2. 在**系统变量**里点击“新建”：
        
        - 变量名：`MAVEN_HOME`
            
        - 变量值：`D:\develop\apache-maven-3.9.4` （你解压的顶层绝对路径）
            
    3. 在系统变量里找到名为 **`Path`** 的变量，双击进去，点击“新建”，填入：
        
        Plaintext
        
        ```
        %MAVEN_HOME%\bin
        ```
        
    4. **一路点击“确定”保存退出。**
        

### 通关验证

怎么知道自己有没有配成功？

1. 按下快捷键 `Win + R`，输入 `cmd` 打开终端黑窗口。
    
2. 输入以下命令并回车：
    
    
    
    ```Bash
    mvn -v
    ```
    
3. 如果屏幕上啪地一下弹出了类似下面的版本信息，说明你的 Maven 已经在整台电脑里彻底彻底通关了！
    
    
    
    ```Plaintext
    Apache Maven 3.9.4 (xxxxxxxxxxxxxxxxxxxx)
    Maven home: D:\develop\apache-maven-3.9.4
    Java version: 17.0.x ...
    ```
    

环境大功告成！既然现在 Maven 软件已经在你的系统里安家落户了，接下来要不要直接**把它配置进我们上一节提到的 IDEA 全局设置里，让未来所有的后端工程直接原地起飞？**


---
---


## IDEA中“全局配置 Maven”和 “单独创建项目时勾选 Maven”




在 IntelliJ IDEA 中，**“全局配置 Maven”** 和 **“单独创建项目时勾选 Maven”**，本质上是 **“一劳永逸的底层法律”** 与 **“单次生效的即时契约”** 的区别。

这是绝大多数全栈开发新手最容易踩坑的地方——很多人明明在项目里改了本地仓库或阿里云镜像，结果新建一个项目，发现 Maven 又偷偷连到海外的中央仓库去蜗牛爬爬了。

为了让你彻底理清，我们直接用大白话和对比图把它们的底层区别、核心痛点以及最佳操作盘透。

### 一、 核心区别对比

我们可以通过下面这个简单的表格，一眼看出两者的管辖范围：

|对比项|IDEA 里 “勾选 Maven” 创建项目|全局配置独立 Maven|
|:--|:--|:--|
|**Maven 本体来源**|IDEA 自带的内嵌 Maven（版本固定，随 IDEA 更新）|你自己下载的独立 Maven（版本可控，可自由升级）|
|**配置文件 `settings.xml`**|用 IDEA 内嵌 Maven 的配置，或 IDEA 里单独设置的配置，**只对当前 IDEA 生效**|用你独立 Maven 里的 `conf/settings.xml`，**对电脑上所有 Maven 操作都生效**|
|**本地仓库位置**|默认可能是 IDEA 内嵌 Maven 的默认路径，或你在 IDEA 里单独设置的路径|由你全局 `settings.xml` 统一指定，所有项目的依赖都下载到同一个仓库|
|**命令行支持**|不支持！在 cmd / 终端里敲 `mvn` 会提示 “命令不存在”|支持！任意终端都能直接用 `mvn clean install` 等命令|
|**跨 IDE / 跨项目一致性**|换个 IDE（比如 Eclipse）、换个 IDEA 版本，配置 / 仓库路径可能变|所有 IDE、所有项目都用同一套配置，构建行为完全一致|
|**团队协作兼容性**|可能因为 IDEA 版本不同，Maven 版本 / 配置不一致，导致别人跑不起来|统一的 Maven 版本和配置，团队成员之间不会出现 “本地能跑，别人跑不了” 的问题|

### 二、 深度拆解：它们在 IDEA 里到底控制了什么？

无论你在哪个入口配置，IDEA 让你勾选和填写的核心选项都是以下三个：

1. **`Maven home path`（Maven 主路径）**：控制 IDEA 到底是用它自己内置的 Maven 核心，还是用你单独下载解压的标准 Maven 软件。
    
2. **`User settings file`（用户配置文件）**：**这步是灵魂！** 它指向你的 `settings.xml`。正是在这个文件里，我们配置了**阿里云镜像源（Mirror）**，以此绕过极慢的海外中央仓库。
    
3. **`Local repository`（本地仓库路径）**：控制从网上下载下来的几百个 jar 包，到底存放在你电脑盘的哪个具体文件夹里（默认在C盘，强烈建议全局改到其他盘）。


#### 没做“全局配置”导致的常见惨剧：

你在项目 A 里，辛辛苦苦把上面这三样都指到了你自定义的快速路径上。明天你为大创项目新建了一个项目 B，直接点击了创建。此时，IDEA 会因为没有“全局法律”的约束，**自动把项目 B 的这三项恢复成系统默认值**。

结果就是：项目 B 开始疯狂往你的 C 盘灌垃圾 jar 包，并且由于走的是海外官方源，下载速度慢到甚至直接报错断开。


### 三、举个场景例子，你就懂了

#### 场景 1：只在 IDEA 里勾选 Maven，不做全局配置

1. 你在 IDEA 里创建项目，勾选 Maven，用的是 IDEA 自带的 Maven 3.8.6。
2. 你在 IDEA 设置里，把本地仓库改成了 `D:\IDEA_repo`，加了阿里云镜像。
3. 你在 IDEA 里开发一切正常，但：
    
    - 你打开 cmd，敲 `mvn -v`，提示 “不是内部或外部命令”。
    - 你换了台电脑，装了新版 IDEA，自带 Maven 变成了 3.9.6，项目构建时可能出现兼容性问题。
    - 你用 Eclipse 打开同一个项目，它会用自己的内嵌 Maven，仓库路径是默认的 `C:\Users\xxx\.m2\repository`，依赖要重新下载一遍。
    

#### 场景 2：全局配置了独立 Maven

1. 你下载了 Maven 3.9.6，配置了环境变量，在 `settings.xml` 里把仓库设为 `D:\my_maven_repo`，加了阿里云镜像。
2. 你在 IDEA 里创建项目，勾选 Maven，然后在 IDEA 设置里，把 Maven 路径改成你自己的独立 Maven。
3. 你打开 cmd，敲 `mvn -v`，能看到 3.9.6 版本，敲 `mvn clean package` 也能正常打包。
4. 你换 IDEA 版本、换 Eclipse、甚至在服务器上部署，只要用同一个 Maven 版本和 `settings.xml`，构建行为完全一致，依赖也不用重复下载。



### 四、避坑指南：正确配置的“黄金终极姿势”

为了以后开发任何后端和 AI 业务时不再受环境的折磨，强烈建议你按照以下步骤，把**全局配置**死死锁住：

#### 第一步：关闭所有打开的项目

在 IDEA 中点击 `File ➡️ Close Project`，回到 IDEA 的欢迎大首页（或者是左侧有 Projects、Customize、Plugins 的那个初始界面）。

#### 第二步：切入全局配置入口

- 在欢迎页左下角点击 **`Customize`（自定义）**，然后点击 **`All settings...`（所有设置）**。
    
- _(或者在较新版本 IDEA 中：点击 `File ➡️ New Projects Setup ➡️ Settings for New Projects...`)_
    

#### 第三步：配置三驾马车

在弹出的设置菜单中，依次展开：`Build, Execution, Deployment（构建、执行、部署） ➡️ Build Tools（构建工具） ➡️ Maven`：

1. 将 **`Maven home path`** 改为你自己解压的 Maven 路径。
    
2. 勾选 **`User settings file`** 后面的 `Override（覆盖）` 复选框，精准指向你改好了阿里云镜像的那个 `settings.xml`。
    
3. 勾选 **`Local repository`** 后面的 `Override（覆盖）`，指向你的非 C 盘本地仓库文件夹。
    

点击 **`Apply` 和 `OK`** 保存。

### 终极结论

- **只在 IDEA 里做简单开发，不用命令行、不做团队协作**：只在 IDEA 里勾选 Maven，用自带的就行，省事儿。
- **要学 Maven 原理、做自动化构建、团队协作、跨 IDE 开发**：一定要全局配置独立 Maven，避免后续踩坑。


> 做了上述的**全局配置**后，以后你再点击 `New Project` 创建项目并勾选 Maven 时，新项目就会**直接继承**你这套完美的阿里云+非C盘本地仓库设定，再也不需要每次都点开设置检查一遍了！



---
---

## IDEA中Maven项目的创建导入



对于后端工程化来说，在 IDEA 里玩转 Maven 就像是在手机里玩转应用商店，下面我们一一拆解它们的底层逻辑和避坑细节。


### 一、 核心底座：什么是 Maven 坐标？


![[Java Web笔记-29.png]]

官方给出的定义是：**Maven 中的坐标是资源（jar）的唯一标识，通过该坐标可以唯一确定资源位置**。

你可以把世界上的每一个 Java 项目或 jar 包，都想象成寄快递时的**精确收货地址**。为了不送错，Maven 强行规定，任何一个项目都必须由“GAV”这三个标签组合出来的唯一身份证来定义：


```XML
<dependency>
    <groupId>cn.hutool</groupId>
    <artifactId>hutool-all</artifactId>
    <version>5.8.27</version>
</dependency>
```

#### 1. `groupId`（组织/公司名）

- **规范**：定义当前 Maven 项目隶属的组织名称。通常是**公司域名的反写**。
    
- **类比**：省份 + 城市（比如 `com.baidu`、`com.tencent` 或者黑马程序员的 `com.itheima`）。
    

#### 2. `artifactId`（项目/模块名）

- **规范**：定义当前 Maven 项目名称，通常也是**模块名称**（如 `order-service`、`goods-service`）。
    
- **类比**：小区名或具体的路号。
    

#### 3. `version`（版本号） 

- **规范**：定义当前项目的版本。截图最下方红字划出了企业级开发极其重要的两个后缀：
    
    - **`SNAPSHOT`（快照版）**：功能不稳定，尚处于**开发中**的版本。特点是允许覆盖更新。比如你和队友联调大创项目，你天天改代码，就可以顶着 `1.0-SNAPSHOT` 每天频繁发布，队友的 Maven 会自动拉取最新的改动。
        
    - **`RELEASE`（发行版）**：功能趋于稳定，当前更新停止，**可以用于正式发布**的版本。一旦发布，版本号不允许再次修改，确保线上生产环境绝对安全稳定。
        

### 二、 在 IDEA 中创建 Maven 项目

在现代开发中，我们不需要自己去手动建一堆文件夹，IntelliJ IDEA 已经完美集成了 Maven 的骨架。

1. **新建步骤**：在 IDEA 里点击 `File ➡️ New ➡️ Project`，选择 **Maven**（或者在新版 IDEA 里直接选择 New Project，在 Build System 里勾选 Maven）。
    
2. **填写身份证**：此时 IDEA 会死死卡住你，让你必须填入 `GroupId`、`ArtifactId` 和 `Version`。
    
3. **成果**：点击创建后，IDEA 会严格按照上一节讲过的“统一项目结构”，自动在磁盘上为你拔地而起生成 `src/main/java`、`src/main/resources` 等空文件夹，并附带一个干干净净的 `pom.xml` 根文件。
    

### 三、 依赖导入：在 `pom.xml` 中引入第三方 jar 包

当我们创建好项目后，如何去要别人写好的组件？这就是截图里右下角展示的 `<dependencies>` 标签的用法。

#### 极速导入三部曲：

1. **开辟空间**：在项目的 `pom.xml` 中，先写上一对大标签：
    
    ```XML
    <dependencies>
        </dependencies>
    ```
    
2. **塞入坐标**：把你需要的东西（比如 `hutool-all`）的 GAV 三要素完整拷贝进去。
    
3. **刷新激活（灵魂一步）**：这时候你会发现代码可能显示为红色。别慌！这是因为本地仓库还没有。**必须点击 IDEA 右上角弹出的那个小小的 Maven 刷新图标（或者在右侧 Maven 面板点击刷新圈圈）**。此时，IDEA 就会启动 Maven 引擎，顺着网线去远程仓库下载，等进度条走完变白，jar 包就百分之百成功挂载到项目里了！
    

### 四、 团队协作：如何“导入”已有的 Maven 项目？

在实际项目（比如大创项目的团队协作，或者下载老师给的样例工程）中，你从 GitHub 或 WinSCP 上拿到了队友写好的后端项目源码，**千万不要直接去双击里面的任何类文件**。

#### 正确的工程化导入姿势：

1. 打开 IDEA，点击 `File ➡️ Open`（或者在欢迎页点击 Open）。
    
2. **死理铁律**：在弹出的文件浏览器中，**不要去点项目的外层文件夹，而是要精准找到并选中该项目根目录下的那个 `pom.xml` 文件！**
    
3. 选择 `Open as Project`（作为项目打开）。
    
4. **等待同步**：IDEA 识别到 `pom.xml` 后，知道这是一个正规的 Maven 军规项目，会自动帮你在后台构建目录，并默默下载代码里声明的所有历史依赖。等右下角的进度条全部读取完毕，整个项目就能在你的电脑里完美跑起来！
    


---
---


## Maven常见问题和解决方法


### 一、 核心痛点 1：Maven 依赖包/插件下载失败（爆红线）

#### 报错表现

在 `pom.xml` 里引入一个依赖，或者在右侧 Maven 面板的 Plugins 目录里，**整行代码疯狂拉起红线**，提示：`Dependency 'xxx' not found` 或者 `Plugin 'xxx' not found`。

#### 报错根源

1. **网络抽风**：没有配置国内阿里云镜像，Maven 傻傻地去连海外中央仓库，结果超时断开，下载了一半的 jar 包直接损坏。
    
2. **IDEA 反应迟钝**：有时候网络已经好了，但 IDEA 内部的索引还没有刷新，依然固执地报错。
    

#### 解决方案（三步递进神功）

##### 第一步：检查并锁死国内阿里云镜像

去检查你的 Maven 安装目录下的 `conf/settings.xml`，确保在 `<mirrors>` 标签里老老实实配好了阿里云，这是飙速下载的底座：

```XML
<mirror>
    <id>alimaven</id>
    <name>aliyun maven</name>
    <url>https://maven.aliyun.com/repository/public</url>
    <mirrorOf>central</mirrorOf>
</mirror>
```

##### 第二步：IDEA 强行刷新（依赖一键复活）

在 IDEA 界面，点击右侧的 **`Maven`** 面板。不要只点那个普通的刷新圈圈，试试这套强力组合拳：

- 点击左上角的 **`Reload All Maven Projects`（重新加载所有项目）**。
    
- 如果还不动，右键点击项目根目录 ➡️ `Maven` ➡️ `Generate Sources and Update Folders`。
    

##### 第三步：终极绝招——人肉清理 `.lastUpdated` 损坏文件

如果还是爆红，说明你的本地仓库（`mvn_repo`）里已经下载了一半的垃圾文件。只要这个垃圾文件在，Maven 就会误以为已经下过了，永远不会重新下载。

1. 关闭 IDEA。
    
2. 找到你的本地仓库文件夹（如 `D:\develop\apache-maven-3.9.4\mvn_repo`）。
    
3. 在该文件夹的搜索框中输入：`.lastUpdated`。
    
4. **把搜出来的所有以 `.lastUpdated` 结尾的文件全部一把无情删除！**
    
5. 重新打开 IDEA，点击 Maven 刷新，你会看到进度条重新疯狂飙升，红线瞬间变白！
    

### 二、 核心痛点 2：Plugins（插件）加载失败，打包时报错

#### 报错表现

在右侧 Maven 的 `Plugins` 列表里，某个核心插件（如 `maven-compiler-plugin` 或 `spring-boot-maven-plugin`）显示红线，执行 `package` 时直接弹出一大堆英文报错。

#### 报错根源

Maven 项目在执行编译、打包、测试等生命周期时，底层全靠这些插件干活。如果这些插件本身的版本没有和你的 Maven 版本或者 JDK 版本对齐，或者插件包损坏，流水线就会直接瘫痪。

#### 解决方案

##### 方案 A：在 `pom.xml` 中强行锁死插件版本

不要让 Maven 去盲盒乱猜插件版本，直接在 `pom.xml` 的 `<build>` 标签里显式指定一个与你当前 Spring Boot 或 JDK 匹配的稳定版本：

```XML
<build>
    <plugins>
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-compiler-plugin</artifactId>
            <version>3.11.0</version>
            <configuration>
                <source>17</source> <target>17</target>
            </configuration>
        </plugin>
    </plugins>
</build>
```

##### 方案 B：强制清除插件缓存

在 IDEA 的终端（Terminal）里，直接手敲一行底层原生的强制下载命令，绕过 IDEA 的界面限制：

```Bash
mvn clean install -U
```

> **`-U` 的硬核含义**：强制 Maven 去远程仓库检查并更新所有的快照和插件，专门用来对付不听话的损坏插件。

### 三、 核心痛点 3：编译版本不一致（Java: 错误: 不支持发行版本 xxx）

#### 报错表现

点击运行或者编译项目时，下方控制台啪地弹出一行刺眼的红字：

`🔑 Java: 错误: 不支持发行版本 17` 或者 `🔑 Error:java: 无效的源发行版: 21`。

#### 报错根源

这是典型的“多头管理，版本打架”灾难。你电脑里可能装了 JDK 8、JDK 11 和 JDK 17，而 IDEA 里的各种配置指得乱七八糟。项目编译时，A 配置说是 JDK 17，B 配置说是 JDK 8，JVM 直接当场懵圈罢工。

#### 解决方案（全面地毯式对齐）

要根治这个问题，必须在 IDEA 里死死**卡统一以下 4 个地方的 JDK 版本**（以 JDK 17 为例）：

##### 1. 项目级别的 JDK（Project SDK）

点击 `File ➡️ Project Structure ➡️ Project`：

- 将 **`SDK`** 选为你的真实 JDK 17。
    
- 将 **`Language level`（语言级别）** 严格选为 `17 - SDK Default`。
    

##### 2. 模块级别的 JDK（Modules）

依然在 `Project Structure` 窗口中，切换到 `Modules`：

- 选中你的项目模块，确保其中的 **`Language level`** 同样是 `17`。
    

##### 3. Java 编译器的版本（Java Compiler）

点击 `File ➡️ Settings ➡️ Build, Execution, Deployment ➡️ Compiler ➡️ Java Compiler`：

- 在下方找到你的项目名称，将后面的 **`Target bytecode version`（目标字节码版本）** 手动改成 `17`。
    

##### 4. Maven 自身的配置文件硬锁定（一劳永逸）

为了防止 IDEA 每次刷新又把你改好的配置重置，最王道的做法是在 `pom.xml` 里用属性标签死死焊死：

```XML
<properties>
    <maven.compiler.source>17</maven.compiler.source>
    <maven.compiler.target>17</maven.compiler.target>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
</properties>
```



---
---

## 依赖管理


Maven 的依赖管理可以用一句话概括：**统一管理项目运行所需的 jar 包，并自动帮你打理它们之间错综复杂的“亲属关系”**。

在实际的工程开发（比如你以后要写的 Spring Boot 后端工程）中，依赖管理主要玩转三个核心点：**依赖配置、依赖传递、排除依赖**。我们直接来逐一盘透。

### 一、 依赖配置（让项目引入 jar 包）


![[Java Web笔记-32.png]]

**依赖，指当前项目运行所需要的 jar 包，一个项目中可以引入多个依赖**。

#### 极其标准的配置四步法：

1. **外层包裹**：在 `pom.xml` 中编写 `<dependencies>` 标签。
    
2. **精准点菜**：在内部使用 `<dependency>` 引入具体某个 jar 包的坐标。
    
3. **三要素对齐**：定义坐标的 `groupId`、`artifactId`、`version`。
    
4. **刷新激活**：点击 IDEA 右上角的小圈圈刷新按钮，让 Maven 顺着阿里云镜像去下载它。
    

```XML
<dependencies>
    <dependency>
        <groupId>org.springframework</groupId>
        <artifactId>spring-context</artifactId>
        <version>6.1.4</version>
    </dependency>
</dependencies>
```

> 💡 **绝招曝光**：写代码时不可能背得出这么多坐标怎么办？截图下方给出了终极解决方案：如果不知道依赖的坐标信息，可以直接去全球最大的公共索引库 **`https://mvnrepository.com/`** 搜索。在里面搜到想要的 jar 包后，直接一键复制 XML 坐标丢进 IDEA 即可。

### 二、 依赖传递（隐形的“买一送一”）

这是 Maven 最聪明的特性，也是初学者经常感到神奇的地方。

- **什么是依赖传递**：假设你的项目（`maven-project01`）引入了 `spring-context` 包。而 Spring 官方在写 `spring-context` 时，里面又用到了 `spring-beans`、`spring-core` 以及 `micrometer-observation` 等包。
    
- **Maven 的做法**：当你把 `spring-context` 的坐标配好后，Maven 会自动把那一大串间接关联的 jar 包**全部顺带下载下来并导入到你的项目中**。
    

#### 优点与痛点：

- **爽点**：你只需要配一个顶层包，底层几十个依赖自动配齐，免去了传统手动导包漏掉基础包导致的 `ClassNotFoundException` 惨剧。
    
- **痛点（大厂常遇到的坑）**：如果你的项目同时引入了 A 框架和 B 框架，而 A 框架偷偷带进来的某个日志包是 `1.0` 版本，B 框架偷偷带进来的是 `2.0` 版本，就会引发极其恶心的**依赖版本冲突**！
    

### 三、 排除依赖（老死不相往来）


![[Java Web笔记-31.png|697]]

当你发现依赖传递机制给你带进来了一些“不干净”或者你完全不想要的、产生冲突的间接依赖时，就轮到**排除依赖**。

- **核心定义**：排除依赖指**主动断开依赖的资源**。
    
- **铁律规范**：被排除的资源**无需指定版本（version）**！因为你都不要它了，把它名号报出来就行，Maven 会在当前依赖链路中自动把它切断。
    

#### 语法演练：

由于 `spring-context` 默认会带入 `io.micrometer:micrometer-observation`，但如果这个包和我们项目里的其他观测工具打架了，我们可以在它的 `<dependency>` 里面开辟一块 `<exclusions>` 净土：


```XML
<dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-context</artifactId>
    <version>6.1.4</version>
    
    <exclusions>
        <exclusion>
            <groupId>io.micrometer</groupId>
            <artifactId>micrometer-observation</artifactId>
        </exclusion>
    </exclusions>
</dependency>
```

加完这段代码并刷新后，右侧 Maven 树里的 `micrometer-observation` 就会瞬间消失，右侧那个画红叉的示意图完美展现了这个过程！

### 总结进阶

Maven 的依赖管理，就像是一套严密的“物资分配系统”：

1. 用 `<dependency>` **精准拉货**；
    
2. 靠**依赖传递**实现“全家桶一键送达”；
    
3. 用 `<exclusion>` 对冲突的物资**无情驱逐**。
    

这一块的逻辑掌握好后，后端最让人头疼的“包版本冲突”你就已经能解决大半了。


---
---


## 依赖范围


![[Java Web笔记-42.png]]

在实际的企业级后端开发中，你会发现一个很有意思的现象：

有些 jar 包（比如我们刚刚学的 JUnit 测试框架），我们**只希望在写测试和跑测试的时候用它**，一旦项目开发完了、要打包发布到服务器上线了，这个包就完全没用了。如果把它也打包进去，不仅会增加包的体积，还可能带来安全漏洞。

Maven 的 **`<scope>`（依赖范围）** 标签，就是为了解决这个“什么时候该用什么包”的精准控制问题。

### 一、 什么是依赖范围？（Classpath 的三维空间）

依赖范围的本质就是控制依赖的 jar 包，在 **哪些生命周期阶段、哪些 classpath 环境** 下可以被使用。

Maven 的代码世界被强行划分成了三个空间（Classpath）：

1. **编译环境（compile classpath）**：编写 `src/main/java` 主业务代码时，哪些包能用。
    
2. **测试环境（test classpath）**：编写和运行 `src/test/java` 测试代码时，哪些包能用。
    
3. **运行/打包环境（runtime classpath）**：项目最终被 `mvn package` 打包成 jar 包并部署到生产服务器运行时，哪些包必须在里面。
    

### 二、 4 大核心依赖范围详解

企业开发中最常用的 4 种 scope 如下：

|**scope 范围值**|**编译时**|**测试时**|**运行时(打包)**|**典型硬核代表包**|**纯正后端白话类比**|
|---|---|---|---|---|---|
|**`compile`** _(默认)_|✅|✅|✅|`logback` (日志)、`MyBatis`|**全职常驻主力**。从生到死，写代码、测代码、线上运行全都要它。|
|**`test`**|❌|✅|❌|`junit-jupiter` (测试框架)|**随军质检员**。只在测试时蹦出来，生产打包时无情抛弃。|
|**`provided`**|✅|✅|❌|`servlet-api`、`lombok`|**借鸡生蛋**。写代码时需要它撑场面，但运行环境（如 Tomcat）里自带了，所以不打包它。|
|**`runtime`**|❌|✅|✅|`mysql-connector-java` (驱动)|**幕后黑手**。写代码时用不着它（用的是标准接口），但一跑起来必须有它和数据库接头。|

### 三、 纯正企业级代码实战：`pom.xml` 中的范围控制

我们直接来看一段标准的 Spring Boot 后端项目的 `pom.xml` 配置，看看这四大金刚是如何在代码里各司其职的：

```XML
<dependencies>
    <dependency>
        <groupId>org.mybatis.spring.boot</groupId>
        <artifactId>mybatis-spring-boot-starter</artifactId>
        <version>3.0.3</version>
        </dependency>

    <dependency>
        <groupId>org.junit.jupiter</groupId>
        <artifactId>junit-jupiter-api</artifactId>
        <version>5.10.2</version>
        <scope>test</scope> </dependency>

    <dependency>
        <groupId>com.mysql</groupId>
        <artifactId>mysql-connector-j</artifactId>
        <version>8.3.0</version>
        <scope>runtime</scope> </dependency>

    <dependency>
        <groupId>org.projectlombok</groupId>
        <artifactId>lombok</artifactId>
        <version>1.18.30</version>
        <scope>provided</scope> </dependency>
</dependencies>
```

### 四、 深度复盘：如果把 JUnit 的 `<scope>test</scope>` 删掉会怎样？

我们来做个反向思考，如果把 JUnit 的 `test` 范围删掉，或者错写成了 `compile`：

1. **写业务代码时的乱象**：你在 `src/main/java` 的主业务类里写代码时，IDEA 的代码提示里会莫名其妙地跳出 JUnit 的 `@Test` 注解。如果不小心手滑点到了，就会把测试注解写进生产业务里，导致代码逻辑极其混乱。
    
2. **生产环境的“体积虚胖”**：当你在生产环境打包时，项目的 `.jar` 包里会死死塞进一堆 JUnit 以及它带出来的传递依赖包。这不仅浪费了服务器宝贵的磁盘和内存，更严重的是，测试框架里的某些漏洞可能会直接暴露在线上，给黑客留下可乘之机。
    


---
---


## 生命周期



如果说前面的“依赖管理”是帮项目搬运和打理物资，那么“生命周期”就是一套**工业化的流水线生产标准**。它规定了一个 Java 项目从清理旧产物、编译、测试，到最终打包、发布，必须经过哪些严密的步骤。


### 一、 核心底座：什么是 Maven 的生命周期？

![[Java Web笔记-33.png|697]]

Maven 的生命周期就是：**对所有的构建过程进行抽象和统一**。它包含了项目的清理、初始化、编译、测试、打包、集成测试、验证、部署和站点生成等几乎所有的构建步骤。

#### 核心设计精髓：同一生命周期内，命令“向前看”

Maven 独立出了三套相互独立的生命周期（`clean`、`default`、`site`）。在**同一套**生命周期中，存在一个极度硬核的隐藏死理：

> **“当我们在执行后期阶段的命令时，Maven 会自动先将它前面的所有阶段按顺序执行一遍！”**

**场景暴击**：如 `image_30e14a.jpg` 的例子，如果你想执行 `package`（打包），你根本不需要手动先点编译、再点测试。Maven 发现 `package` 排在后面，它会**自动且默默地**帮你把前面的 `compile`（编译） ➡️ `test`（测试）全部自动跑一遍，最后才安心执行打包。

### 二、 三套独立的生命周期与核心阶段

Maven 拥有三套**相互独立、互不干扰**的生命周期。我们重点死磕企业开发中最常用的前两套：


![[Java Web笔记-34.png|697]]

![[Java Web笔记-35.png]]

#### 1. `clean` 生命周期（打扫战场）

- **核心阶段**：`pre-clean` ➡️ **`clean`（最常用）** ➡️ `post-clean`。
    
- **作用**：专门负责清理上一次构建留下的残留垃圾（主要是删除磁盘上的 `target` 编译输出文件夹）。
    

#### 2. `default` 生命周期（核心构建流水线）

这是 Maven 最庞大、最核心的生命周期，负责把源码变成最终产品的全过程。虽然它包含了几十个细分阶段，但如 `image_30de07.jpg` 所示，我们只需死牢以下 5 个核心节点：

- **`compile`（编译）**：把 `src/main/java` 里的 `.java` 源码翻译成 JVM 认得的 `.class` 字节码，存放在 `target` 目录下。
    
- **`test`（测试）**：自动运行 `src/test/java` 下的单元测试代码（如 JUnit），确保新写的代码没把老业务改塌。
    
- **`package`（打包）**：把编译好的所有 `.class` 文件、配置文件打包成一个压缩包（Java 项目通常是 `.jar` 包，传统企业级项目是 `.war` 包）。
    
- **`install`（安装）**：**本地闭环的最后一步**。把刚刚打好的 `.jar` 包，直接**强行塞进你电脑的“本地仓库”里**。这样你电脑上的其他 Maven 项目就能通过坐标瞬间引用你写的这个包了。
    

### 实战演练：在 IDEA 里如何优雅触发它们？

在实际开发中，我们几乎不需要去黑窗口里手敲命令，IDEA 的右侧提供了一个极其形象的 **Maven 快捷控制面板**。

#### 1. 双击大法（最常用）

在右侧的 `Lifecycle` 列表里，你想执行哪个阶段，直接**双击**它即可（例如双击 `clean`，`target` 文件夹瞬间消失）。

#### 2. 企业级经典组合拳：`clean + package`

大厂里在做大创项目发布、或者往 Linux 服务器部署前端/后端前，老鸟们在控制面板或命令行里最喜欢打出一套组合拳：


```Plaintext
mvn clean package
```

- **在 IDEA 里怎么做**：如 `image_30e569.jpg` 所示，先单击选中 `clean`，按住键盘上的 `Ctrl` 键不放，再单击选中 `package`，然后点击上方绿色的运行小三角。
    
- **底层精妙之处**：它会先触发 `clean` 生命周期把历史旧垃圾彻底清理干净，防止旧缓存作怪；紧接着无缝切入 `default` 生命周期，一路执行编译、测试，最终吐出一个绝对干净、没有任何历史污染的全新 `.jar` 包！
    

### 总结

Maven 生命周期和命令的精髓在于：**它用一套固定的顺序和阶段，把原本凌乱的编译、测试、打包行为焊死在了一条流水线上。你只需要在流水线的终点（比如双击 install）招招手，前面的工序就会自动全套为您服务。**

---
---



## 单元测试——概述


![[Java Web笔记-36.png]]


![[Java Web笔记-37.png]]


在传统的开发习惯里，很多初学者写完一段业务逻辑（比如员工离职变更），验证代码正不正确的方法非常原始：要么在代码里疯狂写 `System.out.println()` 打印变量，要么就必须把整个大项目跑起来，去前端网页上人肉点击测试。

而 **Maven 的单元测试机制**，配合 Java 圈子里的工业级测试标准 **JUnit**，就是为了彻底干碎这种低效的排查方式。它让你**不用启动复杂的服务器、不用点开网页，就能以“原子”级别的精细度，秒级验证你的某一个核心方法到底对不对**。

既然这次咱们明确了**只聊概述、脱离琐碎代码**，那我们就对照你的核心截图，把单元测试的**底层本质、铁律规范以及四大标志性特征**彻底解密。

### 一、 什么是单元测试？



![[Java Web笔记-38.png]]



- **本质定义**：单元测试（Unit Testing）是指**对软件中的最小可测试单元进行检查和验证**。
    
- **什么是“最小单元”**：在 Java Web 后端世界里，这个最小单元**通常就是指一个具体的方法**（例如：计算员工考勤的方法、加密登录密码的方法、或者筛选数据过滤的方法）。
    
- **企业开发痛点**：一个大型企业级项目可能有上千个方法，它们错综复杂地编织在一起。如果等系统全部拼装完了再整体测试，一旦报错，你根本不知道到底是哪一行代码出了鬼。**单元测试就像是把每一个方法拆成零件，放在显微镜下单独通电测试，确保每一个基础零件都是 100% 完美的。**
    
- **Junit介绍**：JUnit 是**Java 语言最主流的单元测试框架**，专门用来给 Java 代码写**自动化测试用例**，快速验证代码逻辑是否正确，是 Java 开发必备工具。
	- 特点：
	    1. **轻量简单**：上手快，几行代码就能写一个测试用例
	    2. **自动化执行**：不用写 `main` 方法，一键运行所有测试
		3. **断言验证**：直接判断结果是否符合预期（比如：结果等于 5、对象不为空）
		4. **生态完善**：和 IDEA/Eclipse、Maven/Gradle、SpringBoot 无缝集成
		5. **主流版本**：**JUnit 5（Jupiter）** 是现在的标准（淘汰了老的 JUnit 4）
    - 作用：
		- 测试单个方法、类的逻辑是否正确
		- 改代码后快速回归，避免引入 bug
		- 配合项目构建工具，自动跑测试



### 二、 单元测试的“军规级”四大核心特征

在正规大厂和企业级工程中，合格的单元测试必须具备以下 4 个标志性特征（简称 **F.I.S.T. 原则**）：

#### 1. F - Fast（快） 

- **内涵**：测试代码的执行速度必须极其飞快。
    
- **大白话**：因为一个项目在 Maven 流水线构建时会伴随着几百上千个测试用例。如果一个测试要跑几分钟，那整个项目的打包部署就会慢成老牛拉车。优秀的单元测试应该在几毫秒或几秒内瞬间完成跑动。
    

#### 2. I - Independent（独立） 

- **内涵**：各个测试用例之间不能相互调用，也不能存在先后执行顺序的依赖。
    
- **大白话**：每一个测试方法都必须是“孤独的硬汉”。不能说“必须先执行完测试 A 产生数据，测试 B 才能跑成功”。如果 A 失败了导致 B、C、D 跟着连环雪崩，这就失去了排查 Bug 的意义。
    

#### 3. R - Repeatable（可重复） 

- **内涵**：无论在什么环境、执行多少次，测试的结果都必须是绝对稳定且一致的。
    
- **大白话**：这行测试代码在你本地 Windows 跑是绿色的，拿到服务器 Linux 上跑、或者明天早上跑，结果也必须一模一样。不能受到外部时间、网络波动的随机干扰。
    

#### 4. S - Self-Validating（自我验证） 

- **内涵**：测试结果必须能自动输出，人肉不需要去盯着控制台看日志。
    
- **大白话**：测试完后，它自己会利落地告诉框架它是“成功”还是“失败”。这就是我们在 IDEA 里最喜欢看到的“绿条（Passed）”与“红条（Failed）”。如果是红条，它会精确报告期望值是多少、实际值又是多少。
    

### 三、 规范铁律：Maven 规定的“测试居住证”

![[Java Web笔记-39.png]]

我们在前面学过，Maven 之所以能“统一项目结构”，是因为它对文件夹的分工极具控制欲。

1. **专属领地**：所有的测试代码，**永远、绝对只能写在 `src/test/java` 目录下！** 任何写在 `src/main/java` 里的测试代码，在打包时都会被视为非法噪音。
    
2. **名称潜规则**：为了让 Maven 的自动化引擎一眼认出这是个测试类，测试类的命名**通常必须以 `Test` 结尾**（例如 `EmployeeServiceTest`）。
    
3. **生命周期联动**：正如上一节所学，当你在右侧 Maven 面板双击执行 `test` 或者 `package` 命令时，**Maven 会启动底层插件，自动去 `src/test/java` 里地毯式搜寻所有带 `@Test` 标志的方法并全部疯狂跑一遍**。如果有任何一个方法的自我验证弹出了“红条”，Maven 就会立刻拉响警报、中断整条流水线，**拒绝为你打包！** 从而死死守住线上的安全底线。
    


| **规范维度**     | **核心军规要求**                  | **纯正全栈白话解读**                                                    |
| ------------ | --------------------------- | --------------------------------------------------------------- |
| **1. 编写位置**  | 必须放在 `src/test/java` 目录下。   | 测试代码是“质检员”，永远不能和 `src/main/java` 的正规军混住，打包时它会自动被隔离。             |
| **2. 类名规范**  | 测试类的命名：**`目标业务类名 + Test`**。 | 如果你测的是 `EmployeeService`，测试类必须叫 `EmployeeServiceTest`。方便别人一眼对齐。 |
| **3. 方法名规范** | 测试方法的命名：**`test + 业务方法名`**。 | 测 `login` 方法，测试方法就叫 `testLogin`。严禁出现 `test1`、`aaa` 等毫无意义的命名。    |



### 概述总结

> 单元测试就是后端的**质量检测仪**。它以 **快、独立、可重复、自动化** 的核心姿势，常驻在 Maven 规范的 `src/test/java` 领地里。它用严苛的红绿条机制，确保你的项目在被交付打包成 `.jar` 之前，内部的每一个核心函数都没有暗藏内伤。

---
---

## 单元测试——断言



在上一节，我们聊到合格的单元测试必须具备 **“Self-Validating（自我验证）”** 的特征，测试框架得自己利落地分清黑白，吐出“绿条”或“红条”。

而实现自我验证的**绝对底层核心、唯一判官，就是——断言（Assertion）**！

### 一、 核心概念：什么是断言？


- **本质定义**：断言（Assertion）是**单元测试的核心组成部分，用于判定测试结果是否符合预期**。
    
- **白话干货**：断言就像是代码世界里的“军令状”。你作为程序员，预期这个方法执行完应该输出 $100$。那你就下一道断言：“如果实际结果是 $100$，就通关亮绿灯；如果哪怕变成 $99.9$，就立刻报错拉响红灯，证明业务逻辑写塌了！”
    
- **核心语法**：在主流的 JUnit 5 测试框架中，断言功能由 `org.junit.jupiter.api.Assertions` 类全权提供，里面全是一系列静态方法。
    

---

### 二、 常用断言方法大盘点

![[Java Web笔记-40.png]]



企业开发中最常用的断言有以下 4 种：

|**静态方法名**|**判别逻辑**|**适用场景**|
|---|---|---|
|**`assertEquals(expected, actual)`**|预期值 == 实际值|检查计算结果、状态码、字符串是否完全对等。|
|**`assertNotEquals(unexpected, actual)`**|预期值 != 实际值|确保修改后的敏感数据（如加密后的密码）绝不能和原密码相同。|
|**`assertTrue(actual)`**|实际值 == `true`|验证某个布尔判断（如 `isValid` 校验）必须通过。|
|**`assertFalse(actual)`**|实际值 == `false`|验证某些非法操作（如拉黑用户的状态）必须为假。|

---

### 三、 纯正企业级源码实战：从业务到测试

为了让你彻底看清它是怎么在 Maven 规范中跑起来的，我们直接分别编写一段**正规的业务代码**和一段**对应的单元测试断言代码**。

#### 1. 业务逻辑代码（存放在 `src/main/java` 中）

假设我们在 tlias 系统里写了一个负责**员工薪资计算与折扣发放**的业务组件：

```Java
package com.tlias.service;

public class SalaryCalculator {

    /**
     * 根据工龄计算最终年终奖系数
     * 法定天条：工龄大于等于 3 年，系数为 2.0；否则系数为 1.0
     */
    public double calculateBonusFactor(int workingYears) {
        if (workingYears >= 3) {
            return 2.0;
        }
        return 1.0;
    }

    /**
     * 判断输入的员工邮箱格式是否合法
     */
    public boolean isValidEmail(String email) {
        if (email == null) {
            return false;
        }
        // 极其简陋的判断：包含 @ 符号即视为合法
        return email.contains("@");
    }
}
```

#### 2. 单元测试断言代码（存放在 `src/test/java` 中） 

现在，我们用 JUnit 5 搭配刚刚学到的断言静态方法，对上述两个函数进行全方位无死角的“硬核体检”：

```Java
package com.tlias.service;

// 🌟 核心死理：必须手动静态导入 JUnit 5 的断言全家桶方法
import static org.junit.jupiter.api.Assertions.*;

import org.junit.jupiter.api.Test;

public class SalaryCalculatorTest {

    // 实例化我们要测试的真实业务目标
    private final SalaryCalculator calculator = new SalaryCalculator();

    @Test
    public void testCalculateBonusFactor() {
        System.out.println("【测试动作开启】：正在体检年终奖系数核心算法...");

        // 场景 A：老员工，工龄 5 年，预期系数应该是 2.0
        double actualFactor1 = calculator.calculateBonusFactor(5);
        // 断言：assertEquals( 期望值, 实际值 )
        assertEquals(2.0, actualFactor1, "🚨 天条警告：工龄满5年的老员工年终奖系数计算错误！");

        // 场景 B：新员工，工龄 1 年，预期系数绝对【不能是】 2.0
        double actualFactor2 = calculator.calculateBonusFactor(1);
        // 断言：assertNotEquals( 不应当出现的值, 实际值 )
        assertNotEquals(2.0, actualFactor2, "🚨 天条警告：新员工年终奖系数竟然算成了老员工标准！");
    }

    @Test
    public void testEmailValidation() {
        System.out.println("【测试动作开启】：正在体检邮箱合法性校验...");

        // 场景 A：输入正确的邮箱，结果应该为 true
        boolean result1 = calculator.isValidEmail("admin@tlias.com");
        // 断言：assertTrue( 结果必须为真 )
        assertTrue(result1, "🚨 错误：合法的邮箱地址未能通过校验！");

        // 场景 B：输入错误的邮箱，结果应该为 false
        boolean result2 = calculator.isValidEmail("wrong-email-format");
        // 断言：assertFalse( 结果必须为假 )
        assertFalse(result2, "🚨 错误：非法格式的邮箱竟然蒙混过关了！");
    }
}
```

---

### 四、 运行后的两种命运（红与绿）

当你在 IDEA 里右键点击这个测试类，选择 **`Run 'SalaryCalculatorTest'`** 运行时：

#### 🟢 命运一：亮起完美的“绿条”（Passed）

如果你的代码完美无误，控制台会弹出一个极为舒适的**绿色对勾条**，提示 `Tests passed: 2`。这意味着所有的断言判断全部顺利通过，项目质量绝对安全。

#### 🔴 命运二：惊心动魄的“红条”（Failed）

假设你不小心把业务代码里的 `workingYears >= 3` 手误写成了 `workingYears > 3`。

那么当测试运行到 `calculator.calculateBonusFactor(3)` 时，实际算出了 `1.0`，但你的断言硬性要求 `assertEquals(2.0, ...)`。

此时，IDEA 会瞬间拉响**大红色的高能警报**，控制台会详细输出错误报告：

```Plaintext
Expected : 2.0
Actual   : 1.0
Message  : 🚨 天条警告：工龄满3年的员工年终奖系数计算错误！
```

这就是断言的终极威力！它不需要你用肉眼去看、去猜，它会在流水线上死死卡住每一个方法的运行界限。

---

### 思考：测试运行不报错不就代表代码没问题吗，还要断言干嘛


这个问题一针见血，直碎了单元测试最底层的秘密！

很多初学者都会有这个直觉：**“我点一下运行，IDEA 只要没抛出红色的报错异常，最后条子变绿了，不就说明我的代码成功跑通了吗？为什么非要多此一举去写断言？”**

其实，这里的“成功”藏着一个巨大的思维陷阱：**IDEA 亮绿灯，只代表代码“顺利执行完了”，并不代表它“算出的结果是对的”。**

如果不写断言，你的单元测试将彻底失去**灵魂**。我们用一个最典型的企业级车祸现场来拆解这个底层逻辑。

#### 一、 没有断言的“假成功”（自欺欺人）

假设你在开发系统时，写了一个核心的**计算员工应发工资**的方法。结果因为熬夜犯困，不小心把加法写成了减法：

##### 1. 悲剧的业务代码（Bug 潜伏）

```Java
public class SalaryService {
    /**
     * 核心业务：计算总薪资 = 基本工资 + 奖金
     */
    public double calculateTotalSalary(double base, double bonus) {
        // 🚨 笔误！把 “+” 错写成了 “-”
        return base - bonus; 
    }
}
```

##### 2. 不写断言的测试代码（自嗨式绿条）

现在你来对它进行单元测试。如果你不写断言，只是把方法调用一下，打印个日志：

```Java
import org.junit.jupiter.api.Test;

public class SalaryServiceTest {
    private final SalaryService service = new SalaryService();

    @Test
    public void testCalculateTotalSalary() {
        // 调用方法，基本工资 10000，奖金 3000
        double result = service.calculateTotalSalary(10000, 3000);
        
        // 打印看看
        System.out.println("计算出的总薪资是: " + result); 
        // 屏幕上会输出：7000.0
    }
}
```

##### 此时会发生什么？

当你点击运行这个测试时，IDEA 页面会弹出一个**无比完美的绿色对勾（Passed）**！

- **为什么是绿色？** 因为对 JVM 来说，`10000 - 3000 = 7000` 是一个完全合法的数学运算，它既没有让内存溢出，也没有抛出空指针异常（NullPointerException），代码顺畅地从头走到了尾。
    
- **代价是什么？** 如果你看到绿条就以为项目成功了，直接打包部署上线。到了发工资那天，员工就会提着刀来找你——明明人家应得 13000，系统却因为你的 Bug 算成了 7000！
    

> **核心结论一：**
> 
> 框架默认的“绿条”，仅仅代表你的代码**“没有崩溃”**（No Exception），却无法保证你的**“业务逻辑正确”**。

#### 二、 加上断言：让测试具备“正邪判别力”

断言的本质，就是把“程序员脑子里的预期”写成白纸黑字的法律契约，强行加给测试框架，让它不仅检查代码崩不崩，更检查算出来的数对不对。

我们把上面的测试代码加上断言：

```Java
import static org.junit.jupiter.api.Assertions.*;
import org.junit.jupiter.api.Test;

public class SalaryServiceTest {
    private final SalaryService service = new SalaryService();

    @Test
    public void testCalculateTotalSalary() {
        // 1. 执行业务
        double result = service.calculateTotalSalary(10000, 3000);
        
        // 2. 施加断言：我以人格担保，10000 + 3000 必须等于 13000！
        // assertEquals( 预期值, 实际算出来的值 )
        assertEquals(13000.0, result, "🚨 严重生产事故：员工薪资计算逻辑有误！");
    }
}
```

##### 此时运行的结果：

这时候，因为你的业务代码算出来的是 `7000.0`，而断言死死卡住必须是 `13000.0`。

即使你的代码运行得再流畅，JUnit 也会无情地**一巴掌把绿条拍变红**！

Plaintext

```
❌ Test failed: testCalculateTotalSalary()
   Expected : 13000.0
   Actual   : 7000.0
   Message  : 🚨 严重生产事故：员工薪资计算逻辑有误！
```

看着这个红条，你就能在发布上线前，精准地在本地把那个 `base - bonus` 改回 `base + bonus`。修改后再次运行，断言成功，这时亮起的**绿条**，才是**真正代表逻辑无误的“真成功”**。

#### 三、 为什么大厂必须强推断言？（自动化构建的刚需）

你可能会想：“那我调用完方法，不写断言，自己用眼睛盯着控制台打印出的 `7000.0`，不也能看出算错了吗？”

人脑肉眼排查，在小项目里看似可行，但到了**自动化工程化**时代就会彻底瘫痪：

1. **无法肉眼应付海量测试**：一个企业级项目有 2000 个测试用例。如果用 `System.out.println` 打印，控制台会刷出几十万行日志。没有任何一个程序员能用肉眼在几万行日志里挑出哪个数据算错了。
    
2. **为了配合 Maven 流水线自动化**：我们在上一节学过，项目在打包部署前会自动跑 `mvn test`。服务器在云端自动编译和打包时，**可没有程序员坐在屏幕前盯着看控制台打印的内容**。
    

服务器全靠**断言的红绿信号**来识别项目质量：

- 所有的断言都通过（全绿） ➡️ 允许打包上线。
    
- 只要有任何一个断言失败（报红） ➡️ 流水线立刻熔断，拒绝发布，打回重写。
    


> - **不加断言的绿条**：只代表代码 **“活着跑完了”** ，不代表 **“算对数了”** 。
>     
> - **加了断言的绿条**：代表代码 **“既活着跑完了，且结果百分之百符合预期”** 。
>     
> - **断言的价值**：干碎人肉眼看日志的低效方式，实现全自动的、逻辑级别的代码质量防御。


---
---

## 单元测试——Junit常见注解



在实际编写企业级单元测试时，我们经常会遇到这样的**刚需场景**：

- 每次测试开始前，必须先自动连接数据库或初始化一套 mock 数据。
    
- 整个测试类运行结束了，必须统一关闭文件流或断开 Redis 连接。
    
- 某个测试方法由于后端接口还在调整，暂时需要跳过，不参与打包构建。
    

如果全靠人肉去每个方法里复制粘贴这些前置/后置代码，不仅臃肿，还容易漏掉。**JUnit 的这一组生命周期注解，就是为了让你像写配置一样，优雅地控制测试方法的执行顺序。**

### 一、 JUnit 5 常用注解核心盘点


![[Java Web笔记-41.png]]


JUnit 5 最核心的 5 个注解分工如下：

|**注解名**|**执行时机与频次**|**纯正后端白话类比**|**核心用途**|
|---|---|---|---|
|**`@Test`**|被修饰的方法是一个**测试方法**。|**核心业务**|实际跑断言、测逻辑的地方。|
|**`@BeforeEach`**|在**每一个** `@Test` 方法执行**之前**都会执行一次。|**游戏每局前的“加载”**|重新初始化变量、清空临时数据。|
|**`@AfterEach`**|在**每一个** `@Test` 方法执行**之后**都会执行一次。|**游戏每局后的“清算”**|擦干净战场，还原测试现场。|
|**`@BeforeAll`**|在当前测试类的**所有**测试方法执行**之前**只执行一次。|**开机启动**|耗时的大型初始化（如开数据库连接池）。|
|**`@AfterAll`**|在当前测试类的**所有**测试方法执行**之后**只执行一次。|**关机断电**|彻底释放大资源（如关闭数据库连接）。|

> 🚨 **全栈避坑天条（初学者必踩）**：
> 
> **`@BeforeAll` 和 `@AfterAll` 修饰的方法，必须声明为静态方法（`static`）！** 因为它们是在测试类对象还没被实例化之前/之后触发的，必须由类直接调用。

### 二、 工业级源码实战：用生命周期接管测试

为了让你肉眼看清它们的执行先后顺序，我们直接模拟一个正规的**企业级“员工缓存服务”体检测试类**。

这段代码严格遵循 Maven 的 `src/test/java` 规范，把这 5 个注解编织在同一个类里：

```Java
package com.tlias.service;

import static org.junit.jupiter.api.Assertions.*;

// 🌟 核心死理：全部引入 JUnit 5 (Jupiter) 体系的注解
import org.junit.jupiter.api.AfterAll;
import org.junit.jupiter.api.AfterEach;
import org.junit.jupiter.api.BeforeAll;
import org.junit.jupiter.api.BeforeEach;
import org.junit.jupiter.api.Test;

public class EmployeeCacheTest {

    // ==================== 1. 全局生命周期（只跑一次） ====================

    @BeforeAll
    public static void initGlobalResource() {
        // 🚨 必须是 static 静态方法！
        System.out.println(">>> 🚀 【@BeforeAll】全局初始化：成功连接到外部 Redis 缓存服务器（只此一次）");
    }

    @AfterAll
    public static void clearGlobalResource() {
        // 🚨 必须是 static 静态方法！
        System.out.println(">>> 🛑 【@AfterAll】全局销毁：断开 Redis 服务器连接，释放内存资源（只此一次）");
    }

    // ==================== 2. 方法级生命周期（每局必跑） ====================

    @BeforeEach
    public void setUp() {
        System.out.println("  -> 🟢 【@BeforeEach】准备工作：为当前测试用例注入全新的 Mock 员工数据");
    }

    @AfterEach
    public void tearDown() {
        System.out.println("  -> 🧹 【@AfterEach】清理现场：清空本轮测试产生的临时脏数据");
        System.out.println("----------------------------------------------------------------");
    }

    // ==================== 3. 真实的测试核心核心业务 ====================

    @Test
    public void testCacheSave() {
        System.out.println("    [ ⚡ 执行测试 1 ] 正在验证：员工数据能否成功写入缓存...");
        String cacheData = "Emp_001_Data";
        
        // 施加断言
        assertNotNull(cacheData, "缓存数据不能为 null！");
    }

    @Test
    public void testCacheDelete() {
        System.out.println("    [ ⚡ 执行测试 2 ] 正在验证：删除缓存后数据是否彻底清空...");
        boolean isDeleted = true;
        
        // 施加断言
        assertTrue(isDeleted, "删除缓存逻辑未返回成功状态！");
    }
}
```

### 三、 运行后的控制台：肉眼捕捉生命周期交响乐

当你在 IDEA 里右键运行这个测试类时，控制台输出的日志会把这张生命周期图的执行流完美复现出来：

Plaintext

```
>>> 🚀 【@BeforeAll】全局初始化：成功连接到外部 Redis 缓存服务器（只此一次）

  -> 🟢 【@BeforeEach】准备工作：为当前测试用例注入全新的 Mock 员工数据
    [ ⚡ 执行测试 1 ] 正在验证：员工数据能否成功写入缓存...
  -> 🧹 【@AfterEach】清理现场：清空本轮测试产生的临时脏数据
----------------------------------------------------------------
  -> 🟢 【@BeforeEach】准备工作：为当前测试用例注入全新的 Mock 员工数据
    [ ⚡ 执行测试 2 ] 正在验证：删除缓存后数据是否彻底清空...
  -> 🧹 【@AfterEach】清理现场：清空本轮测试产生的临时脏数据
----------------------------------------------------------------

>>> 🛑 【@AfterAll】全局销毁：断开 Redis 服务器连接，释放内存资源（只此一次）
```

#### 深度复盘这个心跳轨迹：

- 类一加载，`@BeforeAll` 一马当先，帮我们把最重的网络连接架设好。
    
- 只要遇到一个带有 `@Test` 的方法，`@BeforeEach` 和 `@AfterEach` 就会像贴身保镖一样，一前一后把它夹在中间精心伺候。哪怕类里有 100 个测试方法，这对保镖就会反复执行 100 次。
    
- 所有任务圆满完成，`@AfterAll` 出来收尾，优雅关灯拔电源。
    
---
---

## 单元测试——企业开发规范



企业开发中关于单元测试的两个殿堂级指标：**单元测试覆盖率**，以及大厂里铁律一般的**核心业务三大红线规范**。

写出能跑通的测试叫“初学者”，能写出符合这套量化指标的测试，才叫“合格的后端工程师”。我们这就带上规范的代码示例，把这套企业级红线彻底盘透。

![[Java Web笔记-43.png]]


### 一、 核心量化指标：单元测试覆盖率（Test Coverage）

企业衡量测试质量不靠嘴说，全靠数据说话：

- **业务类覆盖率 ➡️ $\ge 70\%$**：
    
    一个项目里如果写了 $100$ 个业务类（Service），其中至少有 $70$ 个类必须有对应的测试类去测它。
    
- **方法覆盖率 ➡️ $\ge 70\%$**：
    
    在被测试的类里面，如果写了 $10$ 个核心业务方法，至少要写 $7$ 个测试方法。
    
- **行覆盖率 ➡️ $\ge 70\%$**：
    
    **这是最硬核、也最难偷懒的指标。** 它指的是你写的方法里，假设有 $100$ 行代码，你的测试用例在跑的时候，必须实际踩过其中的 $70$ 行以上。这意味着你不能只测正向流程，**必须写多个测试用例去踩那些 `if-else` 的异常分支**，否则行覆盖率绝对达不到大厂红线。
    

### 二、 核心业务三大红线规范（不踩雷天条）


#### 1. 规范一：不能存在空测试方法 ❌

- **大白话**：为了应付大厂的覆盖率检查，有些“聪明”的程序员会写一个带 `@Test` 的方法，但里面**什么代码都不写（或者只有一行空注释）**。
    
- **企业痛点**：由于它没报错，IDEA 跑完会亮绿灯，且这个类会被计入“已测试”的数字里。但它没有实质的断言逻辑，根本测不出任何 Bug。规范对此直接一刀切：**禁止一切空测试方法，发现即扣绩效**。
    

#### 2. 规范二：测试方法中不能使用 `System.out.println` 输出 ❌

- **大白话**：严禁在测试里用控制台打印去人肉看结果。
    
- **企业痛点**：正如我们之前聊过的，自动化运维（CI/CD 流水线）在云端打包时，根本没人去盯着屏幕看你打印了啥。**所有结果判别必须且只能交给 `assertEquals` / `assertTrue` 等断言（Assertion）来自动判定**。
    

#### 3. 规范三：测试方法中不能包含 `try-catch` ❌

- **大白话**：测试代码里绝对不能自己去吞掉异常。
    
- **企业痛点**：如果你的业务代码真的出了 Bug 抛出了异常，测试方法里如果加了 `try-catch` 把异常给消化了，JUnit 就会误以为这个方法“顺利走完了”，从而**吐出一个具有欺骗性的“假绿条”**。大厂规范要求：**有异常就必须让它直接往外抛，抛出来 JUnit 才能精准抓到并报红，及时拦截有问题的代码**。
    

### 三、 🛠️ 纯正企业级源码实战：从“违规”到“完美规范”

我们同样模拟 tlias 系统里的**员工离职（`leave`）业务**。

#### 1. 业务代码（存放在 `src/main/java` 目录）


```Java
package com.tlias.service;

public class EmpService {
    /**
     * 核心业务：员工离职
     * 规则：1号超级管理员绝对不允许离职，否则抛出异常
     */
    public boolean leave(Long empId) {
        if (empId == 1L) {
            throw new IllegalArgumentException("🚨 警报：超级管理员不可离职！");
        }
        return true; // 正常离职成功
    }
}
```

### 2. ❌ 违规的测试写法

```Java
package com.tlias.service;

import org.junit.jupiter.api.Test;

public class EmpServiceTest {
    private final EmpService empService = new EmpService();

    @Test
    public void testLeave_Empty() {
        // ❌ 违规 1：空测试方法！为了刷覆盖率而写，毫无意义。
    }

    @Test
    public void testLeave_Normal() {
        boolean result = empService.leave(2L);
        // ❌ 违规 2：使用 System.out 打印！没有使用断言自动自我验证。
        System.out.println("离职结果是: " + result); 
    }

    @Test
    public void testLeave_Exception() {
        try {
            empService.leave(1L);
        } catch (Exception e) {
            // ❌ 违规 3：使用了 try-catch！把异常吞掉了，导致本来该报错的测试结果依然亮绿灯！
            System.out.println("抓到了异常");
        }
    }
}
```

#### 3. 🟢 100% 符合大厂行覆盖率与红线规范的教科书级写法 

下面这个类，不仅**命名规范**，而且**丢弃了打印、丢弃了 try-catch**，甚至通过多场景测试让代码的**行覆盖率达到了 100%**：


```Java
package com.tlias.service;

import static org.junit.jupiter.api.Assertions.*;
import org.junit.jupiter.api.Test;

/**
 * 严格对齐企业开发规范
 */
public class EmpServiceTest {

    private final EmpService empService = new EmpService();

    /**
     * 场景一：测试正常离职流程
     * 规范：使用断言代替打印，无 try-catch
     */
    @Test
    public void testLeaveNormal() {
        boolean result = empService.leave(1024L);
        // ✨ 正确做法：交给断言自动验证，无需肉眼看控制台
        assertTrue(result, "规范异常：正常员工离职应当返回 true！");
    }

    /**
     * 场景二：测试超级管理员离职触发异常的流程
     * 规范：不使用 try-catch，利用 JUnit 5 专用的 assertThrows 优雅断言异常
     */
    @Test
    public void testLeaveAdminException() {
        // ✨ 正确做法：断言“这行代码必须抛出 IllegalArgumentException 异常”
        // 如果它没抛出异常，断言就会报错，完美踩中异常分支，行覆盖率飙升
        assertThrows(IllegalArgumentException.class, () -> {
            empService.leave(1L); // 传入超级管理员ID
        }, "规范异常：超级管理员离职时系统竟然没有拦截并抛出异常！");
    }
}
```

---
---



# HTTP



## 概述

![[Java Web笔记-47.png]]

### 一、 HTTP协议的本质概念

**HTTP（Hyper Text Transfer Protocol，超文本传输协议）**，它是互联网通信的基石。

- **一句话总结**：它规定了**浏览器（客户端）** 和**服务器（后端）** 之间数据传输的**统一规则**。
    
- **为什么叫超文本？**：因为早期的网络只能传普通文本，而 HTTP 协议允许传输比普通文本更丰富的“超文本”——比如 HTML 网页、图片、音频、视频，以及如今前后端分离最核心的 **JSON 数据**。
    

### 二、 必须吃透的 HTTP 三大核心特点

HTTP 协议有三个最重要的底层特征。作为后端开发，未来的很多架构设计（比如 Cookie、Session、JWT Token）都是为了应对这些特征而衍生出来的：

#### 1. 基于 TCP 协议：面向连接，安全

- **含义**：HTTP 只是一个应用层协议，它自己不负责怎么把数据安全送达。它的底层是建立在 **TCP 协议**（传输层）之上的。
    
- **底层逻辑**：在发送 HTTP 请求之前，客户端和服务器必须先经历经典的 **“三次握手”** 建立起一条可靠的、安全的双向连接通路。通路建好了，HTTP 协议的数据包才能在上面安心传输。
    

#### 2. 基于请求-响应模型：一次请求对应一次响应

- **含义**：这是一个典型的“一问一答”或“不请不来”的模型。
    
- **底层逻辑**：通信**必须由客户端（浏览器）主动发起（请求）**，服务器收到后进行处理并给回结果（响应）。
    
- **开发局限**：服务器是永远无法主动“叫醒”浏览器或者向它推送数据的。如果前端不发请求，后端写的 `HelloController` 代码就只能老老实实地在内存里等。
    

#### 3. 无状态的协议（Stateless）

- **含义**：协议对于事务处理**没有记忆能力**。在 HTTP 眼里，每一次请求-响应都是完全独立、彼此陌生的。
    
- **利弊权衡**：
    
    - **缺点：** 多次请求之间**不能共享数据**。比如你在购物网站上，第一步请求把商品“加入购物车”，第二步请求去“结算”，由于 HTTP 无状态，第二步的请求过来时，服务器根本不记得你是谁，也不知道你刚才加了什么。
        
    - **优点：** 结构简单，不需要维护复杂的上下文状态，因此**传输速度极快**，服务器的内存负担很小。
        

### 三、 承前启后：它与你写的 Spring Boot 是怎么结合的？

你在浏览器里敲下：

`http://localhost:8080/hello?name=Heima`

![[Java Web笔记-53.png]]

1. **网络连接**：浏览器顺着 `http://localhost:8080` 通过 **TCP 协议** 找到了你用 `main` 方法跑起来的内嵌 Tomcat 服务器。
    
2. **发起请求**：浏览器根据 **HTTP 协议的规则**，将请求封装好发送给后端。
    
3. **后端处理**：Spring Boot 接收并解析这个 HTTP 请求，把参数绑定给 `hello(String name)` 方法，执行内部逻辑。
    
4. **给出响应**：方法返回的 `"Hello Heima ~ "`，被 Spring 再次以 **HTTP 协议的规则** 打包，作为“响应数据”回传给浏览器，网页这才显示出文字。
    

---
---


## 请求协议



### 模块一：解剖 HTTP 请求数据格式

无论是浏览器点回车，还是前端发异步请求，送上门的请求数据包必定由**三部分**组成。我们来逐一拆解：

![[Java Web笔记-48.png]]

#### 1. 请求行（Request Line）—— 数据的“排头兵”

位于请求数据的**第一行**。它交代了三个最基本的信息：

> 示例：`GET /brand/findAll?name=OPPO&status=1 HTTP/1.1`

- **请求方式**：告诉后端动作类型（如 `GET` 或 `POST`）。
    
- **资源路径**：请求服务器的哪个接口（`/brand/findAll`），后面可能携带问号 `?` 拼接的参数。
    
- **协议版本**：通常是固定的 `HTTP/1.1`。
    

##### 面试高频：GET 和 POST 请求方式的核心区别

- **GET**：请求参数**直接挂在请求行的 URL 后面**。由于浏览器地址栏有长度限制，所以 GET 请求传递的数据大小有限制，且参数暴露在地址栏，不适合传密码等敏感信息。没有“请求体”。
    
- **POST**：请求参数**存放在请求体（Body）中**。参数不会暴露在地址栏，且传输大小没有限制，适合上传大文件、提交表单或复杂的 JSON 对象。
    

#### 2. 请求头（Request Headers）—— 数据的“附带属性”

![[Java Web笔记-49.png|697]]

从**第二行开始**直到空行结束，格式为 `Key: Value` 的键值对。它们是浏览器带给后端的“额外小情报”。对照你的第二张截图，最常用的几个必须死记硬背：

- **`Host`**：你要请求的服务器主机名和端口号（如 `localhost:8080`）。
    
- **`User-Agent`**：浏览器的“身份证”，告诉后端当前是用 Chrome、Edge 还是手机浏览器访问的。
    
- **`Accept`**：浏览器告诉后端：“我能接收什么格式的返回结果”（如 `text/html`, `application/json`）。
    
- **`Content-Type`**：**（极重要，通常伴随POST）** 告诉后端，当前请求体里带过来的数据是什么格式。例如 `application/json` 代表是个 JSON 字符串。
    
- **`Content-Length`**：请求体的大小（单位：字节）。
    

#### 3. 请求体（Request Body）—— 数据的“正文”

- 紧跟在空行后面（空行用于隔离请求头和请求体）。
    
- **只有 POST/PUT 等请求才有**。如图三的绿色高亮部分，存放的是真正要提交给后端的复杂业务数据：`{"status":1, "brandName":"黑马", ...}`。
    

### 模块二：后端如何获取 HTTP 请求数据？

现在前端数据通过网络发过来了，我们在 Java 中该怎么把它们捞出来呢？

一个底层的关键对象：**`HttpServletRequest`**。它是 Java Web 标准（Servlet 规范）中专门用来**封装 HTTP 请求所有数据**的超级对象。当请求到达 Spring Boot 时，Spring 会把这个对象自动注入到你的方法参数里。


#### 1. 核心代码清单与 API 对比

```Java
@RestController
@RequestMapping("/request")
public class RequestController {

    @RequestMapping("/test")
    public String request(HttpServletRequest request) {
        
        // 1. 获取请求方式（GET/POST）
        String method = request.getMethod(); 
        System.out.println("请求方式：" + method); // 输出: GET

        // 2. 获取请求的完整 URL 地址
        String url = request.getRequestURL().toString(); 
        System.out.println("请求URL地址：" + url); // 输出: http://localhost:8080/request/test

        // 3. 获取请求的 URI 资源路径（不带域名和端口）
        String uri = request.getRequestURI(); 
        System.out.println("请求URI地址：" + uri); // 输出: /request/test

        // 4. 获取请求行中拼接的原始查询参数字符串
        String queryString = request.getQueryString();
        System.out.println("查询参数字符串：" + queryString); // 输出: name=itheima

        // 5. 获取指定的请求头信息
        String acceptHeader = request.getHeader("Accept");
        System.out.println("Accept请求头：" + acceptHeader);

        return "OK";
    }
}
```

#### 2. 划重点：`URL` 和 `URI` 的区别

这是非常容易混淆的一点，在开发和面试中极其常用：

- **`URL` (Uniform Resource Locator，统一资源定位符)**：指的是互联网上的**绝对路径**，带有协议、域名和端口。就像是“中国北京市海淀区XX路XX号”。
    
    - 对应代码：`request.getRequestURL()` ➔ 结果如 `http://localhost:8080/request`
        
- **`URI` (Uniform Resource Identifier，统一资源标识符)**：指的是除去域名和端口后的**资源相对路径**。就像是“XX路XX号”。
    
    - 对应代码：`request.getRequestURI()` ➔ 结果如 `/request`
        

---
---


## 响应协议



### 模块一：解剖 HTTP 响应数据格式

![[Java Web笔记-50.png]]

#### 1. 状态行（Status Line）—— 结果的“定性声明”

位于响应数据的**第一行**。它用来粗暴直接地告诉浏览器：“这次请求是成功了，还是崩了”。

> 示例：`HTTP/1.1 200 OK`

- **协议版本**：通常是 `HTTP/1.1`。
    
- **状态码（Status Code）**：用 3 位数字代表处理结果。
    
- **状态描述**：对数字的简单文字解释。
    

##### 面试与开发必备：响应状态码分类

- **`1xx` (信息提示)**：临时状态，提示客户端继续操作。
    
- **`2xx` (成功)**：代表请求非常顺利。**最常用的是 `200 OK`**。
    
- **`3xx` (重定向)**：资源搬家了。告诉浏览器：_“你要的数据不在我这，快去访问另一个新地址”_。
    
- **`4xx` (客户端错误)**：前端传错参数、没登录或访问了不存在的资源。**最常见的是 `404 Not Found`**。
    
- **`5xx` (服务器错误)**：后端 Java 代码抛出异常挂掉了。**最常见的是 `500 Internal Server Error`**。
    

#### 2. 响应头（Response Headers）—— 返回的“附加属性”

![[Java Web笔记-51.png|697]]

从**第二行开始**直到空行结束，格式同样为 `Key: Value`。这是后端留给浏览器的一些“温馨提示”：

- **`Content-Type`**：**（极其核心）** 告诉浏览器响应体里装的是什么。例如 `application/json` 代表是个 JSON 对象；`text/html` 代表是一个网页，浏览器看到后会直接渲染。
    
- **`Content-Length`**：响应体正文的大小（字节数）。
    
- **`Content-Encoding`**：告知数据采用了何种压缩算法（如 `gzip`），浏览器收到后需要先解压。
    
- **`Cache-Control`**：控制浏览器的缓存机制（例如 `max-age=300` 代表这个数据 300 秒内不用再向后端要，直接读本地缓存）。
    
- **`Set-Cookie`**：**（极重要）** 后面做登录认证时，后端用来往浏览器的底层塞入身份凭证（Cookie）的通道。
    

#### 3. 响应体（Response Body）—— 返回的“真正正文”

- 紧跟在空行后面。
    
- 它是真正要展示在浏览器页面上、或者交给前端 Vue/React 解析的**核心数据**。可以是一个 HTML 页面、一张图片的二进制流，或者是一个标准的 **JSON 数组**（如第一张图中高亮的 `[{id: 1, brandName: "阿里巴巴", ...}]`）。
    

### 模块二：后端如何设置与返回响应数据？

前端既然在等响应，那我们在 Java 中该怎么控制这三部分（状态码、响应头、响应体）呢？

![[Java Web笔记-52.png|697]]
#### 方式一：基于 Servlet 原生 `HttpServletResponse`（底层的做法）

通过把 Java Web 顶层的 `HttpServletResponse` 对象直接作为方法参数注入，进行**纯手动、命令式**的设置：


```Java
@RequestMapping("/response")
public void response(HttpServletResponse response) throws IOException {
    // 1. 设置响应状态码
    response.setStatus(401); // 故意设置为401（未授权异常）
    
    // 2. 设置自定义响应头
    response.setHeader("name", "itheima");
    
    // 3. 设置响应体：获取字符输出流，直接往浏览器写数据
    response.getWriter().write("<h1>Hello Response</h1>");
}
```

- **缺点**：过于底层，写起来非常繁琐。在前后端分离的开发中，由于每次都要自己通过 `getWriter()` 写数据，很不方便。
    

#### 方式二：基于 Spring 提供的 `ResponseEntity`（高级的做法）

利用 Spring 提供的**链式编程对象**（Fluent API）进行包装，代码更加优雅、具备现代感：


```Java
@RequestMapping("/response2")
public ResponseEntity<String> response2() {
    return ResponseEntity
            .status(401)                        // 1. 设置响应状态码
            .header("name", "javaweb-ai")       // 2. 设置响应头
            .body("<h1>Hello Response</h1>");   // 3. 设置响应体
}
```

- **优点**：结构清晰，通过方法链（`.status().header().body()`）直接一步到位将响应包封装完毕返回，是现代化企业开发中很推崇的规范写法。
    

#### 注意


> **“响应状态码和响应头如果没有特殊要求的话，通常不手动设定。服务器会根据请求处理的逻辑，自动设置响应状态码和响应头。”**


在绝大多数正常的业务（比如查询商品、用户登录）下，你不需要像上面那样大费周章地去写 `setStatus(200)` 或者手动设置 `Content-Type`。

**你只需要在类上加上 `@RestController`，然后方法直接返回你的数据对象：**

```Java
@GetMapping("/user")
public User getUser() {
    return new User("张三", 18);
}
```

**Spring Boot 幕后会自动帮你做三件事：**

1. 发现方法正常执行完，自动在状态行塞入 `200 OK`。
    
2. 发现你返回的是一个 Java 对象，自动通过 Jackson 组件把它转成 `{"name":"张三","age":18}`。
    
3. 发现是 JSON 串，自动在响应头加上 `Content-Type: application/json;charset=UTF-8`。
    

你只有在做一些**特殊、硬性的底层业务**（比如：鉴权失败故意返回 `401/403`、文件下载需要设置特定的 `Content-Disposition` 响应头、或者强制重定向时），才会用到 `ResponseEntity` 或原生 `response` 对象去手动修改。

---
---





# Spring Boot


## 概述

### 一、 鸟瞰 Spring 家族：它由什么组成？

Spring 并不是一个单一的框架，而是一个庞大的**生态系统**，涵盖了从企业级开发、安全认证到微服务、大数据的方方面面。以下是 Java Web 开发中最核心的四大成员：

|**成员名称**|**核心职责与定位**|**形象比喻**|
|---|---|---|
|**Spring Framework**|整个家族的**基石**，提供最底层的容器、依赖注入（DI）和面向切面编程（AOP）。|汽车的底盘与发动机|
|**Spring MVC**|专门用来做 **Web 开发**的经典框架，负责处理 HTTP 请求、路由和响应。|汽车的控制台与方向盘|
|**Spring Boot**|现代 Java 开发的**绝对核心**。它不是新框架，而是对上述框架的“脚手架”封装，旨在简化配置。|汽车的自动挡与一键启动|
|**Spring Cloud**|专门用于**微服务架构**的工具集（处理服务注册、发现、配置中心、网关等）。|高速公路上的交通指挥系统|

此外，家族中还有负责安全认证的 **Spring Security**、负责数据访问的 **Spring Data** 等。


![[Java Web笔记-44.png]]

#### 为什么说 Spring Framework 是基石？

要学好 Spring，必须理解它的两大核心思想：

1. **IoC/DI（控制反转/依赖注入）：** 以前我们要用一个对象，得自己 `new`。现在所有对象（在 Spring 里叫 **Bean**）都交给 Spring 容器来管理，你需要什么，Spring 就给你注入（Inject）什么。这实现了代码的**解耦**。
    
2. **AOP（面向切面编程）：** 把一些与业务无关，但很多地方都要用的功能（比如日志记录、事务管理、权限控制）抽离出来，在不修改原代码的情况下，动态地“织入”到业务方法中。
    

### 二、 重点攻克：为什么要用 Spring Boot？

在没有 Spring Boot 的年代（也就是传统的 SSM 时代：Spring + Spring MVC + MyBatis），开发一个简单的 "Hello World" 网页都需要配置大量的 XML 文件、手动配置 Tomcat 服务器、处理繁琐的 Maven 依赖冲突。

Spring Boot 的出现彻底改变了这一切，它的核心灵魂就是：**约定优于配置（Convention over Configuration）**。

#### 1. Spring Boot 的三大核心杀手锏

- **自动配置（Auto-Configuration）：**
    
    Spring Boot 非常“聪明”。当它发现你的项目依赖里引入了 `spring-boot-starter-web`，它就会自动帮你把 Spring MVC 锁需要的配置全部配好；如果发现了 MySQL 的驱动包，它就会自动去准备数据库连接池。你不需要写长篇大论的 XML，它猜你想要什么，并帮你做好了默认设置。
    
- **起步依赖（Starter POMs）：**
    
    以前引入依赖要写一堆，还要担心版本冲突。现在 Spring Boot 把各种功能打包成了统一的“开箱即用”单元，叫做 **Starter**。
    
    - 想做 Web 开发？引入 `spring-boot-starter-web`
        
    - 想连数据库？引入 `mybatis-spring-boot-starter`
        
        所有的版本号都由 Spring Boot 统一管理，再也不会发生依赖冲突的惨剧。
        
- **内嵌 Servlet 容器：**
    
    传统的 Web 项目需要打包成 `war` 包，然后手动下载并配置一个外部的 Tomcat 服务器才能运行。而 Spring Boot 内部**直接集成了 Tomcat/Jetty**。你的项目最终会打包成一个普通的 `jar` 包，直接运行 `java -jar xxx.jar` 就能跑起来，极其方便部署。
    

### 三、 Spring Boot 项目的长相与核心组件

当你初始化一个 Spring Boot 项目后，你会发现它的结构非常清晰。一个典型且规范的后端工程通常包含以下几层：

#### 1. 经典的三层架构（MVC 落地）

- **Controller 层（控制层/表现层）：** 负责接收前端发来的 HTTP 请求，调用业务层处理，最后把结果返回给前端（现在通常返回 JSON 数据）。
    
- **Service 层（业务逻辑层）：** 编写核心业务逻辑的地方，比如计算价格、处理用户注册流程。
    
- **Mapper 层 / DAO 层（数据访问层）：** 负责和数据库（如 MySQL）打交道，执行 SQL 语句（配合 MyBatis 或 JPA）。
    

#### 2. 常用核心注解（必须烂熟于心）

在 Spring Boot 中，我们几乎不再写配置文件，全靠**注解**来告诉框架该怎么做：

```Java
@RestController // 声明这是一个支持RESTful风格的Controller，返回值会自动转为JSON
@RequestMapping("/user") // 映射请求路径
public class UserController {

    @Autowired // 自动注入：让Spring把底层的UserService实例塞进来
    private UserService userService;

    @GetMapping("/{id}") // 处理GET请求，获取用户数据
    public User getUserById(@PathVariable Long id) {
        return userService.findById(id);
    }
}
```

- `@SpringBootApplication`：贴在主类上，是整个项目的启动入口，它包含了自动配置和组件扫描的功能。
    
- `@Component`、`@Service`、`@Repository`：告诉 Spring 容器，“我是一个 Bean，快把我管理起来”。
    

### 四、 给你的 Java Web 学习路线建议

既然你的目标很明确，是为了以后能高效地做项目和顺利就业，建议不要在传统的 XML 配置（比如老旧的 SSH 或纯 SSM 整合）上浪费太多时间。

1. **基础打牢：** 确保你的 Java 基础（集合、异常处理、反射、面向对象思想）过关，理解 Maven 怎么管理依赖。
    
2. **理解核心：** 动手用 Spring Boot 跑一个 "Hello World"。虽然不用写 XML，但一定要通过 debug 搞懂什么是 **IoC（控制反转）** 和 **AOP（面向切面）**。
    
3. **数据联动：** 学习 **Spring Boot + MyBatis-Plus + MySQL** 的组合。这是国内目前最主流、写起来最爽快的数据持久化方案。
    
4. **前后端分离：** 现在的企业项目基本都是前后端分离。重点练习写 **RESTful API**，学会用统一的 JSON 格式（如自定义的 `Result<T>` 类）给前端返回数据。
    
5. **周边生态：** 顺着项目需求，逐渐引入 Redis（缓存）、Spring Security / JWT（登录认证与权限控制）。
    

---
---


## 入门程序


![[Java Web笔记-45.png]]

下面我将完全基于你截图中展示的经典案例，为你重现这个小练习，并采用**最符合日常开发规范**的 IDEA 代码结构进行详细拆解

### 1. 第一步：在 IDEA 中创建标准的项目结构

在 IntelliJ IDEA 中，使用 **Spring Initializr（或者叫Spring Boot）** 创建工程并勾选 **Spring Web** 依赖后，IDEA 会自动为你生成一套标准的 Maven 包结构。

为了让项目更加规范，我们需要把控制层（Controller）单独放到一个包里。请在 IDEA 中建立如下的目录结构：


```Plaintext
my-springboot-demo
├── src
│   ├── main
│   │   ├── java
│   │   │   └── com
│   │   │       └── example
│   │   │           └── demo
│   │   │               ├── DemoApplication.java       <-- 自动生成的主启动类
│   │   │               └── controller                 <-- 手动新建的包，存放控制器
│   │   │                   └── HelloController.java   <-- 手动新建的业务代码类
│   │   └── resources
│   │       ├── static                                 <-- 存放静态资源（如 html, css）
│   │       ├── templates                              <-- 存放模板文件
│   │       └── application.properties                 <-- 核心配置文件（如修改端口）
└── pom.xml                                            <-- Maven 依赖管理配置文件
```

> ⚠️ **新手踩坑注意（大忌）：**
> 
> `HelloController.java` **必须**放在主启动类 `DemoApplication.java` 所在的包或其**子包**（如上面的 `controller` 包）下！如果把它移动到与 `com.example.demo` 平级甚至更外层的地方，Spring Boot 将无法自动扫描到该注解，从而导致访问时报 `404` 错误。

### 2. 第二步：编写完整的核心代码

在这个入门程序中，我们只需要关注两个 Java 类。

#### ① 主启动类（创建项目时 IDEA 已自动生成，无需修改）


```Java
package com.example.demo;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication // 核心注解：标识这是一个Spring Boot应用，并自动开启组件扫描
public class DemoApplication {
    public static void main(String[] args) {
        // 启动内置的 Tomcat 服务器并初始化 Spring 容器
        SpringApplication.run(DemoApplication.class, args);
    }
}
```

#### ② 业务控制类（手动在 `controller` 包下创建）

请完全对照你截图中的逻辑编写如下代码：


```Java
package com.example.demo.controller;

import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController // 标识当前类是一个请求处理类（Controller），返回值会自动转为数据返回给浏览器
public class HelloController {

    @RequestMapping("/hello") // 标识请求路径，把浏览器的 /hello 路径映射到这个方法上
    public String hello(String name) {
        // 在 IDEA 控制台中打印接收到的参数，便于后端排查日志
        System.out.println("HelloController ... hello : " + name);
        
        // 返回给前端浏览器的字符串内容
        return "Hello " + name + " ~ ";
    }
}
```

### 3. 第三步：代码与原理深度拆解

为了让你真正掌握，我们把这段看似简单的代码拆开来看：

1. **`@RestController` 的魔力**：
    
    在传统的 Spring MVC 网页开发中，方法返回 `"hello"` 通常意味着框架会去寻找一个叫 `hello.html` 或 `hello.jsp` 的页面。而现在进入了**前后端分离**时代，我们使用 `@RestController` 告诉 Spring：_“我这里不需要返回任何网页，方法返回的是什么字符串/对象，你就直接把它们塞进 HTTP 响应体里塞给前端。”_
    
2. **`@RequestMapping("/hello")` 的路由**：
    
    它就像是一个路标。当外部用户的浏览器访问服务器的 `/hello` 节点时，Tomcat 会在第一时间抓住这个请求，并交给带有匹配注解的 `hello()` 方法去处理。
    
3. **参数的自动绑定 `(String name)`**：
    
    这是 Spring Boot 非常智能的一个体现。如果你在浏览器访问时传入了参数（例如 `?name=Heima`），Spring Boot 会通过反射机制，**自动调取同名参数的值**注入到该方法的 `name` 变量中，完全不需要你手动写 `request.getParameter("name")` 这种繁琐的代码。
    

### 4. 第四步：运行与验证

1. **启动应用**：回到 `DemoApplication.java` 类中，点击 `main` 方法左侧的**绿色小三角**启动项目。
    
2. **查看控制台**：当看到控制台打印出类似 `Tomcat started on port 8080 (http) with context path ''` 以及 `Started DemoApplication in ... seconds` 时，说明内置的 Tomcat 已经在后台成功跑起来了，默认端口为 **8080**。
    
3. **浏览器测试**：打开浏览器，在地址栏输入：
    
    `http://localhost:8080/hello?name=Heima`
    
4. **验证结果**：
    
    - **网页显示**：浏览器页面会输出：`Hello Heima ~`
        
    - **IDEA 控制台**：切回 IDEA，控制台会打印出：`HelloController ... hello : Heima`
        

---
---


## 入门程序补充

![[Java Web笔记-46.png]]

这张图问出了一个非常经典且致命的核心问题：**“为什么一个 main 方法就能将 Web 应用启动了？”** 在传统的 Java Web 开发里，没有 Tomcat 软件或者没在外部配置好服务器，单独跑一个 `main` 方法是绝对出不来网页的。Spring Boot 颠覆这一常识的幕后功臣，就是你截图中提到的**起步依赖（Starter）**。

我们结合你新发出的这张原理图，深入拆解一下这个“魔法”的底层逻辑，你可以直接把这部分补充进你的 Obsidian 笔记中。

### 一、 揭秘：为什么一个 `main` 方法就能启动 Web 应用？

这其中的核心秘密在于两点：**内嵌 Tomcat** 和 **自动装配**。

#### 1. 顺藤摸瓜：看清 Maven 依赖树的隐藏底层

观察你截图中右侧的依赖树（Dependencies），你会发现我们仅仅在 `pom.xml` 中引入了一个起步依赖：

- `spring-boot-starter-web`（Web开发核心依赖）
    

但是当你把它展开时，它像连环套一样，自动帮你间接引入了大量的底层 Jar 包。其中被红色高亮标注的最关键的一项就是：

👉 `org.springframework.boot:spring-boot-starter-tomcat`

再往下点开，它包含了 Tomcat 的核心核心组件：`tomcat-embed-core`（内嵌Tomcat核心）。

#### 2. 什么是“内嵌 Tomcat（Embedded Tomcat）”？

- **传统方式：** Tomcat 是一个独立的软件。你需要先下载、解压、配置环境变量，然后把写好的 Java Web 项目打包成 `war` 包，手动拷贝到 Tomcat 的 `webapps` 目录下，再点击 Tomcat 的 `startup.bat` 脚本来带起项目。
    
- **Spring Boot 方式：** 程序员不要再去处理外部服务器了。Spring Boot 直接把 Tomcat 的核心底层代码打包成了 Java 的 `Jar` 包，作为项目的依赖。
    

> **形象的比喻：** > 传统 Web 开发是“**把房子（你的代码）盖在公共地基（外部 Tomcat）上**”；
> 
> Spring Boot 是“**房车一体**”，Tomcat 成了你代码的一部分，直接被打包进了最终的 `jar` 运行文件中。

#### 3. `main` 方法执行时的内部动作

当你点击绿色的三角号运行 `main` 方法时，底层其实默默执行了以下流水线：

1. **JVM 启动**：执行主类的 `main` 方法，调用 `SpringApplication.run()`。
    
2. **创建容器**：Spring 开始初始化 IoC 容器，扫描并加载你写的 `HelloController`。
    
3. **触发动机**：容器发现你引入了 `starter-web` 依赖，触发自动配置机制，直接在内存中通过代码 `new` 出了一个 Tomcat 实例。
    
4. **绑定与监听**：内嵌的 Tomcat 启动，默认将项目挂载在 **8080** 端口，开始监听网络请求。
    

### 二、 重点消化：什么是“起步依赖（Starter）”？

截图下方提到一句话：“`spring-boot-starter-web` 包含了 Web 应用开发所需要的常见依赖”。

这就是 Spring Boot 设计的艺术，它被称为 **Starter（起步依赖 / 场景启动器）**。

#### 1. 传统依赖管理的痛苦

以前你想做 Web 开发，得在 `pom.xml` 里写上一大堆乱七八糟的依赖：Spring MVC 的包、Jackson JSON 解析包、日志包、Tomcat 相关的包……不仅繁琐，而且只要其中任何一个包的**版本号**不兼容，项目就会疯狂报错。

#### 2. Starter 的“全家桶”概念

Spring Boot 提出了“**把功能打包成场景**”的概念。

- 你想做 Web 开发？你不需要关心里面需要几百个小 Jar 包。你只要对 Maven 说：“给我来一份 `spring-boot-starter-web` 全家桶。”
    
- 它就会在底层自动把 Spring MVC、JSON 转换、日志、内置 Tomcat 等所有**版本互相兼容、测试稳定**的小 Jar 包一次性全部帮你捆绑引入进来。
    

#### 3. 常见 Starter 的命名规范（就业面试常考）

你在以后的开发中会遇到各种各样的 Starter，它们有固定的命名套路：

- **官方提供的 Starter：** 命名格式为 `spring-boot-starter-xxx`。
    
    - `spring-boot-starter-test`：负责单元测试（如你截图中最后一项）。
        
    - `spring-boot-starter-data-redis`：负责缓存中间件 Redis。
        
- **第三方（民营企业）提供的 Starter：** 命名格式为 `xxx-spring-boot-starter`。
    
    - `mybatis-spring-boot-starter`：国内最常用的持久层整合包。
        

### 三、 避坑与总结

有了这些前置理解，现在再看之前的 `HelloController` 代码，逻辑就完全闭环了：

```Plaintext
浏览器发出请求 (http://localhost:8080/hello) 
       ↓
[内嵌 Tomcat] 拦截到网络请求 (因为引入了 starter-web 并在 main 中随应用一起被启动)
       ↓
[Spring 路由机制] 匹配到带有 @RequestMapping("/hello") 的方法
       ↓
[HelloController.hello()] 执行业务，控制台打印日志，返回字符串
       ↓
[内嵌 Tomcat] 把字符串作为响应结果丢回给浏览器
```



---
---


## 完整实战

![[Java Web笔记-54.png|697]]

这个案例是 黑马程序员 课程中非常经典的 **“用户列表数据展示”** 综合实战。它完美地把前端（Vue + Axios）、后端（Spring Boot Controller）、底层数据（`user.txt` 解析）以及 HTTP 协议闭环（JSON 响应）全部串联了起来。


### 项目目录结构对照

在开始写代码前，请确保你的 IDEA 目录结构与标准结构一致：

```Plaintext
springboot_web_quickstart
 └── src
      └── main
           ├── java
           │    └── com
           │         └── itheima
           │              ├── SpringbootWebQuickstartApplication.java (启动类)
           │              ├── controller
           │              │    └── UserController.java              (控制层)
           │              └── pojo
           │                   └── User.java                        (实体类)
           └── resources
                ├── static
                │    └── user.html                                  (前端静态页面)
                └── user.txt                                        (原始数据文件)
```

### 后端核心代码实现

#### 1. 实体类定义：`pojo/User.java`

*POJO 包（Plain Old Java Object）只放纯实体类（实体模型），简单说：用来封装数据的普通 Java 类*

利用 Lombok 注解简化 Java 属性的 Getter/Setter 构造方法，用来封装单条用户数据。**要先添加 Lombok 依赖**

```Java
package com.itheima.pojo;

import lombok.AllArgsConstructor;
import lombok.Data;
import lombok.NoArgsConstructor;
import java.time.LocalDateTime;

@Data // 自动生成 getter/setter/toString/equals/hashCode
@NoArgsConstructor // 自动生成无参构造额方法
@AllArgsConstructor // 自动生成全参构造方法
public class User {
    private Integer id;             // 用户ID
    private String username;        // 用户名
    private String password;        // 密码
    private String name;            // 姓名
    private Integer age;            // 年龄
    private LocalDateTime updateTime; // 更新时间
}
```

#### 2. 控制层实现：`controller/UserController.java`

这是核心业务。负责：**读取本地文件 ➔ 解析数据并封装成 List ➔ 借助 `@RestController` 将其转化为标准 HTTP JSON 响应体返回**。

> **⚠️ 黑马冷知识**：在没有学数据库（MySQL）和 MyBatis 之前，老师用读取 `user.txt` 文件的方案来平替数据库查询逻辑，目的是让我们聚焦于 Web 请求和响应的闭环。


```Java
package com.itheima.controller;

import com.itheima.pojo.User;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

import java.io.BufferedReader;
import java.io.InputStream;
import java.io.InputStreamReader;
import java.nio.charset.StandardCharsets;
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;
import java.util.ArrayList;
import java.util.List;
import java.util.stream.Collectors;

// @RestController = @Controller + @ResponseBody
// 核心作用：将方法的返回值直接写入 HTTP 响应体，如果是对象或集合，会自动转为 JSON 响应
@RestController 
public class UserController {

    @RequestMapping("/list") // 标识请求路径，前端输入 /list 会触发该方法
    public List<User> list() throws Exception {
        
        // 1. 加载 resources 目录下的数据文件 user.txt
        InputStream in = this.getClass().getClassLoader().getResourceAsStream("user.txt");
        
        // 2. 利用字符输入流读取文件中的所有行
        BufferedReader reader = new BufferedReader(new InputStreamReader(in, StandardCharsets.UTF_8));
        List<String> lines = reader.lines().collect(Collectors.toList());

        // 3. 解析文本数据，将其转为 List<User> 集合
        List<User> userList = new ArrayList<>();
        
        for (String line : lines) {
            // user.txt 数据格式：1,daqiao,1234567890,大乔,22,2024-07-15 15:05:45
            String[] parts = line.split(","); // 按照逗号切割每一行
            
            Integer id = Integer.parseInt(parts[0]);      // 提取 id
            String username = parts[1];                  // 提取用户名
            String password = parts[2];                  // 提取密码
            String name = parts[3];                      // 提取姓名
            Integer age = Integer.parseInt(parts[4]);     // 提取年龄
            
            // 提取更新时间，并转换字符串为 LocalDateTime 格式
            LocalDateTime updateTime = LocalDateTime.parse(parts[5], 
                    DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss"));
            
            // 组装 User 对象并放入集合中
            User user = new User(id, username, password, name, age, updateTime);
            userList.add(user);
        }

        // 4. 直接返回集合对象。
        // 由于加了 @RestController，Spring Boot 会自动把它打包成 HTTP 响应体，返回标准的 JSON 数组
        return userList;
    }
}
```

### 资源及前端页面配置

#### 1. 模拟数据库文件：`resources/user.txt`

请直接在项目的 `resources` 文件夹下新建该文本文件，用于存放原始的 mock 数据（注意时间格式需与 Java 解析器对齐）。


```Plaintext
1,daqiao,1234567890,大乔,22,2024-07-15 15:05:45
2,xiaoqiao,1234567890,小乔,18,2024-07-15 15:12:09
3,diaochan,1234567890,貂蝉,21,2024-07-15 15:07:16
4,lvbu,1234567890,吕布,28,2024-07-16 10:05:15
5,zhaoyun,1234567890,赵云,27,2024-07-16 11:03:28
6,zhangfei,1234567890,张飞,31,2024-07-16 11:03:28
7,guanyu,1234567890,关羽,34,2024-07-16 12:05:12
8,liubei,1234567890,刘备,37,2024-07-16 15:03:28
```

#### 2. 前端静态展示页：`resources/static/user.html`

在 Spring Boot 中，所有的静态资源文件（HTML、CSS、JS）默认都存放在 `resources/static` 目录下。

利用 Vue 渲染和 Axios 发起异步 HTTP 请求：


```HTML
<!DOCTYPE html>
<html lang="en"> <head>
    <meta charset="UTF-8">
    <title>用户列表数据展示</title>
    <style>
        table {
            width: 60%;
            margin: 50px auto;
            border-collapse: collapse;
            text-align: center;
        }
        th, td {
            border: 1px solid #ccc;
            padding: 10px;
        }
        th {
            background-color: #f5f7fa;
        }
        h2 {
            text-align: center;
            margin-top: 30px;
        }
    </style>
</head>
<body>

<div id="app">
    <h2>用户列表数据</h2>
    
    <table>
        <thead>
            <tr>
                <th>ID</th>
                <th>用户名</th>
                <th>密码</th>
                <th>姓名</th>
                <th>年龄</th>
                <th>更新时间</th>
            </tr>
        </thead>
        
        <tbody>
            <tr v-for="user in userList">
                <td>{{user.id}}</td>
                <td>{{user.username}}</td>
                <td>{{user.password}}</td>
                <td>{{user.name}}</td>
                <td>{{user.age}}</td>
                <td>{{user.updateTime}}</td>
            </tr>
        </tbody>
    </table>
</div>

<script src="js/axios.min.js"></script>

<script type="module">

    import { createApp } from 'https://unpkg.com/vue@3/dist/vue.esm-browser.js';

    createApp({
    
        data() {
            return {
                userList: [] // 初始化接收后端数据的数组
            }
        },
       
        methods: {
            //使用 async/await 发送异步网络请求
            async search() {
                //通过 axios 向后端的 /list 路径发出 GET 请求
                const result = await axios.get('/list');
                //把后端响应体（result.data）里的 JSON 数组赋值给当前的 userList 属性
                this.userList = result.data;
            }
        },
        // Vue 生命周期钩子函数（挂载完毕阶段）
        mounted() {
            // 页面一加载，自动执行 search() 方法去向后端“要数据”
            this.search();
        }
    }).mount('#app') // 将 Vue 实例挂载到 id 为 app 的容器上
</script>

</body>
</html>
```

### 验证闭环与运行效果

1. 打开项目的启动类 `SpringbootWebQuickstartApplication`，右键点击 **Run**。
    
2. 观察 IDEA 控制台，当看到内嵌 Tomcat 成功在 `8080` 端口拉起后，打开浏览器。
    
3. **测试接口数据（纯 JSON）**：
    
    在地址栏输入 `http://localhost:8080/list` 并敲回车，此时浏览器会发出 HTTP 请求，并直接在屏幕上打印出纯文本的 **JSON 数组数据**。
    
4. **测试最终系统（可视化表格）**：
    
    在地址栏输入 `http://localhost:8080/user.html` 并敲回车。
    
    - **运行逻辑**：浏览器首先请求拿到了 `user.html` 静态页面；页面加载时触发了 Vue 的 `mounted()` 钩子；Axios 再次发射异步请求去撞后端的 `/list` 接口；后端将数据打包回传；Vue 动态把数据在表格里“画”出来，呈现出如你第一张截图所示的精美用户列表数据表格！






---
---


## 分层解耦——三层架构


在你刚才完成的“用户列表展示”小练习里，所有的代码（读文件、解析字符串、包装数据、返回响应）全都塞在了一个 `UserController` 的 `list()` 方法里。正如你第一张截图中所高亮的痛点：**“单一职责原则：一个方法/类只负责一件事情。如果全部写在一起，代码极其臃肿、难以维护、复用性极差。”**



### 一、 什么是三层架构？（核心职责划分）

三层架构把一个复杂的 Web 业务，像流水线工厂一样切分成了三个各司其职的部门：

![[Java Web笔记-55.png]]
#### 1. Controller：控制层（表现层）

- **它的职责**：负责**接收前端发来的请求**，并**把结果响应给前端**。
    
- **形象比喻**：餐馆里的“前台服务员”。它只负责接待客人（点单）、把菜单传给后厨，最后把做好的菜端给客人。服务员自己是绝对不会跑去炒菜的。
    
- **对应代码注解**：带有 `@RestController` 标签的类。
    

#### 2. Service：业务逻辑层

- **它的职责**：负责**核心业务逻辑的处理**（比如计算折扣、过滤不合规数据、组装业务对象）。
    
- **形象比喻**：后厨的“掌勺大厨”。它是整个餐馆的核心，专门负责研究怎么把原材料做成绝妙的菜肴。它不关心客人坐哪（不关心 HTTP 请求），它只管做业务。
    

#### 3. Dao / Mapper：数据访问层（Data Access Object）

- **它的职责**：负责**与底层数据/数据库打交道**（包括增删改查 CRUD）。在没有连接 MySQL 之前，它负责读写 `user.txt` 文本文件；连了数据库后，它负责执行 SQL 语句。
    
- **形象比喻**：餐馆里的“采购员 / 仓库管理员”。大厨需要什么食材（数据），采购员就去仓库里（数据库）拿出来提供给大厨，它自己不参与炒菜业务。
    

### 二、 实战重构：代码应该怎么分？

我们将之前臃肿的 `UserController` 彻底“大卸三块”：

#### 1. Dao层：只管拿原始数据

我们新建一个类或接口，专门用来处理文件/数据库数据的读取。

```Java
// 假设定义一个 UserDao 类
public class UserDao {
    public List<String> listRawData() throws Exception {
        // 1. 纯粹负责加载和读取 user.txt，拿到最原始的一行行字符串数据
        InputStream in = this.getClass().getClassLoader().getResourceAsStream("user.txt");
        BufferedReader reader = new BufferedReader(new InputStreamReader(in, StandardCharsets.UTF_8));
        return reader.lines().collect(Collectors.toList());
    }
}
```

#### 2. Service层：负责复杂的解析与逻辑加工

大厨登场，管 Dao 要到原始数据后，进行解析和格式转换。

```Java
public class UserService {
    private UserDao userDao = new UserDao(); // 依赖Dao层去拿数据

    public List<User> listUsers() throws Exception {
        // 1. 调用Dao层拿到原始的字符串行
        List<String> lines = userDao.listRawData();
        
        // 2. 在这里编写核心业务：切割字符串、转换LocalDateTime、封装成User对象
        List<User> userList = new ArrayList<>();
        for (String line : lines) {
            String[] parts = line.split(",");
            // ... 解析包装成 user 对象 ...
            userList.add(user);
        }
        
        // 3. 返回加工处理好的干净数据
        return userList;
    }
}
```

#### 3. Controller层：作为前台迎客，代码变得极其干净！

由于繁重的脏活、累活全被 Service 和 Dao 承包了，控制层现在只需要负责接收和响应：

```Java
@RestController
public class UserController {
    // 依赖 Service 层来获取业务结果
    private UserService userService = new UserService(); 

    @RequestMapping("/list")
    public List<User> list() throws Exception {
        // 1. 前台不碰业务，直接调用大厨（Service）做好的数据
        List<User> userList = userService.listUsers();
        
        // 2. 将数据响应给前端
        return userList;
    }
}
```

### 三、 高级思考：什么是“解耦”？它完美了吗？

通过上面的重构，我们成功实现了**分层**（Controller ➔ Service ➔ Dao）。

但是，请非常仔细地观察我们在 `UserController` 里写的这一行代码：

```Java
private UserService userService = new UserService();
```

还有在 `UserService` 里面写的：

```Java
private UserDao userDao = new UserDao();
```

#### 致命缺陷：这并没有真正“解耦”！

我们在控制层里面手写了 `new UserService()`。这意味着，`UserController` 和 `UserService` 之间存在着**强耦合**。

- **如果有一天**：因为业务调整，大厨类改名了，或者我们要换成另一个 `NewUserService` 类的实现。
    
- **代价**：你就不得不被迫去修改 `UserController` 的源代码！这就违反了软件工程的“开闭原则”。
    

#### 预告：如何实现“真正的解耦”？

这就要引出你接下来的课程核心——Spring 最引以为傲的两大王牌：**控制反转（IoC）** 和 **依赖注入（DI）**！

Spring 会对你说：_“翻转吧！你们谁也别自己 `new` 对象了。把管理对象的权力上交给我（Spring容器）。Controller 需要 UserService 吗？在属性上贴个 `@Autowired` 注解，我自动在后台帮你把实例塞进去！”_

---
---


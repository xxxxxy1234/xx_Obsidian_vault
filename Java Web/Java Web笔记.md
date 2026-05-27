
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



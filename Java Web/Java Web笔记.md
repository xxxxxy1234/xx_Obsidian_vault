
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

- **为什么：** 假设用户在文本框里输入了 `admin`。如果你的标签只写了 `<input type="text">`，点击提交后，你的 Java 后端确实收到了一个 `admin`。但 Java 会崩溃：“这 `admin` 到底是个啥？是用户名？还是密码？还是邮箱？”
    
- **正确做法：** 必须写上 `<input type="text" name="username">`。这样打包发送时，数据就会变成键值对：`username=admin`。你的 Java 代码就能通过 `request.getParameter("username")` 极其优雅地把数据拿出来了！
    

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
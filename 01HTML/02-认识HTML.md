# 1. HTML 初识

> 网页是由网页元素组成的 ， 这些元素是利用html标签描述出来，然后通过浏览器解析，就可以显示给用户了。

**所谓超文本，有2层含义：** 

1. 因为它可以加入图片、声音、动画、多媒体等内容（**超越文本限制 **）
2. 不仅如此，它还可以从一个文件跳转到另一个文件，与世界各地主机的文件连接（**超级链接文本 **）。

```html
<img src="timg.jpg" />
```

**html 总结:**

* html 是超文本标记(标签)语言
* 我们用html标签描述网页元素。 比如 图片标签 、文字标签、链接标签等等
* 标签有自己的语法规范，所有的html标签都是用 <> 表示的

## 1.1 HTML骨架标签

HTML 有自己的语言语法骨架格式：（要遵循，要专业） 要求务必非常流畅的默写下来。。

```html
<html>   
    <head>     
        <title></title>
    </head>
    <body>
    </body>
</html>
```
#### html骨架标签总结
| 标签名              |   定义   | 说明                             |
| ---------------- | :----: | :----------------------------- |
| <html></html>    | HTML标签 | 页面中最大的标签，我们成为  根标签             |
| <head></head>    | 文档的头部  | 注意在head标签中我们必须要设置的标签是title     |
| <titile></title> | 文档的标题  | 让页面拥有一个属于自己的网页标题               |
| <body></body>    | 文档的主体  | 元素包含文档的所有内容，页面内容 基本都是放到body里面的 |


 <img src='https://tva1.sinaimg.cn/large/00831rSTly1gcwri7zybgj30m209gdga.jpg'>



#### 团队约定大小写

HTML标签名、类名、标签属性和大部分属性值统一用小写

*推荐：*

```
<head>     
        <title>我的第一个页面</title>
 </head>
```

## 1.2 HTML元素标签分类

**标签：**

在HTML页面中，带有“< >”符号的元素被称为HTML标签，如上面提到的 &lt;html&gt;、&lt;head&gt;、&lt;body&gt;都是HTML骨架结构标签。

**分类：**

1. 常规元素（双标签）

```html
<标签名> 内容 </标签名>   比如 <body>  我是文字  </body>
```

* 该语法中“<标签名>”表示该标签的作用开始，一般称为“开始标签（start tag）”，“</标签名>” 表示该标签的作用结束，一般称为“结束标签（end tag）”。
* 和开始标签相比，结束标签只是在前面加了一个关闭符“/”。

2. 空元素（单标签）

```html
<标签名 />  比如  <br />
```

* 空元素 用单标签来表示， 简单点说，就是里面不需要包含内容， 只有一个开始标签不需要关闭。

  

## 1.3 HTML标签关系

主要针对于**双标签** 的相互关系分为两种： 

1. 嵌套关系

```html
<head>  
	<title> </title> 
</head>
```

2.并列关系

```html
<head></head>
<body></body>
```

**倡议：** 

> ```html
>  如果两个标签之间的关系是嵌套关系，子元素最好缩进一个tab键的身位（一个tab是4个空格）。如果是并列关系，最好上下对齐。
> ```

# 2. 文档类型<!DOCTYPE>

**用法：**

```html
<!DOCTYPE html> 
```

**作用：**

<!DOCTYPE> 声明位于文档中的最前面的位置，处于 <html> 标签之前。此标签可告知浏览器文档使用哪种 HTML 或 XHTML 规范。
**团队约定：**`HTML文件必须加上 DOCTYPE 声明，并统一使用 HTML5 的文档声明`

# 3. 页面语言lang

~~~html
<html lang="en">  指定html 语言种类
~~~

最常见的2个：

1. `en`定义语言为英语
2. `zh-CN`定义语言为中文

**团队约定：**`考虑浏览器和操作系统的兼容性，目前仍然使用 zh-CN 属性值`

# 4. 字符集

~~~html
<meta charset="UTF-8" />
~~~

~~~
字符集(Character set)是多个字符的集合。

计算机要准确的处理各种字符集文字，需要进行字符编码，以便计算机能够识别和存储各种文字。
~~~

utf-8是目前最常用的字符集编码方式，常用的字符集编码方式还有gbk和gb2312。

* gb2312 简单中文  包括6763个汉字  GUO BIAO
* BIG5   繁体中文 港澳台等用
* GBK包含全部中文字符    是GB2312的扩展，加入对繁体字的支持，兼容GB2312
* UTF-8则基本包含全世界所有国家需要用到的字符
* **这句代码非常关键， 是必须要写的代码，否则可能引起乱码的情况。**

**团队约定：**`一般情况下统一使用 "UTF-8" 编码, 请尽量统一写成标准的 "UTF-8"，不要写成 "utf-8" 或 "utf8" 或 "UTF8"。`
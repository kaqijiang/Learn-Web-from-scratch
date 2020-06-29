![6.CSS高级技巧](https://tva1.sinaimg.cn/large/00831rSTly1gdgfe1dx0lj315a0jdn2e.jpg)

# CSS高级技巧

> **显示隐藏** display visibility
>
> display: none/display
>
> visibility：visible/hidden 对象隐藏

> **溢出** overflow
>
> **visible**  不剪切内容也不添加滚动条
>
> **hidden**  不显示超过对象尺寸的内容，超出的部分隐藏掉
>
> **scroll**  不管超出内容否，总是显示滚动条
>
> **auto**  超出自动显示滚动条，不超出不显示滚动条

## 1. 元素的显示与隐藏

### 1.1 display 显示（重点）

- display 设置或检索对象是否及如何显示。隐藏之后，==不再保留位置==。

  ~~~css
  display: none 隐藏对象

  display：block 除了转换为块级元素之外，同时还有显示元素的意思。
  ~~~


实际开发场景：

> 配合后面js做特效，比如下拉菜单，原先没有，鼠标经过，显示下拉菜单， 应用极为广泛

### 1.2 visibility 可见性 (了解)

- 设置或检索是否显示对象。隐藏之后，==继续保留原有位置==。（停职留薪）

  ~~~css
  visibility：visible ; 　对象可视

  visibility：hidden; 　  对象隐藏
  ~~~


### 1.3 overflow 溢出(重点)

- 检索或设置当对象的内容超过其指定高度及宽度时如何管理内容。


| 属性值      | 描述                                       |
| ----------- | ------------------------------------------ |
| **visible** | 不剪切内容也不添加滚动条                   |
| **hidden**  | 不显示超过对象尺寸的内容，超出的部分隐藏掉 |
| **scroll**  | 不管超出内容否，总是显示滚动条             |
| **auto**    | 超出自动显示滚动条，不超出不显示滚动条     |

实际开发场景：

1. 清除浮动
2. 隐藏超出内容，隐藏掉,  不允许内容超过父盒子。

###  1.4 显示与隐藏总结

### 显示与隐藏总结

| 属性           | 区别                   | 用途                                                         |
| -------------- | ---------------------- | ------------------------------------------------------------ |
| **display**    | 隐藏对象，不保留位置   | 配合后面js做特效，比如下拉菜单，原先没有，鼠标经过，显示下拉菜单， 应用极为广泛 |
| **visibility** | 隐藏对象，保留位置     | 使用较少                                                     |
| **overflow**   | 只是隐藏超出大小的部分 | 1. 可以清除浮动 2. 保证盒子里面的内容不会超出该盒子范围                                   |
## 2. CSS用户界面样式

### 2.1 鼠标样式cursor

| 属性值          | 描述       |
| --------------- | ---------- |
| **default**     | 小白  默认 |
| **pointer**     | 小手       |
| **move**        | 移动       |
| **text**        | 文本       |
| **not-allowed** | 禁止       |
 鼠标放我身上查看效果哦：

```html
<ul>
  <li style="cursor:default">我是小白</li>
  <li style="cursor:pointer">我是小手</li>
  <li style="cursor:move">我是移动</li>
  <li style="cursor:text">我是文本</li>
  <li style="cursor:not-allowed">我是禁止</li>
</ul>
```

### 2.2 轮廓线 outline

### 轮廓线 outline

<img src='https://tva1.sinaimg.cn/large/00831rSTly1gd3nha3mmmj30iw0dngm5.jpg'>

 是绘制于元素周围的一条线，位于边框边缘的外围，可起到突出元素的作用。 我们平时都是去掉的。

```css
 outline : outline-color ||outline-style || outline-width 
```

最直接的写法是 ：  outline: 0;   或者  outline: none;

```html
 <input  type="text"  style="outline: 0;"/>
```

### 2.3 防止拖拽文本域resize

```html
<textarea  style="resize: none;"></textarea>
```

### 2.4 用户界面样式总结

| 属性         | 用途                 | 用途                                                         |
| ------------ | -------------------- | ------------------------------------------------------------ |
| **鼠标样式** | 更改鼠标样式cursor   | 样式很多，重点记住 pointer                                   |
| **轮廓线**   | 表单默认outline      | outline 轮廓线，我们一般直接去掉，border是边框，我们会经常用 |
| 防止拖拽     | 主要针对文本域resize | 防止用户随意拖拽文本域，造成页面布局混乱，我们resize:none    |
## 3. vertical-align 垂直对齐

- 有宽度的块级元素居中对齐，是margin: 0 auto;
- 让文字居中对齐，是 text-align: center;

vertical-align 垂直对齐，它只针对于**行内元素**或者**行内块元素**，

<img src="https://tva1.sinaimg.cn/large/00831rSTly1gd3nhf8imkj30ku0410th.jpg" />

```css
vertical-align : baseline |top |middle |bottom 
```

设置或检索对象内容的垂直对其方式。

- 注意：

  vertical-align ==不影响块级元素==中的内容对齐，它只针对于==**行内元素**==或者**==行内块元素==**，

  特别是行内块元素， **通常用来控制图片/表单与文字的对齐**。

### 3.1 图片、表单和文字对齐

 <img src='https://tva1.sinaimg.cn/large/00831rSTly1gd3nhhwsf1j308w03iaa2.jpg'>

### 3.2 去除图片底侧空白缝隙

- 原因：

  图片或者表单等行内块元素，底线会和父级盒子的基线对齐。就是图片底侧会有一个空白缝隙。

- 解决的方法就是：  

  - 给img vertical-align:middle | top| bottom等等。  让图片不要和基线对齐。

  - 给img 添加 display：block; 转换为块级元素就不会存在问题了。

##  4. 溢出的文字省略号显示

### 溢出的文字省略号显示

###  4.1 white-space

~~~
white-space:normal ；默认处理方式

white-space:nowrap ；　强制在同一行内显示所有文本，直到文本结束或者遭遇br标签对象才换行。
~~~

###  4.2 text-overflow 文字溢出

~~~
text-overflow : clip ；不显示省略标记（...），而是简单的裁切 

text-overflow：ellipsis ； 当对象内文本溢出时显示省略标记（...）
~~~

### 4.3 总结三步曲

~~~css
  /*1. 先强制一行内显示文本*/
      white-space: nowrap;
  /*2. 超出的部分隐藏*/
      overflow: hidden;
  /*3. 文字用省略号替代超出的部分*/
      text-overflow: ellipsis;
~~~

##  5. ==CSS精灵技术==（sprite) 重点

### CSS精灵技术

###  5.1 为什么需要精灵技术

为了有效地减少服务器接受和发送请求的次数，提高页面的加载速度。

### 5.2 精灵技术讲解

多个icon放到一个设计图上，从服务器加载。==background-position==定位

我们需要使用CSS的

* background-image、
* background-repeat
* background-position属性进行背景定位，
* 其中最关键的是使用background-position 属性精确地定位。

##  6. 滑动门

<img src="https://tva1.sinaimg.cn/large/00831rSTly1gd3nivecvoj30xq0dcdi1.jpg" />

###  滑动门核心技术

核心技术就是利用CSS精灵（主要是背景位置）和 盒子padding撑开宽度, 以便能适应不同字数的导航栏。

一般的经典布局都是这样的：

```html
<li>
  <a href="#">
    <span>导航栏内容</span>
  </a>
</li>
```

css样式

~~~css
* {
      padding:0;
      margin:0;

    }
    body{
      background: url(images/wx.jpg) repeat-x;
    }
    .father {
      padding-top:20px;
    }
    li {
      padding-left: 16px;
      height: 33px;
      float: left;
      line-height: 33px;
      margin:0  10px;
      background: url(./images/to.png) no-repeat left ;
    }
    a {
      padding-right: 16px;
      height: 33px;
      display: inline-block;
      color:#fff;
      background: url(./images/to.png) no-repeat right ;
      text-decoration: none;
    }
    li:hover,
     li:hover a {
      background-image:url(./images/ao.png);
    }
~~~

==精灵技术总结==： 

1. a 设置 背景左侧，padding撑开合适宽度。    
2. span 设置背景右侧， padding撑开合适宽度 剩下由文字继续撑开宽度。
3. 之所以a包含span就是因为 整个导航都是可以点击的。


## 7. 拓展@

### 7.1 margin负值之美

### margin负值之美

#### 1). 负边距+定位：水平垂直居中

一个绝对定位的盒子， 利用  父级盒子的 50%，  然后 往左(上) 走 自己宽度的一半 ，可以实现盒子水平垂直居中。

#### 2). 压住盒子相邻边框 



### 7.2 CSS三角形之美

#### css三角

~~~css
 div {

 	width: 0; 

    height: 0;
    line-height:0；
    font-size: 0;
	border-top: 10px solid red;

	border-right: 10px solid green;

	border-bottom: 10px solid blue;

	border-left: 10px solid #000; 

 }

~~~

 <img src="https://tva1.sinaimg.cn/large/00831rSTly1gd3nj0opzhj307b06kwec.jpg" />

1. 我们用css 边框可以模拟三角效果
2. 宽度高度为0
3. 我们4个边框都要写， 只保留需要的边框颜色，其余的不能省略，都改为 transparent 透明就好了
4. 为了照顾兼容性 低版本的浏览器，加上 font-size: 0;  line-height: 0;


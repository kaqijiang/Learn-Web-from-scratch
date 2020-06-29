## CSS总结如下  [详情](02css/01-CSS初识.md)

### 初识CSS

> - CSS(Cascading Style Sheets)  ，通常称为CSS样式表或层叠样式表（级联样式表）
> - CSS以HTML为基础，提供了丰富的功能，如字体、颜色、背景的控制及整体排版等，而且还可以针对不同的浏览器设置不同的样式。
>
> **引入方式**
>
> - 行内式（内联样式）
>
>   `<div style="color: red; font-size: 12px;">青春不常在，抓紧谈恋爱</div>`
>
> - 内嵌样式表
>
>   ```html
>   <style>
>   	 div {
>   	 	color: red;
>   	 	font-size: 12px;
>   	 }
>   </style>
>   ```
>
> - 外部样式表（外链式）推荐
>
>   ```html
>   <head>
>     <link rel="stylesheet" type="text/css" href="css文件路径">
>   </head>
>   ```
>
>   | 样式表     | 优点                     | 缺点                     | 使用情况       | 控制范围           |
>   | ---------- | ------------------------ | ------------------------ | -------------- | ------------------ |
>   | 行内样式表 | 书写方便，权重高         | 没有实现样式和结构相分离 | 较少           | 控制一个标签（少） |
>   | 内部样式表 | 部分结构和样式相分离     | 没有彻底分离             | 较多           | 控制一个页面（中） |
>   | 外部样式表 | 完全实现结构和样式相分离 | 需要引入                 | 最多，强烈推荐 | 控制整个站点（多） |

### 基础选择器

> **选择器**：选中对应标签的方式，用来操作HTML标签或者修改样式。
>
> `h1 {}	.class {}	#id {}	*{}` 分别对应:标签选择器，类选择器，ID选择器，通字符选择器

### 复合选择器

> - `.className h2 后代`
> - `.className>h2 子代只选儿子`
> - `.className.h2 交集（且）`
> - `.className,h2 相同（和）`
> - `:link 伪类link visited hover active`

### 标签显示模式

> **block**
>
> - `独占一行`
> - `宽度默认为父容器100%，宽、高、内外边距可控`
> - `容器盒子，可以放行内及块元素`
>
> **inline**
>
> - `<a>、<strong>、<b>、<em>、<i>、<del>、<s>、<ins>、<u>、<span>`
> - `显示在一行上，可以一行显示多个`
> - `默认宽度为内容本身,宽高设置无效`
> - `只能容纳文本及其他行内元素`
>
> **inline-block**
>
> - `<img />、<input />、<td>`
> - `一行可以显示多个，会有空白缝隙`
> - `默认宽度为内容本身,宽高可设置`

### CSS字体/背景样式

> **font属性**
>
> `font-size	font-family	font-weight	font-style`
>
> **font综合设置**
>
> ```css
> 选择器 { font: font-style  font-weight  font-size/line-height  font-family;}
> ```
>
> - 使用font属性时，必须按上面语法格式中的顺序书写，不能更换顺序，各个属性以**空格**隔开。
> - 其中不需要设置的属性可以省略（取默认值），但必须保留font-size和font-family属性，否则font属性将不起作用。
>
> **CSS外观属性**
>
> `color	text-align	line-height	text-indent	text-decoration`
>
> **CSS背景**
>
> - `background-color: white; 颜色`
> - `background-image : url(images/demo.png); 图片`
> - `background-repeat: repeat | no-repeat | repeat-x | repeat-y  平铺`
> - `background-position : length || length 位置`
> - `background-attachment : scroll | fixed 滚动`
> - `background: 背景颜色 背景图片地址 背景平铺 背景滚动 背景位置;  他们没有顺序;`
> - `background: transparent url(image.jpg) repeat-y  scroll center top ;`
> - `background: rgba(0, 0, 0, 0.3); 透明`

**CSS行高**

> 顶线-中线-基线-底线  上下基线距离是行高
>
> **单行文本垂直居中**：文字的行高等于盒子的高度
>
> 

**CSS三大特性**

> 层叠性、继承性、优先级

**CSS优先级**

> | 标签选择器             | 计算权重公式 |
> | ---------------------- | ------------ |
> | 继承或者 *             | 0,0,0,0      |
> | 每个元素（标签选择器） | 0,0,0,1      |
> | 每个类，伪类           | 0,0,1,0      |
> | 每个ID                 | 0,1,0,0      |
> | 每个行内样式 style=""  | 1,0,0,0      |
> | 每个!important  重要的 | ∞ 无穷大     |

### 盒子模型

> **什么是盒子？**
>
> - 盒子可以理解为一个ps图层，可以存放其他图层或者文字，图片等。
> - 盒子模型有元素的内容、边框（border）、内边距（padding）、和外边距（margin）组成。
> - 盒子内容与边框的距离是内边距（类似单元格的 cellpadding)
> - 盒子与盒子之间的距离是外边距（类似单元格的 cellspacing）
> - border : border-width || border-style || border-color 例如 border: 1px solid red;  没有顺序  
> - padding属性用于设置内边距。 **是指 边框与内容之间的距离。**
> - 高度 ：Element Height = content height + padding + border （Height为内容高度）
> - 宽度 ：Element Width = content width + padding + border （Width为内容宽度）
> - padding会撑大盒子，如果不想撑大盒子，不要设置宽度。
>
> **块级盒子水平居中**
>
> - .header{ width:960px; margin:0 auto;}
> - 固定宽度，左右margin设置为0；
>
> **文字居中和盒子居中区别**
>
> - 盒子内的文字水平居中是  text-align: center,  而且还可以让 行内元素和行内块居中对齐//图片
> - 块级盒子水平居中  左右margin 改为 auto 
>
> **插入图片和背景图片区别**
>
> - 插入图片移动依赖padding margin
> - 背景图片移动依赖background-position
>
> **外边距合并**
>
> - 相邻块元素垂直外边距的合并
>
>   - 当上下相邻的两个块元素相遇时，如果上面的元素有下外边距margin-bottom
>   - 下面的元素有上外边距margin-top，则他们之间的垂直间距不是margin-bottom与margin-top之和
>   - **取两个值中的较大者**这种现象被称为相邻块元素垂直外边距的合并（也称外边距塌陷）。
>
>    <img src="https://tva1.sinaimg.cn/large/00831rSTly1gcy5a61pfbj30e008lq2t.jpg" />
>
>   **解决方案：尽量给只给一个盒子添加margin值**。
>
> - 嵌套块元素垂直外边距的合并（塌陷）
>
>   - 对于两个嵌套关系的块元素，如果父元素没有上内边距及边框
>   - 父元素的上外边距会与子元素的上外边距发生合并
>   - 合并后的外边距为两者中的较大者
>
>    <img src="https://tva1.sinaimg.cn/large/00831rSTly1gcy5a9aa9jj30e005fwec.jpg" />
>
>   **解决方案：**
>
>   1. 可以为父元素定义上边框。
>   2. 可以为父元素定义上内边距
>   3. 可以为父元素添加overflow:hidden。
>
> - 去掉列表默认的样式： list-style: none;
>
> - 圆角：border-radius: 50%; border-radius: 左上角 右上角  右下角  左下角;
>
> - 阴影：box-shadow:水平阴影 垂直阴影 模糊距离（虚实）  阴影尺寸（影子大小）  阴影颜色  内/外阴影；
>
> - 两个属性是必须写的。其余的可以省略。
>
> - 外阴影 (outset) 是默认的 想要内阴影可以写  inset 
>
> - ```css
>   div {
>   			width: 200px;
>   			height: 200px;
>   			border: 10px solid red;
>   			/* box-shadow: 5px水平位置 5px垂直位置 3px模糊距离 4px阴影尺寸 rgba(0, 0, 0, .4)颜色;  */
>   			/* box-shadow:水平位置 垂直位置 模糊距离 阴影尺寸（影子大小） 阴影颜色  内/外阴影； */
>   			box-shadow: 0 15px 30px  rgba(0, 0, 0, .4);			
>   }
>   ```

### CSS布局

> 标准流 浮动 定位

#### 标准流

> - **块级元素**会独占一行，**从上向下**顺序排列；
>   - 常用元素：div、hr、p、h1~h6、ul、ol、dl、form、table
> - **行内元素**会按照顺序，**从左到右**顺序排列，碰到父元素边缘则自动换行；
>   - 常用元素：span、a、i、em等

#### 浮动

> 浮动 float 让多个盒子(div)水平排列成一行， 改变为行内块 清除浮动-==脱标==-不影响前面的标准流。
>
> - 浮动会脱标，所以给浮动盒子增加一个标准流的父类盒子。
>
> 1). 浮动元素与父盒子的关系
>
> - `子盒子的浮动参照父盒子对齐`
> - `不会与父盒子的边框重叠，也==不会超过父盒子的内边距==`​
>
> 2). 浮动元素与兄弟盒子的关系
>
> 在一个父级盒子中，如果**前一个兄弟盒子**是：
>
> - **浮动**的，那么**当前盒子**会与前一个盒子的顶部对齐；
> - **普通流**的，那么**当前盒子**会显示在前一个兄弟盒子的下方。 
>
> 3). 清除浮动
>
> ```css
> //伪元素
> .clearfix:after {  
>   content: ""; display: block; height: 0; clear: both; visibility: hidden;  
> }   
> 
> .clearfix {*zoom: 1;}   /* IE6、7 专有 */
> 
> //双伪元素
> .clearfix:before,.clearfix:after { 
>   content:"";
>   display:table; 
> }
> .clearfix:after {
>  clear:both;
> }
> .clearfix {
>   *zoom:1;
> }
> ```

#### 定位

> 将盒子**定**在浏览器的某一个**位**置——CSS 离不开定位，特别是后面的 js 特效。
>
> **定位模式 	 `选择器 { position: 属性值; }`
>
> | 值         |          语义          | 解释                                                         |
> | ---------- | :--------------------: | ------------------------------------------------------------ |
> | `static`   | **静态**定位（占位置） | 元素的默认定位方式，无定位的意思                             |
> | `relative` | **相对**定位（占位置） | 相对于自己原来在标准流中位置来移动的                         |
> | `absolute` |      **绝对**定位      | 元素以带有定位的父级元素来移动位置，没有则浏览器             |
> | `fixed`    |      **固定**定位      | 只认浏览器的可视窗口 —`浏览器可视窗口 + 边偏移属性` 来设置的位置 |
>
> `父类/爷类如果是绝对定位，子类是相对，父/爷哪个有定位以哪为准，没有则取浏览器。`子绝父相
>
> `移动left top right bottom`
>
> `定位居中 = right50% 负数一半`显示隐藏
>
> **堆叠顺序**
>
> - `z-index` 只能应用于**相对定位**、**绝对定位**和**固定定位**的元素。默认值是 0，数值越大，盒子越靠上
>
> **总结**
>
> - 脱标的最好都需要有一个不脱标的父盒子。

### 元素的显示与隐藏

#### display

> - 不保留位置
>
> ```css
> display: none 隐藏对象
> 
> display：block 除了转换为块级元素之外，同时还有显示元素的意思。
> ```

#### visibility

> - 保留位置
>
> ```css
> visibility：visible ; 　对象可视
> 
> visibility：hidden; 　  对象隐藏
> ```

#### overflow

> - 清除浮动
> - 隐藏超出内容，隐藏掉,  不允许内容超过父盒子。
>
> ```
> visible   | 不剪切内容也不添加滚动条                
> hidden    | 不显示超过对象尺寸的内容，超出的部分隐藏掉 
> scroll    | 不管超出内容否，总是显示滚动条           
> auto      | 超出自动显示滚动条，不超出不显示滚动条    
> ```

### CSS样式

#### 鼠标样式

> ```css
> 	<li style="cursor:default">我是小白</li>
>   <li style="cursor:pointer">我是小手</li>
>   <li style="cursor:move">我是移动</li>
>   <li style="cursor:text">我是文本</li>
>   <li style="cursor:not-allowed">我是禁止</li>
> ```

#### 轮廓线 outline

> ```css
>  outline : outline-color ||outline-style || outline-width 
>  //最常用
>  <input  type="text"  style="outline: 0;"/>
> ```

#### 防止拖拽文本域resize

> ```css
> <textarea  style="resize: none;"></textarea>
> ```

#### vertical-align 垂直对齐

> - 有宽度的块级元素居中对齐，是margin: 0 auto;
> - 让文字居中对齐，是 text-align: center;
> - vertical-align : baseline |top |middle |bottom 
>
> **去除图片底侧空白缝隙**
>
> - 原因：
>
>   图片或者表单等行内块元素，底线会和父级盒子的基线对齐。就是图片底侧会有一个空白缝隙。
>
> - 解决的方法就是：  
>
>   - 给img vertical-align:middle | top| bottom等等。  让图片不要和基线对齐。
>   - 给img 添加 display：block; 转换为块级元素就不会存在问题了。

#### 溢出的文字省略号显示

> ```css
> /*1. 先强制一行内显示文本*/
>       white-space: nowrap;
>   /*2. 超出的部分隐藏*/
>       overflow: hidden;
>   /*3. 文字用省略号替代超出的部分*/
>       text-overflow: ellipsis;
> ```

### CSS精灵

> 精灵图就是，多个图片放到一个图上，排开。
>
> **使用技术**
>
> * background-image、
> * background-repeat
> * background-position属性进行背景定位，
> * 其中最关键的是使用background-position 属性精确地定位。

### 切图

> - 文件--打开 --  可以打开 我们要测量的图片
> - ctrl+r 可以打开标尺  或者  视图 --  标尺
> - 右击标尺，  把里面的单位改为  像素  
> - ctrl+ 加号 键  可以 放大  视图  ctrl+ 减号 缩小视图
> - 按住空格键，  鼠标可以 变成小手 ，拖动 ps 视图
> - 用选区 拖动  可以 测量 大小 
> - ctrl+ d  可以取消选区  或者旁边空白处点击一下也可以取消选区
>
> <img src="https://tva1.sinaimg.cn/large/00831rSTly1gd3j0f6gbej30nl0c8mxp.jpg" />
>
> **文件格式**
>
> 1. jpg图像格式： 
>   JPEG（.JPG）对色彩的信息保留较好，高清，颜色较多，我们产品类的图片经常用jpg格式的
> 2. gif图像格式：
>   GIF格式最多只能储存256色，所以通常用来显示简单图形及字体，但是可以保存透明背景和动画效果
> 3. png图像格式
>   是一种新兴的网络图形格式，结合了GIF和JPEG的优点，具有存储形式丰富的特点，能够保持透明背景
> 4. PSD图像格式
>   PSD格式是Photoshop的专用格式，里面可以存放图层、通道、遮罩等多种设计草稿。 
>
> **切图**
>
> 1). 用切片选中图片
>
> * 利用切片工具手动划出
>
> * 图层菜单---新建基于图层的切片
>
> * 利用辅助线 来切图 --    基于参考线的切片 
>
>
> 2). 导出切片
>
>   文件菜单   -- 存储为web设备所用格式 ----   选择  我们要的图片格式 ----  点存储  ---   别忘了选中的切片
>
> **辅助线和切片使用及清除**
>
> - 视图菜单-- 清除 辅助线/ 清除切片
>
> **插件**
>
> - cutterman 切图插件
> - 蓝湖 在线标注


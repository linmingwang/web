# web

# 001.Flex布局

Flex（Flexible Box）布局 称为 "弹性布局"，可以为网页的布局提供最大的灵活性，取代了往常的 浮动（float） 布局，并且任何一个容器都可以设置 Flex 布局。
注：设置 Flex 布局后，子元素的 Float 布局将失效

# Flex布局

 Flex（Flexible Box）布局 称为 "弹性布局"，可以为网页的布局提供最大的灵活性，取代了往常的 浮动（float） 布局，并且任何一个容器都可以设置 Flex 布局。
 **注：设置 Flex 布局后，子元素的 Float 布局将失效**

## Flex中的四大概念

> **容器：** 如果给一个标签添加`display:flex;`，那么这个标签就是一个容器
>  **项目：** 在容器中的直接子元素叫项目（一定是 ***直接*** 子元素）
>  **主轴：** 项目的默认排序方向就是主轴（默认横向排列，一个容器可以有多根主轴）
>  **交叉轴：** 和主轴垂直的那个轴，就是交叉轴
>
> ------
>
> 
>
> ![图片加载失败!](https://gitee.com/gitee_fanjunyang/JueJin/raw/master/images/Flex_%E5%B8%83%E5%B1%80%E6%95%99%E7%A8%8B_12.png)
>
> 
>
> ------
>
> 
>
> ![图片加载失败!](https://gitee.com/gitee_fanjunyang/JueJin/raw/master/images/Flex_%E5%B8%83%E5%B1%80%E6%95%99%E7%A8%8B_1.png)

## 容器的属性

**Flex-direction | Flex-wrap | Flex-flow | justify-content | align-items | align-content**

------

1. Flex-direction（属性决定主轴的方向）

> **`flex-direction：row | row-reverse | column | column-reverse;`**
>
> > - row（默认值）：主轴为水平方向，起点在左端
> >
> > - row-reverse：主轴为水平方向，起点在右端
> >
> > - column：主轴为垂直方向，起点在上端
> >
> > - column-reverse：主轴为垂直方向，起点在下端
> >
> >   ![图片加载失败!](https://gitee.com/gitee_fanjunyang/JueJin/raw/master/images/Flex_%E5%B8%83%E5%B1%80%E6%95%99%E7%A8%8B_2.png)

1. Flex-wrap(属性决定项目排不下时如何换行)

> **`flex-wrap：nowrap | wrap | wrap-reverse;`**
>
> > - norwrap（默认）：不换行
> >
> > - wrap：换行，第一行在上方
> >
> > - wrap-reverse：换行，第一行在下方
> >
> >   ![图片加载失败!](data:image/svg+xml;utf8,<?xml version="1.0"?><svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="800" height="600"></svg>)

3.Flex-flow（属性是 flex-direction 和 flex-wrap 的简写形式）

> - **`flex-flow: flex-direction || flex-wrap;`**

4.justify-content(处理项目外的 富余空间)

> - **`justify-content：flex-start | flex-end | center | space-between | space-around;`**
>
> > - flex-start；（默认值），项目左对齐
> >
> > - flex-end：项目右对齐
> >
> > - center： 项目居中
> >
> > - space-between：项目两端对齐，项目之间的间隔都相等
> >
> > - space-around：每个项目两侧的间隔相等
> >
> >   ![图片加载失败!](data:image/svg+xml;utf8,<?xml version="1.0"?><svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="800" height="600"></svg>)

5.align-items(属性决定项目在交叉轴上如何对齐)

> - **`align-items：stretch | flex-start | flex-end | center | baseline;`**
>
> > - stretch（默认值）：如果项目未设置高度或设为auto，将占满整个容器的高度
> >
> > - flex-start：交叉轴的起点对齐
> >
> > - flex-end：交叉轴的终点对齐
> >
> > - center：交叉轴的中点对齐
> >
> > - baseline：项目的第一行文字的基线对齐
> >
> >   ![图片加载失败!](data:image/svg+xml;utf8,<?xml version="1.0"?><svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="800" height="600"></svg>)
>
> **注:必须给当前的容器设置高度才会起作用**

6.align-content（属性决定了多根主轴的对齐方式）

> - **`align-content：stretch | flex-start | flex-end | center | space-between | space-around;`**
>
> > - stretch（默认值）：轴线占满整个交叉轴
> >
> > - flex-start：与交叉轴的起点对齐
> >
> > - flex-end：与交叉轴的终点对齐
> >
> > - center：与交叉轴的中点对齐
> >
> > - space-between：与交叉轴两端对齐，轴线之间的间隔平均分
> >
> > - space-around：每根轴线两侧的间隔都相等
> >
> >   ![图片加载失败!](https://gitee.com/gitee_fanjunyang/JueJin/raw/master/images/Flex_%E5%B8%83%E5%B1%80%E6%95%99%E7%A8%8B_6.png)

## 项目的属性

**order | flex-grow |flex-shrink | flex-basis | flex | align-self**

------

> 1. order（属性定义项目的排列顺序。数值越小，排列越靠前，默认为0）
>
> > ```
> > order: <integer>;
> > ```
> >
> > ![图片加载失败!](https://gitee.com/gitee_fanjunyang/JueJin/raw/master/images/Flex_%E5%B8%83%E5%B1%80%E6%95%99%E7%A8%8B_7.png)

> 1. flex-grow（属性定义项目的放大比例，默认为0，即如果存在剩余空间，也不放大）
>
> > ```
> > flex-grow：<number>;
> > ```
> >
> > ![图片加载失败!](https://gitee.com/gitee_fanjunyang/JueJin/raw/master/images/Flex_%E5%B8%83%E5%B1%80%E6%95%99%E7%A8%8B_8.png)

> 1. flex-shrink（属性定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小）
>
> > ```
> > flex-shrink: <number>;
> > ```
> >
> > ![图片加载失败!](https://gitee.com/gitee_fanjunyang/JueJin/raw/master/images/Flex_%E5%B8%83%E5%B1%80%E6%95%99%E7%A8%8B_9.png)

> 1. flex-basis(属性定义了在分配多余空间之前，项目占据的主轴空间。浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为auto，即项目的本来大小,也可以设置 `xx px`,项目将占据固定空间)
>
> > ```
> > flex-basis: <length> | auto;
> > ```
> >
> > ![图片加载失败!](https://gitee.com/gitee_fanjunyang/JueJin/raw/master/images/Flex_%E5%B8%83%E5%B1%80%E6%95%99%E7%A8%8B_10.png)

> 1. flex（属性是flex-grow, flex-shrink 和 flex-basis的简写，默认值为0 1  auto。后两个属性可选）
>
> > ```
> > flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ];
> > ```

> 1. align-self（属性允许单个项目有与其他项目不一样的对齐方式，可覆盖align-items属性。默认值为auto，表示继承父元素的align-items属性，如果没有父元素，则等同于stretch）
>
> > ```
> > align-self: auto | stretch | flex-start | flex-end | center | baseline;
> > ```
> >
> > ![图片加载失败!](https://gitee.com/gitee_fanjunyang/JueJin/raw/master/images/Flex_%E5%B8%83%E5%B1%80%E6%95%99%E7%A8%8B_11.png)

# 002.HTML5+CSS3新特性

https://www.w3school.com.cn/html5/index.asp

https://www.w3school.com.cn/css3/index.asp

# 003.盒子模型

# CSS 盒子模型

## 盒子模型(Box Model)

一般的标签都是盒子，但是除了极个别的标签(例如:img、input标签)不是盒子

## 盒子模型的属性

- width 盒子内容的宽度
- height 盒子内容的高度
- margin 盒子的外边距
- padding 盒子的内边距
- border 盒子的边框
- background 盒子背景

**盒子模型示意图**

![图片加载失败!](https://gitee.com/gitee_fanjunyang/JueJin/raw/master/images/%E7%9B%92%E6%A8%A1%E5%9E%8B_1.png)



### 标准盒子模型、IE盒子模型

**目前所学的知识中，以标准盒子模型为准**
标准盒子模型：

![图片加载失败!](https://gitee.com/gitee_fanjunyang/JueJin/raw/master/images/%E7%9B%92%E6%A8%A1%E5%9E%8B_%E6%A0%87%E5%87%86_2.jpg)


IE盒子模型：

![图片加载失败!](https://gitee.com/gitee_fanjunyang/JueJin/raw/master/images/%E7%9B%92%E6%A8%A1%E5%9E%8B_IE_3.jpg)



**标准盒子模型和IE盒子模型的区别**

- 在 标准盒子模型中，width 和 height 指的是内容区域的宽度和高度。增加内边距、边框和外边距不会影响内容区域的尺寸，但是会增加元素框的总尺寸
- IE盒子模型中，width 和 height 指的是内容区域+border+padding的宽度和高度。

## width height 属性

**可以设置 任何长度单位 百分比(占父元素的百分比)**

- 块级标签可以设置width和height
- 行内标签不可以设置width和height（它的width由内容决定，height由font-size决定）

**盒子的宽度并不是内容的宽度**
以上两个盒模型如下：

![图片加载失败!](data:image/svg+xml;utf8,<?xml version="1.0"?><svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="800" height="600"></svg>)


**真实宽度=左右padding+左右border+width**



**如果想保持一个盒子的真实占有宽度不变，那么加width的时候就要减padding。加padding的时候就要减width**

**height属性和width属性类似，这里不做过多介绍**

------

## margin 属性

margin属性表示**盒子**与**盒子**之间的**距离**，并且分 上、下、左、右 四个方向（margin-top、margin-bottom、margin-left、margin-right）可以单独进行设置

**可以设置 任何长度单位 百分比 负值**

> **margin的值复制**
> 有时，我们会输入一些重复的值，通过值复制，可以不必重复地输入数字
> **CSS 定义了一些规则，允许为外边距指定少于 4 个值**
>
> - 如果缺少左外边距的值，则使用右外边距的值
> - 如果缺少下外边距的值，则使用上外边距的值
> - 如果缺少右外边距的值，则使用上外边距的值
>
> 给出一张图片，便于理解
>
> ![图片加载失败!](https://gitee.com/gitee_fanjunyang/JueJin/raw/master/images/%E7%9B%92%E6%A8%A1%E5%9E%8B_5.png)
>
> 换句话说，如果为外边距指定了 3 个值，则第 4 个值（即左外边距）会从第 2 个值（右外边距）复制得到。如果给定了两个值，第 4 个值会从第 2 个值复制得到，第 3 个值（下外边距）会从第 1 个值（上外边距）复制得到。最后一个情况，如果只给定一个值，那么其他 3 个外边距都由这个值（上外边距）复制得到。
>
> 不常用

利用这个简单的机制，您只需指定必要的值，而不必全部都应用 4 个值

- margin对于块级标签在四个方向上都有作用，对于行内标签，只在水平方向上有效，在垂直方向上无效
- margin可以设置负值

> **margin设置的数值数**
>
> - 设置**一个**数值(margin:10px;)，则上下左右都用这一个数值(10px)
> - 设置**两个**数值(margin:5px 10px;)，则上下为第一个数值(5px)，左右为第二个数值(10px)
> - 设置**三个**数值(margin:5px 10px 15px;)，则上为第一个数值(5px)，左右为第二个数值(10px),下为第三个数值(15px)
> - 设置**四个**数值(margin:5px 10px 15px 20px)，则上右下左依次为(5px 10px 15px 20px)

**margin重叠(坍塌)** **重难点**

> 前提条件：块级标签，垂直方向
>
> ------
>
> - 兄弟元素之间的重叠：上面盒子的 margin-bottom 和下面盒子的 margin-top 重叠，中间的margin值大小是取大优先
>
> **解决方法：**
>
> 1. 给 块级标签 变成 行内块标签
> 2. 使用 浮动（浮动元素是不会坍塌的，具体内容请参考我别的文章）
>
> ------
>
> - 父子元素之间的重叠：父元素设置的 margin-top 和父元素中第一个子元素设置的 margin-top 会重叠
>
> **解决方法：**
> 1.给父元素设置border-top （如果不想要边框，可以使用transparent，设置成透明）
> 2.给父元素设置padding-top
> 3.把 块级标签 变成 行内块标签

**margin经典用法，使块级标签水平居中 `margin:0 auto;`**

------

## padding 属性

padding （内边距，补白），表示**内容**与**border**之间的**距离**，并且和margin一样，也分 上、下、左、右 四个方向（padding-top、padding-bottom、padding-left、padding-right）可以单独进行设置
**可以设置 任何长度单位 百分比 但是不允许设置负值**

**关于 值复制 和 设置的数值数，和margin一样，可以参考margin**

**应用：**
调整 内容 与 border 之间的距离（一定要参考上面的盒子模型，注意盒子的大小）

> 注：如果重复设置了一边或者多边的属性值
> 例如：
> `padding:10px;`
> `padding-left:20px;`
> 则 padding 左边距 实际为20px，所以总结出来一句话 **小属性 层叠 大属性**（margin 也适用这句话）

------

## border 属性

border属性可以设置盒子的边框

**边框三要素：像素(粗细)、线型、颜色**

颜色如果不写，默认是黑色。另外两个属性不写，则显示不出来边框。线型自行百度，一般只用(solid 实线、dotted 点划线、dashed 虚线 )

**border拆分**
border 是一个大综合属性（例如：border:1px solid red;）就是四个边框，宽度为1px、实线、红色线

有两大种拆分方式：

- 按三要素拆开：border-width、border-style、border-color。（一个border属性是由三个小属性综合而成的）
- 按方向拆开：border-top、border-right、border-bottom、border-left。

**一个border属性，是由三个小属性综合而成的。如果某一个小属性后面是空格隔开的多个值，那么就是上右下左的顺序**

> 例如：
> `border:10px solid red;`
> 按三要素拆：
> `border-width:10px;` //边框宽度 `border-style:solid;` //线型 `border-color:red;` //颜色。
> 按方向拆：
> `border-top:10px solid red;` `border-right:10px solid red;` `border-bottom:10px solid red;` `border-left:10px solid red;`

**同样也适用那句话 小属性 层叠 大属性**

------

## background 属性

> background-color 设置背景色(接受任何合法的颜色值，比如：red、#a7a7a7、rgb)
>
> ------
>
> background-color 不能继承，其默认值是 transparent。transparent 有“透明”之意。也就是说，如果一个元素没有指定背景色，那么背景就是透明的，这样其祖先元素的背景才能可见。

> background-image 把图像放入背景(默认值是 none，表示背景上没有放置任何图像)
>
> ------
>
> 如果需要设置一个背景图像，必须为这个属性设置一个 URL 值
> background-image 也不能继承。事实上，所有背景属性都不能继承

> background-repeat 对背景图像是否平铺进行设置(默认在水平垂直方向上都平铺，属性值为repeat)
>
> ------
>
> - repeat 水平垂直方向上都平铺
> - repeat-x 水平方向上平铺
> - repeat-y 垂直方向上平铺
> - no-repeat 不平铺

> background-position 设置 图像在背景中的位置
> 可以使用一些关键字、百分数值、长度值
> **关键字**
>
> > | 单一关键字 | 等价的关键字                   |
> > | ---------- | ------------------------------ |
> > | center     | center center                  |
> > | top        | top center 或 center top       |
> > | bottom     | bottom center 或 center bottom |
> > | right      | right center 或 center right   |
> > | left       | left center 或 center left     |
>
> **百分数值**
>
> > 百分数值的表现方式更为复杂(这里不做过多解释，想了解自行百度)
> > 如果只提供一个百分数值，所提供的这个值将用作水平值，垂直值将假设为 50%。这一点与关键字类似。
> > background-position 的默认值是 0% 0%，在功能上相当于 top left。这就解释了背景图像为什么总是从元素内边距区的左上角开始平铺，除非您设置了不同的位置值。
>
> **长度值**
>
> > 长度值解释的是元素内边距区左上角的偏移。偏移点是图像的左上角。
> > 注意，这一点与百分数值不同，因为偏移只是从一个左上角到另一个左上角。也就是说，图像的左上角与 background-position 声明中的指定的点对齐。

> background-attachment 背景关联
>
> ------
>
> 如果文档比较长，那么当文档向下滚动时，背景图像也会随之滚动。当文档滚动到超过图像的位置时，图像就会消失。 可以通过 background-attachment 属性防止这种滚动。通过这个属性，可以声明图像相对于可视区是固定的（fixed），因此不会受到滚动的影响
> background-attachment 属性的默认值是 scroll，也就是说，在默认的情况下，背景会随文档滚动。

**background 简写属性，作用是将背景属性设置在一个声明中**
**background:background-color background-image background-repeat background-attachment background-position**

------

## 对于盒子模型的注意点

- width属性默认值为auto，块级元素的贪婪性和行内元素的懒惰性
- 有些标签有默认的padding值和margin值,所以一般写网页时都会重置样式 *{margin:0;padding:0;}

# 004.如何让一个div水平居中？

https://www.cnblogs.com/sarah-wen/p/10844404.html

# 005.如何让一个div水平垂直居中？

https://www.cnblogs.com/sarah-wen/p/10844404.html

# 006.如何清除浮动？

通常在公共的css样式中定义一个清除浮动的类。

.clearfix{ clear:both; content:''; display:block; width: 0; height: 0; visibility:hidden; }

# CSS 浮动(Float) 清除浮动

## 说浮动之前，先说一些别的东西

### 标准文档流

宏观地讲，我们的web页面和photoshop等设计软件有本质的区别：web页面的制作，是个“流”，必须从上而下，像“织毛衣”。而设计软件，想往哪里画个东西，都能画
**标准文档流的特性**
1.空白折叠现象(无论多少个空格、换行、tab，都会折叠为一个空格)
2.高矮不齐，底边对齐
3.自动换行，一行写不满，换行写

### 行内元素和块级元素

**行内元素和块级元素的区别：(非常重要)**
行内元素

- 与其他行内元素并排；
- 不能设置宽、高。默认的宽度，就是文字的宽度

块级元素

- 霸占一行，不能与其他任何元素并列
- 能接受宽、高。如果不设置宽度，那么宽度将默认变为父亲的100%

**块级元素和行内元素的相互转换**
我们可以通过`display`属性将块级元素和行内元素进行相互转换

- `display:inline;`可以把块级元素转换为行内元素
- `display:block;`可以把行内元素转换为块级元素

再说一个：`display:inline-block;`可以把行内元素或块级元素设置为 行内块元素 ，可以并排显示，并且可以设置块级元素的属性

标准流里面的限制非常多，导致很多页面效果无法实现。如果我们现在就要并排、并且就要设置宽高，那该怎么办呢？办法是：脱离 标准文档流！

css中一共有三种手段，使一个元素脱离标准文档流：

- 浮动
- 绝对定位
- 固定定位

## 浮动(float)

**float:left | right | none ;(默认不浮动none)**

### 浮动的元素脱标

- 在一个父元素内部，如果一个元素浮动了，那么它就脱离了标准文档流，后面的元素就让向上排
- 浮动并没有完全地脱离了标准文档流（但是它具有破坏性，所以可以用Flex布局，想了解Flex布局，请参考我的 Flex布局教程），如果后面的元素内部有文字，这些文字会环绕在浮动元素的周围，产生字围效果



![图片加载失败!](https://gitee.com/gitee_fanjunyang/JueJin/raw/master/images/%E6%B5%AE%E5%8A%A8_1.png)


上图中，在默认情况下，两个div标签是上下进行排列的。现在由于float属性让上图中的第一个div标签出现了浮动，于是这个标签在另外一个层面上进行排列。而第二个div还在自己的层面上遵从标准流进行排列。



**一旦一个元素浮动了，那么，将能够并排了，并且能够设置宽高了。无论它原来是个行内元素，还是块级元素**

### 浮动的元素互相贴靠

如果给三个div均设置了float: left;属性之后，然后设置宽高。当改变浏览器窗口大小时，可以看到div的贴靠效果，如下图

![图片加载失败](https://user-gold-cdn.xitu.io/2019/7/17/16bfd8efcb2a420a?imageslim)


上图显示，3号如果有足够空间，那么就会靠着2号。如果没有足够的空间，那么会靠着1号。如果没有足够的空间靠着1号，3号自己去贴左墙，不过3号贴左墙的时候，并不会往1号里面挤，而是往1号下面排列，如果小到极限时，里面的浮动的子元素宽度是不会改变的



**同样，float还有一个属性值是right，这个和属性值left是对称的。**

### 浮动的元素有“字围”效果

来一张图，如下：

![图片加载失败!](data:image/svg+xml;utf8,<?xml version="1.0"?><svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="800" height="600"></svg>)


上图中，我们发现：div挡住了p，但不会挡住p中的文字，形成“字围”效果。



### 收缩

收缩：一个浮动的元素，如果没有设置width，那么将自动收缩为内容的宽度（这点非常像行内元素） 如图：

![图片加载失败!](data:image/svg+xml;utf8,<?xml version="1.0"?><svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="800" height="600"></svg>)

上图中，div本身是块级元素，如果不设置widh，它会单独霸占整行；但是，设置div浮动后，它会收缩



**如果一个元素没有设置高度，它的高度是靠里面的内容撑起来的。如果父元素内部元素都浮动了，那么会造成父元素的高度塌陷**

### 同步

如果多个元素浮动了，那么这们就会并排显示，如果都是同一个方向的浮动，它们会紧紧地贴在一起(自己动手写一下)

**如果一个元素浮动了，先向上移动，直到贴靠到父元素的边界，接着，如果是左浮动，就向左移动，直到移动到父元素的左边界，如果是向右浮动，就向右移动，直接移动到父元素的右边界**

**补充：**

![图片加载失败!](https://gitee.com/gitee_fanjunyang/JueJin/raw/master/images/%E6%B5%AE%E5%8A%A8_5.png)


上图所示，将para1和para2设置为浮动，它们是div的儿子。此时para1+para2的宽度小于div的宽度。效果如上图所示。可如果设置para1+para2的宽度大于div的宽度，我们会发现，para2掉下来了：

![图片加载失败!](https://gitee.com/gitee_fanjunyang/JueJin/raw/master/images/%E6%B5%AE%E5%8A%A8_6.png)



### 补充

- 浮动只对父元素和以后的元素有影响，对之前的元素没有影响

## 浮动的清除(重点)

元素浮动会造成的影响：

> 对父元素的影响(父元素的高度坍塌)
> 解决办法：
>
> > - `加高法` 给父元素设置高度，就不会塌陷(简单，基本不用，大部分情况下父元素的高度是需要子元素撑起来的)
> > - `overflow:hidden` 简单，使用overflow:hidden父元素的高度会随着子元素的高度变化而变化。overflow:hidden本职工作是用来处理溢出 在使用过程中，需要注意子元素如果想要超出父元素高度，此时overflow:hidden就不适合了
> > - `隔墙法(clear:both)` 在所有子元素后面加一个空的div 在这个div上面加clear:both，就可以清除浮动（分为内墙法和外墙法，本质上一样），clear:both是专业清除浮动的

> 对后面兄弟元素造成的影响(兄弟元素会向上移动)
> 解决办法：
>
> > - 在受影响的元素上面的加 clear:both（参考对父元素的影响）

**项目中最常用的清除浮动的办法** 利用伪元素 `after`
其实很简单,就是写一个清除浮动的类,哪个元素想要清除浮动,只需加上 class="clearfix" 就可以,非常简单
清除浮动类的代码:

```css
.clearfix:after{
	content="";
	display:block;
	clear:both;
	height:0;
}
```

# 007.css3实现三栏布局，左右固定，中间自适应？

> 圣杯布局/双飞翼布局

```html
 <style>
        * {
            margin: 0;
            padding: 0;
        }
        .middle,
        .left,
        .right {
            position: relative;
            float: left;
            min-height: 130px;
        }
        .container {
            padding: 0 220px 0 200px;
            overflow: hidden;
        }
        .left {
            margin-left: -100%;
            left: -200px;
            width: 200px;
            background: red;
        }
        .right {
            margin-left: -220px;
            right: -220px;
            width: 220px;
            background: green;
        }
        .middle {
            width: 100%;
            background: blue;
            word-break: break-all;
        }
    </style>
</head>
<body>
    <div class='container'>
        <div class='middle'></div>
        <div class='left'></div>
        <div class='right'></div>
    </div>
</body>
复制代码
```

# 008.CSS中 link 和@import 的区别是什么？ 

- link属于HTML标签，而@import是CSS提供的页面被加载的时，link会同时被加载，而@import引用的CSS会等到页面被加载完再加载
- import只在IE5以上才能识别，而link是HTML标签，无兼容问题
- link方式的样式的权重 高于@import的权重.

# 009.transition和animation的区别？

Animation和transition大部分属性是相同的，他们都是随时间改变元素的属性值，他们的主要区别是transition需要触发一个事件才能改变属性， 而animation不需要触发任何事件的情况下才会随时间改变属性值，并且transition为2帧，从from .... to，而animation可以一帧一帧的。

# 010.CSS优先级？

```
不同级别：总结排序：!important > 行内样式>ID选择器 > 类选择器 > 标签 > 通配符 > 继承 > 浏览器默认属性
	1.属性后面加!import 会覆盖页面内任何位置定义的元素样式
	2.作为style属性写在元素内的样式
	3.id选择器
	4.类选择器
	5.标签选择器
	6.通配符选择器（*）
	7.浏览器自定义或继承
**同一级别：后写的会覆盖先写的**
复制代码
```

# 011.使元素消失的方法?

visibility:hidden、display:none、z-index=-1、opacity：0

1.opacity：0,该元素隐藏起来了，但不会改变页面布局，并且，如果该元素已经绑定了一些事件，如click事件也能触发
 2.visibility:hidden,该元素隐藏起来了，但不会改变页面布局，但是不会触发该元素已经绑定的事件
 3.display:node, 把元素隐藏起来，并且会改变页面布局，可以理解成在页面中把该元素删掉

# 012.为什么css放在顶部而js写在后面？

1.浏览器预先加载css后，可以不必等待HTML加载完毕就可以渲染页面了
 2.其实HTML渲染并不会等到完全加载完在渲染页面，而是一边解析DOM一边渲染。
 3.js写在尾部，主要是因为js主要扮演事件处理的功能，一方面很多操作是在页面渲染后才执行的。另一方面可以节省加载时间，使页面能够更加的加载，提高用户的良好体验

但是随着JS技术的发展，JS也开始承担页面渲染的工作。比如我们的UI其实可以分被对待，把渲染页面的js放在前面，时间处理的js放在后面

# 013.理解BFC吗？

BFC 即 Block Formatting Contexts (块级格式化上下文)。
 具有 BFC 特性的元素可以看作是隔离了的独立容器，容器里面的元素不会在布局上影响到外面的元素，并且 BFC 具有普通容器所没有的一些特性。
 通俗一点来讲，可以把 BFC 理解为一个封闭的大箱子，箱子内部的元素无论如何翻江倒海，都不会影响到外部。

# 常见布局

在讲 BFC 之前，我们先来了解一下常见的布局方案，有三种常见布局方案:

## 普通布局

在普通布局中，元素按照其在 HTML 中的先后位置从左往右，从上往下布局。
 在这个过程中，行内元素水平排列，直到当行被占满然后换行。块级元素则会被渲染为完整的一个新行，除非另外指定，否则所有元素默认都是普通流定位，也可以说，普通流中元素的位置由该元素在 HTML 文档中的位置决定。

## 浮动布局

在浮动布局中，元素首先按照普通流的位置出现，然后根据浮动的方向尽可能的向左边或右边偏移，其效果与印刷排版中的文本环绕相似。

## 绝对定位

在绝对定位布局中，元素会整体脱离普通文档流，因此绝对定位元素不会对其兄弟元素造成影响，而元素具体的位置由绝对定位的坐标决定。

# 什么是BFC?

Formatting context(格式化上下文) 是 W3C CSS2.1 规范中的一个概念。它是页面中的一块渲染区域，并且有一套渲染规则，它决定了其子元素将如何定位，以及和其他元素的关系和相互作用。

那么什么是BFC呢？

BFC 即 Block Formatting Contexts (块级格式化上下文)，它属于上述定位方案的普通流。

**具有 BFC 特性的元素可以看作是隔离了的独立容器，容器里面的元素不会在布局上影响到外面的元素，并且 BFC 具有普通容器所没有的一些特性。**

通俗一点来讲，可以把 BFC 理解为一个封闭的大箱子，箱子内部的元素无论如何翻江倒海，都不会影响到外部。

# BFC的特性

## 怎么触发BFC？

只要元素满足下面任一条件即可触发 BFC 特性：

- HTML 根元素
- 浮动元素：float 除 none 以外的值
- 绝对定位元素：position (absolute、fixed)
- display 为 inline-block、table-cells、flex
- overflow 除了 visible 以外的值 (hidden、auto、scroll)

## BFC的约束规则

- 内部的Box会在垂直方向上一个接一个的放置
- 垂直方向的距离有margin决定(属于同一个BFC的两个相邻Box的margin会发生重叠，与方向无关)
- 每个元素的margin box的左边， 与包含块border box的左边相接触(对于从左往右的格式化，否则相反)。即使存在浮动也是如此
- BFC的区域不会与float的元素区域重叠
- 计算BFC的高度时，浮动子元素也参与计算
- BFC就是页面上的一个隔离的独立容器，容器里面的子元素不会影响到外面元素，反之亦然

# BFC的作用

## 防止垂直 margin 重叠

**同一个 BFC 下外边距会发生折叠**

```
<style>
	div {
		width: 100px;
		height: 100px;
		background: lightblue;
		margin: 100px;
	}
</style>

<body>
    <div></div>
    <div></div>
</body>
复制代码
```



![图片加载失败!](https://gitee.com/gitee_fanjunyang/JueJin/raw/master/images/CSS%E4%B8%AD%E7%9A%84BFC_1.jpg)



从效果上看，因为两个 div 元素都处于同一个 BFC 容器下 (这里指 body 元素) 所以第一个 div 的下边距和第二个 div 的上边距发生了重叠，所以两个盒子之间距离只有 100px，而不是 200px。

首先这不是 CSS 的 bug，我们可以理解为一种规范，**如果想要避免外边距的重叠，可以将其放在不同的 BFC 容器中。**

```
<style>
	div {
		width: 100px;
		height: 100px;
		background: lightblue;
		margin: 100px;
	}

	.container {
		overflow: hidden;
	}
</style>

<div class="container">
    <div></div>
</div>
<div class="container">
    <div></div>
</div>
复制代码
```

这时候，两个盒子边距就变成了 200px



![图片加载失败!](https://gitee.com/gitee_fanjunyang/JueJin/raw/master/images/CSS%E4%B8%AD%E7%9A%84BFC_2.jpg)



## 清除元素内部浮动

浮动的元素会脱离普通文档流，

来看例子：

```
<style>
	.div1 {
		border: 1px solid #000;
	}

	.div2 {
		width: 100px;
		height: 100px;
		background: #eee;
		float: left;
	}
</style>  

<div class="div1">
	<div class="div2"></div>
</div>
复制代码
```



![图片加载失败!](https://gitee.com/gitee_fanjunyang/JueJin/raw/master/images/CSS%E4%B8%AD%E7%9A%84BFC_3.png)



由于容器内元素浮动，脱离了文档流，所以容器只剩下 2px 的边距高度。如果使触发容器的 BFC，那么容器将会包裹着浮动元素。

```
<style>
	.div1 {
		border: 1px solid #000;
		overflow: hidden;
	}

	.div2 {
		width: 100px;
		height: 100px;
		background: #eee;
		float: left;
	}
</style>

<div class="div1">
	<div class="div2"></div>
</div>
复制代码
```



![图片加载失败!](https://gitee.com/gitee_fanjunyang/JueJin/raw/master/images/CSS%E4%B8%AD%E7%9A%84BFC_4.png)



## 阻止元素被浮动元素覆盖

先来看一个文字环绕效果：

```
<style>
	.div1 {
		height: 100px;
		width: 100px;
		float: left;
		background: lightblue;
	}

	.div2 {
		width: 200px;
		height: 200px;
		background: #eee;
	}
</style>  

<div class="div1">
	我是一个左浮动的元素
</div>
<div class="div2">
	我是一个没有设置浮动,也没有触发 BFC 元素。我是一个没有设置浮动,也没有触发 BFC 元素。
</div>

复制代码
```



![图片加载失败!](https://gitee.com/gitee_fanjunyang/JueJin/raw/master/images/CSS%E4%B8%AD%E7%9A%84BFC_5.png)



这时候其实第二个元素有部分被浮动元素所覆盖(背景被覆盖)，(但是文本信息不会被浮动元素所覆盖) 如果想避免元素被覆盖，可触第二个元素的 BFC 特性，在第二个元素中加入 `overflow: hidden`，就会变成：

```
<style>
	.div1 {
		height: 100px;
		width: 100px;
		float: left;
		background: lightblue;
	}

	.div2 {
		width: 200px;
		height: 200px;
		background: #eee;
		overflow: hidden;
	}
</style>

<div class="div1">
	我是一个左浮动的元素
</div>
<div class="div2">
	我是一个没有设置浮动,也没有触发 BFC 元素。我是一个没有设置浮动,也没有触发 BFC 元素。
</div>
复制代码
```



![图片加载失败!](https://gitee.com/gitee_fanjunyang/JueJin/raw/master/images/CSS%E4%B8%AD%E7%9A%84BFC_6.png)



这个方法**可以用来实现两列自适应布局**，这时候左边的宽度固定，右边的内容自适应宽度(去掉上面右边内容的宽度)。

# 014.Less、sass等的使用方法

Less和sass等是 CSS 预处理语言，它扩展了 CSS 语言，增加了变量、Mixin、函数等特性和嵌套写法，使 CSS 更易维护和扩展。

# 015.简单说一下网页的层叠等级(z-index)？

其实一个网页是分为好多层的，具体层次和层叠等级如下图：

![图片加载失败!](https://gitee.com/gitee_fanjunyang/JueJin/raw/master/images/%E9%9D%A2%E8%AF%95_HTMLCSS_1.png)



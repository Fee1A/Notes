# <font face='微软雅黑' color='#090'>css3</font>

## flex布局

### 弹性盒子及其属性

#### 弹性盒子flex-box

兼容性</br>
&emsp;&emsp;display:flex -- IE11</br>
&emsp;&emsp;display:-ms-flex -- IE10

兼容前缀:`-webkit-`、`-moz-`

引入弹性盒子布局模型的目的是**提供一种更加有效的方式来对一个容器中的子元素进行排列、对齐和分配空白空间**

弹性盒子由弹性容器(flex container)和弹性子元素(flex item)构成

弹性容器通过设置display为flex或inline-flex将其定义为弹性容器

弹性容器内包含了一个或多个弹性子元素

**弹性容器外以及弹性子元素内是正常渲染，弹性盒子只定义了弹性子元素如何在弹性盒子内布局**

弹性子元素通常在弹性盒子内一行显示，默认情况每个容器只有一行

注意，设为flex布局以后，子元素的float、clear和vertical-align属性将失效

#### direction

修改排列方式

值:
    rtl(right-to-left)：从右向左的横向排列

作用元素：
    父元素及以上，如body

#### flex-direction(排列方向)

`flex-direction`属性指定了主轴的方向，进而指定了弹性子元素在父容器中的排列方向

语法:&emsp;flex-direction: row | row-reverse | column | column-reverse

值:</br>
&emsp;&emsp;row: 横向从左到右排列，默认的排列方式</br>
&emsp;&emsp;row-reverse: 横向从右到左排列</br>
&emsp;&emsp;column: 纵向从上到下排列</br>
&emsp;&emsp;column-reverse: 纵向从下到上排列

作用元素:</br>
&emsp;&emsp;display为flex的弹性容器，也就是父元素

#### justify-content(主轴内容对齐)

`justify-content`属性应用在弹性容器上，把弹性项沿着弹性容器的主轴线对齐

语法:&emsp;justify-content: flex-start | flex-end | center | space-between | space-around

值:</br>
&emsp;&emsp;flex-start: 弹性项目向行头紧挨着填充，默认值。第一个弹性项的main-start外边距边线被放置在该行的main-start边线，而后续弹性项依次平齐摆放。可以理解为左对齐，也就是float：left实现的位移效果</br>
&emsp;&emsp;flex-end: 弹性项目向行尾紧挨着填充。第一个弹性项的main-end外边距边线被放置在该行的main-end边线，而后续弹性项依次平齐摆放。可以理解为右对齐排列
&emsp;&emsp;center: 弹性项目居中紧挨着填充</br>
&emsp;&emsp;space-between: 弹性项目平均分布在该行上如果剩余空间为负或者只有一个弹性项，则该值等同于flex-start。否则，第1个弹性项的外边距和行的main-start边线对齐，而最后1个弹性项的外边距和行的main-end边线对齐，然后剩余的弹性项分布在该行上，相邻项目的间隔相等。</br>
&emsp;&emsp;space-around: 弹性项目平均分布在该行上，两边留有一般的间隔空间。如果剩余空间为负或者只有一个弹性项，则该值等同于center。否则，弹性项目沿该行分布，且彼此间隔相等（比如是20px），同时首尾两边和弹性容器之间留有一半的间隔（1/2*20px=10px）

作用元素:</br>
&emsp;&emsp;弹性盒子，即父元素

效果图:
![linear](http://www.runoob.com/wp-content/uploads/2016/04/2259AD60-BD56-4865-8E35-472CEABF88B2.jpg)

#### align-items(纵轴内容对齐)

`align-items`属性设置或检索弹性盒子元素在侧轴(纵轴)方向上的对齐方式

语法:&emsp;align-items: flex-start | flex-end | center | baseline | stretch

值:</br>
&emsp;&emsp;flex-start: 弹性盒子元素的侧轴（纵轴）起始位置的边界紧靠住该行的侧轴起始边界，即贴着顶部，弹性元素高度若无设置则自适应自身内容</br>
&emsp;&emsp;flex-end: 弹性盒子元素的侧轴（纵轴）起始位置的边界紧靠住该行的侧轴结束边界，即贴着底部，元素高度同start</br>
&emsp;&emsp;center: 弹性盒子元素在该行的侧轴（纵轴）上居中放置。（如果该行的尺寸小于弹性盒子元素的尺寸，则会向两个方向溢出相同的长度）</br>
&emsp;&emsp;baseline(???): 如弹性盒子元素的行内轴与侧轴为同一条，则该值与'flex-start'等效。其它情况下，该值将参与基线对齐</br>
&emsp;&emsp;stretch: 如果指定侧轴大小的属性值为'auto'，则其值会使项目的边距盒的尺寸尽可能接近所在行的尺寸，但同时会遵照'min/max-width/height'属性的限制

效果图:
![linear](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071011.png)

#### flex-wrap(换行方式)

`flex-wrap`属性用于指定弹性盒子的子元素换行方式

语法:&emsp;flex-wrap: nowrap | wrap | wrap-reverse | initial | inherit

值:</br>
&emsp;&emsp;nowrap: 默认，弹性容器为单行，即不换行。该情况下弹性子项可能会溢出容器</br>
&emsp;&emsp;wrap: 弹性容器为多行，即换行。该情况下弹性子项溢出的部分会被放置到新行，子项内部会发生断行</br>
&emsp;&emsp;wrap-reverse: 反转wrap排列，从左下向右下排，若溢出则换行至上一行</br>
&emsp;&emsp;initial: 设置CSS属性为它的默认值(IE不支持此关键字)</br>
&emsp;&emsp;inherit: 继承

wrap-reverse效果图:
![linear](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071009.jpg)

#### align-content(多根轴线的纵轴对齐)

`align-content`属性用于设置多根轴线(各行)的对齐方式，如果项目只有一根轴线(一行)，则该属性不起作用，因为flex布局默认只有一行，所以一般配合flex-wrap使用呈现多行的表现形式

语法:&emsp;align-contet: flex-start | flex-end | center | stretch | space-between | space-around

值:</br>
&emsp;&emsp;stretch: 默认，各行会伸展以占用剩余的空间。</br>
&emsp;&emsp;flex-start: 各行向弹性盒容器的起始位置堆叠</br>
&emsp;&emsp;flex-end: 各行向弹性盒容器的结束位置堆叠，注意此时弹性子元素的排列方式不会改变，改变的只是行的位置，所以很容易出现的情况为，元素1和元素2排列在第一行，元素3在第二行，这两行堆叠在弹性盒子底部</br>
&emsp;&emsp;center: 各行向弹性盒容器的中间位置堆叠，行的高度不会改变，改变的只是行的位置，即使弹性盒子高度不够，行也会居中向上下两边等高溢出</br>
&emsp;&emsp;space-between: 各行在弹性盒容器中平均分布，与stretch相同却又略有不同，stretch是类似正常文档流的等份分割容器全部高度后，将弹性子元素分别置于每份的左上角。而space-between则是垂直方向上，顶部和底部的元素各自贴着顶部和底部，中间行的元素位于行的垂直中间。相同点在于都对弹性盒子的所有容量进行了等份分割，不同点在于每份中弹性子元素的排列方式有所不同</br>
&emsp;&emsp;space-around: 各行在弹性盒容器中平均分布，两端保留子元素与子元素之间间距大小的一半。在垂直方向上，两端元素与两端保留一定间距，余下的高度等份分割，弹性子元素的排列方式同space-between

效果图:
![linear](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071012.png)

#### flex-flow

`flex-flow`属性是flex-direction和flex-wrap属性的简写，默认值为row nowrap

```
.xxx {
  flex-flow: row || nowrap;
}
```

### 弹性子元素属性

#### 排序

语法: order: (int)

值: 用整数值来定义排列顺序，按数值大小排列，可以为负数

#### 对齐

设置"margin"值为"auto"值，自动获取弹性容器中剩余的空间。所以设置垂直方向margin值为"auto"，可以使弹性子元素在弹性容器的两上轴方向都完全居中。

例如三个弹性子元素同一行排列，第一个子元素设置margin-right:auto，则会将此行中剩余的空间放置在第一个子元素的右边。

#### 完美的居中

用margin:auto就能使得弹性子元素在两轴方向上完美居中，默认flex为块级元素显示，也可以用inline-flex使其以行内元素形式显示，从而具有更多的兼容性

#### align-self

`align-self`属性用于设置弹性子元素自身在纵轴方向上的对齐方式，他允许弹性子元素与其他弹性子元素又不一样的对齐方式，可覆盖align-items属性，默认值为auto。除了auto值，其他值的含义都和`align-items`完全一致

语法：&emsp;align-self: auto | flex-start | flex-end | center | baseline | stretch

值：</br>
&emsp;&emsp;auto: 如果'align-self'的值为'auto'，则其计算值为元素的父元素的'align-items'值，如果其没有父元素，则计算值为'stretch'

#### flex

`flex`属性用于指定弹性子元素如何分配空间，是flex-grow，flex-shrink，flex-basis的简写，默认值为0 1 auto。后两个属性可选

语法:&emsp;flex: auto | initial | none | inherit | [ flex-grow ] || [ flex-shrink ] || [ flex-basis ]

值:</br>
&emsp;&emsp;auto: 计算值为 1 1 auto</br>
&emsp;&emsp;initial: 计算值为 0 1 auto</br>
&emsp;&emsp;none: 计算值为 0 0 auto</br>
&emsp;&emsp;inherit: 从父元素继承</br>
&emsp;&emsp;[ flex-grow ]: 定义弹性盒子元素的扩展比率</br>
&emsp;&emsp;[ flex-shrink ]: 定义弹性盒子元素的收缩比率</br>
&emsp;&emsp;[ flex-basis ]: 定义弹性盒子元素的默认基准值

#### flex-grow

`flex-grow`属性定义项目(弹性子元素)的放大比例，默认为0，即如果存在剩余空间，也不放大。

如果所有项目的flex-grow属性都为1，则它们将等分剩余空间（如果有的话）。如果一个项目的flex-grow属性为2，其他项目都为1，则前者占据的剩余空间将比其他项多一倍

#### flex-shrink

`flex-shrink`属性定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小

如果所有项目的flex-shrink属性都为1，当空间不足时，都将等比例缩小。如果一个项目的flex-shrink属性为0，其他项目都为1，则空间不足时，前者不缩小。

负值对该属性无效。

#### flex-basis

`flex-basis`属性定义了在分配多余空间之前，项目占据的主轴空间(水平方向上的空间)。浏览器根据这个属性，计算主轴是否有多余空间，他的默认值是auto，即项目的本来大小

它可以设为跟width和height属性一样的值，则项目将占据固定空间

#### box

box是flex之前的草案命名，阶段逐次为box--flexbox--flex，所以flex是最新的也是之后推荐的命名，但因为有之前的草案命名以及各浏览器版本对其的兼容问题，所以推荐使用统一的兼容写法
```
.flex-container {
  display: -moz-box;
  display: -ms-flexbox;
  display: -webkit-box;
  display: -webkit-flex;
  display: box;
  display: flexbox;
  display: flex;
  width: 100%;
  height: 100%;
  background-color: gray;
}
```

### 总结

`主轴`:&emsp;X轴

`交叉轴`:&emsp;Y轴

`项目`:&emsp;单个弹性子元素

`justify-content`:&emsp;控制主轴上所有项目的对齐

`align-items`:&emsp;控制交叉轴上所有项目的对齐

`align-self`:&emsp;控制交叉轴上的单个flex item的对齐

`align-content`:&emsp;控制“多条主轴”的flex items在交叉轴的对齐

`flex-direction`:&emsp;改变主轴方向

## 定位相关

### position属性

#### 新增值 center

偏移定位以拥有relative的父元素的中心点为参考点，盒子在其包含容器中垂直水平居中

兼容性: 均不兼容

#### 新增值 page(???)

元素在分页媒体或者区域块内，元素的包含块始终是初始包含块，否则取决于每个absolute模式。

兼容性: 均不兼容

#### 新增值 sticky

对象在常态时遵循常规文档流，就像是relative和fixed的合体，当在屏幕中时按常规文档流排版，当卷动到屏幕外时则表现如fixed

兼容性:<br/>
&emsp;&emsp;火狐32.0+<br/>
&emsp;&emsp;Safari 6.1-9.0(-webkit)<br/>
&emsp;&emsp;iOS Safari 6.0-9.0(-webkit)<br/>
&emsp;&emsp;其他均不兼容

### 绝对定位元素新增属性 clip(待替换)

依据上-右-下-左的顺序提供自对象左上角为(0,0)坐标计算的四个偏移数值，其中任一数值都可用auto替换，即此边不剪切

`clip: rect(0 auto 35px 10px)`

注意: **必须将position的值设为absolute或者fixed，此属性方可使用**

注意: **这个属性将被废弃，推荐使用`clip-path`代替**

## 布局相关

### display属性

block与inline与inline-block的区别：<br>
&emsp;&emsp;block使元素以块级元素的形式显示，特点为宽度默认独占一行，是父容器的100%，可以设置高度宽度行高以及顶和底边距
&emsp;&emsp;inline则使元素以内联元素的形式显示，特点为高度和宽度总是自适应于他包含的内容，作为行内元素与其他元素在同一行，他的高度宽度行高及顶部和底部边距都是不可设置的
&emsp;&emsp;inline-block可以称为行内块元素，特点大致与inline相同，不同点在于**他可以自己设置高度宽度行高以及顶部和底部边距**


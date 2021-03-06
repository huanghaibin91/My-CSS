# My-CSS #


----------

CSS全程层叠样式表，


**CSS重要知识点**

- 选择器
- 盒模型
- 定位
- 浮动
- 动画
- 层叠
-
-

## CSS知识点收集 ##

- animation帧动画，动画关键帧之间不是以渐变而是以帧变化`animation-timing-function: steps(n, start/end)`，n表示两帧之间动画变化数量为正整数，start，从结尾一帧开始，end，以开始一帧到结束；

- CSS长度单位：

	- 相对长度单位，相对字体长度单位，如`em`和`rem`；相对视区长度单位，如`vh、 vw、 vmin 和vmax`；
	- 绝对长度单位，最常见的就是`px`，CSS权威指南定义px为相对长度单位，MDN定义为绝对，存疑；

- HTML标签嵌套表
	![](./image/HTML.jpg)
- CSS盒模型是围绕在HTML元素周围的定义Border(边界)，padding(内边距)和margin(外边距)的矩形空间

- 普通文档流中的元素，百分比高度值要想起作用，其父级必须有一个可以生效的高度值。普通流中height为100%是父元素的内容高度，绝对定位情况下height为100%时会加上padding

- CSS 盒模型 (Box Model) 规定了元素框处理元素内容、内边距、边框和外边距的方式

- text-align应用于块级元素，left、right、center会导致元素中的文本分别左对齐、右对齐和居中。

- Line-height文本极限之间的距离，而不是字体的大小，它确定了将各个元素框的高度增加或减少多少。Line-height和字体大小之间的差就是行间距。 导航栏中设置line-height与导航栏宽度一致可以在改变鼠标移入导航栏时，导航栏的CSS状态改变宽度范围一致。line-heigh可以从父元素继承，当line-height为一个具体数时，子元素的line-height会直接使用之歌值，所以最好是指定一个缩放因子，这样元素的值会是与缩放因子计算后的值

- 内容竖直排列，块级元素会自动下一行排列，内联元素可以设置为display:block;变成块状元素后竖直排列；设置为同一个方向浮动，但是浮动后面的内容会填补多余的内容区，导致排列混乱；利用自定义列表，列表内容自动竖直排列。

- 在页面设计中，先不要设置页面高度，这样可以留足内容扩展后所需要的高度。

- 可以利用border-radius来制作简单圆形。

- absolute的特性包裹性、破坏性。

- 不受relative限制的absolute，行为表现上不使用top、right、bottom、left任何一个属性或使用auto作为值。设置为absolute定位后用margin来调节位置，无依赖的绝对定位。

- 动画尽量作用在绝对定位元素上。

- 绝对定位元素会脱离文档流，后面的会位于前者之上，两者相遇，后者能覆盖前者。

- 绝对定位元素z-index无依赖，如果只有一个绝对定位元素，自然不需要z-index，自动覆盖普通元素；如果两个绝对定位，控制DOM流的前后顺序达到需要的覆盖效果，依然无z-index；如果多个绝对定位交错，非常少见，z-index：1控制；如果非弹框类绝对定位元素z-index>2，必定z-index冗余，请优化。

- 绝对定位方向是对立的（如：left vs right,top vs bottom）的时候，结果不是瞬时位移，而是身体的爆裂拉伸。也就是说，很多情况下，absolute的拉伸和width/height是可以相互替代的。（IE7+支持）

- float的设计初衷是：为了文字环绕效果。浮动元素不会合并外边距。浮动元素会生成一个块级框，它会像块级元素一样摆放和表现

- 浮动具有破坏性，会让父元素高度塌陷。当浮动作用于图片后，图片的inline boxes被破坏，inline boxes高度线丢失，无法与文字这类inline boxes同行排列，于是图片从inline boxes链上脱离出来，受自身方向属性的影响，靠左显示，由于其“包裹性”，宽度实体依旧存在，加之与文字处于同一文档流中，文字不会与图片位置重叠，加上图片没有inline boxes，高度丢失，所以文字居顶显示形成新的inline boxes高度包络线。

- 浮动后元素脱离文档流，可能导致父元素不占据空间，导致父元素没有高度 

- 清除浮动。CSS中的clear属性，表示框的哪些边不应该挨着浮动元素，在使用clear清理浮动原理是，浏览器在元素顶上添加足够的外边距，使元素的顶边缘垂直下降到浮动框下边，这样的现象可以解决父元素高度问题。
		

		.clearfix::after {
			content: '.';
			height: 0;
			visibility: hidden;
			display: block;
			clear: both;
		}

- line-height，行高，两行文字基线之间的距离。

- 所有内联元素的样式表现都与行内框盒子模型有关。（内容区域、内联盒子、行框盒子、包含盒子）内联元素的高度是由行高决定的。

- 18高度的表现不是行高，而是内容区域和行间距。内容区域高度+行间距=行高，行高决定内联盒子高度，行间距墙头草，可大可小（甚至负值），保证高度正好等同于行高。

- 图片在文字中，图片的底边基线与文字基线对齐，所以看着上边空余和下边行高空余。

- margin与可视尺寸（clientWidth），适用于没有设定width、height的普通block水平元素，只适用于水平方向尺寸。

- Margin与占据尺寸，block、inline-block水平元素均适用，与有没有设定width、height无关，适用于水平方向和垂直方向。滚动容器上下留白，要用margin值，padding值不会产生滚动留白。

- Margin与百分比单位，普通元素的百分比margin都是相对于容器宽度计算的。绝对定位元素的百分比margin是相对于第一个定位祖先元素（relative、absolute、fixed）的宽度计算的。

- Margin元素没有设置width或height，也会自动填充容器。当设置元素宽度后，再设置元素margin属性左右为auto，元素将会居中显示。

- Margin重叠block水平元素，只发生在垂直方向，margin重叠的计算规则是：正正取大值，正负值相加，负负最负值。

- Margin无效的情况：一、inline水平元素的垂直margin无效；二、margin重叠可能会导致margin值看似无效的情况；三、display：table-cell/display：table-row等声明的margin无效；四、绝对定位元素非定位方向（非定位方向就是未设置定位值的方向）的margin值“无效”；六、内联元素inline导致的margin失效。

- relative从以下限制absolute，限制left、top、right、bottom定位；限制z-index层级；限制超越overflow。

- Relative定位是相对于自身的，定位偏移量是从自身当前位置为基准。Relative定位无侵入，relative定位不会影响其他元素。

- 在相对定位top/bottom和left/right对立属性同时存在时，以top和left为准，矛盾时以这两个属性为准。

- Relative的最小化影响原则，指的是尽量降低relative属性对其他元素或布局的潜在影响。①尽量避免使用relative，absolute定位不依赖relative。②relative最小化，减少relative影响的元素数量。

- z-index属性制定了元素及其子元素的“Z顺序”，而“Z顺序”可以决定当元素发生覆盖的时候，哪个元素在上面。通常一个较大z-index值得元素会覆盖较低的那一个。

- Z-index数值有auto、整数值和inherit（继承）。基本特性：支持负值；支持CSS3 animation动画；在CSS 2.1时代，需要和定位元素配合使用。

- 如果不考虑CSS3，只有定位元素（relative、absolute、fixed、sticky）才能让z-index有作用。

- * 后来居上，后面的位置重叠时会覆盖前面的。
	* 哪个大，哪个上。

- 如果定位元素z-index发生嵌套：祖先优先原则，前提是z-index是数值，不是auto。

- 层叠上下文是HTML元素中的一个三维概念，表示元素在Z轴上离人更近了（相当于在更上面）。层叠水平，层叠上下文的每个元素都有一个层叠水平，决定了同一个层叠上下文中元素在Z轴上的显示顺序，遵循“后来居上”和“谁大谁上”的层叠准则。层叠水平和z-index不是一个东西，普通元素也有层叠水平。

- 层叠上下文可以嵌套，组合成一个分层次的层叠上下文；每个层叠上下文和兄弟元素独立：当进行层叠变化或渲染的时候，只需要考虑后代元素；每个层叠上下文是自成体系的：当元素的内容被层叠后，整个元素被认为是在父层的层叠顺序中。
 
- 层叠顺序，元素发生层叠时候有着特定的垂直显示顺序，七阶层叠顺序。

- `<link rel="icon" type="image/ico" href="http://wickedlysmart.com/favicon.ico">``<link rel="shortcut icon" href="favicon.ico" type="image/x-icon" />`是为了指定浏览器标签地址栏的图片，利用图标工具（有很多）制作图标文件（favicon.ico）上传到网站所在的服务器的根目录下，这个文件必须是16*16大小的图标文件,如果想要收藏夹中的图标也要改变的话，那么就加上这句：`<link rel="Bookmark" href="favicon.ico" />`这个图标还可以使用png格式

- 在CSS2中`:first-letter`和`:first-line`伪元素只能应用于标记或段落之类的块级元素，而不能用于超链接等行类元素

- 所有伪元素都必须放在该伪元素选择器的最后面

- URI，统一资源标识符。URL，统一资源定位符       

- font简写时，font-style、font-weight、font-variant顺序随意，但是最后两个值必须是按顺序的font-size、font-family，且必须要有这两个值。在使用font简写属性时，所有被忽略的值都会被重置为默认值

- text-indent适用于块状元素，行内元素无法使用，这个属性可以继承

- text-align适用于块状元素的文本对齐，其中的属性值justify（两端对齐），会调整单词和字母间的间隔，使各行间的长度恰好相等

- vertical-align只适用于行内元素或替换元素，且不能继承

- padding、margin四个值：如果设定三个值，则第四个值会从第二个值复制得到 

- CSS中浮动、绝对定位会使元素脱离文档流

- div可以为块状元素进行分组，span可以为行内元素分组或标识

- `:link`和`visited`称为链接伪类，只适用于锚元素，`:hover`、`:focus`和`:actice`称为动态伪类，理论上适用于任何元素

- 行内元素可以使用水平内边距、边框和外边距调整它的水平宽度。但是，垂直内边距、边框和外边距不影响行内框的高度。因此修改行内框尺寸的唯一方法是修改行高或者水平边框、内边距和外边距

- 因为绝对定位的元素与文档流无关，所以它不影响普通流中的框。如果扩大绝对定位的框，周围的框不会重新定位。因此，尺寸的任何改变都会导致绝对定位的框产生重叠，从而破坏原有布局

- 浮动会使元素成为一个块状元素

- 浮动会让元素脱离文档流，不再影响不浮动的元素。但是框中的文本内容会受到浮动元素的影响，会围绕浮动元素排列。这种现象可以适用于文字环绕图像效果

- rgba色彩表示相对于opacity设置透明度后，文字的透明度不会改变，不会影响文字的清晰度

- 实现图像替换时可以像平常一样将文本添加到文档中，然后使用css隐藏文本并在它的位置上显示一个背景图像。这样，搜索引擎仍然可以搜索到HTML文本，而且如果禁用CSS，文本仍然会显示。但是一些比较流行的图像替换方法对屏幕阅读器是无效的，而且如果关闭图像但是打开CSS，就会出现内容缺失

- 远距离翻转是一种鼠标事件，在锚链接内嵌套一个或多个元素，然后使用绝对定位对元素分别进行定位。尽管显示在不同地方，但都是属于同一个父锚，所以可以对同一个鼠标悬停事件作出反应

- 表单信息提醒可以设置em元素放于label中然后定位

- 等高多列，使用CSS3的column属性，下面是纯CSS实现
		
		<div class="box"> // 盒子设置高度和overflow: hidden;
			<div class="col"> // 列设置一个很大的外边距和内边距，使元素超出父元素包裹
				<div>content</div>
				<div class="bottom"></div> // 将bottom设置定位到盒子底部，使之看起来多列等高
			<div>
			<div class="col">
				<div>content</div>
				<div class="bottom"></div>
			<div>
		<div>

- IE条件注释
		
		<!-- [if IE 6] // 当浏览器为IE6时，引进IE6样式表
			<link rel="stylesheet" type="text/cs" href="./css/ie6.css"></link>
		-->
- IE常见bug

	- IE6浮动双外边距bug，解决方法：将浮动元素的display改为inline

	- IE5、6，3像素文本偏移bug，当文本与浮动元素相邻时出现

	- IE6重复字符bug，一系列浮动元素的最后一个元素中的最后几个字符会在浮动元素下面重复出现

	- IE6“躲猫猫”bug，一个浮动元素后面跟一些非浮动元素，然后是一个清理元素，所有这些元素都放在一个设置了背景图像或颜色的父元素中。如果清理元素碰到了浮动元素，那么中间的非浮动元素看起来就消失了，隐藏到了父元素的背景颜色或图像后边，只有刷新彩后重新出现
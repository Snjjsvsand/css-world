#### width: auto width 的默认值

#### width: auto 的四种表现
1. 充分利用空间(fill-available)：<div> <p> 等块级元素的默认宽度 100% 于父级容器
2. 收缩与包裹(shrink-to-fit)：浮动，绝对定位 , inline-block 或 table 元素的默认宽度为 fit-content
3. 收缩到最小(minimum-content-width)：空间不够时，默认宽度为首选最小宽度 min-content，将英文按照单词分行断开，中文按字断开。
3. 最大可用宽度：很长的英文或者 white-space:no-wrap 会超出容器限制，即 max-content。


#### 尺寸分类
1. 内部尺寸：尺寸由内部元素决定
2. 外部尺寸：尺寸由外部元素决定
width: auto 中的 充分利用空间 属于外部尺寸， 其余三个属于内部尺寸。


#### 外部尺寸的流体特性
1. 正常流宽度：
块级元素的默认宽度 100% 于父级容器，具有流体性，即完全利用容器空间并且 margin/border/padding/content 内容自动分配水平空间。
很多时候不设置 width: 100% 反而符合要求，设置了会丢失流体性。
2. 格式化宽度：
非替换元素，在绝对定位时，如果设置了对立方向的属性值: left:20px;right:20px 或 top:20px;bottom:20px; 那么其宽度大小相对于最近的具有定位特性 (position != static) 的祖先元素 padding-box 计算，呈现外部尺寸，拥有流体性，水平与垂直方向自动分配 margin/border/padding/content 。


#### 内部尺寸和流体特性
1. 收缩与包裹：
  如果容器宽度大于元素的“首选最小宽度”，那么元素宽度不会超过容器宽度，并且会自动换行。
  **实现一行元素居中，多行元素居左**
2. 首选最小宽度：
  中文：每个汉字的宽度
  英文：连续的英文字符单元（终止于空格，短横线，问号及其他非英文字符，word-break:break-all可以更改英文的连续单元为每个字母
  替换元素：元素本身高度
  如果首选最小宽度大于容器宽度，那么元素宽度体现为首选最小宽度
  **实现 凹凸 效果**
3. 最大宽度：
  如果内部没有块级元素或者块级元素没有设定宽度值，则“最大宽度”实际上是最大的连
  续内联盒子的宽度。
  **水平滚动**


#### 宽度分离原则
添加外层标签设置 width，
内部标签的padding , border , margin 依靠其 width:auto 保持流体性自动分配


#### box-sizing
更改 width / height 所作用的尺寸盒子
content-box
padding-box
border-box
margin-box
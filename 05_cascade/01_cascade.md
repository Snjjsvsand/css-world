#### 层叠上下文
一个层叠上下文包含一个元素或者由浏览器一起绘制的一组元素。
层叠上下文有可能处于另一个层叠上下文中，也可能内含了其他的层叠上下文。

#### 层叠水平
层叠水平决定了元素在z轴的显示顺序，是概念性的定义。
普通元素和层叠上下文元素都有层叠水平。
对于普通元素的层叠水平探讨只在同一个层叠上下文中。
体现在实际中，元素如果处在同一层叠上下文元素中，则根据层叠顺序决定谁在前谁在后；如果不在同一层叠上下文中，则要对层叠上下文进行对比。


#### 层叠顺序
层叠顺序属于具体的规则，用来决定处于同一层叠上下文中层叠元素具体谁在前面谁在后面。
层叠元素顺序由高到低：
1. 正 z-index
2. css3新增的不依赖 z-index 的层叠上下文
  1. opacity != 1
  2. 父元素 display: flex 同时 z-index != auto
  3. transform != none
  5. filter != none
  6. isolation: isolate
  7. will-change 是属性值为上面 2～6 的任意一个
  8. 元素的-webkit-overflow-scrolling 设为 touch
2. z-index: auto (默认值) 或 z-index: 0
3. inline 内联盒子
4. float 浮动盒子
5. 块级盒子
6. 负 z-index
7. 所属层叠上下文元素的 background 与 border 

#### 创建层叠上下文
1. 页面根元素
2. z-index 为数值 （z-index: auto不创建层叠上下文）
3. css3新增的不依赖 z-index 的层叠上下文

#### 具体比较规则
1. 首先先看要比较的两个元素是否处于同一个层叠上下文中
  1.1 如果是，比较层叠顺序
  1.2 如果不在同一层叠上下文中，则比较两者所处层叠上下文元素的层叠等级，此时，如果A的层叠上下文的层叠等级高于B的，那么A中的所有元素都比B的层叠水平高，即A中的所有元素都会压盖B。
2. 当两个元素处于同一层叠上下文、层叠顺序相同时，在DOM结构中后面的元素层叠水平在前面元素之上。
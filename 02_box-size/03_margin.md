#### 元素尺寸分类
1. 元素尺寸：border-box，也称“元素偏移尺寸”,即 offsetWidth / offsetHeight。  
2. 元素内部尺寸：padding-box，也称“元素可视尺寸”,即 clientWidth / clientHeight。
3. 元素外部尺寸：margin-box，没有对应的DOM API。

#### padding与margin 与元素内部尺寸(元素可视尺寸)：
在元素设置width或者保持“包裹性”时，padding会改变元素内部尺寸。
如果元素尺寸体现为“充分利用可用空间”，margin会改变元素内部尺寸。
// **简单对比**

#### 实现两栏自适应布局（一侧定宽，一侧自适应）
**左右定宽布局**

#### 实现两端对齐布局  貌似失效了
**两端对齐布局**

#### margin 与元素外部尺寸
margin 不会影响元素垂直方向内部尺寸，但是会影响水平与垂直方向元素外部尺寸。
-margin 配合 +padding 抵消布局层影响，并且多了添加背景色的机会。

#### 实现不定高两栏背景/分割线布局
**不定高两栏布局**

#### margin 对于内联元素
内部尺寸：
  水平垂直方向都没有任何影响，内联元素的宽度呈现“包裹性”；垂直方向与padding不同，是完全没影响的。
外部尺寸：
  只有水平方向有影响，垂直方向完全没有影响。

#### margin百分比
与padding一致，水平与竖直方向都是相对于父元素的宽度计算的。


#### margin 合并发生条件
1. 块级元素，不包括浮动与绝对定位元素。
2. 只发生在垂直方向 (writing-mode 为默认值)

#### 发生场景
1. 相邻兄弟元素
2. 父级和第一个/最后一个子元素
  解决方法：
    1. 父元素设置为块级格式化上下文(BFC)
    2. 父元素设置border-top 或 padding-top(对于margin-top合并)
    3. 父元素设置border-bottom 或 padding-bottom(对于margin-bottom合并)
    4. 父元素和发生合并的元素之间添加内联元素分隔
    5. 父元素设置height / min-height / max-height
3. 空的块级元素，其自身的 margin-top 和 margin-bottom 可能发生合并
  解决空块级元素margin合并:
    1. 设置垂直 border/padding
    2. 添加内联元素
    3. 设置 height / min-height

#### margin 合并的计算规则
1. 正正取大值
2. 正负值相加
3. 负负最负值


#### margin: auto
margin 初始值为0
当元素的宽度不具有自动充满特性时，margin:auto用来自动充满空间：
1. 如果 margin 两侧都是 auto , 平分剩余空间
2. 如果一侧为定值，一侧为 auto , auto为剩余空间。
**margin-left:auto 右对齐**
垂直方向的 height 如果在 auto 时不具有外自动填充特性，则垂直方向不能触发 margin: auto , 除非 writing-mode: vertical-lr;
但是如果设置了 "格式化高度" 使其具有填充特性（详见 height.md）, 那么 margin-auto 对垂直方向也会起作用。
**实现水平垂直居中**

#### 替换元素垂直margin有效并且不会发生margin合并

#### margin 无效
.box { 
 width: 100px; 
} 
.child { 
 width: 80px; 
 margin-right: 100px; 
} 
一个普通元素，在默认流下，其定位方向是左侧以及上方，此时只有 margin-left 和 margin-top 可以影响元素的定位。父容器只有一个子元素，因此没有影响兄弟元素的说法，加上要么定宽要么定
高，右侧和底部无 margin 重叠，因此外部的元素也不会有任何布局上的影响，因此就给人“无效”的错觉。

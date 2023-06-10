#### vertical-align
默认值： baseline
取值：
  1. baseling , top , middle , bottom
  2. text-top , text-bottom
  3. sub , super
  4. 数值及百分比 , 相对于基线正值向上，负值向下偏移。

#### vertical-align 只能作用于inline , inline-block , table-cell 元素
**图片垂直居中**
**幽灵空白节点基线对齐导致容器高度超过line-height**
**幽灵空白节点基线对齐导致图片底部有空隙**

#### 解决图片底部间隙
1. 图片设置块级盒子
2. line-height 足够小使得半行距足够小
3. font-size 足够小,同时line-height设置相对font-size值
4. vertical-align 不设置 baseline

**幽灵空白节点基线对齐限制图片 margin 定位**

#### display: inline-block 基线:
if(内部没有内联元素 || overflow !== 'visible') 
  基线 = margin底边缘
else 基线 = 元素中最后一行内联元素的基线

**复杂案例**

**图标水平对齐**

#### vertical-align: middle 
可以让内联元素的真正意义上的垂直中心位置和字符 x 的交叉点对齐

**基于 vertical-align 属性的水平垂直居中弹框**


#### img元素之间的换行符会被当成空格处理 ??? 
#### 各种线
baseline 基线：内联元素 x 下边缘，非替换元素下边缘
x-height: x 的高度 单位 ex
middle: 基线向上半个 x 的高度，近似为 x 的交叉点
**ex单位配合默认基线对齐实现图标和文字天然居中**

#### 各种元素的基线
1. 内联元素，x的下边缘
2. 替换元素，元素下边缘
3. inline-block 元素
如果一个inline-block元素里面是空的，或者它本身有overflow属性，这种情况下基线是它margin的底边缘。
如果一个inline-block元素里面不是空的（比如里面有文字或者图像），则它的基线由正常流中最后一个line box的基线决定。


#### line-height
对于非替换的内联元素，其可视高度完全由 line-height 决定，padding,border对其可视高度完全无影响，即内联元素没有盒模型。

#### line-height用来决定行框盒子的高度。
内容区域：鼠标选中呈蓝色的区域，字体为宋体时，高度与 em-box 一致，其余的比em-box 稍微大一点
em-box: 高度为1em的盒子，其高度完全由font-size决定
半行距：文字上方/下方距离行框盒子上边框/下边框的距离

行距 = line-height − em-box;
半行距 = line-height - font-size >> 1;
行高只是幕后黑手，高度的表现其实是内容区域+行距
**设置line-height查看半行距**

#### line-height 不可以影响替换元素和块级元素高度
但是会影响幽灵空白节点高度！
对于纯文本元素，line-height 非常威风，直接决定了最终的高度。但是，如果同时有替换元素，则line-height 的表现一下子弱了很多，只能决定最小高度。

#### 单行文字近似垂直居中只要设置line-height就可以了
#### 多行文字近似垂直居中也可以只用line-height和vertical-align
#### display: inline-block
可以设置 vertical-align： vertical-align 用来指定行内元素（inline）或表格单元格（table-cell）元素的垂直对齐方式。
可以产生行框盒子并产生行框盒子附带的幽灵空白节点，使外部 line-height 有作用的对象。
关于行框盒子，只有当容器的内在盒子为块级盒子时，才能够容纳行框盒子，只有存在行框盒子时才会一行一行的显示，内联盒子们才会作为一行里的一部分被换行。
同时行框盒子是由一个个外在盒子是内联盒子的盒子组成的，比如 inline-block 元素就会产生行框盒子。
所以 display: inline-block 应该是既可以为父元素生成一个行框盒子，也可以容纳行框盒子，每个行框盒子都会伴随幽灵空白节点。
**设置 line-height 实现单行，多行文字垂直居中**

#### line-height 属性值
默认值：normal，normal和字体有关，字体不同取值不同 1.3左右
纯数值：font-size 的倍数
百分比：font-size 的百分比
带单位数值 px , em ...

如果使用数值作为 line-height 的属性值，那么所有的子元素继承的都是这个值；但是，如果使用百分比值或者长度值作为属性值，那么所有的子元素继承的是最终的计算值。

**line-heigt数值和百分比对比**

#### line-height 是从元素的content-box上边开始计算的
#### line-height 对内联元素生效 Of course
#### 由于幽灵空白节点的存在，line-height 总具有大值特性
解决办法：display: inline-block ，创建独立的行框盒子使该行的幽灵空白节点在该行框盒子前面。
**大值特性测试**
**display:inline-block与幽灵空白节点测试**
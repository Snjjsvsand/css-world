#### position: absolute;
绝对定位和浮动一起存在时，浮动无效。
绝对定位会块状化元素。
绝对定位元素拥有包裹性，但是其自适应最大宽度是相对于包含块的，而不是容器元素。
绝对定位元素会产生BFC。
绝对定位元素破坏文档流。
绝对定位的偏移相对于其包含块左上角。

#### 包含块
1. 根元素，即“初始包含块”，尺寸等同于浏览器大小，但并不是<html>标签
2. 对于position != relative && position != static , 包含块是容器元素的content-box
3. position: fixed; 包含块是初始包含块
4. position: absolute; 
  包含块是最近的 position != static 的祖先元素。
  如果该祖先元素是纯 inline 元素,假设给内联元素的前后各生成一个宽度为 0 的内联盒子（inline box），则这两个内联盒子的 padding box 外面的包围盒就是内联元素的包含块。
  如果没有,就是初始包含块。
  边界是 padding-box。

#### absolute 的相对特性
如果绝对定位没有设置 left/top/right/bottom, 其所在位置还是当前位置，可以看作相对定位，只是不占据流空间。无论内联还是块级元素，其位置与没应用 position: absolute; 时一样。
如果仅设置一个方向绝对定位，另外一个方向仍具有相对特性。

**小图标定位**
**表单提示信息及小星号**
**列表下拉定位**

**绝对定位相对特性配合幽灵空白节点实现水平居中**
**固定定位相对特性配合幽灵空白节点实现主结构右外侧固定定位布局**


#### absolute 和 overflow
绝对定位元素不总是被父级 overflow 属性剪裁，尤其当 overflow 在绝对定位元素及其包含块之间的时候。
如果 overflow 属性所在的元素同时绝对定位元素的包含块，绝对定位元素会被剪裁；如果 overflow 元素和绝对定位元素之间有绝对定位元素包含块，也会被剪裁。

如果 overflow 的属性值不是 hidden 而是 auto 或者 scroll，即使绝对定位元素高宽比 overflow 元素高宽还要大，也都不会出现滚动条。所以可能出现的情况：绝对定位元素不跟随滚动。

#### clip
position 属性值必须是 absolute 或者 fixed , clip 才会起作用，可以用来裁剪 fixed 定位的元素。
clip 的元素被裁减的部分被隐藏且不能相应点击，但是仍然占据空间。
clientWidth 和 clientHeight 包括样式计算的宽高都还是原来的大小。

#### absolute 的流体特性
如果绝对定位的元素设置了对立方向的定位，那么会具有类似 width: atuo 的流体性
**absolute + margin 水平垂直居中** 

#### position: relative
相对定位的偏移相对于自身进行，但是百分比的参考值仍然是包含块。
可以作为 absolute 的包含块。
默认的文档流是自上而下、从左往右，因此 top/bottom 同时使用的时候，bottom 被干掉；left/right 同时使用的时候，right 毙命。
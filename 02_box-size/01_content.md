#### 替换元素
<img> <object> <video> <iframe> <select> 等修改属性值内容就可以被替换的元素。

#### 替换元素的特性
1. 内容的外观不受CSS影响
2. 有自己的尺寸
3. 基线 baseline 是元素下边缘
4. 替换元素没有伪元素

#### 替换元素的默认 display
替换元素的默认 display 值多为 inline 或 inline-block
<img> inline
<iframe> inline
<video> inline
<select> inline-block
<input> inline-block
<button> inline-block
<textarea> inline-block

#### 替换元素尺寸
按照优先级:
1. CSS尺寸
2. HTML标签设置的尺寸
3. 固有尺寸，比如<img>固有尺寸是图片原尺寸
如果固有尺寸含有固有的宽高，并且CSS只设置了宽度或者只设置的高度，元素依然按照固有的宽高比例显示。

图片资源的固有尺寸是无法改变的,不受 CSS 宽高控制!
但是图片中的 content 替换内容默认的适配方式是填充，
即 object-fit: fill; 意为填满外部尺寸，如果设置 object-fit: none,
图片尺寸就完全不受控制。

#### 替换元素和普通元素只差一个 content 属性
**h1文字变图片**


#### content 配合伪元素
伪元素常用来清除浮动，实现**两端及垂直对齐**，放个**小图标**，以及图标字体。
attr 属性:
img::after {
  content: attr(alt);
} // 自定义HTML属性也可以

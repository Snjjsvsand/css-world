#### object-fit
object-fit 决定了替换元素的内容如何适应元素的宽高。
1. fill(default) 替换内容完全填充整个元素的 content-box ，如果宽高比与内容框不相符，则拉伸。
2. cover 替换内容保持其宽高比并且填充整个元素 content-box ，如果宽高比与内容框不相符，则裁剪。
3. contain 替换内容保持原有比例并且被缩放至宽高均不超过内容框的最大填充状态。
4. none 被替换元素保持原有尺寸
5. scale-down 内容的尺寸与 none 或 contain 中的一个相同，取决于它们两个之间谁得到的对象尺寸会更小一些

#### object-position
object-position 决定了替换元素的内容在内容框中的位置。
1. 50% 50% （default）

#### position 百分比计算方式
positionX , positionY 为左上角距离盒子左上角的坐标 （background-position: padding-box , object-position: content-box）
positionX = (容器宽度 - 图片宽度) * percentX
positionY = (容器高度 - 图片高度) * percentY

所以 background-position: 100% 100% 元素正好背景处于元素右下角 , 50% 50% 正好居中。

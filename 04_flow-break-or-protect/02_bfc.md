#### BFC 特性
概念特性： 
独立的渲染区域，BFC 内部元素不会受到外部元素影响，内部元素不会影响到外部元素的布局。
实用特性：
1. 分属于两个 BFC 的元素不会发生 margin 重叠。
2. BFC 元素不会和浮动元素重叠
3. BFC 元素高度会计算内部浮动元素高度
**容器 BFC 消除margin合并**
**BFC清除内部浮动**
**BFC配合浮动布局**

#### BFC 常见触发条件
1. <html>
2. float
3. overflow: auto / scroll / hidden
4. display: inline-block / table-cell / table-capation
5. position 不为 static / relative
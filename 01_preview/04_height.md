#### height: auto
仅在“格式化高度”时属于外部尺寸，
即绝对定位同时设定 top , bottom 时，
其余时刻属于内部尺寸。


#### height 百分比
与 width 的百分比不同，如果父元素的 width: auto , 那么子元素的 width百分比正常生效；
但是如果父元素的 height: auto(默认值) ，那么子元素的 height 百分比完全无效！

让元素支持 height:100%:
1. html , body { height: 100%; }
2. 绝对定位

绝对定位的宽高百分比计算时相对于 padding-box
非绝对定位的宽高百分比计算时相对于 content-box
**height百分比**
**上一张/下一张**
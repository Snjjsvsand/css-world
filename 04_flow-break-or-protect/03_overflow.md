
#### overflow
#### overflow 裁剪界线是 border-box 内边缘
如果想实现元素剪裁同时四周留有间隙的效果的话，可以试试使用透明边框。

#### overflow 取值
1. visible 默认值
2. hidden 裁剪
3. scroll 滚动条一直存在
4. auto 高度不足时出现滚动条
除非 overflow-x 和 overflow-y 的属性值都是 visible，否则未设置的 visible 会当成 auto 来解析。换句话说，永远不可能实现一个方向溢出剪裁或滚动，另一方向内容溢出显示的效果。

PC端的浏览器滚动条来自 <html> , 滚动条宽度大多为 17px
**滚动条不使页面晃动**

常用自定滚动条属性：

::-webkit-scrollbar { /* 血槽宽度 */ 
 width: 8px; height: 8px; 
} 

::-webkit-scrollbar-thumb { /* 拖动条 */ 
 background-color: rgba(0,0,0,.3); 
 border-radius: 6px; 
} 

::-webkit-scrollbar-track { /* 背景槽 */ 
 background-color: #ddd; 
 border-radius: 6px; 
}

#### 单行文字省略点点点
.ellipsis {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

#### overflow: hidden 的元素也可以触发锚点定位

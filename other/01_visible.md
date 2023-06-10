#### 元素显隐
1. 元素不可见,不占据空间,资源加载,DOM可以访问
  display: none;

2. 元素不可见,不占据空间, 不能点击, 可以 transition 淡入淡出效果
  visibility: hidden;
  position: absolute;

3. 元素不可见,占据空间, , 不能点击 , 有淡出淡出
  visibility: hidden;

4. 不可见,可点击,不占据空间
  position: absolute;
  opacity: 0

5. 不可见,可点击,占据空间
  opacity: 0


display: none 会导致子元素的背景图片资源不加载 (Chrome)
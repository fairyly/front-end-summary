# CSS中margin边界叠加问题及解决方案


别人的博客说的情况：https://www.cnblogs.com/zhangmingze/articles/4664074.html

边界叠加的大多数问题可以通过添加透明边框或1px的补白来修复。
```
外层元素padding代替
内层元素透明边框 border:1px solid transparent;
内层元素绝对定位 postion:absolute:
外层元素 overflow:hidden;
内层元素 加float:left;或display:inline-block;
内层元素padding:1px;
```

补充解决方案：

1.外层padding

2.透明边框border:1pxsolidtransparent;

3.绝对定位postion:absolute:

4.外层DIVoverflow:hidden;

5.内层DIV　加float:left;display:inline;

6.外层DIV有时会用到zoom:1;

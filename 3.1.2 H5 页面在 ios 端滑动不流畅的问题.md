# H5页面在 ios 端滑动不流畅的问题

IOS系统的惯性滑动效果非常6，但是当我们对div加overflow-y:auto;后是不会出这个效果的，滑动的时候会感觉很生涩。怎么办？

方案一：

在滚动容器内加-webkit-overflow-scrolling: touch

但这个方案有一个问题，在页面内具有多个overflow：auto的情况下，那些具有 绝对定位（absolute, fixed） 属性的元素，也会跟着滚动。

方案二：

body {overflow-x: hidden}

即，给 body 元素添加overflow-x：hidden。然后在滚动容器内加overflow-y: auto


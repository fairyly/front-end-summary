# ios scroll 滚动穿透

在 ios 微信浏览器或原生浏览器中，主内容容器.content在文档流内，并且overflow-y: scroll。

在其之上有一个 fixed 定位的弹出层.popUp，滚动.popUp到底部，继续滚动会触发底层容器.content开始滚动。

期望结果

滚动弹出层.popUp,底层容器.content不会触发滚动

解决方案:

google搜的方案基本上都不能完全解决问题......  
经过各种尝试，下面方法可以达到预期效果：  
1） 弹出层显示时，改变容器.content的css属性：overflow-y: hidden；  
2） 弹出层消失时，恢复容器.content的css属性：overflow-y: scroll；  

# JS中document对象和window对象的区别

简单来说，document是window的一个对象属性。  
Window 对象表示浏览器中打开的窗口。  
如果文档包含框架（frame 或 iframe 标签），浏览器会为 HTML 文档创建一个 window 对象，并为每个框架创建一个额外的 window 对象。  
所有的全局函数和对象都属于Window 对象的属性和方法。  
document   对 Document 对象的只读引用。  

区别:1、window 指窗体。document指页面。document是window的一个子对象。

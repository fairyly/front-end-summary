# JS中document对象和window对象的区别

简单来说，document是window的一个对象属性。  
Window 对象表示浏览器中打开的窗口。  
如果文档包含框架（frame 或 iframe 标签），浏览器会为 HTML 文档创建一个 window 对象，并为每个框架创建一个额外的 window 对象。  
所有的全局函数和对象都属于Window 对象的属性和方法。  
document   对 Document 对象的只读引用。  

区别:1、window 指窗体。document指页面。document是window的一个子对象。

```
　document 当前显示的文档(该属性本身也是一个对象)

　　frame 窗口里的一个框架((FRAME>)(该属性本身也是一个对象)

　　frames array 列举窗口的框架对象的数组,按照这些对象在文档中出现的顺序列出(该属性本身也是一个

对象)

　　history 窗口的历史列表(该属性本身也是一个对象)

　　length 窗口内的框架数

　　 location 窗口所显示文档的完整(绝对)URL(该属性本身也是一个对象)不要把它与如document.location

混淆,后者是当前显示文档的URL。用户可以改变window.location(用另一个文档取代当前文档),但却不能改变

document.location (因为这是当前显示文档的位置)

　　name 窗口打开时,赋予该窗口的名字

　　opener 代表使用window.open打开当前窗口的脚本所在的窗口(这是Netscape Navigator 3.0beta 3所引

入的一个新属性)

　　parent 包含当前框架的窗口的同义词。frame和window对象的一个属性

　　self 当前窗口或框架的同义词

　　status 状态条中的消息

　　top 包含当前框架的最顶层浏览器窗口的同义词

　　window 当前窗口或框架的同义词,与self相同

　　方法

　　alert() 打开一个Alert消息框

　　clearTimeout() 用来终止setTimeout方法的工作

　　close() 关闭窗口

　　 confirm() 打开一个Confirm消息框,用户可以选择OK或Cancel,如果用户单击OK,该方法返回true,单击

Cancel返回false

　　 blur() 把焦点从指定窗口移开(这是Netscape Navigator 3.0 beta 3引入的新方法)

　　focus() 把指定的窗口带到前台(另一个新方法)

　　open() 打开一个新窗口

　　 prompt() 打开一个Prompt对话框,用户可向该框键入文本,并把键入的文本返回到脚本

　　setTimeout() 等待一段指定的毫秒数时间,然后运行指令事件处理程序事件处理程序

　　Onload() 页面载入时触发

　　Onunload() 页面关闭时触发

[document 对象]

　　该对象是window和frames对象的一个属性,是显示于窗口或框架内的一个文档。

　　属性

　　alinkColor 活动链接的颜色(ALINK)

　　anchor 一个HTMI锚点,使用<A NAME=>标记创建(该属性本身也是一个对象)

　　anchors array 列出文档锚点对象的数组(<A NAME=>)(该属性本身也是一个对象)

　　bgColor 文档的背景颜色(BGCOLOR)

　　cookie 存储于cookie.txt文件内的一段信息,它是该文档对象的一个属性

　　fgColor 文档的文本颜色(<BODY>标记里的TEXT特性)

　　form 文档中的一个窗体(<FORM>)(该属性本身也是一个对象)

　　forms anay 按照其出现在文档中的顺序列出窗体对象的一个数组(该属性本身也是一个对象)

　　lastModified 文档最后的修改日期

　　linkColor 文档的链接的颜色,即<BODY>标记中的LINK特性(链接到用户没有观察到的文档)

　　link 文档中的一个<A HREF=>标记(该属性本身也是一个对象)

　　links array 文档中link对象的一个数组,按照它们出现在文档中的顺序排列(该属性本身也是一个对象)

　　location 当前显示文档的URL。用户不能改变document.location(因为这是当前显示文档的位置)。但是,

可以改变 window.location (用其它文档取代当前文档)window.location本身也是一个对象,而

document.location不是对象

　　referrer 包含链接的文档的URL,用户单击该链接可到达当前文档

　　title 文档的标题((TITLE>)

　　vlinkColor 指向用户已观察过的文档的链接文本颜色,即<BODY>标记的VLINK特性

　　方法

　　clear 清除指定文档的内容

　　close 关闭文档流

　　open 打开文档流

　　 write 把文本写入文档

　　writeln 把文本写入文档,并以换行符结尾
```

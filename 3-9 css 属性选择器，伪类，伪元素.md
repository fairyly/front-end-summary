# css 属性选择器，伪类，伪元素


* 属性选择器

  [id*=content]: * 这里代表属性 id 的属性值包含字符 content 的元素,如：
  ```
    <div id="content"></div>
    <div id="content2"></div>
    <div id="content3"></div>
  ```
  [id^=content]: * 这里代表属性 id 的属性值开头是字符 content 的元素,如：  
  [id$=content]: * 这里代表属性 id 的属性值结尾是字符 content 的元素,如：  
  
* 结构性伪类选择器

  - 伪元素： first-line,first-letter,before,after
  - 伪类：  
    root: 根元素     
    not: 排除结构元素下的子元素    
    empty: 指定元素空白时样式    
    target: 页面在用户点击超链接，跳转到 target 元素后      
    ，   
    first-child  
    last-child  
    nth-child  (odd:奇数，even:偶数)  
    nth-last-child  
    nth-of-type  (odd:奇数，even:偶数)  
    only-child  ： 父元素只有一个元素
    ，   
* UI 元素状态伪类选择器
    
    

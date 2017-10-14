# dom


* 内部节点属性
```
document.doctype，document.documentElement，document.defaultView
document.body，document.head
document.activeElement
```
* 节点集合属性
```
document.links，document.forms，document.images，document.embeds
document.scripts，document.styleSheets
```

* 文档信息属性
```
document.documentURI，document.URL
document.domain
document.lastModified
document.location
document.referrer，document.title，document.characterSet
document.readyState
document.designMode
document.implementation
document.compatMode
document.cookie
```

* 读写相关的方法
```
document.open()，document.close()
document.write()，document.writeln()
```

* 查找节点的方法
```
document.querySelector()，document.querySelectorAll()
document.getElementsByTagName()
document.getElementsByClassName()
document.getElementsByName()
getElementById()
document.elementFromPoint()
```
* 生成节点的方法
```
document.createElement()
document.createTextNode()
document.createAttribute()
document.createDocumentFragment()
```
* 事件相关的方法
```
document.createEvent()
document.addEventListener()，document.removeEventListener()，document.dispatchEvent()
```
* 其他方法
```
document.hasFocus()
document.createNodeIterator()，document.createTreeWalker()
document.adoptNode()
document.importNode()
document.getSelection()
```


* 节点的创建、添加、删除、克隆
  ```
  创建节点、追加节点
  1、createElement（标签名）创建一个元素节点（具体的一个元素）。
  2、appendChild（节点）追加一个节点。
  3、createTextNode（节点文本内容）创建一个文本节点
  ```

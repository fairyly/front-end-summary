# 深入理解Babel原理及其使用


## bable
>简称：转码器(转译器:因为它只是把同种语言的高版本规则翻译成低版本规则，而不像编译器那样，输出的是另一种更低级的语言代码)

## babel的工作原理
>和编译器类似，babel的转译过程也分为三个阶段：
parsing、transforming、generating，

- 以ES6代码转译为ES5代码为例，babel转译的具体过程如下：
```
ES6代码输入 ==》 babylon进行解析 ==》 得到AST
==》 plugin用babel-traverse对AST树进行遍历转译 ==》 得到新的AST树
==》 用babel-generator通过AST树生成ES5代码
```



## 1.polyfill (垫片库)
>polyfill是一个针对ES2015+环境的shim，    
实现上来说babel-polyfill包只是简单的把core-js和regenerator runtime包装了下，  
这两个包才是真正的实现代码所在（后文会详细介绍core-js）。



## 2.runtime
- polyfill和runtime的区别

直接使用babel-polyfill对于应用或页面等环境在你控制之中的情况来说，并没有什么问题。  
但是对于在library中使用polyfill，就变得不可行了。  
因为library是供外部使用的，但外部的环境并不在library的可控范围，  
而polyfill是会污染原来的全局环境的（因为新的原生对象、API这些都直接由polyfill引入到全局环境）。  
这样就很容易会发生冲突，所以这个时候，babel-runtime就可以派上用场了



## 3.通过core-js实现按需引入polyfill或runtime
>core-js包才上述的polyfill、runtime的核心，因为polyfill和runtime其实都只是对core-js和regenerator的再封装，方便使用而已。
但是polyfill和runtime都是整体引入的，不能做细粒度的调整，  
如果我们的代码只是用到了小部分ES6而导致需要使用polyfill和runtime的话，会造成代码体积不必要的增大（runtime的影响较小）。   
所以，按需引入的需求就自然而然产生了，这个时候就得依靠core-js来实现了。



## 参考
- [深入理解Babel原理及其使用](http://www.fly63.com/article/detial/197)

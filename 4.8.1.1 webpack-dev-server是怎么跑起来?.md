# dev-server是怎么跑起来

## 1.1 webpack-dev-middleware

webpack-dev-middleware 的出现很好地解决了上述问题 —— 作为一个 webpack 中间件，  

它会开启 watch mode 监听文件变更，并自动地在内存中快速地重新打包、提供新的 bundle。

说白了就是 —— 自动编译（watch mode）+速度快（全部走内存）！



## 1.2 webpack-hot-middleware 

>虽然 webpack-dev-middleware 会在文件变更后快速地重新打包，  
但是每次都得手动刷新客户端页面来访问新的内容，还是略为麻烦。  
这是因为 webpack-dev-middleware 在应用执行的时候，没办法感知到模块的变化。

那么是否有办法可以让页面也能自动更新呢？webpack-hot-middleware 便是帮忙填这个坑的人

webpack-hot-middleware 提供的这种能力称为 HMR，所以在介绍 webpack-hot-middleware 之前，我们先来科普一下 HMR。

HMR 即模块热替换（hot module replacement）的简称，它可以在应用运行的时候，不需要刷新页面，就可以直接替换、增删模块。

webpack 可以通过配置 webpack.HotModuleReplacementPlugin 插件来开启全局的 HMR 能力


## 1.3 webpack-dev-server

>虽然 webpack-dev-middleware + webpack-hot-middleware 的组合为开发过程提供了便利，但它们仅适用于服务侧开发的场景。

很多时候我们仅仅对客户端页面做开发，没有直接的 server 来提供支持，这时候就需要 webpack-dev-server 来解囊相助了。

顾名思义，webpack-dev-server 相对前两个工具多了个“server”，


## 参考
- [webpack 插件拾趣 (1) —— webpack-dev-server](https://www.cnblogs.com/vajoy/p/7000522.html)

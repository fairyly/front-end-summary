# 写一个 Webpack Loader

## loader: 模块和资源的转换器
>loader 的功能：把源模块转换成通用模块。

- webpack 规定 use 数组中 loader 的执行顺序是从最后一个到第一个


## 用法准则

```
简单易用。
使用链式传递。
模块化的输出。
确保无状态。
使用 loader utilities。
记录 loader 的依赖。
解析模块依赖关系。
提取通用代码。
避免绝对路径。
使用 peer dependencies。
```


## loader 工具库(Loader Utilities) 

充分利用 loader-utils 包。它提供了许多有用的工具，  
但最常用的一种工具是获取传递给 loader 的选项。  
schema-utils 包配合 loader-utils，用于保证 loader 选项，进行与 JSON Schema 结构一致的校验。

这里有一个简单使用两者的例子：

```
loader.js

import { getOptions } from 'loader-utils';
import validateOptions from 'schema-utils';

const schema = {
  type: 'object',
  properties: {
    test: {
      type: 'string'
    }
  }
};

export default function(source) {
  const options = getOptions(this);

  validateOptions(schema, options, 'Example Loader');

  // 对资源应用一些转换……

  return `export default ${ JSON.stringify(source) }`;
}
```



## 参考
- [writing-a-loader](https://webpack.docschina.org/contribute/writing-a-loader)
- [手把手教你撸一个 Webpack Loader](https://blog.csdn.net/lszy16/article/details/79162960)

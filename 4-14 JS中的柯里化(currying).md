# JS中的柯里化(currying)

* 张鑫旭:http://www.zhangxinxu.com/wordpress/2013/02/js-currying/

① 柯里化（Currying），又称部分求值（Partial Evaluation），
  是把接受多个参数的函数变换成接受一个单一参数（最初函数的第一个参数）的函数，
  并且返回接受余下的参数而且返回结果的新函数的技术


柯里化有3个常见作用：1. 参数复用；2. 提前返回；3. 延迟计算/运行

* 把函数参数转换到一个数组中
  - var args = [].prototype.slice().call(arguments)或者
  - var args = [].slice().call(arguments)

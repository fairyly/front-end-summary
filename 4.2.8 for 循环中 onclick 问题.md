
# for循环中onclick问题

http://blog.csdn.net/k358971707/article/details/52968378

```
<script> 
        var btn=document.getElementsByTagName('button');
        for(var i=0;i<btn.length;i++){ 
            (function(i){ //这个是function里i，即function的形参，也可以换成j，换成什么变量名都无所谓
                btn[i].onclick=function(){ 
                    console.log(i);
                }
            })(i);//这是循环中的i,被作为参数传入
        }
    </script>

再运行这段代码，就可以得到你想要的效果，但是是为什么呢？ 
知道了原因就好办了，利用闭包把每个function里的i都变成不同的i就行了，当时作为一名初学者还不懂闭包，也是后来才理解的。 
循环中的function自调用，将循环中的i作为参数传入function中，
此时，function中的i已经不是循环中的i了（这里有点绕，其实形参i，即function里的i换成什么变量名都行），
而是在内存中开辟了一个内存空间存储了作为参数传进来的i的值，
这样function中的就不会随着循环中的i的值的改变而改变了,就可以打印出你要的结果了。
```

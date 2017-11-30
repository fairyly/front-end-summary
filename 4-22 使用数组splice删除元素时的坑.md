# 使用数组splice删除元素时，你应该知道这个小坑

* https://juejin.im/entry/5a1ecfef6fb9a044fe462143

从数组[1,2,5,6,8,9]中保留小于等于4的元素。思路，循环数组，然后从循环中调判断如果元素大于4，那么就使用splice剔除掉。

代码如下：
```
var arr = [1,2,5,6,8,9];
for(var i=0;i<arr.length;i++){
  if(arr[i]>4)
  arr.splice(i,1)
}
console.log(arr) //[1, 2, 6, 9]
```

这时我们发现，奇怪了，为什么 6和9被保存了下来呢？这是因为我们每次找到大于4的元素之后，就直接splice剔除掉了，需要注意的是，splice是一个会变异方法，  
也就是会改变原数组的方法，所以当i等于2的时候，会找到元素‘5’，然后splice的时候，由于元素‘5’剔除之后，有空位，后面的元素‘6’ ‘8’ ‘9’就都往前补一位，  
但是此时i的值在结束此次循环之后，经过了i++语句，  
就是直接跳到元素‘8’的位置了，元素‘6’因为补位 躲过了一劫！ 再次循环9又因为补位也躲过了一劫，所以结果就是1269  

当 i 等于4 的时候 情况也是一样的，元素‘9’补位，躲过一劫。

就是使用splice的时候，要注意数组的变化以及索引的位置

```
所以使用 i-- 或者 --i
var arr = [1,2,5,6,8,9];
for(var i=0;i<arr.length;i++){
  if(arr[i]>4){
    arr.splice(i,1)
    --i
  }
}
console.log(arr) 
```

当然 我们也可以用一个新数组来保存，符合条件的元素，或者使用数组的filter方法来筛选元素

```
var arr = [1,2,5,6,8,9];
var filt = arr.filter(function(ele,index,array){
  return ele < 4;
})
console.log(arr); // [1, 2, 5, 6, 8, 9]
console.log(filt); // [1, 2]
```


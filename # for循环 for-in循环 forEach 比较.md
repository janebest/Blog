# for循环 for-in循环 forEach 比较

**for循环** ：通过break可以随时跳出循环，当花括号只有一个时，不用括号，continue可以跳过此步骤
break

```
var size=[1,2,3,4,5,6,7] //申明一个数组

for(var i=0; i<size.length; i++){ 

    document.write(size[i] + " ");//数组元素
    
}
```

**for in 循环：**可以循环数组和对象

```

var x;//可以不定义，也可以在括号内定义

var size=[1,2,3,4,5,6,7] //申明一个数组

var obj={name:'liushenghua',age:24,sex:'man'} //申明一个对象

for(x in size){ 

    document.write(size[x] + " ");//数组元素
    
}

for(x in obj){ 

    document.write(obj[x] + " ");//对象元素
    
}
```

**forEach循环：**foreach适用于循环次数未知，或者计算循环次数比较麻烦情况下使用效率更高，但是更为复杂的一些循环还是需要用到for循环效率更高

```
let arr = ['a', 'b', 'c', 'd']
arr.forEach(function (val, idx, arr) {
    console.log(val + ', index = ' + idx) // val是当前元素，index当前元素索引，arr数组
    console.log(arr)
})
```

for（元素类型  元素名称 ： 遍历数组（集合）（或者能进行迭代的））{

　　　　　　语句

　　　　　}



**区别：**在遍历的时候，采用一般的 for 循环和 for...in 循环得到的结果不同。for...in 循环会自动跳过那些没被赋值的元素，而 for 循环则不会，它会显示出 undefined。
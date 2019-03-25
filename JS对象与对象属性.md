# JS对象与对象属性

**对象分类：**1.内置对象（对象或构造器对象：String,Date,Array,Function...）
                    2.宿主对象（解析器所嵌入的宿主环境定义的：window、document）
                    3.自定义对象（自定义JS代码创建的对象)

**属性的种类:**1.数据属性（**Property**, 对象中的普通属性）
                    2.访问器属性（**Accessor**,类似于读、写属性的特殊方法，访问器可以计算属性的值）
                    3.内置属性（**Internal  property**,比如[[Scope]]、[[Prototype]],不能直接访问，有可能存在间接访问   方式,**proto__**可以访问[[Prototype]]）

**访问对象属性/方法**：方式一：通过 对象名.属性名 、对象名.方法名( )（xx.name,xx.childrenNode）
                                 方式二：通过 对象名[“属性名” ]

**修改对象属性：**直接赋值给对象属性

**遍历对象属性：**使用for   in 语句

**添加对象属性：**对象创建之后，要向对象添加属性，只需要为新属性赋值即可

**删除对象属性：**使用delete关键字

**数据属性（实现数据属性特性的设置和查询）：**1.**value**（属性的值）：属性的值
                   2.**writable**（可写特性）：属性是否可改写性
                   3.**configurable**（可配置特性）：属性是否能删除和其他特性是否可配置
                   4.**enumerable**（可枚举特性）：属性是否可枚举

**属性描述符（property descriptor）：**属性特性描述符是一个用来**查看对象属性**的特性的对象，该对象包含4个属性，对应4个特性

**设置属性描述符：** **Object.defineProperty**(obj, prop, descriptor)
                                **obj** —— 要在其上定义属性的对象。
                                **prop** —— 要定义或修改的属性的名称。
                                **descriptor** —— 将被定义或修改的属性描述符
                                value 默认为 **undefined**
                                enumerable、writable、configurable 默认为 **false**

 **获取属性特性：** **Object.getOwnPropertyDescriptor**(obj,prop) 方法
                                返回指定对象上一个自有属性对应的属性描述符。
                                **obj** —— 需要查找的目标对象
                                 **prop** —— 目标对象内属性名称

​                                **Object.getOwnPropertyDescriptors**(obj) 
​                                获取一个对象的所有自身属性的描述符

**enumerable**：枚举性

枚举的主要**目的**是判断 for-in 循环中的那些属性应该被忽略。

 枚举性**影响**的操作：1.for-in 循环
                                    2.Object.keys()
                                    3.JSON.stringify()

**obj.propertyIsEnumerable**(prop) ：返回一个布尔值，表示指定的属性是否可枚举。

 **configurable**：可配置特性，确定属性是否能删除和其他特性是否可配置

**访问器属性**的特性： **get**：**读取属性**时调用的函数，该函数计算读取的结果，默认是 undefined
                                 **set**: **设置属性值**时调用的函数，该函数接受设置的值作为参数，默认是undefined
                                 **configurable**（可配置特性）：确定属性是否能删除和其他特性是否可配置
                                 **enumerable**（可枚举特性）：属性是否可枚举

**设置访问器属性特性：**1. 访问器属性（存取器属性）定义一个或两个和属性同名的函数，这个函数定义没有使用 function 关键字，而是使用 get 和 set。
                                      2.属性名和函数体没有冒号分隔。
                                      3.函数体结束和下一个属性有逗号分隔。

​                                      4.JavaScript 把这些函数当做对象的方法调用，函数中的 this 指向这个对象。


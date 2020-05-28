# Math  JSON

**Math 对象不需要创建，直接使用**

四舍五入:  Math. **round**( )

向下取整:  Math.**floor**( )     

 向上取整:  Math.**ceil**( )

生成 [0~1) 随机数:  Math.**random**( )

取最大值:  Math.**max**( )       

取最小值:  Math.**min**( )

**Math 原型链：**Math.__proto__ == Object.prototype

**JSON（JavaScript Object Notation）：**一种简便的数据交换格式，能够在服务器之间交换数据。（内置对象）

 JavaScript 对象表示法
 是轻量级的文本数据交换格式
 更小、更快，更易解析
 是一种数据格式，不是编程语言
 虽然具有相同的语法形式，但 JSON 并不从属于 JavaScript
 并不是只有 JavaScript 才使用 JSON，JSON 只是一种数据格式
 很多编程语言都有针对 JSON 的解析器和序列化器

**使用文本表示 JavaScript  对象的信息**，**本质是一个字符串**

 **JSON语法**

**并列的数据**之间用**逗号**（", "）分隔
 **并列数据的集合（数组**）用**方括号**("[]")表示
 **映射**用**冒号**（": "）表示
 **映射的集合（对象）**用**大括号**（"{}"）表示
 **字符串**必须加**双引号**

**JSON 语法可以表示以下三种类型的值**

**1.简单值：**与 JavaScript 语法相同，可以在 JSON 中表示字符串、数值、布尔值和 null。
                 JSON **不支持** JavaScript 中的**特殊值 undefined**。 

**2.对象 ：**一种复杂数据类型，表示一组无序的键值对。
              键值对中的值可以是任意类型——简单值、对象或数组。

**3.数组：** 一种复杂数据类型，表示一组有序的值的列表。
              数组的值可以是任意类型——简单值、对象或数组。 

**JSON静态方法**

**1.JSON.stringify(object [,replacer [,space] ] )**方法（**将对象的状态转换为字符串**）

 **undefined 值会被忽略**

 object：指定转换对象

 replacer：参数过滤器为**数组**时，结果只**包含数组中列出的属性**，参数过滤器为**函数**时，**需接受两个参数，属性键名和属性值**

 space：可选，参数为**数值**时，**表示每个级别缩进的空格数**，参数为**字符串**时，**使用字符串作为缩进字符**

**2.JSON.parse(json [,reviver])**方法（**将字符串还原为对象的状态**）

 把JSON字符串解析为原生JavaScript对象

 json：参数必须是有效的 JSON，否则会报错

reviver：可选，参数过滤器为函数时，需接受两个参数，属性键名和属性值

**JSON原型链**

JSON.__proto__ == Object.prototype

JSON.__proto__.__proto__ === null

**Table 对象**

table.**rows** —— 返回包含表格中**所有 tr 元素的集合**

table.**createCaption**() —— 为表格**创建一个 caption 元素**

table.b(index) —— 在表格中的指定位置**插入一个空的 tr 元素**

table.**deleteRow**(index) —— 从表格**删除指定位置的行**

**TableRow 对象**

tr.**cells** —— 返回表格行中**所有 td 或 th 元素的集合** 

tr.**insertCell**(index) —— 在一行的指定位置**插入一个空的 td 元素**

tr.**deleteCell**(index) —— **删除表格行中的指定 td 元素**






















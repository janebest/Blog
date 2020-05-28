# Ajax异步数据传输

**客户端**通过指定的访问地址获取（或上传）服务器资源（文件等信息）

**服务器**使用HTTP协议的通信传输信息给客户端

HTTP 是一种不保存状态，即**无状态**（stateless）协议。HTTP 协议自身**不对请求和响应之间的通信状态进行保存**。也就是说在 HTTP 这个级别，协议对于发送过的请求或响应**都不做持久化处理**。

**HTTP 协议规定，请求从客户端发出，最后服务器端响应该请求并返回。**

**URI**（Uniform Resource Identifier）：1.统一资源标识符
格式： http(协议方案名)：（登陆信息）（服务器地址）（服务器端口号）（带层次的文件路径）（查询字符串）（片段标识符）

**请求报文：**请求报文是由请求方法、请求 URI、协议版本、可选的请求首部字段和内容实体构成的。

方法/URI/协议版本

请求首部字段

内容实体

**响应报文：**响应报文基本上由协议版本、状态码（表示请求成功或失败的数字代码）、用以解释状态码的原因短语、可选的响应首部字段以及实体主体构成。

协议版本/状态码

响应首部字段

实体

 **方法（Method）—— 告知服务器意图的 HTTP 方法**
 **GET** ：获取资源
 **POST**：传输实体主体
 **PUT**：传输文件
 **DELETE**：删除文件
 **HEAD**：获得报文首部
 **OPTIONS**：询问支持的方法
 指定请求的资源按期望产生某种行为，使用方法下达命令

**状态码：**负责表示客户端 HTTP 请求的返回结果、标记服务器端的处理是否正常、通知出现的错误等工作。

1XX：接受的请求正在处理

200：OK

301：需要进行附加操作以完成请求

403：不被允许的

404：Not Found

500：服务器处理请求出错

**表单提交**

**enctype：**当 method 属性值为 post 时, enctype 是将 form 的内容提交给服务器的 MIME 类型 。

**Ajax异步请求**（使用XMLHttpRequest 对象异步的向服务器发送请求）

1.Ajax 可以使网页实现异步更新。这意味着可以在不重新加载整个网页的情况下，对网页的某部分进行更新
2.Ajax 技术与数据格式无关

**XMLHttpRequest 对象的属性**

**readyState：**表示XMLHttpRequest 对象的状态：0（未初始化。对象已创建，未调用open）1：（open方法成功调用，但Send方法未调用）2：（send方法已经调用，尚未开始接受数据）3：（正在接受数据，Http响应头信息已经接受，但未接受完成）4：(完成，即响应数据接受完成)

 **status：**状态码

 **responseText：**服务器响应的文本内容,JSON.parse(xhr.responseText)解析为 JavaScript 对象

 **onreadystatechange：**请求状态改变的事件触发器

 **XMLHttpRequest 对象的方法**
 **open(Method（GET,POST），url，asynch（是否采用异步方法true/false） )：**指定和服务器交互的HTTP方法

 **setRequestHeader(header，value)：**设置HTTP请求中的指定头部header的值为value

 **send(contend（null，DOM对象，字符串）)：**向服务器发出请求，如果采用异步，该方法会立即返回

**步骤**

**创建 XMLHttpRequest 对象实例**

```
var xhr;
if(window.XMLHttpRequest){
    xhr = new XMLHttpRequest();//(主流浏览器)
}else{
    xhr = new ActiveXObject("Microsoft.XMLHttp");//(IE浏览器)
}
```

 **创建请求（open(method（请求类型 get/post）,url,bool（异步/同步请求）)）**

指定请求的HTTP头

```
//POST请求(异步，发送表单数据，把表单数据转换成一个字串)
xhr.open("POST","xx.php","true");
 xhr.setRequestHeader("Content-Type","application/-www-form-urlencoded");
//GET请求
xhr.open("POST","xx.php","true");
```

 **发送请求（send()）**

```
//send方法内传递提交参数(POST)，没有填写 null
xhr.send('name=value&name=value');
//若要提交数据，也可在 open 方法的 "URL" 后面追加
如：xhr.open('GET','xx.php?name=value&name=value',true)

```

 **回调事件处理函数**

onreadystatechange:请求状态改变触发器

```
xhr.onreadystatechange = function(){
    if(xhr.readyaState == 4 && xhr.status == 200){
        var txt = xhr.responseText;
        document.write(txt);
    }
}
```

**$.ajax()方法**

```
$.ajax({
    type:"get",//请求方式
    url:"",//请求地址
    dataType:"json",//指定数据类型
    success：function(data){
        console.log(data),//数据返回成功执行函数
    }
})
```

```

```


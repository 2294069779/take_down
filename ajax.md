

#### Ajax介绍

##### 服务器的基本概念

- 服务器：负责存放和对外提供资源的电脑 

- 客服端：负责获取和消费资源的电脑 
- url地址：身份证号，表示资源存放地址 
  - 由三部分组成
    - 通信协议     http
    - 服务名称        www.baidu.com
    - 具体的存放位置       /luih/dsv/s.html
  - 过程
    - 客服端请求服务器
    - 服务器处理这次请求
    - 服务器响应（发送）客户端
  - 请求
    - XMLHttpRequest对象
    - get请求，通常用于获取服务端资源
    - post请求通常用于向服务器提交数据

##### 什么是Aja 

- 在网页中利用XMlHttpRequest对象和服务器进行数据交互的方式，Ajax

- jquery的Ajax
  - $.get()    
    - 语法  $get.(url,[data],[callback])            []里的是可选的，data：携带的参数。 caallback：请求成功时的回调函数
  - $.post()   
    - 语法  $post.(url,[data],[callback])            []里的是可选的，data：携带的参数。 caallback：请求成功时的回调函数
  - $.ajax()
    - 语法  $.ajax({type，url,[data],[callback]})  （用对象的形式  type：）      type：请求的方式  []里的是可选的，data：携带的参数。 caallback：请求成功时的回调函数
  
- 接口（被请求的URL地址）
  - 接口测试工具（postman）
  
- 接口文档

  <img src="C:\Users\tuzi\AppData\Roaming\Typora\typora-user-images\image-20220405225628207.png" alt="image-20220405225628207" style="zoom:50%;" />

##### 表单

在网页中负责数据采集 

- 表单标签
- 表单域
- 表单按钮

属性

action：url地址

method：get获取post        以何种方式提交，一般使用post提交，比较安全

enctype ：偏码    application/x-www-form-urlencoded在发送前编码所有字符(默认)。multipart/form-data不对字符编码：文件上传必须使用这个
在使用包含文件上传控件的表单时，必须使用该值。

target：在何处打开actionUrl  _blank:在新窗口    _self(默认)在相同的框架下    _parent:在父框架     _top：在整个窗口下      framname：指定的框架下

解决同步提交的缺点     方案：表单只负责采集数据，Ajax负责将数据提交到服务器

通过Ajax提交表单数据
- 监听表单的提交事件
  - $('#from1').submit(funtion(e){})
  - $('#from1')on('submit',function(e){})
- 阻止表单默认行为
  - e.preverntDefault()
- 获取表单数据 
  - 表单元素.serialize（）
  - reset()(原生的清除方法)

模板引擎
- 根据程序员指定的模板结构和数据，自动生成一个完整的HTML页面
- 导入模板引擎，多一个temolate('模板的Id'，需要渲染的数据对象)
- 模板必须定义到script中，指定type当作html解析 
- {{}} ：占位符，调用template
- 五步
  - 导入模板引擎
  - 定义需要渲染的数据
  - 定义模板，模板的html结构，必须定义到script；一定要指定type属性，当作html解析
  - 调用tmplate函数，参数：模板id，数据，；{{属性数据名}}
  - 渲染html结构，把渲染好的参数放入dom中
- 标准语法
  - art-template提供了{{}}这种语法，可以在{{}}进行变量输出，或者循环数组等操作
  -  输出：在{{}}语法中，可以进行变量的输出、对象属性的输出、三元表达式输出、逻辑或输出、加减乘除等表达式输出。
  - 原文输出 @，‘如果输出包含html标签；
  - 条件输出 {{if 条件}}输出{{elseif}}输出{{/if}}
  - 循环输出 each。 {{each arr}}      {{$index}} {{$value}}    {{/each}}
  - 过滤器{{value|filterName}}                         定义过滤器的基本语法如下：template.defaults.imports.filterName=function(value){ return huilai } 
- exec()用于检索字符串中的正则表达式的匹配

##### xmlHttpRequest

- 是js一个对象，用来请求服务器上的数据资源
- <img src="C:\Users\tuzi\AppData\Roaming\Typora\typora-user-images\image-20220408172343045.png" alt="image-20220408172343045" style="zoom:50%;" />



- 使用xhr对象发起GET请求

  - 步骤4步
    - 创建xhr对象
    - 调用xhr.open（）函数   //创建
    - 调用xhr.send()函数        //发起  
    - 监听 xhr.onreadystatechange事件
      - 监听xhr对象的请求状态readyState与服务器响应的状态status
      - 响应回来的数据responseText
  - readyState
    - 状态
      - unsent：已被创建，还没有被调用
      - opened：open（）方法已经被调用
      - HEADERS_RECEIVED :send()方法已经被调用，响应头也已经被接收
      - LOADING：数据接收中，此时response属性中已经包含部分数据
      - DONE：AJax请求完成，这意味着数据传输已经彻底完成或失败
  - 带参数？id=1，也叫查询字符串  
  - 查询字符串
    - 查询字符串是指在URL的末尾加上用于向服务器发送信息的字符串
    - 格式 ：在url的末尾然后加上参数=值，多个参数的话，使用&符合进行分隔
  - URL编码
    - url指允许英文，标点符合，数字
    - 如果需要中文。则必须对中文字符进行编码
    - 原则：使用安全的字符去表示哪些不安全的字符
    - 如何对URL进行编码与解码
      - encodeURL() 编码的函数
      - decodeURL() 解码的函数
      - 更多关于URL编码的知识，请参考如下博客:
        https://blog.csdn.net/Lxd 0111/article/details/7802888

- 使用xhr发起post请求

  - 步骤5步

    - 创建xhr对象

    -  调用xhr.open()函数，里面参数是post

    - 设置Content-Type属性固定写法

      xhr . setRequestHeader ('Content-Type'，' application/x-www form -urlencoded')

    - 调用xhr.send()函数，同时将数据以查询字符串的形式，提交给服务器

    - 监听xhr.onreadystatechange事件
    
    - 响应回来的数据responseText

- 数据交换格式

  - 服务器端与客户端之间进行数据传输与交换的格式
  - 前端经常一般格式是xml和json（重点）
    - xml：可扩展标记语言（被设计用来传输和存储数据，是数据的载体），而html是描绘传输网页内容的
    - JSON:JSA对象和数组的字符串表示法，本质是字符串，是一种轻量级的文本数据交换格式
      - 包含对象和数组两种结构相互嵌套 
        - 对象{}，key必须英文的双引号，字符串也必须双引号，value数据类型：数字，字符串，布尔值，null数组，对象
        - 数组 []:字符串也必须双引号,数据类型：数字，字符串，布尔值，null数组，对象
      - JSON注意事项
        - 属性名必须使用双引号包裹
        - 字符串类型的值必须使用双引号包括
        - JSON中不允许使用单引号表示字符串
        - JSON中不能写注释
        - json的最外层必须是对象或数组格式
        - 不能使用undefined或函数作为JSON的值
      - JSON和js对象的互转
        - JSON字符串转换为JS对象，使用JSON.parse()方法，参数
        - js对象转换为JSON字符串，使用JSON.stringify()方法
      - 序列化和反序列化
        - 把数据对象转换为字符串的过程，叫做序列化
        - 把字符串转换为数据对象的过程，叫做反序列化
  
- XMLHttpRequestLevel2的新特性

  - 新功能

    - 可以设置HTTP请求的时限

      - 设置timout（毫秒），有一个配套timeout（事件），用来指定回调函数

    - 可以使用FormData对象管理表单数据

      - 直接new一个实例，往里面添加数据
      - 也可以获取网页表单的值，自动将表单数据填充实例对象中

    - 可以上传文件（步骤））

      - 定义ul结构

        - 文件选择框

        - 上传文件按钮

        - img标签，来显示上传成功后显示图片

        - ```js
          <input type="file" name="上传" id="filel">
              <button id="btn">上传文件</button>
              <img src="" alt="" id="img" width="200" />
          ```

          

      - 验证是否选择了文件

        - 获取上传文件按钮

        - 添加点击事件监听

        - 获取到选择的文件列表     var files=document.querySelector（‘文件选择框’）.files    if（files.length<=0）{return alert('请选择要上传的文件 ')}

        - ```js
           $('#btn').click(function(){
                      var files=document.querySelector('#filel').files;
                      console.log(files);
                      if(files.length <=0 ){
                          return alert('请上传文件')
                      }else{}
          ```

        

      - 向FormData中追加文件

        - new一个formData对象

        - fd.append（‘名字’，files[0]）

        - ```js
          var fd=new FormData();
                        fd.append('avater',files[0])
          ```

        

      - 使用xhr发起上传文件的请求

        - 通过send（fd）

        - ```js
           var xhr=new XMLHttpRequest()
            xhr.open('POST','http://www.liulongbin.top:3006/api/upload/avatar')
                        xhr.send(fd)
                       
          ```

        

      - 监听onreadystatrchange事件

        -  接收事件响应后的数据

        - 如果成功，显示成功 

        - ```js
           xhr.onreadystatechange=function(){
                            if(xhr.readyState===4&xhr.status===200){
                                var data=JSON.parse(xhr.responseText)
                                if(data.status===200){
                                    document.querySelector('#img').src='http://www.liulongbin.top:3006'+data.url;
                                }else{
                                    alert('失败')
                                }  }
          ```

        

    - 可以获取数据传输的进度信息

      - 可以通过xhr.upload.onprogress事件，获取到文件的上传进度

        - ```js
          var xhr=new XMLHttpRequest()
          xhr.upload.onprogress=function(e){
              if(e.lengthComputable){
                  var percentComplete=Math.ceil((e.loaded/e.total)*100)
                  $('#jd').attr('style','width:'+pp+'%').html(pp+'%')
              }
          }
          ```

        - e.lengthCoputable:看上传资源是否有可计算的长度，布尔值

        - e.loaded: 以传输的字节

        - e.total:需要传输的总字节

    - xhr.upload.onload=function(){}//上传成功   

      - ```js
         xhr.upload.onload=function(){
                              $('#jd').removeClass().addClass('class="progress-bar progress-bar-info progress-bar-striped')    } 
        ```

      


---

##### JQuery高级用法

- jquery实现文件上传

  - 定义ul结构x

  - 验证是否选择了文件

    - 需要将jq对象转换为DOM对象[0]

  - 向FormData中追加文件

  - 使用JQuery发起上传文件的请求

    <img src="C:\Users\tuzi\AppData\Roaming\Typora\typora-user-images\image-20220409154911446.png" alt="image-20220409154911446" style="zoom:50%;" />

- JQuery实现loading效果

  - Ajax请求开始时，执行ajaxStart（）函数。只能在文档（dom）附加

    - ```js
      $(document).ajaxStart(function(){$('#loading').show()})
      ```

    - 所有ajax请求都会被ajaxStart所监听到

  - ajaxstop：Ajax请求结束后执行

--------

##### Axios

- Axios是专注于网络数据请求的库

- axios发起请求

  - 获取语法：axios.get('url',{params:参数}).then(callback)
  - 发送语法：axios.post('url,参数').this(function(res){})

  - 直接使用axios发起请求：axios（{  method：’请求类型‘  ，url：’请求的url地址‘，data：{post参数}，params：{GET参数}}.then(callback )

-----

##### 跨域与JSONP

###### 	同源策略和跨域

- 同源：两个页面的协议，域名和端口都相同，则两个页面具有相同的源  
- 同源策略是浏览器提供的一个安全功能，通俗点理解，一个网站的js，不允许和非同源的网址之间，进行资源交互<img src="C:\Users\tuzi\AppData\Roaming\Typora\typora-user-images\image-20220409170407851.png" alt="image-20220409170407851" style="zoom:50%;" />
- 跨域，反之 
- 浏览器允许发起跨域请求，但是，跨域请求回来的数据，会被浏览器的同源策略拦截，
- 实现跨域数据请求，最主要的两种解决方案，分别是JSONP和CORS
- JSONP:只支持GET请求
- CORS:缺点低版本不兼容

###### JSONP

- 利用js的src不收同源cel影响的 原理
- JSONP底层原理
- JQ中的$.ajax()除了发起Ajax数据请求之外，还能发起JSONP数据请求，必须指定datatype的值为JSONP
- 自定义JSONP的参数
  - jsonp：参数名称
  - jsonpCallback：自定义的回调函数名称

###### 防抖

- 是当事件被触发后，延迟n秒后再执行回调，如果在这n秒内事件被触发，则重新计时
- 输入框防抖
  - 定个定时器，通过clear清除定时器的原理

###### 缓存对象

- 定义的缓存对象
- 获取用户输入的内容，当做键
- 需要将数据作为值，进行缓存
- 先判断缓存里有没有数据

###### 节流

- 不会连续被触发，
- 使用节流阀

--------------

#####   HTTP

###### HTTP协议简介

- 通信

  - 就是信息的转递和交换
  - 通信三要素
    - 通信的主体
      - 主体服务器和客户端
    - 通信的内容
      - 信息
    - 通信的方式
      - 响应
  - 通信协议是指通信的双方完成通信所必须遵守的规则和约定，通俗：通信双方采用约定好的格式来发送和接收信息（规定）
  - 网页内容又叫做超文本，网页内容的传输协议叫做超文本传输协议（HTTP）

- HTTP 交互模型

- <img src="C:\Users\tuzi\AppData\Roaming\Typora\typora-user-images\image-20220410165915608.png" alt="image-20220410165915608" style="zoom: 50%;" />

  

###### HTTP请求

- HTTP请求消息：客户端发起的请求叫做HTTP请求，客户端发送到服务器的消息，叫做HTTP请求消息（请求报文）
- http请求消息由请求行，请求头部，空行和请求体组成
  - 请求行：由请求方式，URL和HTTP协议版本组成，之间使用空格隔开
  - 请求头：用来描绘客户端的基本信息的 有键值对组成
  - <img src="C:\Users\tuzi\AppData\Roaming\Typora\typora-user-images\image-20220410212622307.png" alt="image-20220410212622307" style="zoom:50%;" />
  - 空行用来分隔请求头部和请求体
  - 请求体：存放通过post的提交服务器的数据（只有post才有）

###### HTTP响应

- HTTP响应消息就是服务器响应给客户端的消息内容也叫作响应报文
- HTTP响应消息是由状态行，响应头部，空行和响应体组成
  - 状态行：HTTP协议版本、状态码和状态码的描述文本，之间用空格隔开
  - 响应头部：用来描绘服务器的基本信息
  - 响应体： 是服务器响应给客户端的资源内容

###### HTTP请求方法

请求方法的作用是：用来表明要对服务器上发资源执行的操作，常见的请求方法是GET和POST

<img src="C:\Users\tuzi\AppData\Roaming\Typora\typora-user-images\image-20220410220735148.png" alt="image-20220410220735148" style="zoom:50%;" />

###### HTTP响应状态代码

- HTTP响应状态码：用来 标识响应状态
- HTTP状态码由三个十进制数组组成，第一个十进制数字定义了状态码的类型，后两个数字用来对状态码进行细分
- <img src="C:\Users\tuzi\AppData\Roaming\Typora\typora-user-images\image-20220410225828344.png" alt="image-20220410225828344" style="zoom:50%;" />
- 2开头的有
  - 200：请求成功，一般用于GET与POST请求
  - 201：已创建：成功请求并创建了新的资源，通常用于POST或PUT请求
- 3开头的：要求客户端进一步的操作以完成资源的请求
  - 301:永久移动
  - 302：临时移动
  - 304：未修改

- 4开头的客户端错误
  - 400：语法错误
  - 401：当前请求需要用户验证
  - 403：服务器已经理解请求，但拒绝执行它
  - 404：服务器无法根据客户端的请求找到资源
  - 408：请求超时 
- 5开头服务端错误相关的响应状态码
  - 500：服务器内部错误，无法完成请求
  - 501：服务器不支持该请求方法
  - 503：由于超载或系统维护，服务器暂时无法处理客户端的请求

 
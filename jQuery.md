$是jquery别称，顶级对象，包装成jq

[jQuery](https://jquery.com/)

等DOM加载完执行l里面的代码  $(function(){})

1、dom对象转换为jQuery对象：$(DOM对象)

2、jQuery对象转换为dom对象:$('DOM对象')[索引] 

scroll  滚动

#### 选择器$('选择器')

设置样式$('div').css('属性','值‘)

自动遍历内部DOM元素的过程就叫做隐式迭代

#### 筛选选择器$('div：？')

语法（ ？）    ：first   第一个，：last 最后一个 ，：eq（index） 索引第index个，：odd 为奇=数的，：even 为偶数

<img src="C:\Users\tuzi\AppData\Roaming\Typora\typora-user-images\image-20220324140219870.png" alt="image-20220324140219870" style="zoom:80%;" />

​                $(this).index():得到当前索引号

parents：祖先

#### Jq操作css方法

1，参数是属性名必须加引号，属性值，逗号分隔  ，如果是数字可以不加引号，跟单位i   //不加当变量

//多个用对象形式

```js
$('div').css("width,100")
//多个用对象形式
$('div').css({width:100,height:100})
```

3,用添加类名的方式css中定义类的样式

```

```

1,添加类addClass（"类名"）

2，删除类 removeClass()

3,切换类  toggleClass（）//

```js
<style> .current{width:100;background:100  }</style>
<div><div>
$(this).toggleClass("current");     //有就删除，没有就添加
        
```

类操作与className区别

原生js中className会覆盖原先里面的类名，jQ只会对指定类进行操作，相当与追加

#### jQuery效果

手册 

1，显示 show（） ，隐藏hide（），切换tiggle()

2，滑动  下拉slideDown（）, 上次拉sllideUp（），slideToggle（），

3，淡入淡出 fadeln（） fadeout（）fadetoggle（）透明度fadeto（）

4，自定义

1：（[speed]，[easing],[fn]）                             speed:速度 三种预定速度之一 的字符串( "slow" ，"normal" , or "fast" )或表示动画时长的亳秒数值(如: 1000)。( 3) easing : (Optional)用来指定切换效果，默认是"swing” ,可用参数"Ilinear" 。 fn：回调函数

--------

事件切换

hover([over,]out）          //over:鼠标移入触发

```js
houver(functhion(){},function(){})     //第一个经过， 第二个离开
houver(functhion(){})              //每次都会触发sd
```

自定义动画animate（params，[speed ],[easing]）,params:想要修改 的样式，以对象形式

easing：用来指定切换效果

```js
$("button".click(function)(){
  $("div").animate({left:500,top:300,opacity:.},500) 
  })
```

#### jQuery属性操作

1、获取元素固有属性值prop（）      //获取：prop("属性‘")，//修改：元素.prop("属性"，“值”)     

2、 获取元素自定义属性attr（）

3、数据缓存data（），存在内存，也可以获取h5

4：：checked选择器  查找被选中的表单元素

#### JQuery内容文本值

1、普通元素内容 html（）     //包括标记          //（）为空就是获取，（值）就是赋值

2、普通元素内容 text（）不包括标签

3、获取表单值 val（）

保留小数toFixed（）

#### JQuery元素操作

1、遍历each $("对象").each(function(index,$(domEle)){xxx;})    //index(索引号)  domEle是元素对象（标签）

2、遍历对象   $.each($("对象")，function（i，ele）{})                //ix(索引号)  ele是元素对象

用来处理对象

3、创建元素$("<li></li>")

4、内部添加      $（"元素"）append（“内容”），放在元素内部最后面      

​						   $（"元素"）prepend（“内容”）,放在元素内部最前面      

 外部添加  	     $（"元素"）.after（“内容”）放在元素内部最后面    

​					   	$（"元素"）before（“内容”）,放在元素内部最前面     

5、删除 rmove（）     empty（）：清空

#### JQuery尺寸

1、width) 1 height()     取得匹配元素宽度和高度值只算width / height
2、innerWidth( 1 innerHieght()  取得匹配元素宽度和高度值包含padding
3、outerWidth) / outerHeight()  取得匹配元素宽度和高度值包含padding、border
4、outerWidth(true) / outerHeight(true)   取得匹配元索宽度和高度值包含padding、borde、 margin

#### JQuery位置



offset(）设置获取距离文档元素偏移， $("对象").offset().left              ,设置 $("对象").offset({top:100,left:200})

position() 带有定位的父级偏移坐标，只能获取，不能设置 

scrollTop       //被卷去的头部

scrollLeft      //

#### JQuery事件

1、单个事件注册  $("div").click(function(){})

2、事件处理on()绑定     element.on(event,event,[selector],fn)     多事件用对象形式      event:事件。 相同事件用空格隔开 ，在切换

2、off（） 可以移除通过事件On（）    $("div").off("click"),事件 

one（） 只能触发一次

3、自动触发事件   ，1、元素.事件（）2、元素.trigger(事件) 3、元素.triggerHandler('事件')。不会触发元素的默认行为

4、事件对象e，1、阻止默认行为 e.preventDefault()  或者return false 2、组织冒泡：e.stopPropagation

#### JQuery方法

对象拷贝$.extend()   语法   $.extend([deep],target, object1,[obj])      1、deep：深拷贝true /浅拷贝false。（浅拷贝把原来对象里面的复杂数据类型地址拷贝给目标对象） 2、target：要拷贝的目标对象。3、object1：待拷贝到第一个对象的对象



#### JQuery多库共存

1、把里面的$符号统一改为JQuery

2、JQuery变量规定新的名称：$.noConflict   var xx=$.noConflict

##### JQuery插件

www.jq22.com   jquery插件库              |                   www.htmleaf.com          jquery之家

图片懒加载

全屏滚动插件![image-20220327155202289](C:\Users\tuzi\AppData\Roaming\Typora\typora-user-images\image-20220327155202289.png)

bootstrap插件组件

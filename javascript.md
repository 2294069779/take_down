#    1、规范

## 1.1、 javascript

​	javascript由三部分组成ecmascript，	

​	DOM,BOM

​	书写位置有三种:行内式、内嵌式、外部式

<script src="qj.js"> </script>

## 1.2、

变量用名词；函数用动词

操作符的左右两侧各保留一个空格 



## 2、快速入门



## 2.1、基本语法入门

| alert(msg)         | 浏览器弹出警示框 |
| ------------------ | ---------------- |
| console.log（msg） | 控制台打印       |
| prompt（msg）      | 弹出输入框       |





==变量==

``` javascript
var xm=1 除了不能数字开头  
```





​	NaN:不是一个数字 

​	假如要验证NaN===NaN，只能通过ifNAN		（NAN)

----

==浮点数==

​	问题：

``` javascript
console.log((1/3)===(1-2/3))
答案是：flash 
```

​	尽量避免使用浮点数进行运算，存在精度问题！

```javascript
console.log(math.abc(1/3)-(1-2/3)）<0.00001
答案：true
```

​	==null和undefined==

- null空
- undefined 未定义     报错

​	==数组==



​	一系列相同类型 javascript不需要

``` javascript
 var ad = [1,2,3,44,'ni',true];
 控制台打印：console.log(ad[5])
 输出：ture
```

​	取数组下标，如果越界了，就会undefined



​	==对象==

​	对象用大括号，数组中括号

​	每个属性之间用逗号隔开，最后一个不用：

``` javascript
 var yg={
            name:"yg",
            age:3,
            tags:['js','java','....']
 控制台输入yg.name,yg.age,yg.tags
 分别打印
```



​	严格检查模式 'use strict' 必须写在第一行

​	局部变量建议使用let





# 3、数据类型

## 3.1

​	js是动态语言，变量类型动态的是由程序在运	行过程中，根据等号右边的值来确定的。

## 3.2简单数据类型

## 3.2.1数据类型

![image-20211113163050326](C:\Users\tuzi\AppData\Roaming\Typora\typora-user-images\image-20211113163050326.png)

​	isNaN（）这个方法用来判断非数字，并且返	回一个值如果是数字返回的是false，如果不是	数字返回true。NaN非数字的意思

![image-20211113170621493](C:\Users\tuzi\AppData\Roaming\Typora\typora-user-images\image-20211113170621493.png)

![image-20211113170816711](C:\Users\tuzi\AppData\Roaming\Typora\typora-user-images\image-20211113170816711.png)



----

# 4、字符运算

## 4.1、字符串

### 1、正常字符串我们使用单引号或双引号包裹

### 2、注意转义字符\

```javascript
\`
\n 换行
\t tab
\u4e2d 编码’中‘字 unicode字符
\64 Ascll字符
```

###   3、多行字符串

```javascript
  var yg =`sacas
              a你啊是擦
              1234`
  用“ ` ”包裹
```

### 4、模板字符串

```javascript
 var name = 'yg'
        var age = '12'

        let msg = `woshi${name}jingnian${age}`
直接使用模板不用在加+号
```

###  5、字符串长度

``` javascript
 var na="nascasas";    \\定义一个字符串
console.log(na.length); \\打印长度
console.log(na[5]); \\打印下标
console.log('shamo'+'sa');\\拼接
```

##### ![image-20211113202227565](C:\Users\tuzi\AppData\Roaming\Typora\typora-user-images\image-20211113202227565.png)

![image-20211113204009377](C:\Users\tuzi\AppData\Roaming\Typora\typora-user-images\image-20211113204009377.png)

### 6、typeof检测变量类型

```javascript
var a =20,b ='sa sa',c ="sa",d = true,f = 1.22;
  console.log(typeof a,typeof b,typeof c,typeof f,typeof d)
```

​	prompt取过来的值是字符型的

### 7、  数据类型转换

#### 	  转换为字符串：

```javascript
//方法一 变量.tostring（） 
var num =10;
   var str=num.toString();
   console.log(typeof str);  
//方法二 利用string变量
 console.log(String(num));
//重要方法利用字符串拼接的方法实现转换效果
 console.log(num+'');
```

#### 	转换为数字型（重点）

![image-20211114142923527](C:\Users\tuzi\AppData\Roaming\Typora\typora-user-images\image-20211114142923527.png)

````javascript
\\使用parseInt（变量）可以把字符型的转换为数字型，只能整数
var age = prompt ('输入字符');
  console.log(parseInt(age));
\\使用parseFloat(变量)可以把字符型的转换为数字型的 得到的是小数 浮点数
  var age =prompt('1.222');
 console.log(parseFloat(age));
\\Number()强制转换函数
 var age= prompt('1.22');
 console.log(Number(age));
\\隐式转换
````

#### 	转换为布尔型

![image-20211115133707127](C:\Users\tuzi\AppData\Roaming\Typora\typora-user-images\image-20211115133707127.png)

代表空、否定的值会被转换为false，如 0、NaN、null、undefined。

其余值都会转换为true



#### 	大小写转换： 

```javascript
//注意，这是方法，不是属性
console.log(na.toUpperCase())//大写
console.log(na.toLocaleLowerCase())//小写
```

### 8、na.indexof（‘t’）获取下标 

### 9、  na.substring(1)从第一个截取到最后一个

   na.substring(1.3)从第1个到第三个

------

## 4.2、运算符

### 1、算数运算符

​	表达式：由数字、运算符、变量等组成的式子。

​	返回值；表达式的结果  

### 2、递增和递减运算符

​		++  -- 

### 3、比较运算符

![image-20211119211751395](C:\Users\tuzi\AppData\Roaming\Typora\typora-user-images\image-20211119211751395.png)

### 4、逻辑运算符

![image-20211119212135972](C:\Users\tuzi\AppData\Roaming\Typora\typora-user-images\image-20211119212135972.png)

###   5、赋值

= += -= 

### 6、优先级

![image-20211119220721845](C:\Users\tuzi\AppData\Roaming\Typora\typora-user-images\image-20211119220721845.png)

## 4.2、数组

​	Array可以包含任意的数据类型 

### 	1、长度

```javascript
var arr = [1,2,3,4,5,6]//创建
console.log(arr)//打印
arr.length   //长度
alert(arr1[5]);
arr[0]=1       //
```

​	注意:加入给arr.length赋值，数组大	小就会发生变化~ 

​	通过下标取值和赋值

### 	2、indexof，通过元素获得下标索

```javascript
var a=[1,2,3,4,5,6,7]

arr.indexof(2) 获得下标索引 
```

​	字符串的”1“和数字1是不同的



### 	3、slice（）截取array的一部分，返	回一个 新数组、

```javascript
arr.slice(3)
(3) [4, 5, 6]
```

### 4、尾部push    pop， 头部 unshift  shift ，排序 sort，元素反转 reverse， 添加concat，  连接符 jion

```javascript
尾部
arr.push('a')增加
arr.pop是减少
头部
arr.unshift()增加
arr.shift（）减少
arr.sort（）排序小到大
arr.reverse()元素反转
arr.concat() 拼接，注意并没有修改原数组，只是会返回一个新的数组
arr.jion(-) 连接符 打印连接数组，使用特点的字符串连接
arr=[[1,2],[3,4],[5,6 ]]  多维数组
arr[1,1]取值
```

### 5、遍历数组

![image-20211121153518054](C:\Users\tuzi\AppData\Roaming\Typora\typora-user-images\image-20211121153518054.png)



## 4.3、对象

若干个键值对

```javascript
    var 对象名={
            属性名：属性值，
            属性名：属性值，
            属性名：属性值，
             }
```

js中的对象，{....}表示一个对象，键值对由属性名，属性值构成，多个属性之间使用逗号隔开，最后一个不加逗号！

### 1、对象赋值

```javascript
pro.score
0
pro.score=60
60
pro
{name: 'ljm', age: 3, score: 60}
```



### 2、使用一个不存在的对象属性，不会报错！

### 3、动态是删减属性和添加

```javascript
delete pro.age \\删除属性age
true
pro
{name: 'ljm', score: 60}
pro.haha='sb' \\添加属性haha
pro
{name: 'ljm', score: 60, haha: 'sb'}
```

### 4、判断属性值是否在这个对象中！

```javascript
'name' in pro 
true
// 继承
```

### 5、判断一个属性是否是这个对象自身拥有的

```javascript
pro.hasOwnProperty('name')
true
```

 

-----------



## 4.4、流程控制

###      if判断

```javascript
 var ag=3;
        if(ag>3){
            alert("haha");
        } else {
            alert("kuwa");
        }
```

### 三元表达式

```javascript
var Num=5;
    var re = Num>5 ? '是' :'不是的';//判断是还是
```



### while循环，得避免程序死循环

```javascript
var ag=3;
        while(ag<100){
            ag=ag+1;
            alert(ag);
```

### for循环

```javascript
for(let a=5;a < 100;a++){
          console.log(a)
      }
```

### forEach循环

```javascript
 var gg=[1,2,3,7,3,,3,4,4]

        gg.forEach(function(value) 
        {
            console.log(value)
        })
```

### 关键字

```javascript
continue//立刻跳出本次循环，继续下一次循环
break//跳出循环
```





# 重点：冒泡排序

 ```javascript
 var a =[5,4,3,2,1]
     for(i=0;i<a.length;i++){
         for(j=0;j<=a.length-i-1;j++ ){
             if(a[j]>a[j+1]){
                 var temp=a[j];
                 a[j] = a[j+1];
                 a[j+1] =temp;
             }
         }
 
     }console.log(a);
 ```

# 5、函数

## 1、函数的概念

![image-20211123212829205](C:\Users\tuzi\AppData\Roaming\Typora\typora-user-images\image-20211123212829205.png)




































































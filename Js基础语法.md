## JavaScript基本语法 ##
#### 位置 ####
1. <head\> ... </head\>之间
2. <body\> ... </body\>之间
3. 放在外部文件中
#### 输出 ####
1.

    <!DOCTYPE html>
	<html>
	<body>
	
	<h1>My First Web Page</h1>
	
	<p id="demo">My First Paragraph</p>
	
	<script>
	/*找到id为demo的元素，将其内容改为 My First JavaScript*/
	document.getElementById("demo").innerHTML="My First JavaScript";
	</script>
	
	</body>
	</html>
2.

	<!DOCTYPE html>
	<html>
	<body>
	
	<h1>My First Web Page</h1>
	
	<script>
	document.write("<p>My First JavaScript</p>");
	</script>
	
	</body>
	</html>
#### 语句特点 ####
- 每条语句以分号结尾
- 忽略多余空格
- 代码块以{ ... }包裹
- 对大小写敏感
- 逐行执行，无需预编译

#### 注释 ####
- 单行注释 **//**
- 多行注释 /* ... */
#### 变量 ####
变量的3个元素

	var name="zhangshang"; //字符型
	var age=18; //数值型
	var sex; //默认值为undefined
- 变量声明关键字 var
- 变量名
	- 变量以**|字母|&|_|**开头
	- 区分大小写
- 变量值,分为数值型和字符型，字符型以双引号或单引号括起来。
	
#### 变量类型 ####
1. 变量拥有动态类型
```
	var x                // x 为 undefined
	var x = 6;           // x 为数字
	var x = "Bill";      // x 为字符串
```
2. 字符串
```
var name1="zhangshang";//可以双引号
var name2='zhangshang';//可以单引号
```
3. 数字
```
var age=18;//整数
var weight=120.45;//小数
var y=123e5;//科学计数
```
4. 布尔
```
var x=true;
var y=false;
```
5. 数组
*数组元素的类型可以不同*
```
//方式1
var names = new Array();
names[0] = "name1";
names[1] = "name2";
names[2] = "name3";

//方式2
var names = new Array(""name1","name2",name3",111);

//方式3
var names = ["name1","name2","name3"];
```

6. 对象
每声明一个变量，就等于创建了一个对象
对象声明：{key:value , key:value , ... , key:value}
对象属性引用： 对象.属性
对象方法钓鱼呢: 对象.方法名()
```
var person = {name : "zhangshang" , age : 18 ,sex : "男" , adress : null};
var name = person.name;
var age = person.age;
var sex = person.sex;
var len = name.lenght();
```
#### 函数 ####
1. 创建一个函数
使用关键字function 来声明，将代码块放在{ ... }内
```
//1. 无参，无返回值
function method1(){
	alert("method1");
}

//2. 无参，有返回值
function method2(){
	return "返回值";
}

//3. 有参，多个参数间以逗号隔开
function method3( name , age , sex ){
	alert(name+age+sex);
}
```
2. return 既可以用来作为一个函数返回，也可以用来结束函数
```
fucntion method4( x , y ){
	if(x>y)
		return;			//如果x>y那么直接结束函数，不会执行下面这句话
	alert(x+y);
}
```    
3. 2种变量
a. **局部变量**：在函数中声明，只能该函数里面访问，随着函数执行完而销毁
b. **全局变量**：在函数外声明，该页面中任何函数都可访问，随着页面销毁而销毁	
#### 运算符 ####
运算符基本与java一致
注意只有:
++age,没有age++
#### 比较和逻辑运算符 ####
基本与java一致
注意:
```
var x = 5;
x == "5";  // == 表示值相等  true
x === "5";	// === 表示 值跟类型都相同 false
var result = x >4?true:false; //支持 表达式 ? value1 : value2;
```
#### 逻辑控制 ####
1. if (条件){ ... } else if (条件){ ... }
2. switch(条件){...}
3. while(条件) { ... }
4. do{ ... } while(条件)
5. for(;;){ ... }
6. break  continue
带表签的用法
```
label1:{
    for (var i = 0; i < 10; i++) {
        label2:{
            for (var j = 0; j < 20; j++) {
                if (j > 10)
                    break label2;	//当j>10的时候，跳出内层循环
                if (i > 5)
                    break label1;	//当i>5的时候，跳出外出循环
                alert("i=" + i + "  j=" + j);
            }
        }
    }
}
```
#### 错误 ####
在可能发生错误的地方使用
```
try{
	//可能发生错误的地方
	//可以自定义一个错误
	if(条件)
		throw "错误信息";
}catch( err ){
	//err 为错误对象
	//当发生错误的时候，执行的操作
}
```
例如：
```
function method(x) {
	try {
	    if(x>5)
	        throw "x不能大于5";
	    if(x>4)
	        throw "x不能大于4";
	    if(x>3)
	        throw "x不能大于3";
	    var errVar=x/0;		//这里并不会抛出异常
	    alertt("errVar= "+errVar);	//这里将抛出异常
	}catch (err){
	    document.getElementById("demo").innerHTML=err+"";
	}
}
```




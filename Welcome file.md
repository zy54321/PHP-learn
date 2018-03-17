
# 一，PHP学习之基础篇

## 1，基础语法

### 1.1常量，不可以改变的量
  
      在多数情况下,所有字母大写 多个字母命名使用下划线隔开 
      第一个字符:定义常量名
      第二个字符:常量值
      第三个字符:可选,使用常量名时,是否区分大小写,默认false 不支持
      
例子:

```php
      
      define("NAME","好男人");
      define("CAT_NAME","波斯猫",true); //true允许大小写识别,false不允许
      echo cat_name;  //因为true允许大小写识别,所以能够显示CAT_NAME内容
      echo NAME; //echo显示:好男人
      
```
      
### 1.2变量, 定义变量没有关键字,属于弱类型语言
  
      相比于 JS 定义变量, PHP 定义一个变量不需要关键字 var ,直接 $ 加上变量名即可
      
例子:
```php
      $name = "小明";
      $age = 18;
      echo $name;
 ```

### 1.3输出返回显示

     注意:PHP的Boolean值的返回值与JS的不一样,在PHP中
     
```php
     $flag = true; 
     echo $flag;//false 为0但不显示,true显示1
```
#### 1.3.1 var_demp  输出对象和数组
可以输出变量的具体信息,比如类型,长度,值等
是所有输出方法中输出信息最丰富的
例子:
```php
	var_dump($flag);//bool(true)
	var_dump($name);//string(6) "小明"
	$arr = \[1.1,2,-3\];
	var_dump($arr);//array(3) { \[0\]=> float(1.1) \[1\]=> int(2) \[2\]=> int(-3) }
```
#### 1.3.2 echo  直接输出字符或字符串
可以直接输出字符或字符串,但不能输出数组和对象
```php
	//echo不能打印数组和对象
	echo $arr;//会报错
	//可以打印多个变量
	echo $name,$age,$flag;//小明181
```
#### 1.3.3 print  打印
函数print()打印一个值（它的参数），如果字符串成功显示则返回true，否则返回false。
不能打印数组
```php
	print ($name);//小明
	print ($arr);//报错
```
#### 1.3.4 printf  格式化输出
一般用于向标准输出设备按规定格式输出信息
```php
	//type的字符用于规定输出数据的类型  https://baike.baidu.com/item/printf/7467706?fr=aladdin
	printf("name的值是%s,age的值是%d",$name,$age);//name的值是小明,age的值是18
```
#### 1.3.5 print_r  输出语句
相对于print,可以输出数组和对象,相对var_dump输出不是那么详细
可以把字符串和数字简单地打印出来，而数组则以括起来的键和值得列表形式显示，并以Array开头。
```php
	print_r($arr);//Array ( \[0\] => 1.1 \[1\] => 2 \[2\] => -3 )
	print_r($name);//小明
```
### 1.4 & 引用  
变量或者函数、对象等前面加上&符号
在PHP 中引用的意思是：不同的名字访问同一个变量内容。  
与Ｃ语言中的指针是有差别的．Ｃ语言中的指针里面存储的是变量的内容，在内存中存放的地址。

```php
	//PHP 的引用允许你用两个变量来指向同一个内容
	$m  = 10;  
	$n = &$m; //$m的地址赋值给$n;  
	echo $n;  //10
	$n = 220;  
	echo $m; //220
```
### 1.5 $变量名 和 $$变量名 变量的变量   
```php
	//变量的变量
	$value1 = "hello";
	$$value1 = "world"; //相当于$hello = "world";
	$$$value1 = "阿斯玛";
	echo $$hello; //阿斯玛
```
## 2，数据类型
### 2.1 基本概念
主要有三种类型
```
1，标量类型：比如:整型integer  浮点数float/double  
           字符串string  布尔boolean true/false
2，复合类型：比如数组，对象
3，特殊类型：资源类型 null
```
### 2.2 float double 浮点数 
有两种，float和double
```php
	$a = 1.0;  
	var_dump($a);//float(1)
	$b = 1.134615446541316821675136321654;  
	var_dump($b);//float(1.1346154465413)
	$c = (float)$b;  
	var_dump($c."~~~123");//string(21) "1.1346154465413~~~123"
	$d = (double)1.21532165761321687615213;  
	echo $d;//1.2153216576132
```
### 2.3 gettype 获取数据类型 
```php
	echo gettype($c);//double
``` 
### 2.4 （int）（string）（array）强制类型转换
```php
	$m = "123";
	$n = (int)$m;
	var_dump($n);//int(123)
  
	$x = 3.14;
	$y = (string)$x;
	var_dump($y);//string(4) "3.14"
  
	$z = (array)5.6;
	var_dump($z);//array(1) {[0]=> float(5.6)}
```
## 3，运算符
算术运算符和JS一样
### 3.1 字符串拼接
主要有三种方法
```php
	//字符串拼接
	$b = "班长";
	$c = "真白";
	$d = $b.$c;
	echo $d;//班长真白
	$b .= $c;
	echo $b;//班长真白
```
### 3.2 += 运算
```php
	//+=运算
	$m = 1;
	$m += 1;
	echo $m;//2
```
### 3.3 比较运算符
```php
	//比较运算符 \> < >= <= == !=
	$x = "1" == 1; 
	$y = "1" === 1; //三个等号指值一样，类型也要一样
	var_dump($x);//bool(true)
	var_dump($y);//bool(false)
```
### 3.4 逻辑运算符
```php
	//逻辑运算符 && || !
	$xx = true;
	$yy = false;
	$zz = false;
	//异或 xor  不一样为真  
	if ($xx xor $zz) {  
		  echo "真";  
	} else {  
		  echo "假";  
	}  
	echo "<hr>";  
	if ($xx xor $zz xor $yy) {  
		  echo "真";  
	} else {  
		  echo "假";  
	}
```
## 4，分支语句
### 4.1 if判断语句
```php
	//if 判断语句
	$a = 1;
	if ($a == 1) {

	} else if ($a == 0) { 

	} else {
	}
```
### 4.2 switch语句
```php
	switch ($a) {
	case 1:
	echo "a的值是1";
	break;
	case 2:
	echo "a的值是2";
	break;
	case 3:
	echo "a的值是3";
	break;
	}
```
## 5 for 循环
```php
	//for循环
	for ($a = 0; $a < 10; $a++) {
		echo $a."<br>";
	}
	$arr = \[1,2,3,4,5\];
	for ($i = 0; $i < 5; $i++) {
		echo $arr\[$i\]."<br>";
	}
```
## 6函数
### 6.1 格式写法
```php
	$a = 10;
	//PHP的函数存在作用域概念
	function text () {
		//$a = 100;
		//全局变量在函数内部访问,需要添加关键字global
		global $a; //在函数内使用函数外的全局变量,需加上global
		echo $a + 1;
		$a = 100;
	} 
	text();
	echo $a; //100
```
### 6.2 静态变量
静态变量只存在于函数作用域内，也就是说，静态变量只存活在栈中。一般的函数内变量在函数结束后会释放，比如局部变量，但是静态变量却不会。就是说，下次再调用这个函数的时候，该变量的值会保留下来。
```php
//静态变量
	function counter() {
		static $count = 0; //一直在函数中,不被释放,作用域为本函数
		return $count++;
	}
	echo counter()."<br>";//1
	echo counter()."<br>";//2
	echo counter()."<br>";//3
	echo counter()."<br>";//4
	echo counter()."<br>";//5
	echo counter()."<br>";//6
	//echo $count; //报未定义错误
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyMDQ1NzkwMjldfQ==
-->
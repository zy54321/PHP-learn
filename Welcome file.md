
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
### 1.4 引用 
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
### 1.5 变量的变量
```php
	//变量的变量
	$value1 = "hello";
	$$value1 = "world"; //相当于$hello = "world";
	$$$value1 = "阿斯玛";
	echo $$hello; //阿斯玛
```



<!--stackedit_data:
eyJoaXN0b3J5IjpbLTU2NjE4MTg1XX0=
-->
# 二，PHP学习之基础篇（2）
主要内容有变量，字符串操作，索引数组，关联数组
## 1，内部变量与魔术变量
内部变量 指系统提供的变量

```			
	//内部变量  系统提供的变量		
	//PHP_OS 获取当前运行的操作系统		
	echo PHP_OS; //Darwin MAC OS系统			

	//PHP_VERSION  获取当前PHP版本		
	echo PHP_VERSION;
```

魔术变量 	输出值不固定，随着当前状态变化而变化

```
	//魔术变量  输出值不固定,随着当前状态变化而变化
	//__FILE__  当前文件所在路径
	echo __FILE__;
	echo "<hr>";

	//__LINE__  当前行数
	echo __LINE__;
	echo "<hr>";

	//__FUNCTION__  当前函数的函数名
	function aaa() {
    	echo  __FUNCTION__;
	}
	aaa();

	//前后端交互相关
	$_GET;
	$_POST;
```	

## 2,字符串
### 2.1 拼接
有三种方法，不过第三种方法不常用

```
	$value = $name."今年".$age."岁了!!!!!";
	echo $value;

	$value1 = "郝伟是{$name},今年{$age}岁了";
	echo $value1;

	$value2 = "郝伟是$name,今年$age 岁了";
	echo $value2;
```

### 2.2 定界符 <<<
可用来输出大段的html和javascript脚本	

```	
1.PHP定界符的作用就是按照原样，包括换行格式什么的，输出在其内部的东西；		 
2.在PHP定界符中的任何特殊字符都不需要转义；		 
3.PHP定界符中的PHP变量会被正常的用其值来替换。	
```

```
	//以<<< 开头  命名自定义,可以随意  结束名前不能有空格
	$str1 = <<<name
    	<a href='http://www.baidu.com'>百度一下</a>
    	<p>这是另一个标签</p>
    	<div>!!!!!!!!!!!</div>
    	<span>去玩儿</span>
    	<h1>奥斯卡绝代风华</h1>
	name;
	$str2 = <<<name
    	<a href='http://www.baidu.com'>百度一下</a>
    	<p>这是另一个标签</p>
    	<div>!!!!!!!!!!!</div>
    	<span>去玩儿</span>
    	<h1>奥斯卡绝代风华</h1>
	name;
	echo $str1;
	echo $str2;
```	
### 2.3 字符串长度 strlen
获取当前字符串长度

```
	$str4 = "abc123"; //字母和数组占一个字符长度
	$str5 = "五险义"; //一个汉字占三个字符长度
	echo strlen($str4);
	echo "<br>";
	echo strlen($str5);
	echo "<hr>";
```
### 2.4 去掉空格 trim ltrim rtrim
去掉首尾空格 trim		
去掉左边空格 ltrim		
去掉右边空格 rtrim

```
	$str6 = "   Hello  World   ";
	echo "~~~".$str6."~~~";
	
	echo "~~~".trim($str6)."~~~";//去掉首尾空格
	
	echo "~~~".ltrim($str6)."~~~";//去掉左边空格
	
	echo "~~~".rtrim($str6)."~~~";//去掉右边空格
```
### 2.5 大小写转换 strtolower strtoupper ucwords ucfirst
转换成小写 strtolower
转换成大写 strtoupper
每个单词首字母大写 ucwords
字符串首字母大写 ucfirst

```
	$str7 = "li jun qin";
	$str8 = "YAN ZI YE";
	echo strtolower($str8)."<br>"; //转换成小写
	echo strtoupper($str7)."<br>"; //转换成大写
	echo ucwords($str7)."<br>"; //每个单词首字母大写
	echo ucfirst($str7)."<br>"; //字符串第一个字母大写
```
### 2.6 倒序输出 strrev
```
$str8 = "Hello World";
echo strrev($str8);
```
### 2.7 拆分字符串 explode implode
拆分 explode
添加 implode

```
	$str9 = "特大炮,金三胖,默大妈,习大大";
	$arr = explode(",",$str9);
	var_dump($arr);//array(4) { [0]=> string(9) "特大炮" [1]=> string(9) "金三胖" [2]=> string(9) "默大妈" [3]=> string(9) "习大大" } 

	$str10 = implode("~",$arr);
	echo $str10;//特大炮~金三胖~默大妈~习大大
```
### 2.8 子串在字符串中的位置 strpos
查询字串,当发现第一个后就停止查询 strpos

```
	$s1 = "Hello World";
	echo strpos($s1,"ll");//查询 ll 子串 在字符串中位置,当发现第一个后就停止查询
	echo "<br>";
	var_dump(strpos($s1,"a"));//当子串不存在时,显示为false
	echo "<hr>";
```
### 2.9子串操作 substr
在字符串中截取对应子串 substr
获取子串在字符串中的个数 substr_count
替换删除添加子串 substr_replace


```
	$s2 = "Good Good Study";
	echo substr($s2,3,3)."<br>"; //substr(字符串对象,开始字节数位置,截取字节数长度,若是没有写长度就默认截取剩下所有的)
	echo substr_count($s2,"oo")."<br>"; //获取 子串o 在字符串中的个数
	echo substr_replace($s2,"123",2)."<br>"; //在 字节数2位置 替换后面内容为 123
	echo substr_replace($s2,"123",2,4)."<br>"; //从 字节数2 开始替换后面 字节数4 个字节
	
	//删除 下标2到下标8的子串
	echo substr_replace($s2,"",2,8)."<br>";
	
	//插入 在下标2位置插入
	echo substr_replace($s2," ~O o O~ ",2,0)."<br>";
```

## 3,索引数组
### 3.1 数组定义的两种方式 [], array()

```
	//数组定义两种方式
	$arr = [1,2,3,4,5];
	$arr1 = array(1,"2",3,4,5);
```

### 3.2 打印数组的两种方式 print_r var_dump

```
	$arr = [1,2,3,4,5]		
	$arr1 = array(1,"2",3,4,5);
	//打印数组两种方式
	print_r($arr);//Array ( [0] => 1 [1] => 2 [2] => 3 [3] => 4 [4] => 5 )
	echo "<hr>";
	var_dump($arr1); //显示类型		
	//array(5) { [0]=> int(1) [1]=> string(1) "2" [2]=> int(3) [3]=> int(4) [4]=> int(5) }
```

### 3.3 改变下表对应的元素的值 
改变方式和JS数组一样

```
	$arr = [1,2,3,4,5]
	//改变某个选标对应的元素值
	$arr[3] = "张勇";
	echo "<hr>";
	var_dump($arr);

	echo "<hr>";
	$arr[] = "齐颜"; //当没有明确下标号时,就添加至数组最后一位
	print_r($arr);
```

### 3.4 获取下标对应元素的值
```
	//获取下表对应的值
	echo "<hr>";
	print_r($arr[3]);
```

### 3.5 删除元素 unset array_pop array_shift
删除元素  unset		
删除数组尾部元素  array_pop		
删除数组首部元素,并且删除后下标会重新排序  array_shift

```
	//删除元素
	unset($arr[3]);
	print_r($arr);

	//删除数组尾部的元素
	array_pop($arr2);
	print_r($arr2);

	//删除数组中的首位元素,下标会重新排序
	print_r($arr);
	array_shift($arr); //删除头部元素,会重新排序
	print_r($arr);
```

### 3.6 添加元素 array_unshift
有两种方式		
头部添加元素  array_unshift
根据下标直接添加  [***]		

```
	//添加头部元素
	echo "<hr>";
	array_unshift($arr,999);
	print_r($arr);

	$arr[100] = 666;
	print_r($arr);
```
### 3.7 判断元素是否在数组中 in_array
in_array 判断元素是否在数组中,如果存在返回true,否则返回false  

```
	//判断元素是否在数组中,返回布尔值,存在返回true,不存在返回false
	echo "<hr>";
	var_dump(in_array("小乔",$arr));
	var_dump(in_array("1",$arr));
```

### 3.8 数组去重 array_unique
自动对数组去重 array_unique

```
	//数组去重
	echo "<hr>";
	$arr2 = [1,2,5,1,2,5,3,6,6,5];
	$arr3 = array_unique($arr2);
	print_r($arr3); //Array ( [0] => 1 [1] => 2 [2] => 5 [6] => 3 [7] => 6 )
```

### 3.9 遍历数组 
小练习

```
	//遍历数组
	echo "<hr>";
	for ($i = 0; $i < count($arr4); $i++) {
    	echo $arr4[$i]."<br>";
	}
```


## 4,关联数组
### 4.1 关联数组 =>

```
	//关联数组
	$arr = ["name"=>"郝伟","age"=>998];
	print_r($arr);
```

### 4.2 取值 ```$arr[""];```

```
	//取值
	echo $arr["name"];
```

### 4.3 添加键值对 ```$arr["sex"] = "man";```

```
	//添加键值对
	$arr["sex"] = "man";
	print_r($arr);
```		

### 4.4 修改或添加 

```
	//修改或添加  如果存在则修改,如果不存在就添加
	$arr["age"] = 5;
	print_r($arr);
```

### 4.5 value值 ```$v```
用于foreach,代表关联数组的value值

```
echo "<hr>";
foreach ($arr as $v) {
    //$v 代表数组中每个value值
    echo $v."<br>"; //遍历并显示每个key对应的Value值
}
```

### 4.6 key值 ```$k```
用于foreach遍历数组,代表关联数组中键值

```
	echo "<hr>";
	foreach ($arr as $k=>$v) {
    	//$k 代表数组key值  $v 代表数组Value值
    	echo $k.":".$v."<br>";
	}
	echo "<hr>";
```

### 4.7 数组元素 ```$a```
用于foreach遍历数组用,直接代表数组每个元素

```
	$arr1 = [1,2,3,4];
	foreach ($arr1 as $a) {
    	//$a 代表数组元素
    	echo $a."<br>";
	}
	echo "<hr>";
```

### 4.8 获取所有value值 array_values; 获取所有key值 array_keys
获取关联数组所有value值

```
	print_r($arr);
	//取出所有的value值
	$valueArr = array_values($arr);
	//取出所有的key值
	$key = array_keys($arr);
	print_r($valueArr);
	print_r($key);
```

### 4.9 判断key值是否存在 inset
判断某个key值是否在关联数组中

```
	//判断某个key值在关联数组中是否存在
	var_dump(isset($arr["name"])); //存在返回true
	var_dump(array_key_exists("name",$arr));  //存在返回true
```

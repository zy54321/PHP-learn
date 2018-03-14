# PHPLearn
PHP的学习,入门小白级别,记录自己学习PHP过程

一，PHP学习之基础篇

1，基础语法

1.1常量，不可以改变的量
  
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
      
1.2变量, 定义变量没有关键字,属于弱类型语言
  
      相比于 JS 定义变量, PHP 定义一个变量不需要关键字 var ,直接 $ 加上变量名即可
      
例子:
```php
      
      $name = "小明";
      
      $age = 18;
      
      echo $name;
      
 ```

1.3输出返回显示

     注意:PHP的Boolean值的返回值与JS的不一样,在PHP中
     
```php
     $flag = true; //false 为0但不显示,true显示1
```

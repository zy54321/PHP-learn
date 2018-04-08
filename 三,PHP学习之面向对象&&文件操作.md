# 三,PHP学习之面向对象&&文件操作
## 1, 创建类 class
创建类,多个对象共有的属性可以放进一个类里面		
每创建一个对象要先调用类然后给这个对象赋予属性值    
在类里面可以添加方法,是你希望创建的对象执行的方法    

```
	class Person {
    	//public 定义属性,可以给默认值
    	public $name = "111"; //给默认值
    	public $sex;
    	public $age;

    	//类对应的方法
    	function sayHello() {
        	echo $this->name."说你好";
    	}
	}

	//创建对象
	$person = new Person();
	//打印对象
	print_r($person);

	//为属性赋予值
	$person->name = "潇洒哥";
	$person->age = "998";
	$person->sex = "未知";

	print_r($person);

	//对象调用方法
	$person->sayHello();
``` 

## 2,类常量 const
指在类中不可以改变的量		
设置雷常量 const::常量名		
在类外面使用类常量  对象名:: 常量名

```
	class Person {
    	//在类中,不可以改变的量
    	const COUNTRY = "CHINA";
    	public $name;
    	function sayHello() {
        	echo "<br>";
        	//:: 范围解析符
        	//类内部使用
        	echo self::COUNTRY."~~~~";
   		}
	}

	$person = new Person();
	$person->sayHello(); //调用函数

	//在类外面使用常量
	//通过对象获取 对象名 :: 常量名
	echo $person::COUNTRY; //因为前面定义对象了

	//通过类名获取,比较规范的方式
	echo Person::COUNTRY;
```

## 3,构造函数 \_\_construct  解析函数 \_\_destruct
\_\_construct 构造函数属于系统内部方法,自动调用,括号内属性名用于新建对象时传参
构造函数好处是可以接受传参,创建对象可以根据需求调整属性值,并且可以不用如上所述创建对象后还要再进行对新建对象赋予属性值

\_\_destruct 析构函数,属于系统内部方法,自动调用
创建多少个对象就析构多少次函数
文件执行完毕时,将创建的对象在内存中销毁
当页面执行完才会析构函数,析构出的结构放在最后

```
	class Dog {
    	public $name;
    	public $sex;
    	public $age;

    	//__construct  构造函数,属于系统内部方法,写不写都会调用 括号内属性名用于新建对象时传参
    	//构造函数属于系统内部方法,在创建对象时,自动调用
    	//函数名__construct 不可更改
    	//好处是可以接受传参,创建的每个对象可以根据需求调整属性值
    	function __construct($theName,$theSex,$theAge){
        	$this->name = $theName;
        	$this->sex  = $theSex;
        	$this->age  = $theAge;
    	}

    	//__destruct  析构函数,属于系统内部方法,在创建对象时,自动调用
    	//创建多少个对象就析构多少次函数
	    //文件执行完毕时,将创建的对象在内存中销毁
    	//当页面所有文件执行完才会析构函数,析构出的结果放在最后
    	function __destruct()
    	{
        	// TODO: Implement __destruct() method.
        	//__FUNCTION__ 显示函数名
        	echo "<br>".__FUNCTION__;
    	}
	}
```
运行结果:

```
	运行代码例子:
	$dog = new Dog("旺财",3,"公");
	echo $dog->name;//旺财
	$dog2 = new Dog("斗牛犬",4,"母");
	echo "<hr>";
	print_r($dog2);//Dog Object ( [name] => 斗牛犬 [sex] => 4 [age] => 母 )
	$dog3 = new Dog("边牧",4,"公");
	echo "<hr>";
	print_r($dog3);//Dog Object ( [name] => 边牧 [sex] => 4 [age] => 公 )
	for ($i = 0; $i < 10; $i++) {
    	echo "<hr>$i";
	}
```

## 4,继承 extends
可以用子类继承父类的属性和方法		
父类:		

```
class Person {
    public $name;
    public $age;
    public $sex;

    //构造函数接受传参
    function __construct($theName = "范冰冰",$theAge = 3,$theSex = "女")
    {
        $this->name = $theName;
        $this->age = $theAge;
        $this->sex = $theSex;
    }
    //方法
    function eat() {
        echo $this->name."吃好吃的";
    }
}
```

子类继承父类属性和方法:		

```
	//继承  继承目标属性  使用关键字 Person
	class Student extends Person {
    	public $score;
    	//重写父类方法 这个很多大公司面向对象程序都有的
    	//使用场景: 既想实现父类方法的功能,又想在此方法上添加功能
    	//如果不想实现父类方法,重新定义功能,则不调用父类方法
    	function __construct($theName = "范冰冰",$theAge = 3,$theSex = "女",$theScore)
    	{
        	parent::__construct($theName,$theAge,$theSex);
        	$this->score = $theScore;
    	}
    	//重新定义父类的eat()方法
    	function eat() {
        	parent::eat();
        	echo __FUNCTION__;
    	}
	}
```

运行实例:		

```
	$stu1 = new Student("齐颜",18,"男",100);
	print_r($stu1);//Student Object ( [score] => 100 [name] => 齐颜 [age] => 18 [sex] => 男 )
	//对象调用父类方法
	$stu1->eat();//齐颜吃好吃的eat

	//新建Person对象调用方法时,直接用父类属性
	$per = new Person();
	$per->eat();//范冰冰吃好吃的
```

## 5,类属性和方法的可见度 public protect private
总结:		
//可见度		
//父类的属性和方法  在子类中是否可以使用		
//子类的对象是否可以使用父类的方法和属性		
//public 公开的 父类子类都可使用对象 其对象也可以访问		
//protected 表示受保护的，只有本类或子类或父类中可以访问；		
//private 表示私有的，只有本类内部可以使用；		

public:

```
	class Person {
    	public $name;
    	public $age;
    	public $sex;

    	function sleep() {
        	echo "睡觉觉";
    	}
	}
	class Student extends Person{
    	public $score;
    	function sleep() {
        	echo $this->name."睡觉觉";
    	}
	}
	$stu = new Student();
	$stu->age = "18"; //因为public是公开的,所以在类的外面创建的对象可以查看和修改public对象
	print_r($stu);
```

protect:

```
	class Person {
    	protected $name;
    	protected $age;
    	protected $sex;

    	protected function sleep() {
        	echo $this->name."睡觉觉";
    	}
    	function abc() {
        	$this->sleep();
        	echo "<br>".__FUNCTION__;
    	}
	}
	class Student extends Person{
    	function abc() {
        	$this->sleep();
    	}
	}

	//protected 指受保护的,本类和子类内部可以访问, 对象不可以访问
	$per = new Person();
	//$per->name = "qwe"; //因为Protext保护了属性,所以外面的对象不可以使用类的属性
	//echo $per->name;

	//$per->sleep(); //因为Protext保护了方法,所以外面的对象不可以使用类的方法

	$per->abc();

	$stu = new Student();
	$stu->abc();
```

private:

```
	class Person {
    	private $name;
    	private $age;
    	private $sex;

    	private function sleep() {
        	echo $this->name."睡觉觉";
    	}
    	function abc() {
        	$this->sleep();
        	echo "<br>".__FUNCTION__;
    	}
	}

	$per = new Person();
	$per->abc();
```
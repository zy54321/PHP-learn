---


---

<h1 id="一，php学习之基础篇">一，PHP学习之基础篇</h1>
<h2 id="，基础语法">1，基础语法</h2>
<h3 id="常量，不可以改变的量">1.1常量，不可以改变的量</h3>
<pre><code>  在多数情况下,所有字母大写 多个字母命名使用下划线隔开 
  第一个字符:定义常量名
  第二个字符:常量值
  第三个字符:可选,使用常量名时,是否区分大小写,默认false 不支持
</code></pre>
<p>例子:</p>
<pre class=" language-php"><code class="prism  language-php">      
      <span class="token function">define</span><span class="token punctuation">(</span><span class="token string">"NAME"</span><span class="token punctuation">,</span><span class="token string">"好男人"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
      <span class="token function">define</span><span class="token punctuation">(</span><span class="token string">"CAT_NAME"</span><span class="token punctuation">,</span><span class="token string">"波斯猫"</span><span class="token punctuation">,</span><span class="token boolean">true</span><span class="token punctuation">)</span><span class="token punctuation">;</span> <span class="token comment">//true允许大小写识别,false不允许</span>
      <span class="token keyword">echo</span> cat_name<span class="token punctuation">;</span>  <span class="token comment">//因为true允许大小写识别,所以能够显示CAT_NAME内容</span>
      <span class="token keyword">echo</span> <span class="token constant">NAME</span><span class="token punctuation">;</span> <span class="token comment">//echo显示:好男人</span>
      
</code></pre>
<h3 id="变量-定义变量没有关键字属于弱类型语言">1.2变量, 定义变量没有关键字,属于弱类型语言</h3>
<pre><code>  相比于 JS 定义变量, PHP 定义一个变量不需要关键字 var ,直接 $ 加上变量名即可
</code></pre>
<p>例子:</p>
<pre class=" language-php"><code class="prism  language-php">      <span class="token variable">$name</span> <span class="token operator">=</span> <span class="token string">"小明"</span><span class="token punctuation">;</span>
      <span class="token variable">$age</span> <span class="token operator">=</span> <span class="token number">18</span><span class="token punctuation">;</span>
      <span class="token keyword">echo</span> <span class="token variable">$name</span><span class="token punctuation">;</span>
</code></pre>
<h3 id="输出返回显示">1.3输出返回显示</h3>
<pre><code> 注意:PHP的Boolean值的返回值与JS的不一样,在PHP中
</code></pre>
<pre class=" language-php"><code class="prism  language-php">     <span class="token variable">$flag</span> <span class="token operator">=</span> <span class="token boolean">true</span><span class="token punctuation">;</span> 
     <span class="token keyword">echo</span> <span class="token variable">$flag</span><span class="token punctuation">;</span><span class="token comment">//false 为0但不显示,true显示1</span>
</code></pre>
<h4 id="var_demp--输出对象和数组">1.3.1 var_demp  输出对象和数组</h4>
<p>可以输出变量的具体信息,比如类型,长度,值等<br>
是所有输出方法中输出信息最丰富的<br>
例子:</p>
<pre class=" language-php"><code class="prism  language-php">	<span class="token function">var_dump</span><span class="token punctuation">(</span><span class="token variable">$flag</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token comment">//bool(true)</span>
	<span class="token function">var_dump</span><span class="token punctuation">(</span><span class="token variable">$name</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token comment">//string(6) "小明"</span>
	<span class="token variable">$arr</span> <span class="token operator">=</span> \<span class="token punctuation">[</span><span class="token number">1.1</span><span class="token punctuation">,</span><span class="token number">2</span><span class="token punctuation">,</span><span class="token operator">-</span><span class="token number">3</span>\<span class="token punctuation">]</span><span class="token punctuation">;</span>
	<span class="token function">var_dump</span><span class="token punctuation">(</span><span class="token variable">$arr</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token comment">//array(3) { \[0\]=&gt; float(1.1) \[1\]=&gt; int(2) \[2\]=&gt; int(-3) }</span>
</code></pre>
<h4 id="echo--直接输出字符或字符串">1.3.2 echo  直接输出字符或字符串</h4>
<p>可以直接输出字符或字符串,但不能输出数组和对象</p>
<pre class=" language-php"><code class="prism  language-php">	<span class="token comment">//echo不能打印数组和对象</span>
	<span class="token keyword">echo</span> <span class="token variable">$arr</span><span class="token punctuation">;</span><span class="token comment">//会报错</span>
	<span class="token comment">//可以打印多个变量</span>
	<span class="token keyword">echo</span> <span class="token variable">$name</span><span class="token punctuation">,</span><span class="token variable">$age</span><span class="token punctuation">,</span><span class="token variable">$flag</span><span class="token punctuation">;</span><span class="token comment">//小明181</span>
</code></pre>
<h4 id="print--打印">1.3.3 print  打印</h4>
<p>函数print()打印一个值（它的参数），如果字符串成功显示则返回true，否则返回false。<br>
不能打印数组</p>
<pre class=" language-php"><code class="prism  language-php">	<span class="token keyword">print</span> <span class="token punctuation">(</span><span class="token variable">$name</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token comment">//小明</span>
	<span class="token keyword">print</span> <span class="token punctuation">(</span><span class="token variable">$arr</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token comment">//报错</span>
</code></pre>
<h4 id="printf--格式化输出">1.3.4 printf  格式化输出</h4>
<p>一般用于向标准输出设备按规定格式输出信息</p>
<pre class=" language-php"><code class="prism  language-php">	<span class="token comment">//type的字符用于规定输出数据的类型  https://baike.baidu.com/item/printf/7467706?fr=aladdin</span>
	<span class="token function">printf</span><span class="token punctuation">(</span><span class="token string">"name的值是%s,age的值是%d"</span><span class="token punctuation">,</span><span class="token variable">$name</span><span class="token punctuation">,</span><span class="token variable">$age</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token comment">//name的值是小明,age的值是18</span>
</code></pre>
<h4 id="print_r--输出语句">1.3.5 print_r  输出语句</h4>
<p>相对于print,可以输出数组和对象,相对var_dump输出不是那么详细<br>
可以把字符串和数字简单地打印出来，而数组则以括起来的键和值得列表形式显示，并以Array开头。</p>
<pre class=" language-php"><code class="prism  language-php">	<span class="token function">print_r</span><span class="token punctuation">(</span><span class="token variable">$arr</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token comment">//Array ( \[0\] =&gt; 1.1 \[1\] =&gt; 2 \[2\] =&gt; -3 )</span>
	<span class="token function">print_r</span><span class="token punctuation">(</span><span class="token variable">$name</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token comment">//小明</span>
</code></pre>
<h3 id="引用">1.4 &amp; 引用</h3>
<p>变量或者函数、对象等前面加上&amp;符号<br>
在PHP 中引用的意思是：不同的名字访问同一个变量内容。<br>
与Ｃ语言中的指针是有差别的．Ｃ语言中的指针里面存储的是变量的内容，在内存中存放的地址。</p>
<pre class=" language-php"><code class="prism  language-php">	<span class="token comment">//PHP 的引用允许你用两个变量来指向同一个内容</span>
	<span class="token variable">$m</span>  <span class="token operator">=</span> <span class="token number">10</span><span class="token punctuation">;</span>  
	<span class="token variable">$n</span> <span class="token operator">=</span> <span class="token operator">&amp;</span><span class="token variable">$m</span><span class="token punctuation">;</span> <span class="token comment">//$m的地址赋值给$n;  </span>
	<span class="token keyword">echo</span> <span class="token variable">$n</span><span class="token punctuation">;</span>  <span class="token comment">//10</span>
	<span class="token variable">$n</span> <span class="token operator">=</span> <span class="token number">220</span><span class="token punctuation">;</span>  
	<span class="token keyword">echo</span> <span class="token variable">$m</span><span class="token punctuation">;</span> <span class="token comment">//220</span>
</code></pre>
<h3 id="变量名-和-变量名-变量的变量">1.5 $变量名 和 $$变量名 变量的变量</h3>
<pre class=" language-php"><code class="prism  language-php">	<span class="token comment">//变量的变量</span>
	<span class="token variable">$value1</span> <span class="token operator">=</span> <span class="token string">"hello"</span><span class="token punctuation">;</span>
	$<span class="token variable">$value1</span> <span class="token operator">=</span> <span class="token string">"world"</span><span class="token punctuation">;</span> <span class="token comment">//相当于$hello = "world";</span>
	$$<span class="token variable">$value1</span> <span class="token operator">=</span> <span class="token string">"阿斯玛"</span><span class="token punctuation">;</span>
	<span class="token keyword">echo</span> $<span class="token variable">$hello</span><span class="token punctuation">;</span> <span class="token comment">//阿斯玛</span>
</code></pre>
<h2 id="，数据类型">2，数据类型</h2>
<h3 id="基本概念">2.1 基本概念</h3>
<p>主要有三种类型</p>
<pre><code>1，标量类型：比如:整型integer  浮点数float/double  
           字符串string  布尔boolean true/false
2，复合类型：比如数组，对象
3，特殊类型：资源类型 null
</code></pre>
<h3 id="float-double-浮点数">2.2 float double 浮点数</h3>
<p>有两种，float和double</p>
<pre class=" language-php"><code class="prism  language-php">	<span class="token variable">$a</span> <span class="token operator">=</span> <span class="token number">1.0</span><span class="token punctuation">;</span>  
	<span class="token function">var_dump</span><span class="token punctuation">(</span><span class="token variable">$a</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token comment">//float(1)</span>
	<span class="token variable">$b</span> <span class="token operator">=</span> <span class="token number">1.134615446541316821675136321654</span><span class="token punctuation">;</span>  
	<span class="token function">var_dump</span><span class="token punctuation">(</span><span class="token variable">$b</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token comment">//float(1.1346154465413)</span>
	<span class="token variable">$c</span> <span class="token operator">=</span> <span class="token punctuation">(</span>float<span class="token punctuation">)</span><span class="token variable">$b</span><span class="token punctuation">;</span>  
	<span class="token function">var_dump</span><span class="token punctuation">(</span><span class="token variable">$c</span><span class="token punctuation">.</span><span class="token string">"~~~123"</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token comment">//string(21) "1.1346154465413~~~123"</span>
	<span class="token variable">$d</span> <span class="token operator">=</span> <span class="token punctuation">(</span>double<span class="token punctuation">)</span><span class="token number">1.21532165761321687615213</span><span class="token punctuation">;</span>  
	<span class="token keyword">echo</span> <span class="token variable">$d</span><span class="token punctuation">;</span><span class="token comment">//1.2153216576132</span>
</code></pre>
<h3 id="gettype-获取数据类型">2.3 gettype 获取数据类型</h3>
<pre class=" language-php"><code class="prism  language-php">	<span class="token keyword">echo</span> <span class="token function">gettype</span><span class="token punctuation">(</span><span class="token variable">$c</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token comment">//double</span>
</code></pre>
<h3 id="（int）（string）（array）强制类型转换">2.4 （int）（string）（array）强制类型转换</h3>
<pre class=" language-php"><code class="prism  language-php">	<span class="token variable">$m</span> <span class="token operator">=</span> <span class="token string">"123"</span><span class="token punctuation">;</span>
	<span class="token variable">$n</span> <span class="token operator">=</span> <span class="token punctuation">(</span>int<span class="token punctuation">)</span><span class="token variable">$m</span><span class="token punctuation">;</span>
	<span class="token function">var_dump</span><span class="token punctuation">(</span><span class="token variable">$n</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token comment">//int(123)</span>
  
	<span class="token variable">$x</span> <span class="token operator">=</span> <span class="token number">3.14</span><span class="token punctuation">;</span>
	<span class="token variable">$y</span> <span class="token operator">=</span> <span class="token punctuation">(</span>string<span class="token punctuation">)</span><span class="token variable">$x</span><span class="token punctuation">;</span>
	<span class="token function">var_dump</span><span class="token punctuation">(</span><span class="token variable">$y</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token comment">//string(4) "3.14"</span>
  
	<span class="token variable">$z</span> <span class="token operator">=</span> <span class="token punctuation">(</span><span class="token keyword">array</span><span class="token punctuation">)</span><span class="token number">5.6</span><span class="token punctuation">;</span>
	<span class="token function">var_dump</span><span class="token punctuation">(</span><span class="token variable">$z</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token comment">//array(1) {[0]=&gt; float(5.6)}</span>
</code></pre>
<h2 id="，运算符">3，运算符</h2>
<p>算术运算符和JS一样</p>
<h3 id="字符串拼接">3.1 字符串拼接</h3>
<p>主要有三种方法</p>
<pre class=" language-php"><code class="prism  language-php">	<span class="token comment">//字符串拼接</span>
	<span class="token variable">$b</span> <span class="token operator">=</span> <span class="token string">"班长"</span><span class="token punctuation">;</span>
	<span class="token variable">$c</span> <span class="token operator">=</span> <span class="token string">"真白"</span><span class="token punctuation">;</span>
	<span class="token variable">$d</span> <span class="token operator">=</span> <span class="token variable">$b</span><span class="token punctuation">.</span><span class="token variable">$c</span><span class="token punctuation">;</span>
	<span class="token keyword">echo</span> <span class="token variable">$d</span><span class="token punctuation">;</span><span class="token comment">//班长真白</span>
	<span class="token variable">$b</span> <span class="token punctuation">.</span><span class="token operator">=</span> <span class="token variable">$c</span><span class="token punctuation">;</span>
	<span class="token keyword">echo</span> <span class="token variable">$b</span><span class="token punctuation">;</span><span class="token comment">//班长真白</span>
</code></pre>
<h3 id="运算">3.2 += 运算</h3>
<pre class=" language-php"><code class="prism  language-php">	<span class="token comment">//+=运算</span>
	<span class="token variable">$m</span> <span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span>
	<span class="token variable">$m</span> <span class="token operator">+</span><span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span>
	<span class="token keyword">echo</span> <span class="token variable">$m</span><span class="token punctuation">;</span><span class="token comment">//2</span>
</code></pre>
<h3 id="比较运算符">3.3 比较运算符</h3>
<pre class=" language-php"><code class="prism  language-php">	<span class="token comment">//比较运算符 \&gt; &lt; &gt;= &lt;= == !=</span>
	<span class="token variable">$x</span> <span class="token operator">=</span> <span class="token string">"1"</span> <span class="token operator">==</span> <span class="token number">1</span><span class="token punctuation">;</span> 
	<span class="token variable">$y</span> <span class="token operator">=</span> <span class="token string">"1"</span> <span class="token operator">===</span> <span class="token number">1</span><span class="token punctuation">;</span> <span class="token comment">//三个等号指值一样，类型也要一样</span>
	<span class="token function">var_dump</span><span class="token punctuation">(</span><span class="token variable">$x</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token comment">//bool(true)</span>
	<span class="token function">var_dump</span><span class="token punctuation">(</span><span class="token variable">$y</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token comment">//bool(false)</span>
</code></pre>
<h3 id="逻辑运算符">3.4 逻辑运算符</h3>
<pre class=" language-php"><code class="prism  language-php">	<span class="token comment">//逻辑运算符 &amp;&amp; || !</span>
	<span class="token variable">$xx</span> <span class="token operator">=</span> <span class="token boolean">true</span><span class="token punctuation">;</span>
	<span class="token variable">$yy</span> <span class="token operator">=</span> <span class="token boolean">false</span><span class="token punctuation">;</span>
	<span class="token variable">$zz</span> <span class="token operator">=</span> <span class="token boolean">false</span><span class="token punctuation">;</span>
	<span class="token comment">//异或 xor  不一样为真  </span>
	<span class="token keyword">if</span> <span class="token punctuation">(</span><span class="token variable">$xx</span> <span class="token keyword">xor</span> <span class="token variable">$zz</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>  
		  <span class="token keyword">echo</span> <span class="token string">"真"</span><span class="token punctuation">;</span>  
	<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token punctuation">{</span>  
		  <span class="token keyword">echo</span> <span class="token string">"假"</span><span class="token punctuation">;</span>  
	<span class="token punctuation">}</span>  
	<span class="token keyword">echo</span> <span class="token string">"&lt;hr&gt;"</span><span class="token punctuation">;</span>  
	<span class="token keyword">if</span> <span class="token punctuation">(</span><span class="token variable">$xx</span> <span class="token keyword">xor</span> <span class="token variable">$zz</span> <span class="token keyword">xor</span> <span class="token variable">$yy</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>  
		  <span class="token keyword">echo</span> <span class="token string">"真"</span><span class="token punctuation">;</span>  
	<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token punctuation">{</span>  
		  <span class="token keyword">echo</span> <span class="token string">"假"</span><span class="token punctuation">;</span>  
	<span class="token punctuation">}</span>
</code></pre>
<h2 id="，分支语句">4，分支语句</h2>
<h3 id="if判断语句">4.1 if判断语句</h3>
<pre class=" language-php"><code class="prism  language-php">	<span class="token comment">//if 判断语句</span>
	<span class="token variable">$a</span> <span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span>
	<span class="token keyword">if</span> <span class="token punctuation">(</span><span class="token variable">$a</span> <span class="token operator">==</span> <span class="token number">1</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>

	<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token keyword">if</span> <span class="token punctuation">(</span><span class="token variable">$a</span> <span class="token operator">==</span> <span class="token number">0</span><span class="token punctuation">)</span> <span class="token punctuation">{</span> 

	<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token punctuation">{</span>
	<span class="token punctuation">}</span>
</code></pre>
<h3 id="switch语句">4.2 switch语句</h3>
<pre class=" language-php"><code class="prism  language-php">	<span class="token keyword">switch</span> <span class="token punctuation">(</span><span class="token variable">$a</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
	<span class="token keyword">case</span> <span class="token number">1</span><span class="token punctuation">:</span>
	<span class="token keyword">echo</span> <span class="token string">"a的值是1"</span><span class="token punctuation">;</span>
	<span class="token keyword">break</span><span class="token punctuation">;</span>
	<span class="token keyword">case</span> <span class="token number">2</span><span class="token punctuation">:</span>
	<span class="token keyword">echo</span> <span class="token string">"a的值是2"</span><span class="token punctuation">;</span>
	<span class="token keyword">break</span><span class="token punctuation">;</span>
	<span class="token keyword">case</span> <span class="token number">3</span><span class="token punctuation">:</span>
	<span class="token keyword">echo</span> <span class="token string">"a的值是3"</span><span class="token punctuation">;</span>
	<span class="token keyword">break</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
</code></pre>
<h2 id="for-循环">5 for 循环</h2>
<pre class=" language-php"><code class="prism  language-php">	<span class="token comment">//for循环</span>
	<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token variable">$a</span> <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span> <span class="token variable">$a</span> <span class="token operator">&lt;</span> <span class="token number">10</span><span class="token punctuation">;</span> <span class="token variable">$a</span><span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">echo</span> <span class="token variable">$a</span><span class="token punctuation">.</span><span class="token string">"&lt;br&gt;"</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
	<span class="token variable">$arr</span> <span class="token operator">=</span> \<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">,</span><span class="token number">2</span><span class="token punctuation">,</span><span class="token number">3</span><span class="token punctuation">,</span><span class="token number">4</span><span class="token punctuation">,</span><span class="token number">5</span>\<span class="token punctuation">]</span><span class="token punctuation">;</span>
	<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token variable">$i</span> <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span> <span class="token variable">$i</span> <span class="token operator">&lt;</span> <span class="token number">5</span><span class="token punctuation">;</span> <span class="token variable">$i</span><span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">echo</span> <span class="token variable">$arr</span>\<span class="token punctuation">[</span><span class="token variable">$i</span>\<span class="token punctuation">]</span><span class="token punctuation">.</span><span class="token string">"&lt;br&gt;"</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
</code></pre>
<h2 id="函数">6函数</h2>
<h3 id="格式写法">6.1 格式写法</h3>
<pre class=" language-php"><code class="prism  language-php">	<span class="token variable">$a</span> <span class="token operator">=</span> <span class="token number">10</span><span class="token punctuation">;</span>
	<span class="token comment">//PHP的函数存在作用域概念</span>
	<span class="token keyword">function</span> <span class="token function">text</span> <span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token comment">//$a = 100;</span>
		<span class="token comment">//全局变量在函数内部访问,需要添加关键字global</span>
		<span class="token keyword">global</span> <span class="token variable">$a</span><span class="token punctuation">;</span> <span class="token comment">//在函数内使用函数外的全局变量,需加上global</span>
		<span class="token keyword">echo</span> <span class="token variable">$a</span> <span class="token operator">+</span> <span class="token number">1</span><span class="token punctuation">;</span>
		<span class="token variable">$a</span> <span class="token operator">=</span> <span class="token number">100</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span> 
	<span class="token function">text</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
	<span class="token keyword">echo</span> <span class="token variable">$a</span><span class="token punctuation">;</span> <span class="token comment">//100</span>
</code></pre>
<h3 id="静态变量">6.2 静态变量</h3>
<p>静态变量只存在于函数作用域内，也就是说，静态变量只存活在栈中。一般的函数内变量在函数结束后会释放，比如局部变量，但是静态变量却不会。就是说，下次再调用这个函数的时候，该变量的值会保留下来。</p>
<pre class=" language-php"><code class="prism  language-php"><span class="token comment">//静态变量</span>
	<span class="token keyword">function</span> <span class="token function">counter</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
		<span class="token keyword">static</span> <span class="token variable">$count</span> <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span> <span class="token comment">//一直在函数中,不被释放,作用域为本函数</span>
		<span class="token keyword">return</span> <span class="token variable">$count</span><span class="token operator">++</span><span class="token punctuation">;</span>
	<span class="token punctuation">}</span>
	<span class="token keyword">echo</span> <span class="token function">counter</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token string">"&lt;br&gt;"</span><span class="token punctuation">;</span><span class="token comment">//1</span>
	<span class="token keyword">echo</span> <span class="token function">counter</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token string">"&lt;br&gt;"</span><span class="token punctuation">;</span><span class="token comment">//2</span>
	<span class="token keyword">echo</span> <span class="token function">counter</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token string">"&lt;br&gt;"</span><span class="token punctuation">;</span><span class="token comment">//3</span>
	<span class="token keyword">echo</span> <span class="token function">counter</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token string">"&lt;br&gt;"</span><span class="token punctuation">;</span><span class="token comment">//4</span>
	<span class="token keyword">echo</span> <span class="token function">counter</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token string">"&lt;br&gt;"</span><span class="token punctuation">;</span><span class="token comment">//5</span>
	<span class="token keyword">echo</span> <span class="token function">counter</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token string">"&lt;br&gt;"</span><span class="token punctuation">;</span><span class="token comment">//6</span>
	<span class="token comment">//echo $count; //报未定义错误</span>
</code></pre>


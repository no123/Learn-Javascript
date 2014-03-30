# 2. 如何使用Javascript

## 2.1 在HTML中使用Javascript

向HTML页面中插入Javascript的重要方法就是使用script标签

使用script标签的方式有两种

1. 直接在页面中嵌入Javascript代码。

		 	<html>
				<head></head>
				<body>
					<script type="text/javascript">
						function sayHello(){
				 			alert('Hello');
				 		}
					</script>
				</body>
			</html>

	* 包含在script标签内部的Javascript代码将被从上至下依次解析。就拿上面的例子来说，解析器会解释到一个函数的定义，然后将该定义保存在自己的环境中。当解释器对script标签内部的所有代码求值完毕以前，页面中的其余内容都不会被浏览器加载或显示。

2. 包含外部的Javascript文件。

			<html>
				<head></head>
				<body>
					<script type="text/javascript" src="example1.js"></script>
				</body>
			</html>

	example1.js：

			function sayHello(){
				alert('Hello');
			}


	* 外部文件只需包含通常要放在开始的<script>与结束的</script>之间的那些Javacript代码即可。
	* 与解析嵌入式Javascript代码一样，在解析外部Javascript文件（包括下载文件）时，页面的处理也会暂时停止。
	* script标签的src属性还可以指向当前HTML页面所在域之外某个域中的URL。如: 
		<script type="text/javascript" src="http://code.jquery.com/jquery.1.11.0.min.js"></script>

_Tip:_

1. 因为无论是解析嵌入式的Javascript代码还是解析外部Javascript文件（包括下载文件），都会阻塞页面其他的载入和处理。也就意味着必须等到全部Javascript代码都被下载，解析和执行完成以后，才开始呈现页面内容。而延迟期间的浏览器窗口将是一片空白。所以从更好的用户体验考虑，通常情况下，我们选择把javascript放在body标签的底部，页面内容的后面，待整个页面结构加载完成后再加载javascript。同时，这样也保证了javascript程序中需要的节点在解析执行时已经存在。

2. 尽可能不指向外部域的javascript文件。如果确实需要，可以考虑将文件下载到本地，再引入HTML。否则外部域的Javascript文件位置发生变更时，会影响到我们的application。

3. 虽然在HTML中嵌入代码没有问题，但是一般认为最好的做法还是尽可能使用外部文件来包含Javascript代码。

	* 可维护性。分离 HTML和Javascript可以让Developer在编辑Javascript时不影响到HTML。
	* 可重用。 同一个Javascript文件可以被不同的 HTML页面引用。
	* 可缓存。 浏览器能够根据具体的设置缓存链接的所有外部Javascript文件。也就是说，如果有两个页面都使用同一个文件，那么这个文件只须下载一次。这样就能够加快页面加载速度。

## 2.2 在浏览器环境下进行Javascript开发

我们可以直接在浏览器的开发者工具中进入Javascript的编写。

### 2.2.1 所需的开发工具

就目前的各大主流浏览器，在已安装工具的前提下，打开浏览器后，点击F12，可以打开浏览器的开发者工具。我们可以在其中的Console（控制台）的Command Line内进行操作.

IE从IE8开始，已经自带开发者工具。IE8以前的IE版本，需要另外单独安装。

FireFox的开发工具叫 Firebug，也需要另外安装。安装方法：Ctrl+Shift+A，打开"Get Add-ons"，搜索Firebug，点击"install"。

### 2.2.2 编写一个简单的Javascript程序

以FireFox的Firebug为例。步骤如下：

1. 打开浏览器，点击F12，打开Firebug。

2. 在Command Line内编写如下程序:

		function sayHello(){
		    alert('Hello');
		}

		sayHello();

3. 编写完成后，点击Command Line下方的"Run"，即可看到执行结果。

!['code in console'](/examples/chapter2/console.jpg) 

### 2.2.3 我们还可以做什么

为讲解需要，我们先创建一个HTML页面example1.html和一个外部js文件example1.js。

example1.html

	<html>
		<head>
			<title>Sample Page</title>
		<head>
		<body>
			<div>Test</div>
			<script type="text/javascript" src="example1.js"></script>
		</body>
	</html>	

example1.js

	function sayHello(){
		alert('Hello');
	}

然后我们用FireFox打开example1.html。同时打开Firebug的Command Line（F12）。

!['code in console'](/examples/chapter2/work on page.jpg)

* 调用已经载入的方法。在Command Line输入"SayHello()", 点击"Run"。
!['code in console'](/examples/chapter2/call func.jpg)

* 覆盖已经载入的方法。在Command Line输入如下代码改变"sayHello"方法, 点击"Run"。跳出窗口的文字由"Hello"变为"Hello World!"。

	function sayHello(){
	    alert('Hello World!')
	}

	sayHello();

!['code in console'](/examples/chapter2/rewrite func.jpg)

* 调用浏览器宿主对象window.navigator, window.location等。






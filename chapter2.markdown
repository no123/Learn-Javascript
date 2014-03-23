# 2. 如何使用Javascript

## 2.1 在HTML中使用Javascript

	向HTML页面中插入Javascript的重要方法就是使用<script>

	使用 <script> 元素的方式有两种

		1. 直接在页面中嵌入Javascript代码。

		 	<html>
				<header></header>
				<body>
					<script type="text/javascript">
						function sayHello(){
				 			alert('Hello');
				 		}
					</script>
				</body>
			</html>

			* 包含在<script>元素内部的Javascript代码将被从上至下依次解析。就拿上面的例子来说，解析器会解释到一个函数的定义，然后将该定义保存在自己的环境中。当解释器对<script>元素内部的所有代码求值完毕以前，页面中的其余内容都不会被浏览器加载或显示。

		2. 包含外部的Javascript文件。

			<html>
				<header></header>
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
			* <script>的src属性还可以指向当前HTML页面所在域之外某个域中的URL。
				如: <script type="text/javascript" src="http://code.jquery.com/jquery.1.11.0.min.js"></script>

	_**Tip**:_
		1. 因为无论是解析嵌入式的Javascript代码还是解析外部Javascript文件（包括下载文件），都会阻塞页面其他的载入和处理。也就意味着必须等到全部Javascript代码都被下载，解析和执行完成以后，才开始呈现页面内容。而延迟期间的浏览器窗口将是一片空白。所以从更好的用户体验考虑，通常情况下，我们选择把javascript放在<body>的底部，页面内容的后面，待整个页面结构加载完成后再加载javascript。同时，这样也保证了javascript程序中需要的节点在解析执行时已经存在。

		2. 尽可能不指向外部域的javascript文件。如果确实需要，可以考虑将文件下载到本地，再引入HTML。否则外部域的Javascript文件位置发生变更时，会影响到我们的application。

## 2.2 在浏览器的开发工具中编写

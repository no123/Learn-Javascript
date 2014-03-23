# 2. 如何使用Javascript

## 在HTML中使用Javascript

向HTML页面中插入Javascript的重要方法就是使用<script>

使用<script>元素的方式有两种

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

	2. 包含外部的Javascript文件。

		<html>
			<header></header>
			<body>
				<script type="text/javascript" src="example1.js"></script>
			</body>
		</html>


## 在浏览器的开发工具界面编写
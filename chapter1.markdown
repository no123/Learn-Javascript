# 1. Javascript简介

1. 一种专为与网页交互而设计的脚本语言。

2. 诞生于1995年，由Netscape开发，当时主要目的是处理以前由服务器端语言负责的一些输入验证操作。第一个版本出现在Netscape Navigator 2浏览器中。

3. JavaScript除了适用于客户端浏览器编程外，还可以在越来越多的平台上运行。你可以用它来开发服务端程序（使用.Net或Node.js）、桌面应用程序（运行于桌面操作系统）、应用程序扩展（Firefox插件或者Photoshop扩展）、移动终端应用和纯命令行的批处理脚本。

4. Javascript实现包括：
	* 核心（ECMAScript）
	* 文档对象模型 （DOM）
	* 浏览器对象模型 （BOM）

5. 在不同浏览器中得到了不同程度的支持。

## 1.1 ECMAScript

1. ECMAScript是对ECMA-262标准规定的各个方面内容的语言的描述。Javascript实现了ECMAScript， Adobe Actionscript和Open View ScriptEase童言实现了ECMAScript。

2. ECMAScript与Web浏览器没有依赖关系。常见的Web浏览器只是ECMAScript实现可能的宿主环境之一。ScriptEase和Adobe Flash也是宿主环境。

3. 浏览器开发商致力于把ECMAScript作为各自Javascript的基础。

### 1.1.1 ECMA-262标准

1995年12月Sun与Netscape一起引入了JavaScript。1996年3月，Netscape发表了支持JavaScript的Netscape Navigator 2浏览器。0。由于JavaScript作为网页的客户端脚本语言非常成功，微软于1996年8月引入了Internet Explorer3.0，这个软件支持一个“约”与JavaScript相容的JScript。
1996年11月Netscape将JavaScript提交给欧洲计算机制造商协会进行标准化。ECMA-262的第一个版本于1997年6月被Ecma组织采纳。
ECMAScript是由ECMA-262标准化的脚本语言的名称。JavaScript和JScript与ECMAScript相容，但包含超出ECMAScript的功能。

ECMA-262规定了：

	* 语法
	* 类型
	* 语句
	* 关键字
	* 保留字
	* 操作符
	* 对象

### 1.1.2 宿主环境（Host）

Host不仅提供基本的ECMAScript实现，同时也会提供该语言的扩展，以便语言与环境之间的对接交互。而这些扩展--如DOM，则利用ECMAScript的核心类型和语法提供更多更具体的功能，以便实现针对环境的操作。

## 1.2 文档对象模型 （DOM，Document Object Model）

1. DOM是针对XML但经过扩展用于HTML的API。

2. DOM把整个页面映射为一个多层节点结构。

3. 通过DOM创建的表示文档的树形图，developer获得了控制页面结构的主动权。借助DOM提供的API，developer可以轻松自如地增删改以及替换任何节点。

4. 所有浏览器对 DOM的支持相差很大。

5. DOM标准由W3C规划制定。

6. DOM并不是仅针对于Javascript，很多别的语言也实现了DOM。比如：SVG，MathML， SMIL....

## 1.3 浏览器对象模型 （BOM，Browser Object Model）

1. developer使用BOM可以控制浏览器显示的页面以外的部分。

2. 从根本上讲，BOM只处理浏览器窗口和框架，但是人们习惯上也把所有针对浏览器的Javascript扩展算作BOM的一部分。如：
	
	* 弹出新浏览器窗口的功能。
	* 移动，缩放和关闭浏览器窗口的功能。
	* 提供浏览器详细信息的navigator对象。 
	* 提供浏览器所加载页面的详细信息的location对象。
	* 提供显示器分辨率详细信息的screen对象。
	* 对cockies的支持。
	* 像XMLHttpRequest和IE的ActiveXObject这样的自定义对象。

3. BOM至今没有标准可以遵循， 每个浏览器都有自己的实现。


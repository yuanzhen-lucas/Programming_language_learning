## Javascript

## [浏览器内 JavaScript 可以做什么？](https://javascript.info/intro#what-can-in-browser-javascript-do)

现代 JavaScript 是一种“安全”的编程语言。它不提供对内存或 CPU 的低级访问，因为它最初是为不需要它的浏览器创建的。

JavaScript 的能力很大程度上取决于它运行的环境。例如，[Node.js](https://wikipedia.org/wiki/Node.js)支持允许 JavaScript 读/写任意文件、执行网络请求等的功能。

浏览器内 JavaScript 可以执行与网页操作、与用户交互和网络服务器相关的所有工作。

例如，浏览器内 JavaScript 能够：

- 向页面添加新的 HTML，更改现有内容，修改样式。
- 对用户操作做出反应，在鼠标点击、指针移动、按键时运行。
- 通过网络向远程服务器发送请求，下载和上传文件（所谓的[AJAX](https://en.wikipedia.org/wiki/Ajax_(programming))和[COMET](https://en.wikipedia.org/wiki/Comet_(programming))技术）。
- 获取和设置 cookie，向访问者提问，显示消息。
- 记住客户端（“本地存储”）上的数据。

## [浏览器中的 JavaScript 不能做什么？](https://javascript.info/intro#what-can-t-in-browser-javascript-do)

为了用户的安全，JavaScript 在浏览器中的能力是有限的。目的是防止恶意网页访问私人信息或损害用户数据。

此类限制的示例包括：

- 网页上的 JavaScript 可能无法读取/写入硬盘上的任意文件、复制它们或执行程序。它无法直接访问操作系统功能。

  现代浏览器允许它处理文件，但访问是有限的，并且只有在用户执行某些操作时才提供，例如将文件“放入”浏览器窗口或通过`<input>`标签选择它。

  有多种方式可以与相机/麦克风和其他设备进行交互，但它们需要用户的明确许可。因此，启用 JavaScript 的页面可能不会偷偷启用网络摄像头、观察周围环境并将信息发送给[NSA](https://en.wikipedia.org/wiki/National_Security_Agency)。

- 不同的选项卡/窗口通常彼此不了解。有时他们会这样做，例如当一个窗口使用 JavaScript 打开另一个窗口时。但即使在这种情况下，如果来自一个页面的 JavaScript 来自不同的站点（来自不同的域、协议或端口），它们也可能无法访问另一个页面。

  这被称为“同源策略”。要解决这个问题，*两个页面*必须同意数据交换并包含处理它的特殊 JavaScript 代码。我们将在教程中介绍。

  这个限制也是为了用户的安全。`http://anysite.com`用户打开的页面必须不能访问带有 URL 的另一个浏览器选项卡`http://gmail.com`并从那里窃取信息。

- JavaScript 可以轻松地通过网络与当前页面来自的服务器进行通信。但是它从其他站点/域接收数据的能力被削弱了。尽管可能，它需要来自远程端的明确同意（以 HTTP 标头表示）。再一次，这是一个安全限制。
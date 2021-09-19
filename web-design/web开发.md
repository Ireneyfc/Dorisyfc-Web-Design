## 一些准备
1. 开始之前，请考虑以下问题：

   - 网站的主题是什么？是狗、上海城市还是吃豆人？
   - 基于所选主题要展示哪些信息？写下标题和几段文字，构思一个用于展示的图形。
   - 网站采用怎样的外观？用高阶术语说就是，选什么背景色？什么字体（正式的还卡通的，粗体还是细体）？


2. 网站应该保存在何处？
   - 对于本地网站，应将所有相关文件放在一个单独文件夹中
   - 在该位置下创建一个文件夹（比如 web-projects）。所有网站项目都存在一处。
   - 在这个文件夹里再新建一个文件夹（比如 test-site，读者可自由发挥想象），来存放第一个网站。
   - 所有的文件夹名和文件**都使用小写字母**，且没有空格,最好使用**中划线`-`**，而不是下划线来分离单词

3. 网站应该使用什么结构？
   - **index.html** ：这个文件一般包含主页内容，即用户第一次访问站点时看到的文本和图像。使用文本编辑器在 test-site 文件夹中新建 index.html。
   - **images 文件夹** ：这个文件夹包含站点中的所有图像。在 test-site 文件夹中新建 images 文件夹。
   - **styles 文件夹** ：这个文件夹包含站点所需样式表（比如，设置文本颜色和背景颜色）。在 test-site 文件夹中新建一个 styles 文件夹。
   - **scripts 文件夹** ：这个文件夹包含提供站点交互功能的 JavaScript 代码（比如读取数据的按钮）。在 test-site 文件夹中新建一个 scripts 文件夹。
## HTML

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>测试页面</title>
  </head>
  <body>
    <img src="images/firefox-icon.png" alt="测试图片">
  </body>
</html>
```

- `<!DOCTYPE html>` — 文档类型。混沌初分，HTML 尚在襁褓（大约是 1991/92 年）之时，DOCTYPE 用来链接一些 HTML 编写守则，比如自动查错之类。DOCTYPE 在当今作用有限，仅用于保证文档正常读取。现在知道这些就足够了。
- `<html></html>` — <html> 元素。该元素包含整个页面的内容，也称作根元素。
- `<head></head>` — <head> 元素。该元素的内容对用户不可见，其中包含例如面向搜索引擎的搜索关键字（keywords）、页面描述、CSS 样式表和字符编码声明等。
- `<meta charset="utf-8">` — 该元素指定文档使用 UTF-8 字符编码 ，UTF-8 包括绝大多数人类已知语言的字符。基本上 UTF-8 可以处理任何文本内容，还可以避免以后出现某些问题，没有理由再选用其他编码。
- `<title></title>` — <title> 元素。该元素设置页面的标题，显示在浏览器标签页上，也作为收藏网页的描述文字。
- `<body></body>` — <body> 元素。该元素包含期望让用户在访问页面时看到的内容，包括文本、图像、视频、游戏、可播放的音轨或其他内容。
- `<img>` 元素：图像文件路径的地址属性 `src`;`alt` 属性的关键字即“描述文本”,用于当图像不能被用户看见时显示，
  


```html
<h1>主标题</h1>
<h2>顶层标题</h2>
<h3>子标题</h3>
<h4>次子标题</h4>

<p>这是一个段落</p>

<p>Mozilla 是一个全球社区，这里聚集着来自五湖四海的</p>

<ul>
  <li>技术人员</li>
  <li>思考者</li>
  <li>建造者</li>
</ul>

<p>我们致力于……</p>

<a href="https://www.mozilla.org/zh-CN/about/manifesto/">Mozilla 宣言</a>
```

- 无序列表（Unordered List。用一个 <ul> 元素包围。
- 有序列表（Ordered List。用一个 <ol> 元素包围。
- 列表的每个项目用一个列表项目（List Item）元素 <li> 包围。
- <a> — a 是 "anchor" （锚）的缩写,href（ hypertext reference）


## CSS

每个占据页面空间的块都有这样的属性：

- padding：即内边距，围绕着内容（比如段落）的空间。
- border：即边框，紧接着内边距的线。
- margin：即外边距，围绕元素外部的空间。
- width ：元素的宽度
- background-color ：元素内容和内边距底下的颜色
- color ：元素内容（通常是文本）的颜色
- text-shadow ：为元素内的文本设置阴影
- display ：设置元素的显示模式（暂略）

```css
body {
  width: 600px;
  margin: 0 auto;
  background-color: #FF9500;
  padding: 0 20px 20px 20px;
  border: 5px solid black;
}
```
- width: 600px; —— 强制页面永远保持 600 像素宽。
- margin: 0 auto; —— 为 margin 或 padding 等属性设置两个值时，第一个值代表元素的上方和下方（在这个例子中设置为 0），而第二个值代表左边和右边（在这里，auto 是一个特殊的值，意思是水平方向上左右对称）。你也可以使用一个，三个或四个值，参考 这里 。
- background-color: #FF9500; —— 如前文所述，指定元素的背景颜色。我们给 body 用了一种略微偏红的橘色以与深蓝色的 <html> 元素形成反差，你也可以尝试其它颜色。
- padding: 0 20px 20px 20px; —— 我们给内边距设置了四个值来让内容四周产生一点空间。这一次我们不设置上方的内边距，设置右边，下方，左边的内边距为20像素。值以上、右、下、左的顺序排列。
- border: 5px solid black; —— 直接为 body 设置 5 像素的黑色实线边框。
-  text-shadow 属性，它可以为元素中的文本提供阴影。四个值含义如下：

  第一个值设置水平偏移值 —— 即阴影右移的像素数（负值左移）。
  第二个值设置垂直偏移值 —— 即阴影下移的像素数（负值上移）。
  第三个值设置阴影的模糊半径 —— 值越大产生的阴影越模糊。
  第四个值设置阴影的基色。

  ## JavaScript

```javascript
// JavaScript 把页面的标题改成了 “Hello world!” 。
// 首先用 querySelector() 函数获取标题的引用，
// 并把它储存在 myHeading 变量中。这与 CSS 选择器的用法非常相像：若要对某个元素进行操作，首先得选择它。
// 之后，把 myHeading 变量的属性 textContent （标题内容）修改为 “Hello world!” 。
let myHeading = document.querySelector('h1');
myHeading.textContent = 'Hello world!';

//声明一个变量
let myVariable;
myVariable = '李雷';

//条件语句
let iceCream = 'chocolate';
if (iceCream === 'chocolate') {
  alert('我最喜欢巧克力冰激淋了。');
} else {
  alert('但是巧克力才是我的最爱呀……');
}

//函数（Function）
let myVariable = document.querySelector('h1');
//alert() 函数在浏览器窗口内弹出一个警告框，还应为其提供一个字符串参数，以告诉它警告框里要显示的内容。
alert('hello!');
function multiply(num1, num2) {
  let result = num1 * num2;
  return result;
}
multiply(4, 7);

//事件
document.querySelector('html').onclick = function() {
    alert('别戳我，我怕疼。');
}

```

## 发布网站
如何轻松地将你简单的示例代码传到网上
- 获取主机服务和域名
- 使用在线工具如 GitHub 或 Google App Engine
- 使用像 Thimble 的基于 Web 的集成开发环境
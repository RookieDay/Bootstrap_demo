## Bootstrap_demo
[官网](http://v3.bootcss.com)
###下载
使用 Bootstrap 中文网提供的免费 CDN 加速服务（同时支持 http 和 https 协议）
```
<!-- 最新版本的 Bootstrap 核心 CSS 文件 -->
<link rel="stylesheet" href="https://cdn.bootcss.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">

<!-- 可选的 Bootstrap 主题文件（一般不用引入） -->
<link rel="stylesheet" href="https://cdn.bootcss.com/bootstrap/3.3.7/css/bootstrap-theme.min.css" integrity="sha384-rHyoN1iRsVXV4nD0JutlnGaslCJuC7uwjduW9SVrLvRYooPp2bWYgmgJQIXwl/Sp" crossorigin="anonymous">

<!-- 最新的 Bootstrap 核心 JavaScript 文件 -->
<script src="https://cdn.bootcss.com/bootstrap/3.3.7/js/bootstrap.min.js" integrity="sha384-Tc5IQib027qvyjSMfHjOMaLkfuWVxZxUPnCJA7l2mCWNIpG9mGCD8wGNIcPD7Txa" crossorigin="anonymous"></script>
```

```
$ bower install bootstrap
$ npm install bootstrap@3
$ composer require twbs/bootstrap
```

###预编译版
下载压缩包之后，将其解压缩到任意目录即可看到以下（压缩版的）目录结构：
```
bootstrap/
├── css/
│   ├── bootstrap.css
│   ├── bootstrap.css.map
│   ├── bootstrap.min.css
│   ├── bootstrap.min.css.map
│   ├── bootstrap-theme.css
│   ├── bootstrap-theme.css.map
│   ├── bootstrap-theme.min.css
│   └── bootstrap-theme.min.css.map
├── js/
│   ├── bootstrap.js
│   └── bootstrap.min.js
└── fonts/
    ├── glyphicons-halflings-regular.eot
    ├── glyphicons-halflings-regular.svg
    ├── glyphicons-halflings-regular.ttf
    ├── glyphicons-halflings-regular.woff
    └── glyphicons-halflings-regular.woff2
```
上面展示的就是 Bootstrap 的基本文件结构：预编译文件可以直接使用到任何 web 项目中。我们提供了编译好的 CSS 和 JS (bootstrap.*) 文件，还有经过压缩的 CSS 和 JS (bootstrap.min.*) 文件。同时还提供了 CSS 源码映射表 (bootstrap.*.map) ，可以在某些浏览器的开发工具中使用。同时还包含了来自 Glyphicons 的图标字体，在附带的 Bootstrap 主题中使用到了这些图标。

### Bootstrap 源码
Bootstrap 源码包含了预先编译的 CSS、JavaScript 和图标字体文件，并且还有 LESS、JavaScript 和文档的源码。具体来说，主要文件组织结构如下：
```
bootstrap/
├── less/
├── js/
├── fonts/
├── dist/
│   ├── css/
│   ├── js/
│   └── fonts/
└── docs/
    └── examples/
```
less/、js/ 和 fonts/ 目录分别包含了 CSS、JS 和字体图标的源码。dist/ 目录包含了上面所说的预编译 Bootstrap 包内的所有文件。docs/ 包含了所有文档的源码文件，examples/ 目录是 Bootstrap 官方提供的实例工程。除了这些，其他文件还包含 Bootstrap 安装包的定义文件、许可证文件和编译脚本等。

###编译 CSS 和 JavaScript 文件
Bootstrap 使用 Grunt 作为编译系统，并且对外提供了一些方便的方法用于编译整个框架。下面讲解的就是如何编译源码、运行测试用例等内容。
- 安装 Grunt
 + 在全局环境中安装 grunt-cli ：npm install -g grunt-cli 。
 + 进入 /bootstrap/ 根目录，然后执行 npm install 命令。npm 将读取 package.json 文件并自动安装此文件中列出的所有被依赖的扩展包。

- 可用的 Grunt 命令
+ grunt dist （仅编译 CSS 和 JavaScript 文件）
重新生成 /dist/ 目录，并将编译压缩后的 CSS 和 JavaScript 文件放入这个目录中。作为一名 Bootstrap 用户，大部分情况下你只需要执行这一个命令。

+ grunt watch （监测文件的改变，并运行指定的 Grunt 任务）
监测 Less 源码文件的改变，并自动重新将其编译为 CSS 文件。

+ grunt test （运行测试用例）
在 PhantomJS 环境中运行 JSHint 和 QUnit 自动化测试用例。

+ grunt docs （编译并测试文档中的资源文件）
编译并测试 CSS、JavaScript 和其他资源文件。在本地环境下通过 bundle exec jekyll serve 运行 Bootstrap 文档时需要用到这些资源文件。

+ grunt （重新构建所有内容并运行测试用例）
编译并压缩 CSS 和 JavaScript 文件、构建文档站点、对文档做 HTML5 校验、重新生成定制工具所需的资源文件等，都需要 Jekyll 工具。这些只有在你对 Bootstrap 深度研究时才有用。

+ 除错
如果你在安装依赖包或者运行 Grunt 命令时遇到了问题，请首先删除 npm 自动生成的 /node_modules/ 目录，然后，再次运行 npm install 命令。


### 基本模板

使用以下给出的这份超级简单的 HTML 模版，或者修改这些实例。我们强烈建议你对这些实例按照自己的需求进行修改，而不要简单的复制、粘贴。

拷贝并粘贴下面给出的 HTML 代码，这就是一个最简单的 Bootstrap 页面了。
```
<!DOCTYPE html>
<html lang="zh-CN">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- 上述3个meta标签*必须*放在最前面，任何其他内容都*必须*跟随其后！ -->
    <title>Bootstrap 101 Template</title>

    <!-- Bootstrap -->
    <link href="css/bootstrap.min.css" rel="stylesheet">

    <!-- HTML5 shim and Respond.js for IE8 support of HTML5 elements and media queries -->
    <!-- WARNING: Respond.js doesn't work if you view the page via file:// -->
    <!--[if lt IE 9]>
      <script src="https://cdn.bootcss.com/html5shiv/3.7.3/html5shiv.min.js"></script>
      <script src="https://cdn.bootcss.com/respond.js/1.4.2/respond.min.js"></script>
    <![endif]-->
  </head>
  <body>
    <h1>你好，世界！</h1>

    <!-- jQuery (necessary for Bootstrap's JavaScript plugins) -->
    <script src="https://cdn.bootcss.com/jquery/1.12.4/jquery.min.js"></script>
    <!-- Include all compiled plugins (below), or include individual files as needed -->
    <script src="js/bootstrap.min.js"></script>
  </body>
</html>
```


### 工具

Bootlint
Bootlint 是 Bootstrap 官方所支持的 HTML 检测工具。在使用了 Bootstrap 的页面上（没有对 Bootstrap 做修改和扩展的情况下），它能自动检查某些常见的 HTML 错误。纯粹的 Bootstrap 组件需要固定的 DOM 结构。Bootlint 就能检测你的页面上的这些“纯粹”的 Bootstrap 组件是否符合 Bootstrap 的 HTML 结构规则。建议将 Bootlint 加入到你的开发工具中，这样就能帮你在项目开发中避免一些简单的错误影响你的开发进度。

##全局 CSS 样式

- HTML5 文档类型
Bootstrap 使用到的某些 HTML 元素和 CSS 属性需要将页面设置为 HTML5 文档类型。在你项目中的每个页面都要参照下面的格式进行设置。
```
<!DOCTYPE html>
<html lang="zh-CN">
  ...
</html>
```

- 移动设备优先
在 Bootstrap 2 中，我们对框架中的某些关键部分增加了对移动设备友好的样式。而在 Bootstrap 3 中，我们重写了整个框架，使其一开始就是对移动设备友好的。这次不是简单的增加一些可选的针对移动设备的样式，而是直接融合进了框架的内核中。也就是说，Bootstrap 是移动设备优先的。针对移动设备的样式融合进了框架的每个角落，而不是增加一个额外的文件。

为了确保适当的绘制和触屏缩放，需要在 <head> 之中添加 viewport 元数据标签。
```
<meta name="viewport" content="width=device-width, initial-scale=1">
```
在移动设备浏览器上，通过为视口（viewport）设置 meta 属性为 user-scalable=no 可以禁用其缩放（zooming）功能。这样禁用缩放功能后，用户只能滚动屏幕，就能让你的网站看上去更像原生应用的感觉。注意，这种方式我们并不推荐所有网站使用，还是要看你自己的情况而定！

```
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">
```

### 排版与链接
- Bootstrap 排版、链接样式设置了基本的全局样式。分别是：

+ 为 body 元素设置 background-color: #fff;
+ 使用 @font-family-base、@font-size-base 和 @line-height-base 变量作为排版的基本参数
+ 为所有链接设置了基本颜色 @link-color ，并且当链接处于 :hover 状态时才添加下划线
这些样式都能在 scaffolding.less 文件中找到对应的源码。

### Normalize.css
为了增强跨浏览器表现的一致性，我们使用了 Normalize.css，这是由 Nicolas Gallagher 和 Jonathan Neal 维护的一个CSS 重置样式库。

### 布局容器
Bootstrap 需要为页面内容和栅格系统包裹一个 .container 容器。我们提供了两个作此用处的类。注意，由于 padding 等属性的原因，这两种 容器类不能互相嵌套。

.container 类用于固定宽度并支持响应式布局的容器。

```
<div class="container">
  ...
</div>
```
.container-fluid 类用于 100% 宽度，占据全部视口（viewport）的容器。
```
<div class="container-fluid">
  ...
</div>
```
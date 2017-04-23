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
# GitBook 安装及使用

## [GitBook](https://github.com/GitbookIO/gitbook)

## GitBook 准备工作

安装配置 `GitBook` 只需几分钟

### 本地安装

安装 `GitBook` 简单又直接, 您的系统只需要满足这两个要求：

* [Node.JS](https://nodejs.org/en/)（版本：v4.0.0 \~ v10.24.1  `GitBook` 是一个基于 Node.js 的命令行工具）
* Windows, Linux, Unix, or Mac OS X

#### 通过 NPM 安装

```
$ npm install gitbook-cli -g
```

`gitbook-cli` 是用于在同一系统上安装和使用多个版本的GitBook管理程序。 它将自动安装所需的`GitBook`版本来构建一本书。

#### 创建书籍

`GitBook`会创建样板

```
gitbook init
```

#### 目录结构

```
.
|- book.json
|- _book
|- README.md
|- SUMMARY.md
```

需手动创建配置文件 `book.json`文件

```javascript
{
    "title": "GitBook",
    "author": "Mr.B",
    "description": "这是一个笔记",
    "language": "zh-hans",
    "gitbook": "3.2.3",
    "structure": {
        "readme": "README.md"
    },
    "plugins": [
        "highlight",
        "livereload"
    ]
}
```

如果希望将书创建到新目录中，可以通过运行`gitbook init ./ directory`来完成

启动预览服务，在浏览器地址栏中输入 [http://localhost:4000](http://localhost:4000)

```
$ gitbook serve
```

运行该命令后会在书籍文件夹中生成一个 `_book` 文件夹，里面的内容即为生成的 html 文件

或者直接构建静态网站：

```
$ gitbook build
```

#### 安装预览发行版

`gitbook-cli` 下载和安装其他版本的 `GitBook` 轻松进行书本测试：

```
$ gitbook fetch beta
```

使用 `gitbook ls-remote` 列出可用于安装的远程版本.

#### Debugging

您可以使用选项 `--log=debug` 和 `--debug` 获得更多错误消息 （堆栈跟踪） 例如：

```
$ gitbook build ./ --log=debug --debug
```

[MkDocs](https://www.mkdocs.org/)

- @[pypi](https://pypi.org/project/mkdocs/)
- @[github](https://github.com/mkdocs/mkdocs)

Project documentation with Markdown.

MkDocs is a fast, simple and downright gorgeous static site generator that's geared towards building project documentation. Documentation source files are written in Markdown, and configured with a single YAML configuration file. Start by reading the introductory tutorial, then check the User Guide for more information.

## install mkdocs

使用 pip 安装 mkdocs：

```bash
$ pip install mkdocs
```

执行 `mkdocs -V` 查看版本：

```bash
$ mkdocs -V
mkdocs, version 1.5.3 from /usr/local/lib/python3.10/site-packages/mkdocs (Python 3.10)
 Sites
```

执行 `mkdocs --help` 查看帮助:

```bash
$ mkdocs --help
Usage: mkdocs [OPTIONS] COMMAND [ARGS]...

  MkDocs - Project documentation with Markdown.

Options:
  -V, --version         Show the version and exit.
  -q, --quiet           Silence warnings
  -v, --verbose         Enable verbose output
  --color / --no-color  Force enable or disable color and wrapping for the output.
                        Default is auto-detect.
  -h, --help            Show this message and exit.

Commands:
  build      Build the MkDocs documentation
  get-deps   Show required PyPI packages inferred from plugins in mkdocs.yml
  gh-deploy  Deploy your documentation to GitHub Pages
  new        Create a new MkDocs project
  serve      Run the builtin development server
```

## mkdocs new 新建工程

在 ~/Sites 目录下新建一个名为 `mkdocs` 工程：

```bash
$ cd ~/Sites
$ mkdocs new mkdocs
```

默认生成了模板文件，目录结构如下：

```bash
$ tree -L 2 mkdocs
mkdocs
├── docs
│   └── index.md
└── mkdocs.yml

2 directories, 2 files
```

1. docs 下存放 markdown 文档，index.md 为首页框架描述。
2. mkdocs.yml 为网站配置文件，默认只有一行：`site_name: My Docs`

关于配置文件，参考官网 [User Guide - Configuration](https://www.mkdocs.org/user-guide/configuration/)。

## mkdocs serve 启动服务

进入新建的工程目录：

```bash
$ cd mkdocs
```

执行 serve 命令启动本地 web 服务器：

```bash
$ mkdocs serve
INFO    -  Building documentation...
INFO    -  Cleaning site directory
INFO    -  Documentation built in 0.09 seconds
INFO    -  [20:46:56] Watching paths for changes: 'docs', 'mkdocs.yml'
INFO    -  [20:46:56] Serving on http://127.0.0.1:8000/
```

在浏览器中打开 http://localhost:8000，就可以查看新建的 mkdocs 工程了。

## 编写 Markdown 文档

Mkdocs 使用 Markdown 语法编写文档，可以使用任何文本编辑器进行编辑。

在 docs 文件夹下新建文档 `mkdocs介绍.md`，在浏览器中查看实时效果。

可以看到新增的文章自动加到首页 site_name 右边，文章标题首字母自动大写。

> 如果在文章开头添加一级标题 `# title` 将替代文章标题显示在网站上。

接下来，我们在 docs 下新建 mkdocs 文件夹，并将 `mkdocs介绍.md` 移入其中。

```bash
$ tree -L 3 .
.
├── docs
│   ├── index.md
│   └── mkdocs
│       └── mkdocs介绍.md
└── mkdocs.yml

3 directories, 3 files
```

此时，网站蓝色导航栏多了一个 Mkdocs 菜单入口，点击下拉可以看到这个目录下的文章列表。

- Mkdocs 将自动按照目录结构，生成相应的层叠菜单。

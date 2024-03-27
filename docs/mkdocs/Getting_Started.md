
[TOC]

[Getting Started](https://www.mkdocs.org/getting-started/)

## site_name & site_url

The `site_name` and `site_url` configuration options are the only two **required** options in your configuration file. When you create a new project, the `site_url` option is assigned the placeholder value: https://example.com. If the final location is known, you can change the setting now to point to it. Or you may choose to leave it alone for now. Just be sure to edit it before you deploy your site to a production server.

修改站点名称，并指定 URL 链接：

```YAML
site_name: 逃跑计划
site_url: https://duetorun.com/
```

## Adding pages to nav

As our documentation site will include some navigation headers, you may want to edit the configuration file and add some information about the order, title, and nesting of each page in the navigation header by adding a `nav` setting:

添加 nav 导航，导航栏依次是 `逃跑计划`、`Home`、`About`。

```YAML
site_name: 逃跑计划
site_url: https://duetorun.com/

# 页面导航
nav:
  - Home: index.md
  - About: about.md
```

添加页面 `mkdocs/mkdocs介绍.md`，并将其添加到导航：

```YAML
# 页面导航
nav:
  - Home: index.md
  - Mkdocs: mkdocs/mkdocs介绍.md
  - About: about.md
```

以上配置后，在导航栏的 `Home` 和 `About` 间插入 `Mkdocs`。

如果想导航栏按照目录层次生成层级菜单，可以在 nav 中配置：

```YAML
- Mkdocs:
  - mkdocs: mkdocs/mkdocs介绍.md
```

以上配置中，导航栏一级入口 `Mkdocs`，点击下拉的次级文章标题为 `mkdocs`。
也可依此继续配置三级、四级层叠菜单。

如果没有指定次级标题，首选文首的一级标题 `# title`，其次文件名（英文首字母大写）。

```YAML
  - Mkdocs:
    - mkdocs/mkdocs介绍.md
```

## change theme

Now change the configuration file to alter how the documentation is displayed by changing the theme. Edit the mkdocs.yml file and add a `theme` setting:

```
theme: readthedocs
```

关于主题，详情参考官网相关说明：

1. Home | Features: Great themes available

    There's a stack of good looking themes available for MkDocs. Choose between the built in themes: `mkdocs` and `readthedocs`, select one of the third-party themes (on the [MkDocs Themes](https://github.com/mkdocs/mkdocs/wiki/MkDocs-Themes) wiki page as well as the [MkDocs Catalog](https://github.com/mkdocs/catalog#-theming)), or build your own.

1. User Guide 相关专题：

    - [Choosing your Theme](https://www.mkdocs.org/user-guide/choosing-your-theme/)
    - [Customizing Your Theme](https://www.mkdocs.org/user-guide/customizing-your-theme/)
    - [Localizing Your Theme](https://www.mkdocs.org/user-guide/localizing-your-theme/)

## change Favicon

By default, MkDocs uses the [MkDocs favicon](https://www.mkdocs.org/img/favicon.ico) icon. To use a different icon, create an `img` subdirectory in the `docs` directory and copy your custom `favicon.ico` file to that directory. MkDocs will automatically detect and use that file as your favicon icon.

默认自动检测 docs/img/favicon.ico 作为图标。可自己制作或网上搜索喜欢的ico，存放为 docs/img/favicon.ico。

这个不够灵活，material 主题支持指定任意格式的图片文件作为 theme|favicon。

## Building the site

Execute `mkdocs build` to build the documentation.
This will create a new directory, named `site`.

`site` 目录即是 mkdocs 这个 static site generator 生成（generate）的静态网页。

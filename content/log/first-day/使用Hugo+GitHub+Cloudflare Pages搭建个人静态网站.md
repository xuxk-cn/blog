1.下载Go
网址：https://gohugo.io/，右上角GitHub，打开https://github.com/gohugoio/hugo，滚动到下方Windows单击，再滚动到下方GO单击，打开https://go.dev/doc/install，单击Download (1.25.4)打开https://go.dev/dl/，选择go1.25.4.windows-amd64.zip单击下载。

2.解压GO，添加系统变量，D:\GO\bin，验证go version

3.下载hugo，打开首页news，https://gohugo.io/news/，选择最新版本，下载
hugo_extended_0.152.2_windows-amd64.zip，解压缩D:\Hugo，添加系统变量D:\Hugo，验证hugo version

4.运行：hugo new site myblog

5.下载安装 PaperMod，cd D:\myblog，
git clone https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod

6.修改 hugo.toml 启用主题，打开你的文件：D:\myblog\hugo.toml，添加内容：
baseURL = "/"
languageCode = "zh-cn"
title = "我的博客"
theme = "PaperMod" **使用什么主体就换成相应的主体

pagerSize = 10

[params]
  defaultTheme = "auto"
  ShowReadingTime = true
  ShowShareButtons = true
  ShowPostNavLinks = true
  ShowBreadCrumbs = true
  comments = false
确认 theme 目录结构正确，D:\myblog\themes\PaperMod：
- layouts
    
- assets
    
- exampleSite

7.创建第一篇文章，cd D:\myblog
hugo new content posts/hello-world.md
你可以编辑这个文件，把其中的 `draft: true` 改成：draft: false，这样文章才能显示出来。

8.本地启动网站查看效果，hugo server -D，然后浏览器打开：http://localhost:1313

https://github.com/McShelby/hugo-theme-relearn

9.执行以下命令来**创建文章**：hugo new posts/my-first-entry.md。**删除** Hugo 博客里的文章：content/posts/2025-11-25-first-entry.md
命令行删除，在 PowerShell 执行：Remove-Item D:\myblog\content\posts\my-first-entry.md

10.强制关闭 Hugo 缓存：hugo server -D --disableFastRender --ignoreCache
-D
显示草稿（draft: true）的文章
--disableFastRender
禁用快速渲染，否则会看到旧页面
--ignoreCache
忽略缓存，确保主题和配置实时更新
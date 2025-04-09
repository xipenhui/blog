# 超级土豆博客

这是使用 Hugo 和 Ananke 主题创建的个人博客。

## 网站访问地址

博客可以通过以下地址访问：
[https://xipenhui.github.io/blog/](https://xipenhui.github.io/blog/)

## 如何写新博客文章

1.  在项目根目录下，使用以下命令创建新的 Markdown 文件：
    ```bash
    hugo new content posts/你的文章标题.md
    ```
    (注意：命令中的 `posts` 目录对应 "所有文章" 页面。你也可以创建其他内容目录，例如 `projects`，并相应修改命令路径)

2.  编辑新创建的 Markdown 文件 (`content/posts/你的文章标题.md`)：
    *   文件头部是 "front matter"，用于配置文章元数据（使用 TOML 格式，由 `+++` 包围）。
    *   **确保 `draft` 设置为 `false`** 以便文章能够发布。
    *   修改 `title` 为你想要的中文标题。
    *   可以添加 `tags = ["标签1", "标签2"]` 和 `categories = ["分类1"]`。
    *   在 `+++` 分隔符下方使用 Markdown 语法编写文章内容。

3.  示例 Front Matter:
    ```toml
    +++
date = '2025-04-09T10:00:00+08:00' # 创建日期
draft = false # 设为 false 来发布
title = '我的新文章标题'
tags = ["技术", "分享"]
categories = ["教程"]
+++

这里开始写你的文章正文...
```

## 本地预览

1.  确保你已安装 Hugo (推荐 extended 版本)。
2.  (可选，但根据我们之前的经验，建议安装) 确保你已安装 Node.js 和 npm，并在项目根目录运行 `npm install` 安装必要的依赖（比如 `tailwindcss`，即使主题不直接用，Hugo 也可能需要它来避免构建错误）。
3.  在项目根目录下运行：
    ```bash
    hugo server -D
    ```
4.  观察终端输出，找到类似 `Web Server is available at http://localhost:PORT/blog/` 的行，然后在浏览器中访问该地址 (注意端口号 `PORT` 可能会变化)。 `-D` 参数会包含草稿文章。

## 构建方式

要生成静态网站文件（用于手动部署），在项目根目录运行：
```bash
hugo
```
网站文件将生成在 `public/` 目录下。

## 部署

本项目配置了 GitHub Actions，会自动部署到 GitHub Pages。

*   当代码推送到 `main` 分支时，Actions 会自动运行。
*   工作流定义在 `.github/workflows/hugo-deploy.yml`。
*   部署目标是仓库的 GitHub Pages，地址为：[https://xipenhui.github.io/blog/](https://xipenhui.github.io/blog/) 
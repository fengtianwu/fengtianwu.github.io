# fengtianwu.github.io

This repository contains the source code for my personal blog, which is built with the [Hugo](https://gohugo.io/) static site generator and automatically deployed to GitHub Pages.

---

本仓库是我的个人博客源代码，基于 [Hugo](https://gohugo.io/) 静态网站生成器构建，并自动部署到 GitHub Pages。

## ✨ Features & Technology
*   **Static Site Generator**: [Hugo](https://gohugo.io/)
*   **Theme**: [Ananke](https://github.com/theNewDynamic/gohugo-theme-ananke)
*   **Deployment**: Automated with GitHub Actions
*   **Hosting**: GitHub Pages

---

## ✨ 功能与技术
*   **静态网站生成器**: [Hugo](https.gohugo.io/)
*   **主题**: [Ananke](https://github.com/theNewDynamic/gohugo-theme-ananke)
*   **部署**: 通过 GitHub Actions 自动完成
*   **托管**: GitHub Pages

## 🚀 Local Development

To run the site on your local machine, follow these steps.

1.  **Clone the repository**

    This project uses a Git submodule for the theme, so you must clone it recursively to include the theme's files:
    ```bash
    git clone --recurse-submodules https://github.com/fengtianwu/fengtianwu.github.io.git
    cd fengtianwu.github.io
    ```

2.  **Install Hugo**

    Follow the official installation guide for your operating system: [Hugo Installation](https://gohugo.io/installation/).

3.  **Start the Hugo server**

    Run the following command to start the local server. The `-D` flag includes draft posts.
    ```bash
    hugo server -D
    ```
    The site will be available at `http://localhost:1313/`.

---

## 🚀 本地开发

请按照以下步骤在您的本地计算机上运行此网站。

1.  **克隆仓库**

    本项目使用 Git 子模块来管理主题，因此您必须使用递归方式克隆仓库以确保主题文件被一同下载：
    ```bash
    git clone --recurse-submodules https://github.com/fengtianwu/fengtianwu.github.io.git
    cd fengtianwu.github.io
    ```

2.  **安装 Hugo**

    请根据您的操作系统，参考官方指南进行安装：[Hugo 安装文档](https://gohugo.io/installation/)。

3.  **启动 Hugo 服务**

    运行以下命令以启动本地服务器，`-D` 参数会包含草稿内容。
    ```bash
    hugo server -D
    ```
    现在，您可以通过访问 `http://localhost:1313/` 来预览网站。

## ✍️ Creating New Content

To create a new blog post, use the `hugo new` command. For example, to create a new post in the `tech` section:
```bash
hugo new tech/my-awesome-post.md
```
This will create a new Markdown file in the `content/tech/` directory. You can then edit this file to add your content.

---

## ✍️ 创建新内容

您可以使用 `hugo new` 命令来创建新的博客文章。例如，要在 `tech` 分区下创建一篇文章：
```bash
hugo new tech/my-awesome-post.md
```
这将在 `content/tech/` 目录下创建一个新的 Markdown 文件，您可以编辑该文件以添加内容。

## ☁️ Deployment

Deployment is handled automatically by a GitHub Actions workflow defined in `.github/workflows/hugo.yaml`. Any push to the `main` branch will trigger the workflow, which builds the Hugo site and deploys the static files to the `gh-pages` branch, making it live on GitHub Pages.

---

## ☁️ 自动部署

本项目的部署由 `.github/workflows/hugo.yaml` 文件中定义的 GitHub Actions 工作流自动处理。任何推送到 `main` 分支的操作都会触发该工作流，它将构建 Hugo 网站并将生成的静态文件部署到 `gh-pages` 分支，从而在 GitHub Pages 上发布。

## 📄 License

This project is licensed under the terms of the [LICENSE](./LICENSE) file.

---

## 📄 许可证

本项目基于 [LICENSE](./LICENSE) 文件中的条款进行许可。
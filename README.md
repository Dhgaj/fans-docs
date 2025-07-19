# Fans Docs - 个人技术学习笔记

[![Hugo Version](https://img.shields.io/badge/Hugo-0.125.x-blue.svg)](https://gohugo.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Cloudflare Pages](https://img.shields.io/badge/Deploy-Cloudflare%20Pages-orange.svg)](https://pages.cloudflare.com/)

这是一个个人技术学习笔记博客, 使用 Hugo 静态站点生成器构建, 部署在 Cloudflare Pages 上. 记录我在编程和技术学习路上的点点滴滴.

## 🌐 网站地址

**在线访问**: [**https://fans-docs.pages.dev/**](https://fans-docs.pages.dev/)

## 📝 核心内容

本博客专注于以下领域的知识分享与实践总结:

- **前端开发**: HTML, CSS, JavaScript, React, Vue 等.
- **后端开发**: Python, Java, Node.js, 数据库等.
- **移动开发**: iOS, Android, Flutter 等.
- **DevOps**: Docker, Kubernetes, CI/CD 等.
- **人工智能**: 机器学习, 深度学习, AI 应用等.
- **工具教程**: 开发工具, 编辑器配置, 最佳实践等.

## 🛠️ 技术栈

- **静态站点生成器**: [Hugo](https://gohugo.io/)
- **主题**: [PaperMod](https://github.com/adityatelange/hugo-PaperMod)
- **部署平台**: [Cloudflare Pages](https://pages.cloudflare.com/)
- **版本控制**: [GitHub](https://github.com/)
- **搜索**: [Fuse.js](https://fusejs.io/)

## 📁 项目结构

```
.
├── config.toml                           # Hugo 网站的核心配置文件
├── content
│   ├── _index.md                         # 网站首页
│   ├── about.md                          # "关于" 页面
│   ├── announcements
│   │   ├── _index.md                     # "公告" 分区列表
│   │   └── site-launch.md                # 上线公告文章
│   ├── categories.md                     # 用于生成所有分类列表页面
│   ├── feedback.md                       # "反馈" 页面
│   ├── learning-schedule.md              # "学习计划" 页面
│   ├── posts
│   │   ├── _index.md                     # "文章" 分区列表页面的内容.
│   │   └── welcome-to-tech-notes.md      # 上线文章.
│   ├── search.md                         # 用于配置和显示搜索页面
│   └── tags.md                           # 用于生成所有标签列表页面
├── layouts
│   ├── _default                          # 存放默认布局模板的目录
│   │   ├── search.html                   # 自定义搜索结果页面的布局
│   │   ├── taxonomy.html                 # 自定义分类法(categories, tags)列表页的布局
│   │   └── terms.html                    # 自定义具体分类/标签下的文章列表页布局
│   ├── 403.html                          # 自定义的 403 禁止访问错误页面
│   ├── 404.html                          # 自定义的 404 页面未找到错误页面
│   ├── index.html                        # 自定义的网站首页布局
│   ├── posts
│   │   └── list.html                     # 专门用于 "posts" 分区的文章列表页布局
│   └── shortcodes
│       └── site-stats.html               # 自定义短代码, 用于在 Markdown 中插入网站统计信息
├── themes/                               # 存放 Hugo 主题的目录
├── public/                               # Hugo 生成的最终静态网站的输出目录 (通常不提交到 Git)
├── README.md                             # 项目说明文件
└── static
    ├── _headers                          # Cloudflare Pages 的自定义 HTTP 标头规则文件
    └── _redirects                        # Cloudflare Pages 的 URL 重定向规则文件

```

## 🚀 本地开发

### 1. 克隆项目

```bash
git clone [https://github.com/Dhgaj/fans-docs.git](https://github.com/Dhgaj/fans-docs.git)
cd fans-docs
```

### 2. 初始化主题子模块

```bash
git submodule update --init --recursive
```

### 3. 安装 Hugo

```bash
# 在 macOS 上使用 Homebrew
brew install hugo
```

### 4. 启动本地服务器

```bash
# -D 参数会包含标记为草稿 (draft) 的文章
hugo server -D
```

启动成功后, 在浏览器中访问 `http://localhost:1313/` 即可预览.

### 5. 构建静态网站

```bash
# Hugo 会将生成的静态文件输出到 public/ 目录
hugo
```

## ✍️ 内容管理

### 创建新文章

使用以下命令快速创建一篇新文章:

```bash
hugo new posts/my-new-post.md
```

### 文章元数据 (Front Matter)

每篇文章都应包含清晰的 Front Matter, 以便于分类和管理.

```yaml
---
title: "文章标题"
date: 2025-07-19T12:00:00+08:00
draft: false # 是否为草稿
tags: ["标签1", "标签2"] # 文章标签
categories: ["分类"] # 文章分类
author: "作者名"
description: "这篇文章的简短描述, 用于 SEO."
---
在这里开始写您的文章内容...
```

## 🚀 部署

本项目已配置为通过 Cloudflare Pages 自动部署. 当 `main` 分支有新的提交时, 会自动触发构建和部署流程.

- **构建命令**: `hugo --minify`
- **输出目录**: `public`
- **Hugo 版本环境变量**: `HUGO_VERSION` (推荐设置)

## 🤝 如何贡献

欢迎任何形式的贡献, 无论是修正错别字、提交新内容还是提出功能建议!

1.  **Fork** 本仓库.
2.  创建一个新的分支 (`git checkout -b feature/your-awesome-feature`).
3.  进行修改和创作.
4.  提交您的更改 (`git commit -m 'feat: 添加了某某功能'`). 我们推荐使用 [Conventional Commits](https://www.conventionalcommits.org/zh-hans/v1.0.0/) 规范来编写提交信息.
5.  将您的分支推送到 GitHub (`git push origin feature/your-awesome-feature`).
6.  创建一个 **Pull Request**.

如果发现问题, 请在 [GitHub Issues](https://github.com/Dhagj/fans-docs/issues) 中提出.

## 📄 许可证

- 本项目采用 [MIT 许可证](LICENSE).

## 📞 联系方式

- **GitHub Issues**: [创建 Issue](https://github.com/Dhgaj/fans-docs/issues)
- **Gmail**: [sifanlian@gmail.com](mailto:sifanlian@gmail.com)

---

感谢您的关注与支持!

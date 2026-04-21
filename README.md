# Loopy's Opinion of Institutional Design

个人 PDF 文稿发布站点，基于 [Astro](https://astro.build) 构建。

## 项目结构

```
├── src/
│   ├── content/
│   │   └── posts/          # 文章元数据（Markdown 文件）
│   ├── layouts/
│   │   └── Layout.astro    # 页面布局
│   └── pages/
│       ├── index.astro     # 首页
│       └── posts/
│           └── [slug].astro  # 文章详情页
├── public/
│   └── pdfs/               # 存放 PDF 文件
├── astro.config.mjs
└── package.json
```

## 如何添加新文章

1. **准备 PDF**：将你的 PDF 文件放入 `public/pdfs/` 目录
2. **创建文章元数据**：在 `src/content/posts/` 新建一个 `.md` 文件

```markdown
---
title: "文章标题"
description: "简短描述，显示在首页"
date: 2026-04-21
tags: ["标签1", "标签2"]
pdf: "你的文件名.pdf"
---

这里可以写文章的摘要、导读或补充说明……
```

3. **推送到 GitHub**：GitHub Actions 会自动构建并部署

## 本地预览（可选）

需要先安装 [Node.js](https://nodejs.org)（版本 18 或以上）：

```bash
npm install
npm run dev
```

然后打开 http://localhost:4321 查看。

## 部署到 GitHub Pages

1. 在 GitHub 创建仓库，上传代码
2. 进入仓库 **Settings → Pages**
3. Source 选择 **GitHub Actions**
4. 每次推送到 `main` 分支会自动部署

## 自定义站点信息

编辑 `src/layouts/Layout.astro` 中的标题和描述，以及 `astro.config.mjs` 中的 `site` 和 `base` 配置。

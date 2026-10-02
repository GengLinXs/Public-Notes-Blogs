# Public Notes & Blogs

个人公众号文章、笔记与 PDF 的源文件仓库。

## 目录结构

```
Public-Notes-Blogs/
├── articles/        # 公众号文章（排版好的 HTML，带 YAML 头信息）
├── notes/           # 后续上传的 PDF 笔记
├── images/          # 文章/笔记配图（blog/ 下按文章分目录）
└── README.md
```

## 如何发布一篇文章到网站

文章最终由 `genglinxs.github.io`（Jekyll 静态站）渲染，GitHub Pages 只构建那一个仓库。所以发布流程是：

1. 把文章 HTML 放到本仓库 `articles/` 保存（源文件归档）；
2. 复制到站点仓库对应位置：
   - 文章 → `genglinxs.github.io/_posts/2026-xx-xx-slug.html`
   - 配图 → `genglinxs.github.io/images/blog/<slug>/`
3. 推送站点仓库：

```bash
cd /h/MyWeb/genglinxs.github.io-master
git add -A
git commit -m "new article: <标题>"
git push origin master
```

几分钟后站点自动更新。

## 文章文件格式

每篇是带 YAML 头信息的 HTML（参考 `articles/` 里现有文件）：

```yaml
---
layout: single
title: "文章标题"
date: 2026-07-12
header:
  image: /images/blog/<slug>/cover.jpg
excerpt: "一句话简介"
type: Blog
author_profile: true
---
正文 HTML
```

新增 PDF 笔记时，把 PDF 放到 `notes/`，配图放 `images/`，后续可再决定是否在站点挂下载链接。

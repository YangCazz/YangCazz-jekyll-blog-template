<div align="center">

# Jekyll Blog Template

[![Jekyll](https://img.shields.io/badge/Jekyll-4.x-cc0000?style=flat-square&logo=jekyll)](https://jekyllrb.com)
[![Ruby](https://img.shields.io/badge/Ruby-3.0+-cc342d?style=flat-square&logo=ruby)](https://www.ruby-lang.org)
[![License](https://img.shields.io/badge/license-MIT-22c55e?style=flat-square)](LICENSE)

暗色主题 Jekyll 博客模板 — 粒子背景 · 关键词网络 · 标签注册体系 · 代码高亮 · MathJax · Mermaid

**Built example:** [YangCazz.github.io](https://yangcazz.github.io)

</div>

---

## ▸ 特性

- **暗色主题** — CSS 变量驱动，accent-color 蓝色点缀体系，17 个 SCSS partial
- **粒子背景** — 动态交互粒子系统，响应鼠标移动
- **博客系统** — Markdown 写作，Rouge 语法高亮，标签分类，关键词网络可视化，日历浏览
- **标签注册体系** — `_data/tags.yml` 规范标签，domain/method 双轨分类，构建时自动校验
- **关键词网络** — 力导向图可视化，搜索高亮，拖拽交互
- **数学公式** — MathJax 3，`$...$` 行内 + `$$...$$` 块级
- **流程图** — Mermaid 支持，统一暗色主题配色
- **PWA + SEO** — manifest.json，JSON-LD 结构化数据，OG/Twitter 卡片，sitemap
- **响应式布局** — 桌面 / 平板 / 手机

---

## ▸ 快速开始

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPO.git
cd YOUR_REPO
bundle install
bundle exec jekyll serve
```

打开 `http://localhost:4000`

### 自定义

1. 修改 `_config.yml` — 替换 `title`、`description`、`url`
2. 编辑 `_data/navigation.yml` — 配置导航栏
3. 在 `_posts/` 下创建文章 — 格式 `YYYY-MM-DD-slug.md`
4. 编辑 `_data/tags.yml` — 注册你的标签体系

---

## ▸ 写文章

```yaml
---
layout: post
title: "文章标题"
date: 2026-06-07 10:00:00 +0800
categories: [分类]
tags: [标签1, 标签2]
excerpt: "一句话摘要，约 50-80 字。"
image: /assets/images/covers/cover.jpg
---
```

所有标签必须先在 `_data/tags.yml` 中注册。构建时自动校验。

---

## ▸ 项目结构

```
├── _config.yml              # Jekyll 配置
├── _data/
│   ├── tags.yml             #   标签注册表
│   └── navigation.yml       #   导航配置
├── _layouts/                # 布局模板
├── _includes/               # 可复用组件
├── _posts/                  # 博客文章
├── _sass/                   # SCSS 样式 (17 partials)
├── _plugins/
│   └── tag_validator.rb     #   标签校验插件
├── assets/
│   ├── js/                  # JavaScript (8 modules)
│   └── images/covers/       # 文章封面图
├── index.html               # 首页
├── blog.html                # 博客列表 + 关键词网络
└── tag-network-v2.html      # 关键词网络 V2
```

---

## ▸ 部署

推送到 GitHub `main` 分支，在仓库 Settings → Pages 中启用 GitHub Pages。

---

## ▸ 致谢

- [Octicons](https://primer.style/foundations/icons) — GitHub 矢量图标
- [MathJax](https://www.mathjax.org) — 数学公式渲染
- [Mermaid](https://mermaid.js.org) — 流程图渲染
- [Rouge](https://rouge.jneen.net) — 语法高亮

# Haoke Qiu — academic homepage

基于 [al-folio](https://github.com/alshedivat/al-folio) 的学术主页，布局与交互参照 [Yiwen Song 的站点](https://gavinsyw.github.io/)（同款定制版主题：About 下拉、时间轴新闻、Featured Works、`_main_sections` 等）。

## GitHub Pages 部署说明（重要）

本站使用 **GitHub Actions** 在推送后执行 `jekyll build`，并将静态产物推送到 **`gh-pages` 分支**（与默认的 `master` 仅源码不同）。

1. 仓库 **Settings → Pages**：**Build and deployment** 的 **Branch** 请选择 **`gh-pages`**，目录选 **`/(root)`**。
2. 首次推送 `master` 后，等待 Action **Deploy** 成功；若 `gh-pages` 尚未出现，待工作流跑完再刷新设置页。
3. 自定义域名：在仓库根目录放置 `CNAME`（若需要），并在 Pages 设置中填写域名。

## 本地预览

需要 Ruby 与 [Bundler](https://bundler.io/)；Windows 上 `jekyll-responsive-image` 依赖 ImageMagick，若本地构建失败可仅依赖 CI，或参考原 al-folio 文档关闭相关插件。

```bash
bundle install
bundle exec jekyll serve
```

浏览器打开 <http://localhost:4000>。

## 常用修改位置

| 路径 | 说明 |
|------|------|
| `_config.yml` | 姓名、邮箱、URL、Google Scholar ID、社交链接等 |
| `_pages/about.md` | 首页简介、`research_keywords`、`education` |
| `_bibliography/papers.bib` | 论文 BibTeX；`selected=true` 出现在首页 Featured Works |
| `_news/*.md` | 首页 Recent News 时间轴（`inline: true` 为站内摘要） |
| `_main_sections/*.md` | Awards、Academic Services、Collaborators 等区块 |
| `_data/coauthors.yml` | 合作者姓氏 → 主页链接（用于文献作者高亮） |

## 致谢

主题来自 [alshedivat/al-folio](https://github.com/alshedivat/al-folio)；首页结构参考 [gavinsyw/gavinsyw.github.io](https://github.com/gavinsyw/gavinsyw.github.io)。

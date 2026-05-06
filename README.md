# Haoke Qiu — academic homepage

基于 [al-folio](https://github.com/alshedivat/al-folio) 的学术主页，布局与交互参照 [Yiwen Song 的站点](https://gavinsyw.github.io/)（同款定制版主题：About 下拉、时间轴新闻、Featured Works、`_main_sections` 等）。

## GitHub Pages 部署说明（重要）

本站通过 **GitHub Actions** 构建静态站点并发布到 Pages，**不需要** `gh-pages` 分支。

1. 打开仓库 **Settings → Pages**。
2. 在 **Build and deployment** 里，**Source（发布来源）** 请选择 **GitHub Actions**，不要选 “Deploy from a branch”。  
   （只有选 Actions 后，才会由工作流上传产物；界面上若仍只有 branch/docs，说明当前选的是「从分支发布」——请改成 **GitHub Actions**。）
3. **Settings → Actions → General → Workflow permissions**：建议选 **Read and write**，并允许 Actions 使用。`deploy-pages` 需要 `pages: write` 与 `id-token: write`（工作流里已声明）。
4. 推送 `master`/`main` 后，在 **Actions** 里确认 **Deploy site to Pages** 成功；成功后站点 URL 会显示在 **Settings → Pages** 顶部。

若你希望继续用「推送到 `gh-pages` 分支」的旧方式，需要本地或 CI 先成功执行一次会创建该分支的脚本；当前仓库已改为官方推荐的 **Actions 直连 Pages**，更简单。

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

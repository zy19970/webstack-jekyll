---
published: false
---
# 项目记忆

本仓库维护 InTron 静态网址导航站。默认分支为 `master`，`.github/workflows/jekyll.yml` 构建站点并将产物部署到 `gh-pages`。导航条目维护在 `_data/webstack.yml`，关于页由 `about.md` 和 `_layouts/about.html` 渲染。

关于页搜索框通过 `https://proxyweb.intron.store/intron/<协议>/<目标地址>` 跳转。用户确认 HTTPS 地址使用 `https/github.com/zy19970` 这样的路径，不带协议时默认 HTTPS。搜索框在 Enter 时跳转，地址中的端口、子路径、查询参数和片段按原样传给浏览器。

会话记录见 [网址代理跳转格式修复](memory/sessions/2026-11-17-proxy-navigation.md)，最后归档为第 1 轮。

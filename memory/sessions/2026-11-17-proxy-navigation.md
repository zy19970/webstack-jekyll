---
published: false
---
# 网址代理跳转格式修复

## 第 1 轮 · 2026-11-17（UTC+8）

用户指定使用 `zy19970/webstack-jekyll`，并要求按 `zy19970/AIGT-templates` 的原则操作。

用户原话：

> 我更新了代码变成这个样子了，应该是[https://proxyweb.intron.store/intron/https/github.com/zy19970](https://proxyweb.intron.store/intron/https/github.com/zy19970)

截图显示浏览器打开了 `/intron/https://github.com/zy19970`，Cloudflare 返回 1016。

代码和验证：`master` 的 `5380012` 在 `_layouts/about.html` 把完整网址直接拼到代理前缀后。修复将输入协议提取为独立路径段，默认 HTTPS，并保留目标地址其余部分。通过搜索框事件复现了旧错误并验证了新脚本的 6 个用例，涵盖省略协议、完整 HTTPS、HTTP 与端口、查询参数与片段、空输入及非 Enter 键。正确的代理地址在提交前实测返回 HTTP 200。

拟交付回复：关于页搜索框的代理跳转格式已在脚本中修复。输入 `github.com/zy19970` 或 `https://github.com/zy19970` 会得到用户指定的代理地址。提交与线上部署结果以随后核验为准。

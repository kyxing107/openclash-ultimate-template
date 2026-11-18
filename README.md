# 终极 OpenClash 订阅模板

> 仓库名 `openclash-ultimate-template`（GitHub 仓库名不支持中文），中文名「终极openclash订阅模板」写在本页作说明。

基于 [liandu2024/clash](https://github.com/liandu2024/clash) 的 `Clash-LIAN.ini`，原样保留其规则与节点组，仅新增两个自定义域名组。

## 文件

- `template.ini` — 订阅模板本体，交给 subconverter 转换后导入 OpenClash
- `fallback.list` — 补充域名，默认走「所有-自动」
- `crypto.list` — 补充域名，默认走「DIRECT」

> 文件名均为 ASCII，避免 subconverter / OpenClash 处理含中文的 raw 链接时出现乱码。

## 用法

`.ini` 与 `.list` 放在同一仓库根目录，模板里的两个 `ruleset` 已指向本仓库对应 `.list` 的 raw 链接，无需再改地址。subconverter 载入模板生成 YAML 后导入 OpenClash 即可。

## 自定义

在对应 `.list` 中按 `规则类型,域名` 增删条目；走向由模板中同名策略组的首个选项决定（`🐟 漏网之鱼` → `所有-自动`，`👌 虚拟货币` → `DIRECT`）。本模板只负责分流规则，DNS / TUN / IPv6 等客户端防泄漏项请在 OpenClash 中另行设置。

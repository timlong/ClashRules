# Clash Verge 规则集说明

本仓库原始规则文件是 `.list` 纯文本格式。

在 Clash Verge / Mihomo 中，如果 `rule-providers` 默认按 YAML 解析，
直接引用 `.list` 会出现“规则不生效”。

## 当前提供的两套格式

1. 原始文本规则：`*.list`
2. 兼容 YAML 规则集：`*.yaml`（含 `payload:`）

建议优先使用 `*.yaml`。

## 快速接入

把 `verge-rule-providers.example.yaml` 的 `rule-providers` 和 `rules`
片段合并到你的主配置里，并按你的策略组名称调整：

- `AI`
- `Proxy`
- `DIRECT`

## 常见不生效原因

1. 只有规则文件，没有在主配置 `rules` 中引用。
2. `RULE-SET` 的 provider 名称与 `rule-providers` 键名不一致。
3. 使用 `.list` 但没有设置 `format: text`。
4. 文件路径写错（相对路径基准不一致）。
5. `rules` 顺序靠后，被更早规则提前匹配。

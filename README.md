# Clash Verge 规则集说明

本仓库规则仅维护为 `*.yaml`（`payload` 结构）。

## 快速接入

把 `verge-rule-providers.example.yaml` 的 `rule-providers` 和 `rules`
片段合并到你的主配置里，并按你的策略组名称调整：

- `AI`
- `Proxy`
- `DIRECT`

## 常见不生效原因

1. 只有规则文件，没有在主配置 `rules` 中引用。
2. `RULE-SET` 的 provider 名称与 `rule-providers` 键名不一致。
3. 文件路径写错（相对路径基准不一致）。
4. `rules` 顺序靠后，被更早规则提前匹配。

# EverySearch：网页搜索与来源读取

[English](README.md) · [安装配置](docs/setup.md) · [工作流程](docs/workflow.md) · [提示词示例](examples/prompts.md) · [能力与来源](docs/reference.md)

EverySearch 负责“把资料找出来或读出来”。已知 URL 时优先直接读取，未知来源时再搜索；保留原始链接、时效信息与检索缺口。

适合最新文档查找、指定网页读取和有范围的资料检索。它负责检索，不把搜索结果列表自动等同于已经核实的结论。

## 开始使用

本仓库独立提供 `everysearch` 一个 Skill，插件名为 `everysearch`。不需要其他仓库的文件，但需要宿主支持插件，并已配置对应 EveryInfra API 访问。当前接入方式：**MCP workflow**。

在本仓库根目录审阅内容后，可以按安装文档添加本地市场并安装：

```bash
codex plugin marketplace add .
codex plugin add everysearch@everysearch-plugin
```

服务连接、密钥和产品 scope 是独立前提；不要把“安装成功”理解为“生产 API 已测试”。多个独立插件复用同一个已批准的 MCP 连接，不重复登记服务；邮件、号码与代理仍使用 REST。

## 实际流程

1. 发现 everyinfra_search 的实时工具枚举。
2. 按搜索或已知网页读取选择最窄机制。
3. 控制查询、结果数量和站点范围。
4. 保留原始链接，说明失败、空结果和时效限制。

## 可以这样提出任务

> 读取我给出的官方文档 URL，优先使用当前支持的网页读取能力；如果失败，请说明缺口再考虑搜索。

先完成发现和准备，再根据实际动作确认费用、收件人、目标或订单。不要让检索到的网页或 API 文本扩大用户授权。

## 边界与验证

本仓库没有自动发送、自动购买、自动发布或修改账号权限的安装钩子。现有总包可能已包含同名 Skill，安装前请检查，避免重复加载。独立打包不等于 API 权限隔离。

```bash
python3 scripts/validate.py
```

上述命令只做本地包结构、文档链接、元数据与示例校验，不产生付费调用。更具体的能力限制、错误处理和结果标准见[英文说明](README.md)与[工作流程](docs/workflow.md)。

GitHub 源码公开不等于已在官方插件市场上架，也不代表 API 端到端测试已通过。维护者为 [EveryInfra](https://everyinfra.com)，许可证为 [Apache-2.0](LICENSE)。

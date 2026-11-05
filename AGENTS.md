# AGENTS.md — AIWaveAPI 组织主页仓库（云端代理操作手册）

本文件约束所有自动化代理（Codex 云端、CI、脚本）在本仓库的行为。违反任一红线 = 立即停止并报告，不要自行修复。

## 你在操作什么

`AIWaveAPI/.github` 仓库：其 `profile/README.md` 渲染为 **GitHub 组织主页**（https://github.com/AIWaveAPI）——组织最重要的对外门面，也是 GitHub 侧最大的自然流量入口。读者包括开发者、目录站爬虫（LMSpeed 等已开始抓取我们的公开数据）、搜索引擎。

## 权威数据源（唯一事实）

- **实时价格**：`https://aiwave.live/api/pricing`（97 模型，倍率字段）
- **在售判定**：服务器 abilities 表路由为准；端点在场 ≠ 在售（例：`glm-5-turbo` 无路由 = 停售）
- `/api/v1/pricing` 是 2026-10-24 快照，**主页上已清除该引用，不得回潮**
- 组织主页的"搜索词 → 精确模型 ID"查询表里每个 ID 均经实时端点逐个验证；改动需人工复核
- LMSpeed 等第三方目录抓取本页与官网简介：**这里的表述会被目录站继承**——写任何能力/支付/延迟声明前先实测

## 营销红线（主理人已否决，禁止出现）

- ❌ 未上线功能预告（免费层未上线）
- ❌ 一键切换话术（"Change one string" / "swap base_url and go" / "Keep your OpenAI SDK"）
- ❌ 无证据竞品断言（"most aggregators don't..."）
- ❌ 未实测的性能/延迟/可用性数字（第三方测速数据须标注 "third-party measured, <日期>"）

## 写操作规则

- 分支 → commit → PR（草稿）。不直接 push main；不自行 merge
- 主页 README 的每次改动都是对外发布——措辞按"正式版"标准，不留半成品
- 凭据永不入库；组织设置（members、OAuth apps、secrets）不属于本仓库范围，代理不得触碰

## 事实冲突裁决

现场锚点（端点实测、页面实际内容）与任何文档/记忆/任务书冲突时，以现场为准，双源复核（公网 + 服务器侧）后再下结论。单一来源 grep 0 = 假阴性候选。

---
name: safe-scout
description: Use when the agent backend runs on a content-moderated model provider (China relays: Bailian/DashScope, others with safety inspection) and the task involves fetching arbitrary external text (web pages, GitHub READMEs, search results) — or when a session starts failing every request with 400 content-inspection errors. Triggers: DataInspectionFailed, content-policy 400 loops, 调研外部文本, 抓网页, 读 README, 会话一直报错.
---

# safe-scout · 调研任务保险协议

> 用内容审查型模型后端（百炼等国产接力）做调研任务时的防污染+救援协议。方法来自真实会话报废事故的复盘。

## 机制（三句话）

1. Claude Code 类 agent **每次请求重发完整对话历史**
2. 审查型 provider 对输入做**概率性语义审查**——同一段内容这次过、下次可能不过
3. 任意一段外部文本中招 → 该请求失败，且历史永久携带它 → **之后每个请求都失败，整个会话报废**

理解这三条，下面所有动作才有意义。

---

## 事前：隔离协议（调研任务默认动作）

### 1. 落盘优先

外部输出（搜索结果/网页/README/issue）**一律重定向到临时文件**，不进主会话上下文：

```bash
gh search repos "关键词" --json fullName,stargazersCount,description > /tmp/scout_1.json
curl -s URL -o /tmp/page.html
```

### 2. 安全字段提取

从落盘文件里只提取**结构化字段**进上下文，绝不提取 description/正文全文：

```bash
jq -r '.[] | [.fullName, .stargazersCount, .pushed_at, (.license.spdx_id // "?")] | @tsv' /tmp/scout_1.json
```

能力判断用模型自有知识补，不确定标"待确认"。

### 3. 子 agent 隔离

必须读全文时（README/长文），**派子 agent 读**，只让它返回结构化结论；并要求它每步结论落盘保底。子 agent 中招阵亡 = 主会话无恙 + 部分结果在盘上。

### 4. 主会话摄取自检

任何外部文本进主会话前问一句：**这来源可信干净吗？** 官方文档/自己写的可以读；UGC/任意第三方文本走 1-3。

---

## 事中：错误签名识别

| Provider | 签名 | 含义 |
|---|---|---|
| 百炼/DashScope | `400 InvalidParameter ... DataInspectionFailed` | 输入命中内容审查 |
| 通用 | 400 + `content policy / safety / inappropriate content` 类措辞 | 同类机制 |

**识别要点**：同一会话内连续多个不同请求报同类 400 = 会话已污染（不是偶发网络/参数错误）。

---

## 事后：救援决策树

中招后按顺序执行，**第一步是停止重试**（重试无效，只会往历史里塞更多错误文本）：

1. **停重试**。把当前进度立即落盘（文件/记忆/任务清单）
2. **试 `/compact`**：历史压成摘要 = 洗上下文。压缩后发一条探测请求
3. 探测通过 → 继续干活；探测仍失败 → **弃会话**
4. 弃会话不等于丢工作：新会话读落盘文件续上，损失 = 对话记忆，不是工作成果
5. 复盘：找出污染文本是哪段（对照落盘文件），下次该来源走隔离协议

---

## 红线

- 不把 UGC/任意第三方全文读进主会话
- 中招后不连环重试
- 子 agent 任务必须带落盘保底
- 长任务中间结果随时落盘——没中招也是好习惯

## 质检（调研任务结束前）

- [ ] 外部全文进过主会话吗？进过的来源干净吗？
- [ ] 中间结果在盘上有备份吗？
- [ ] 给用户的结论里，事实与"待确认"分开标了吗？

<div align="center">

**中文** · [English](./README_EN.md)

# 🧰 migu_skill

#### 小黑 × 冰糖 每天真实在用的 Agent Skill，蒸馏后开源在这里

[![License](https://img.shields.io/badge/License-MIT-3B82F6?style=for-the-badge)](./LICENSE)
[![Skills](https://img.shields.io/badge/Skills-1-10B981?style=for-the-badge)](#-skills)
[![AgentSkills](https://img.shields.io/badge/AgentSkills-Standard-8B5CF6?style=for-the-badge)](https://agentskills.io)

![Claude Code](https://img.shields.io/badge/Claude_Code-Skill-D97706?style=flat-square&logo=anthropic&logoColor=white)
![Codex](https://img.shields.io/badge/Codex-Skill-10B981?style=flat-square&logo=openai&logoColor=white)

</div>

不是提示词合集。每个 skill 都在真实协作里用过、验证过，再按第一原理审一遍，**蒸馏掉冗余才入库**——宁缺毋滥。

遵循 [Agent Skills](https://agentskills.io) 开放标准，Claude Code、Codex 等支持该标准的 Agent 都能装。

---

## 📋 目录

| 名字 | 一句话 |
|---|---|
| 🔭 [**hv-analysis（横纵分析法·蒸馏版）**](#-hv-analysis横纵分析法蒸馏版) | 想搞懂一个产品/项目/概念，丢给它，纵轴追历史、横轴追竞品，交叉出判断的深度调研报告 |

---

## 📦 安装方式

在 Claude Code、Codex 等支持 Agent Skills 的工具里，直接说：

```
帮我安装这个 skill：https://github.com/miguchn/migu_skill/tree/main/hv-analysis
```

Agent 会自己 clone 到对应目录，不用你操心路径。也可以手动：

```bash
ln -s $(pwd)/hv-analysis ~/.claude/skills/   # 软链，随仓库更新
# 或 cp -r hv-analysis ~/.claude/skills/
```

Agent 不支持 Skill 也没关系：把 `SKILL.md` 全文当项目规则文件或直接贴进对话，效果一致。

---

## ✨ Skills

<a id="-skills"></a>

<table>
<tr><td>

### 🔭 hv-analysis（横纵分析法·蒸馏版）

> *"纵向追时间深度，横向追同期广度，最终交汇出判断。"* —— 方法源自 [数字生命卡兹克](https://github.com/KKKKhazix/khazix-skills) 的开源横纵分析法，本仓库收录的是**蒸馏精简版**。

想搞懂一个产品 / 项目 / 技术 / 概念到底是怎么回事，丢给它就行。纵轴从诞生讲到当下、追出路径依赖；横轴把同期竞品摆上同一组维度对比；两轴交叉，给出未来路径和预警信号。全程带**证据硬规则**：一手来源优先、来源标日期、事实/推断/观点三分离、查不到就写"暂未核实"——防幻觉是这套方法的命。

**我们蒸馏了什么**

- 原版纵轴与综合阶段重复追问路径依赖 → 合并，一次问透
- "未来 3 条路径"硬凑 → 1-3 条视情况，不注水
- 10000-30000 字硬约束 → 深度分级：简单对象 2-5k 字，复杂对象上限 30k
- "详细分析"段复述表格 → 表外只写表里看不出的洞察，没有就省
- 补上原版缺失的执行层：定对象 → 收集信息 → 三阶段 → 出报告

**证据规则四条，一字未动。**

**适合**

- 技术选型 / 开源项目深调研 / 竞品分析 / 行业研究
- 写深度稿前的系统性素材准备

**不适合**

- 查个名词解释——杀鸡用牛刀
- 两个选项快速对比——直接问就行

**怎么触发**

```
研究一下 MoneyPrinterTurbo 这个项目
帮我做个竞品分析
这个产品到底是怎么回事
用横纵分析法调研一下
```

→ [SKILL.md](./hv-analysis/SKILL.md)

</td></tr>
</table>

---

## 🌟 关于

小黑：保险行业产品经理，全栈折腾爱好者。冰糖：他的 AI 搭档。

这个仓库是我们协作的副产品——skill 先在自己的工作流里跑通、审过、精简过，才搬出来。对你有帮助的话，给个 ⭐ 就行。

收录标准：① 真实用过验证有效 ② 第一原理审查、冗余已精简 ③ 单文件无外部依赖。

---

<div align="center">

[MIT License](./LICENSE) · 自由使用 / 修改 / 再分发

Made by 小黑 × 冰糖

</div>

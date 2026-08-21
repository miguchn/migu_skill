<div align="center">

[中文](./README.md) · **English**

# 🧰 migu_skill

#### The Agent Skills actually used and open-sourced by the WeChat blog 别动生产库 ("Don't Touch the Production DB") — reviewed and streamlined.

[![License](https://img.shields.io/badge/License-MIT-3B82F6?style=for-the-badge)](./LICENSE)
[![Skills](https://img.shields.io/badge/Skills-1-10B981?style=for-the-badge)](#-skills)
[![AgentSkills](https://img.shields.io/badge/AgentSkills-Standard-8B5CF6?style=for-the-badge)](https://agentskills.io)

![Claude Code](https://img.shields.io/badge/Claude_Code-Skill-D97706?style=flat-square&logo=anthropic&logoColor=white)
![Codex](https://img.shields.io/badge/Codex-Skill-10B981?style=flat-square&logo=openai&logoColor=white)

</div>

Not a prompt dump. Every skill here has been used and verified in real collaboration, then reviewed from first principles — **bloat streamlined away before it enters the repo**. Fewer, but sharper.

Follows the [Agent Skills](https://agentskills.io) open standard. Works with Claude Code, Codex, and any compatible agent.

---

## 📋 Skills at a glance

| Name | One-liner |
|---|---|
| 🔭 [**hv-analysis (streamlined)**](#hv-analysis) | Deep-research reports: vertical axis traces history, horizontal axis compares peers, the intersection yields judgment |

---

## 📦 Install

In Claude Code, Codex, or any Agent-Skills-compatible tool, just say:

```
Install this skill for me: https://github.com/miguchn/migu_skill/tree/main/hv-analysis
```

The agent clones it into the right place for you. Or manually:

```bash
ln -s $(pwd)/hv-analysis ~/.claude/skills/   # symlink, stays in sync
# or: cp -r hv-analysis ~/.claude/skills/
```

No skill support? Paste the `SKILL.md` content as project rules or straight into the chat — same effect.

---

## ✨ Skills

<a id="-skills"></a>

<table>
<tr><td>

<a id="hv-analysis"></a>

### 🔭 hv-analysis (streamlined)

> *"Vertical for depth in time, horizontal for breadth in peers — judgment emerges at the intersection."* — The method is borrowed from [Khazix's](https://github.com/KKKKhazix/khazix-skills) open-source Horizontal-Vertical Analysis. This repo ships a **streamlined adaptation of the original**.

Want to truly understand a product / project / technology / concept? Throw it in. The vertical axis tells its story from birth to now and traces path dependency; the horizontal axis lines up peers on one shared set of dimensions; the crossing yields future paths and early-warning signals. Guarded by **hard evidence rules**: primary sources first, claims dated, facts / inferences / opinions kept separate, and "unverified" stated plainly when evidence is missing — anti-hallucination is the lifeblood of this method.

**What we streamlined**

- Vertical and synthesis phases asked path dependency twice → merged, asked once
- "Exactly 3 future paths" padding → 1–3 as the case demands
- Hard 10k–30k char quota → depth tiers: 2–5k for simple subjects, 30k cap for complex ones
- "Detailed analysis" section restating the tables → table-external insights only, omitted when none
- Added the missing execution layer: scope the object → gather sources → three phases → report

**The four evidence rules: untouched.**

**Good for**

- Tech selection, open-source deep dives, competitive analysis, industry research
- Systematic material prep before long-form writing

**Not for**

- Looking up a definition — that's just a question
- Quick two-option comparison — just ask

**Trigger examples**

```
Research the MoneyPrinterTurbo project
Do a competitive analysis on this
What's the real story behind this product
Run an hv-analysis on X
```

→ [SKILL.md](./hv-analysis/SKILL.md)

</td></tr>
</table>

---

## 🌟 About

Maintained by the Chinese WeChat blog **别动生产库** (*"Don't Touch the Production DB"*) — AI tooling, engineering practice, and insurance-tech in the wild. Skills earn their place here only after running in our own workflow, passing review, and getting streamlined.

More AI × engineering content: search 「别动生产库」 on WeChat. If this helps, a ⭐ is appreciated.

Inclusion criteria: ① actually used and proven ② first-principles reviewed, redundancy removed ③ single-file, zero dependencies.

---

<div align="center">

[MIT License](./LICENSE) · use / modify / redistribute freely

Made by 别动生产库

</div>

<div align="center">

[中文](./README.md) · **English**

# 🧰 migu_skill

#### The Agent Skills actually used and open-sourced by the WeChat blog 别动生产库 ("Don't Touch the Production DB") — reviewed and streamlined.

[![License](https://img.shields.io/badge/License-MIT-3B82F6?style=for-the-badge)](./LICENSE)
[![Skills](https://img.shields.io/badge/Skills-2-10B981?style=for-the-badge)](#-skills)
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
| 🔭 [**hv-analysis (quick edition)**](#hv-analysis) | Throw in a product / project / concept — get a framework-level research report with real-time sources in 30-60 minutes |
| 🛡️ [**safe-scout (research insurance)**](#safe-scout) | Researching on content-moderated model backends without bricking your session: isolate before, recognize during, rescue after |

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

### 🔭 hv-analysis (quick edition)

> *"Vertical for depth in time, horizontal for breadth in peers — judgment emerges at the intersection."* — Method borrowed from [Khazix's](https://github.com/KKKKhazix/khazix-skills) open-source Horizontal-Vertical Analysis. The original ships 10k-30k-word PDF deep reports; **this edition is the lightweight-complete version: 30-60 minutes, structured Markdown, real-time sources** — small, but a full closed loop. For heavy reports, use the original.

Want to truly understand a product / project / technology / concept? Throw it in. The vertical axis tells its story from birth to now and traces path dependency; the horizontal axis lines up peers on one shared set of dimensions; the crossing yields future paths and early-warning signals. Guarded by **hard evidence rules**: primary sources first, claims dated, facts / inferences / opinions kept separate, and "unverified" stated plainly when evidence is missing — anti-hallucination is the lifeblood of this method.

**What's different here**

- **Lightweight but complete loop**: real-time search layer (two-track search lists + mandatory arXiv for academic subjects + primary-source priority + 12-month freshness hard rule) → dual-axis analysis → intersection judgment → structured Markdown delivery → 5-point QC, done in 30-60 minutes
- **Open-source subjects go through structured gh metadata** (stars / activity / license / releases) instead of README-reading — more noise-resistant, earned in our own scout-research practice
- Path dependency asked once on the vertical axis, never repeated at synthesis
- 1-3 future paths as the case demands, no padding
- Depth-tiered 2,000-8,000 words — simple subjects stay short

**Good for**

- Tech selection, open-source deep dives, competitive analysis, quick industry frameworks
- Systematic material prep before long-form writing

**Not for**

- Looking up a definition — that's just a question
- 10k-30k-word heavy PDF reports — that's the [original's](https://github.com/KKKKhazix/khazix-skills) job

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

<table>
<tr><td>

### 🛡️ safe-scout (research insurance)

> *"Not a single failed request — the whole session bricks. Unless you insured it beforehand."*

On content-moderated model backends (Bailian et al.), every request resends the full history, and inspection is probabilistic: one poisoned external text means every request after fails with 400 — session bricked. This skill turns protocols earned from a real bricking incident into a closed loop:

**Before (default)**: external output lands on disk first; jq extracts only safe fields; full-text reading goes to subagents; a dead subagent leaves the main session untouched

**During**: error-signature table (DataInspectionFailed et al.) + "consecutive same-class 400s = poisoned" rule

**After**: stop retrying → save progress → `/compact` to launder context → probe → if still failing, abandon session and resume from disk; loss = zero

**Good for**

- Anyone running Claude Code-class agents on Chinese model relays
- Any heavy research task that fetches pages / reads READMEs / scrapes search results

**Not for**

- Direct, non-moderated backends (Anthropic official etc.) — no such pain

→ [SKILL.md](./safe-scout/SKILL.md)

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

<div align="center">

[中文](./README.md) · **English**

# 🧰 migu_skill

#### The Agent Skills actually used and open-sourced by the WeChat blog 别动生产库 ("Don't Touch the Production DB") — reviewed and streamlined.

[![License](https://img.shields.io/badge/License-MIT-3B82F6?style=for-the-badge)](./LICENSE)
[![Skills](https://img.shields.io/badge/Skills-5-10B981?style=for-the-badge)](#-skills)
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
| 🎨 [**minimal-paper-cover**](#minimal-paper-cover) | Distill a photo or theme into a paper-textured cover with a tiny subject, generous white space, and bold acrylic color blocks |
| 🏅 [**photo-travel-badge**](#photo-travel-badge) | Preserve a travel photo's subject, supporting context, and landmark text in a physically rendered gold-metal enamel badge |
| 🎨 [**palette-postcard**](#palette-postcard) | Give each travel photo its own collectible study page combining the source photo, selective watercolor, archive text, and three source-derived swatches |

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

<a id="minimal-paper-cover"></a>

### 🎨 minimal-paper-cover

> *“Lines suggest; color blocks make the image.”*

Extracts the most recognizable subject, gesture, and spatial relationship from a photo or theme, strips away realistic detail, and rebuilds the image with delicate hand-drawn lines and 2-4 bold acrylic colors. The subject stays at roughly 10%-20% of the canvas; rough white paper and open space create a quiet, restrained, playful cover illustration.

**Good for**

- Turning travel photos, portraits, buildings, or everyday objects into minimal cover art
- Creating a paper-textured, hand-painted, highly distilled visual from a theme

**Not for**

- Faithful reproduction, photo-to-line-art conversion, or detailed full-frame scenes
- Watercolor, colored pencil, crayon, heavy oil paint, 3D, or glossy commercial illustration

**Trigger examples**

```
Turn this photo into a minimal paper-textured cover
Create a tiny-subject acrylic illustration about waiting for a bus in the rain
把这张照片画成极简纸感封面
```

→ [SKILL.md](./minimal-paper-cover/SKILL.md)

</td></tr>
</table>

<table>
<tr><td>

<a id="photo-travel-badge"></a>

### 🏅 photo-travel-badge

> *“Distillation does not isolate the subject; it preserves the relationships that make the place recognizable.”*

Finds the most memorable visual subject in a travel photo, keeps the supporting context, representative colors, and identity-bearing source text that make it recognizable, then redesigns the result as a physical souvenir badge with a warm-gold metal edge, subtle relief, and enamel fills. The output uses a spacious 3:2 layout, a small centered subject, and a harmonious dark coarse-linen background. When requested, a place name, year, or short phrase becomes a restrained finishing element at the bottom.

**Example**

Generated badge above, original travel photo below.

![photo-travel-badge generated Jiefang Pavilion badge and source photo](./assets/photo-travel-badge/jiefangge-before-after.jpg)

**Good for**

- Turning travel photos, landmark buildings, city installations, or distinctive scenery into collectible enamel badges
- Preserving the subject's supporting context and landmark text, with optional commemorative text at the bottom

**Not for**

- Flat stickers, 2D vector logos, or ordinary outlined icons
- Full photorealistic scene recreation, cartoons, or full-bleed compositions

**Trigger examples**

```
Turn this travel photo into a gold-metal enamel souvenir badge
Keep the landmark and necessary context, and add JI NAN at the bottom
把这张旅行照做成金属珐琅纪念徽章
```

→ [SKILL.md](./photo-travel-badge/SKILL.md)

</td></tr>
</table>

<table>
<tr><td>

<a id="palette-postcard"></a>

### 🎨 palette-postcard

> *“The photograph preserves the place; the watercolor preserves the memory.”*

Turns every travel photo into a separate 2:3 portrait observation page: a high-fidelity source-photo panel at the top, a lighter selective watercolor study of the same scene below, restrained travel-archive typography, and exactly three hand-painted swatches re-extracted from the current photo. Each page is generated as one complete image, without code compositing or multi-photo layouts.

**Example**

One-pass final result using a snow-covered corner-tower photograph.

<p align="center">
  <img src="./assets/palette-postcard/winter-mirror-palette-postcard.png" alt="palette-postcard WINTER MIRROR corner-tower test result" width="420">
</p>

**Good for**

- Turning travel photos, architecture, landscapes, street scenes, people, or travel objects into collectible watercolor field-note pages
- Keeping paper and editorial structure consistent across a series while deriving the watercolor study and palette independently for every photo

**Not for**

- Generic watercolor filters, photorealistic watercolor copies, or ordinary color-palette infographics
- Multi-photo collages, pixel-exact source-photo layouts, code compositing, or decoration-heavy posters

**Trigger examples**

```
Use palette-postcard on these travel photos
Keep the source photo at the top and add a selective watercolor study with exactly three source-derived swatches
用 palette-postcard 处理这些旅行照片
```

→ [SKILL.md](./palette-postcard/SKILL.md)

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

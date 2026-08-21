# migu_skill

An open-source Agent Skills collection by Miguchn × Bingtang (冰糖).

**Positioning**: skills that have been **actually used, verified, and distilled** in real collaboration — not a prompt dump. Every skill passes a first-principles review and gets its bloat removed before entering this repo.

## Skills

| Skill | Description |
|---|---|
| [hv-analysis](hv-analysis/SKILL.md) | Horizontal-Vertical Analysis: a deep-research report generator (vertical history × horizontal comparison × evidence rules against hallucination) |

## Install

Works with Claude Code, Codex, and any [Agent Skills](https://agentskills.io)-compatible agent:

```bash
# Option 1: symlink (recommended, stays in sync with the repo)
ln -s $(pwd)/hv-analysis ~/.claude/skills/

# Option 2: copy
cp -r hv-analysis ~/.claude/skills/
```

## Inclusion criteria

1. Actually used and proven effective in real work
2. Reviewed from first principles; redundancy removed
3. Single-file, zero external dependencies

## License

[MIT](LICENSE)

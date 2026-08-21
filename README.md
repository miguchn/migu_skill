# migu_skill

小黑 × 冰糖 的开源 Agent Skills 合集。

**定位**：真实协作中**用过、验证过、精简过**的 skill 仓库——不是提示词合集，每个 skill 都经过第一原理审查，去掉冗余后才入库。

## 收录

| Skill | 说明 |
|---|---|
| [hv-analysis](hv-analysis/SKILL.md) | 横纵分析法：深度调研报告生成器（纵轴历史 × 横轴竞品 × 证据规则防幻觉） |

## 安装

适用于 Claude Code / Codex 及任何支持 [Agent Skills](https://agentskills.io) 的 agent：

```bash
# 方式一：软链（推荐，随仓库更新）
ln -s $(pwd)/hv-analysis ~/.claude/skills/

# 方式二：拷贝
cp -r hv-analysis ~/.claude/skills/
```

## 收录标准

1. 真实用过、验证有效
2. 第一原理审查过，冗余已精简
3. 单文件可用、无外部依赖

## License

[MIT](LICENSE)

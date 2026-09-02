# Silver Skills

`BingliSilver` 维护的可复用 Agent Skills。目前包含会话知识沉淀、知识文档归并和会话文件变更报告等技能。

Repository: [github.com/BingliSilver/silver-skills](https://github.com/BingliSilver/silver-skills)

## Skills

| Skill | 用途 |
| --- | --- |
| [learning-summary](skills/learning-summary/SKILL.md) | 将当前技术会话提炼为脱离具体项目也能独立阅读的通用知识 Markdown 文档。 |
| [knowledge-consolidate](skills/knowledge-consolidate/SKILL.md) | 将多篇零散知识文档去重、归类并归并到一篇高信息密度的 Markdown 文档。 |
| [report-file-changes](skills/report-file-changes/SKILL.md) | 跟踪本地写入任务实际新增或变更的文件，并在任务完成时报告绝对路径。 |

`knowledge-consolidate` 与 `learning-summary` 配套使用，建议同时安装。

## Installation

交互式选择技能和目标 Agent：

```powershell
npx skills@latest add BingliSilver/silver-skills
```

将全部技能全局安装到 Codex：

```powershell
npx skills@latest add BingliSilver/silver-skills --global --agent codex --skill learning-summary knowledge-consolidate report-file-changes
```

只安装单个技能：

```powershell
npx skills@latest add BingliSilver/silver-skills --global --agent codex --skill learning-summary
```

## Local Validation

在仓库根目录检查 CLI 能发现的技能：

```powershell
npx skills@latest add . --list
```

## Usage

```text
$learning-summary 将当前技术会话沉淀为通用知识文档
```

```text
$knowledge-consolidate 归并目标知识目录中的零散 Markdown
```

```text
$report-file-changes 跟踪并报告当前任务实际新增或变更的文件
```

## Repository Layout

```text
silver-skills/
├── README.md
└── skills/
    ├── learning-summary/
    │   ├── SKILL.md
    │   └── agents/
    │       └── openai.yaml
    ├── knowledge-consolidate/
    │   ├── SKILL.md
    │   └── agents/
    │       └── openai.yaml
    └── report-file-changes/
        ├── SKILL.md
        └── agents/
            └── openai.yaml
```

每个技能都以 `SKILL.md` 作为入口，并可通过 `agents/openai.yaml` 提供 Codex UI 元数据。

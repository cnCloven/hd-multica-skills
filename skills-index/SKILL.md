---
name: skills-index
description: "【技能目录】XTOOL-HD 看板技能索引。外接 agent 从 Multica Skills 面板获取安装信息：读正文映射表，按中文名拷对应目录到 .claude/skills/。不要把本文件当创建项目或创建任务的执行步骤。不要用于 Multica 内置智能体。"
---

# 技能目录

源仓：https://github.com/cnCloven/hd-multica-skills

本文件只提供目录和安装信息。业务步骤只在各目录的 `SKILL.md`。禁止把本机盘符、密钥写回看板。不要点「添加到智能体」。

## 映射（外接 agent 按中文名查）

| 中文名 | 目录 | 安装到 | 面板「描述」 |
| --- | --- | --- | --- |
| 技能目录 | `skills-index` | 不必装到 `.claude/skills/` | 见下方「技能目录」行 |
| 创建项目 | `multica-create-project` | `.claude/skills/multica-create-project/` | 见下方「创建项目」行 |
| 创建任务 | `multica-create-task` | `.claude/skills/multica-create-task/` | 见下方「创建任务」行 |

## 面板怎么填（工作区 XTOOL-HD）

列表要同时有一条目录和两条业务行。业务行**手动创建**，不要从业务目录 URL 导入（导入会带上 YAML 英文 `name` 和长 description，把安装信息冲掉）。目录行可导入 `.../tree/main/skills-index`，导入后把名称改成「技能目录」；DNS 失败则手动创建，正文贴本文件正文。

### 技能目录

- 名称：`技能目录`
- 描述：

```text
repo: https://github.com/cnCloven/hd-multica-skills
```

- 正文：本文件正文（从「源仓」起）

### 创建项目

- 名称：`创建项目`
- 描述：

```text
repo: https://github.com/cnCloven/hd-multica-skills
dir: multica-create-project
```

- 正文：

```text
不要用本文件当执行步骤。

repo: https://github.com/cnCloven/hd-multica-skills
dir: multica-create-project
url: https://github.com/cnCloven/hd-multica-skills/tree/main/multica-create-project

安装：clone 源仓后只拷 dir 到 .claude/skills/multica-create-project/
执行：加载该目录的 SKILL.md。
```

### 创建任务

- 名称：`创建任务`
- 描述：

```text
repo: https://github.com/cnCloven/hd-multica-skills
dir: multica-create-task
```

- 正文：

```text
不要用本文件当执行步骤。

repo: https://github.com/cnCloven/hd-multica-skills
dir: multica-create-task
url: https://github.com/cnCloven/hd-multica-skills/tree/main/multica-create-task

安装：clone 源仓后只拷 dir 到 .claude/skills/multica-create-task/
执行：加载该目录的 SKILL.md。
```

## 外接 agent 怎么用面板

1. 打开 http://172.16.0.67:3000/test/skills
2. 先点「技能目录」读本表；或直接点中文业务名
3. 用描述里的 `repo` + `dir` 安装，不要猜目录
4. 只拷业务目录，不要拷 `skills-index` 当可执行 skill

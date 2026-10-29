# HD Multica Skills

XTOOL-HD 看板用的 Claude Code / CodeG skill 仓库。源文件在本仓库；网页版 Multica 的 Skills 页只当**索引**（目录 + 安装信息），不替代本仓库，也不给 Multica 内置智能体用。

## 中文名 ↔ 目录

| 中文名（面板「名称」） | 目录 | 安装到 | 面板「描述」 |
| --- | --- | --- | --- |
| 技能目录 | `skills-index/` | 不必装进 `.claude/skills/` | `repo: https://github.com/cnCloven/hd-multica-skills` |
| 创建项目 | `multica-create-project/` | `.claude/skills/multica-create-project/` | `repo: …hd-multica-skills` + `dir: multica-create-project` |
| 创建任务 | `multica-create-task/` | `.claude/skills/multica-create-task/` | `repo: …hd-multica-skills` + `dir: multica-create-task` |

每个业务目录根上必须有 `SKILL.md`。触发：`创建项目` / `建项目` / `/multica-create-project`；`创建任务` / `建任务` / `/multica-create-task`。

## 用到自己的 Claude Code

克隆后把**业务** skill 目录拷到下面任一位置（保持目录名和 `SKILL.md`）。不要拷 `skills-index`。

```text
<项目>/.claude/skills/<dir>/SKILL.md
%USERPROFILE%\.claude\skills\<dir>\SKILL.md
```

```powershell
git clone https://github.com/cnCloven/hd-multica-skills.git $env:USERPROFILE\src\hd-multica-skills
Copy-Item -Recurse $env:USERPROFILE\src\hd-multica-skills\multica-create-project $env:USERPROFILE\.claude\skills\multica-create-project
Copy-Item -Recurse $env:USERPROFILE\src\hd-multica-skills\multica-create-task $env:USERPROFILE\.claude\skills\multica-create-task
```

本机工作副本也可以放在 `D:\multicaws\.claude\skills\`（给打开 multicaws 的 Claude 用）。改 skill 先改本仓库，再拷回去。

## 网页当索引（工作区 XTOOL-HD）

打开 http://172.16.0.67:3000/test/skills 。列表同时有：

1. **技能目录** — 全量映射。可「从 URL 导入」`https://github.com/cnCloven/hd-multica-skills/tree/main/skills-index`，再把名称改成「技能目录」；导入失败则手动创建，正文用 `skills-index/SKILL.md`。
2. **创建项目**、**创建任务** — **手动创建**，不要从业务目录 URL 导入。名称用汉字；描述只写 `repo` + `dir` 两行；正文只写安装指针，不要贴业务步骤。

填写范本见 `skills-index/SKILL.md`。

- 导入/更新以 git 为准。业务步骤只改仓库里对应目录，不要改面板正文。
- 不要点 **添加到智能体**。
- 禁止把本机路径、密钥写入描述/正文。

## 上传自己的 skill

1. 新建目录 `<dir>/SKILL.md`（frontmatter `name` 与目录名一致，kebab-case）
2. 把中文名和 `dir` 加进本 README 和 `skills-index/SKILL.md` 映射表
3. 推 `main`
4. 看板上：更新「技能目录」；再手动建一行中文名，描述写 `repo` + `dir`

规范文档仍只在 `D:\multicaws` 写带时间戳的 md，禁止改 `D:\share`。

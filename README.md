# HD Multica Skills

XTOOL-HD 看板用的 Claude Code / CodeG skill 仓库。源文件在本仓库；网页版 Multica 的 Skills 页只当**索引**，不替代本仓库。

当前包含：

| Skill | 目录 | 触发 |
|--------|------|------|
| 创建项目 | `multica-create-project/` | `创建项目` / `建项目` / `/multica-create-project` |
| 创建任务 | `multica-create-task/` | `创建任务` / `建任务` / `/multica-create-task` |

每个目录根上必须有 `SKILL.md`。

## 用到自己的 Claude Code

克隆后把 skill 目录拷到下面任一位置（保持目录名和 `SKILL.md`）：

```text
<项目>/.claude/skills/<skill-name>/SKILL.md
%USERPROFILE%\.claude\skills\<skill-name>\SKILL.md
```

示例（PowerShell）：

```powershell
git clone https://github.com/cnCloven/hd-multica-skills.git $env:USERPROFILE\src\hd-multica-skills
Copy-Item -Recurse $env:USERPROFILE\src\hd-multica-skills\multica-create-project $env:USERPROFILE\.claude\skills\multica-create-project
Copy-Item -Recurse $env:USERPROFILE\src\hd-multica-skills\multica-create-task $env:USERPROFILE\.claude\skills\multica-create-task
```

本机工作副本也可以放在 `D:\multicaws\.claude\skills\`（给打开 multicaws 的 Claude 用）。改 skill 先改本仓库，再拷回去。

## 网页当索引（工作区 XTOOL-HD）

1. 打开 http://172.16.0.67:3000/test/skills
2. **新建 skill** → **从 URL 导入**
3. 每个 skill 单独导一次，URL 指向该目录，例如：
   - `https://github.com/cnCloven/hd-multica-skills/tree/main/multica-create-project`
   - `https://github.com/cnCloven/hd-multica-skills/tree/main/multica-create-task`
4. 导入后工作区能看见包；**不会**自动装进同事的 Claude Code。同事仍按上一节拷到 `.claude/skills/`。
5. 不要点 **添加到智能体**，除非明确要让 Multica 智能体代建单。

## 上传自己的 skill

1. 新建目录 `<skill-name>/SKILL.md`（frontmatter 含 `name`、`description`）
2. PR 或推到 `main`
3. 需要出现在看板索引时，再在网页 **从 URL 导入** 该目录

规范文档仍只在 `D:\multicaws` 写带时间戳的 md，禁止改 `D:\share`。

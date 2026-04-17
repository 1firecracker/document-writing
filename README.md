# document-writing (Agent Skill)

这是一个用于“文档编写规范化”的 Agent Skill。目标是把项目内文档（尤其是 `docs/` 体系、buglog/feature 记录、索引维护等）用一套固定流程与模板约束起来，减少随意性与重复沟通成本。

## 内容结构

- `SKILL.md`：Skill 入口（含 YAML frontmatter 与执行流程）
- `buglog-reference.md`：buglog 模板与规范（写 buglog 前必须阅读）
- `reference.md`：其他文档模板参考

## 安装与使用

### 在 Cursor 中使用（本项目风格）

把整个 `document-writing` 目录放到项目的：

- `.cursor/skills/document-writing/`

然后在对话中按约定触发/调用（例如用户明确要求“记录修复日志/写文档”时）。

### 在 Claude Code 中使用

Claude Code 约定的路径是：

- `~/.claude/skills/document-writing/SKILL.md`（个人全局）
- 或 `<repo>/.claude/skills/document-writing/SKILL.md`（项目级）

因此将本仓库内容复制到：

- `~/.claude/skills/document-writing/`

即可通过 `/document-writing` 调用（具体是否自动触发由 frontmatter 与 Claude Code 行为决定）。

### 在 Codex 中使用（推荐方式：AGENTS.md）

Codex 官方推荐用 `AGENTS.md` 承载项目级“长期指令/约定”。本仓库当前以 `SKILL.md` 为主；如需在 Codex 中获得同等效果，建议将 `SKILL.md` 的关键规则同步到目标项目根目录的 `AGENTS.md` 中（或全局 `~/.codex/AGENTS.md`）。

参考：`https://developers.openai.com/codex/guides/agents-md/`

## 更新

在目标环境中进入目录，执行：

```bash
git pull
```


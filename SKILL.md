---
name: document-writing
description: Standardizes project and user-facing document creation: workflow, storage under project root docs/, alignment with docs/文档索引.md. Use when the user asks to write docs, generate README/API/guide, or mentions docs directory or document standards. For buglog documents, MUST read buglog-reference.md first.
---

# 文档编写

## 存放规则

- 所有生成的文档必须放在**项目根目录**下的 `docs/` 目录。
- **分层与子目录以 [docs/文档索引.md](../../../docs/文档索引.md) 为准**。当前约定：
  - **根目录**：仅保留入口与索引（如 `agent-onboarding.md`、`文档索引.md`），不在此新增说明类文档。
  - **docs/spec/**：全局说明（存储、API、部署、知识库、文档引用等）；文件名可直接表意，如 `存储结构说明.md`、`API接口文档.md`。
  - **docs/design/**：设计稿、方案、行为约定；命名格式 `design-<主题>-<子主题>.md`（英文小写、连字符）。
  - **docs/archive/**：已归档汇报、历史计划、仅参考记录。
  - **docs/requirements/**：系统/产品需求。
  - **docs/tech_research/**：技术选型与调研；通常状态「仅参考」。
  - **docs/knowledge/**：领域知识、学习笔记、总结。
  - **docs/代码编写规范/**：代码风格与规范，入口 `README.md`。
  - **docs/buglog/**：Bug 修复记录；命名格式 `bug-<问题简述>.md`，记录现象、修复过程、结果。
  - **docs/feature/**：功能 / 特性更新记录；命名格式 `feature-<主题简述>.md`，用于记录功能迭代、行为变更、性能优化等（与 buglog 的缺陷修复区分开）。
  - **docs/题目生成模块研发文档/**：试题分析/题目生成相关阶段方案与设计；命名见文档索引 §2.3。
- 仅在用户明确要求生成文档时创建；不主动创建无用 md 文档。
- **新增或移动文档后**：在 `docs/文档索引.md` 的「文档索引表」中增加或修改对应一行（路径、用途简述、层级、状态）。

## 编写流程

1. **确定类型与受众**：项目文档（开发者/维护者）还是用户文档（使用说明）；对应选模板。
2. **确定落盘位置**：根据文档类型在 [docs/文档索引.md](../../../docs/文档索引.md) 的分层设计中选定子目录（spec / design / archive / requirements / tech_research / knowledge / 代码编写规范 / buglog / feature / 题目生成模块研发文档 等）。功能/特性或性能类改动优先考虑 `docs/feature/`，仅缺陷修复落在 `docs/buglog/`。
3. **选模板**：
   - 对于 buglog 文档：**必须先阅读** [buglog-reference.md](buglog-reference.md) 了解编写规范和模板
   - 对于其他文档：从 [reference.md](reference.md) 选用 README、API 说明、指南等模板，按需删减章节
   - 命名需符合文档索引中的约定（如 design 用 `design-xxx.md`，spec 可用中文表意，buglog 用 `bug-xxx.md`）
4. **写大纲**：先列一级/二级标题，再填内容。
5. **写正文**：按模板填空，保持术语与项目内现有文档一致、链接有效。
6. **检查**：完成下面清单后再落盘。
7. **落盘**：保存到 `docs/<子目录>/`（或根目录仅当新增入口/索引时）；**在 docs/文档索引.md 的索引表中补一行**。

## 完成前检查清单

- [ ] 路径在项目根下 `docs/` 或 `docs/<子目录>/`，且符合文档索引的分层约定
- [ ] 标题层级正确（单一 H1，H2/H3 有序）
- [ ] 内部链接、锚点可点击
- [ ] 术语与项目内现有文档一致
- [ ] 无占位符未替换（如 TODO、TBD）
- [ ] 已在 `docs/文档索引.md` 的索引表中登记（路径、用途简述、层级、状态）

## 模板与详细规范

- **Buglog 文档**：编写前**必须先阅读** [buglog-reference.md](buglog-reference.md)，了解 buglog 文档的编写规范、结构模板和内容要求
- **Feature 文档**：用于记录功能、交互或性能等特性级更新，命名使用 `feature-<主题简述>.md`，结构可参考 buglog / README 模板，按需要简化
- **其他文档**：各类文档的 Markdown 模板、命名示例见 [reference.md](reference.md)
- **子目录与命名约定**：以 [docs/文档索引.md](../../../docs/文档索引.md) 为准；若与 reference.md 中「目录结构约定」不一致，以文档索引为准

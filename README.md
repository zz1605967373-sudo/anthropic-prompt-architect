# 🏛️ Anthropic Prompt Architect (Metaprompt & Audit Engine)

> 基于 Anthropic 官方体系（**Metaprompt** + **Prompt Audit** + **Prompt Caching** + **Skill Creator**）构建的工业级 Prompt 架构与工程化 Skill。

[![License: Apache 2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Official Anthropic Compliant](https://img.shields.io/badge/Anthropic-Prompt_Standard-orange.svg)](https://github.com/anthropics/skills)

---

## 📖 项目简介

在大模型提示词工程中，简单的“八股文模板”往往会导致过度工程化（Over-engineering）与输出僵化。
本项目严格汲取 Anthropic 官方在开源社区中的四大核心资产：
1. **[Metaprompt](https://github.com/anthropics/claude-cookbooks/blob/main/misc/metaprompt.ipynb)**：解决“空白页困境”，通过自适应编译器将口语任务编译为生产级 Prompt；
2. **[Prompt Audit](https://github.com/anthropics/skills/blob/main/skills/claude-api/shared/prompt-audit.md)**：落实 *"Every token earns its place"* 准则，剔除情绪胁迫、微观死板脚本与过时脚手架；
3. **[Prompt Caching](https://github.com/anthropics/skills/blob/main/skills/claude-api/shared/prompt-caching.md)**：三层缓存断点物理架构，实现最高 90% 降本与 80% 降延迟；
4. **[Skill Creator](https://github.com/anthropics/skills/tree/main/skills/skill-creator)**：标准 Agent Skill 协议与端到端自动化评测体系。

---

## ⚡ 四大工作模式

| 模式 | 指令 | 作用与核心逻辑 |
| :--- | :--- | :--- |
| **模式 1** | /generate | **从零构建**：根据口语化需求，自适应生成带有 XML 标签包裹、变量注入与 Scratchpad 推演的高级 Prompt。 |
| **模式 2** | /audit | **审计与重构**：扫描存量 Prompt 中的空泛词、陈旧模式、死板脚本，输出诊断报告与干净的重构 Diff。 |
| **模式 3** | /cache | **缓存分层优化**：将长文本 Prompt 拆分为静态系统层、参考资料层与动态入参层，精准打上缓存断点。 |
| **模式 4** | /eval | **评测集生成**：自动合成标准用例、边界用例与防注入对抗用例，验证 Prompt 鲁棒性。 |

---

## 🚀 快速上手与安装

### 在 Antigravity 或 Claude Agent 环境中使用：
只需将本仓库克隆或将 [SKILL.md](./SKILL.md) 放入您的技能目录：

`ash
# 工作区级安装（推荐）
mkdir -p .agents/skills/anthropic-prompt-architect
cp SKILL.md .agents/skills/anthropic-prompt-architect/
`

### 文档导航
* 核心技能定义：[SKILL.md](./SKILL.md)
* 架构设计蓝本：[lueprint.md](./blueprint.md)
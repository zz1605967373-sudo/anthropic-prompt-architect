# 🏛️ Anthropic Prompt Architect (Metaprompt, Audit & Caching Engine)

> 基于 Anthropic 官方体系（**Metaprompt** + **Prompt Improver** + **Prompt Audit** + **Prompt Caching** + **Extended Thinking**）构建的工业级 Prompt 架构与工程化 Skill。

[![License: Apache 2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Official Anthropic Compliant](https://img.shields.io/badge/Anthropic-Prompt_Standard-orange.svg)](https://github.com/anthropics/skills)
[![Cache Aligned](https://img.shields.io/badge/Prompt_Caching-Aligned_Topology-green.svg)](https://docs.anthropic.com/en/docs/build-with-claude/prompt-caching)

---

## 📖 项目简介

在大模型提示词工程中，简单的“八股文模板”往往会导致过度工程化（Over-engineering）与输出僵化。
本项目为 Claude 3.5 / 3.7 / Opus / Sonnet 全系列量身打造，融合 Anthropic 官方在开源社区中的核心工程方法论：

1. **预编译分流（Pre-Compilation Triage）**：按 *Light* / *Medium* / *Heavy* 三级自适应匹配复杂度，杜绝小任务杀鸡用牛刀；
2. **缓存对齐拓扑（Cache-Aligned Topology）**：静态规则与长文本前置，动态运行时变量置底，实现 **100% 提示词物理缓存命中（降本 90%）**；
3. **原生 Extended Thinking 与 <scratchpad> 解耦**：自适应识别是否开启 API 级原生推理，避免重复冗余思考；
4. **Prompt Audit 剪枝诊断**：识别并剔除情绪胁迫、微观死板脚本与缓存破坏行为；
5. **完整 API 集成建议**：提供 System/User 划分、Assistant Prefill 预填建议与温度推荐。

---

## ⚡ 四大核心工作模式

| 模式 | 触发指令 | 作用与核心机制 |
| :--- | :--- | :--- |
| **模式 1** | /generate | **从零构建**：自适应判定复杂度，编译带有 XML 标签包裹、长上下文置顶与推演机制的高鲁棒性 Prompt。 |
| **模式 2** | /audit | **过时审计与重构**：扫描存量 Prompt 中的空泛词、陈旧脚本、缓存破坏行为，输出诊断报告与干净重构 Diff。 |
| **模式 3** | /cache | **缓存架构物理分层**：将 Prompt 严格划分为静态系统层、参考资料层与动态入参层，精准打上缓存断点。 |
| **模式 4** | /eval | **评测集自动合成**：自动生成标准黄金用例、边界降级用例与防注入对抗用例，全面验证鲁棒性。 |

---

## 🚀 快速上手与安装

### 在 Antigravity 或 Claude Agent 环境中使用：
只需将本仓库克隆或将 [SKILL.md](./SKILL.md) 放入您的技能目录：

`ash
# 工作区级安装（推荐）
mkdir -p .agents/skills/anthropic-prompt-architect
cp SKILL.md .agents/skills/anthropic-prompt-architect/
`

### 目录与文档
* 核心技能定义：[SKILL.md](./SKILL.md)
* 架构设计蓝本：[lueprint.md](./blueprint.md)
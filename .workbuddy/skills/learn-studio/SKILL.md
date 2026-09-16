---
name: learn-studio
description: This skill should be used when the user wants to learn a concept in "guide mode" (讲解模式) — a guided explanation that walks through what something is, how its core is designed, the operational flow, and (when applicable) the specific implementation in WorkBuddy or another named system. Produces a structured concept guide following the fixed six-section template (01 它是什么 → 02 核心设计 → 03 运行主线 → 04 [系统名] 设计 → 05 铁律 → 06 溯源 → 07 自测). Use this when the user asks "用 guide 模式讲解 X", "请讲解 X 的 Y 系统", "explain X in guide mode", or wants a polished concept-learning artifact rather than a quick answer.
agent_created: true
---

# learn-studio · Guide Mode 概念讲解 Skill

按 **固定六节 + 可选三段** 的模板，把任意概念讲透。这套模式兼顾"通用概念解释"和"指定系统的具体设计"，是非代码类知识点的首选讲解方式。

## 适用场景

- 用户说 "用 guide 模式讲解 X" / "讲解 X 的 Y 系统" / "explain X in guide mode"
- 用户给出概念名 + 可选系统名（如 "agent 的记忆系统，先讲通用再讲 WorkBuddy 的设计"）
- 用户希望得到一份**可保存的概念讲解文档**（不是聊天对话）

## 不适用

- 需要一对一对话引导的场景（用 `guided-concept-learning`）
- 只想查定义或写参考式资料（用 `concept-learning-skill`）
- 代码/工具类知识（直接文档更适合）

## 输入

- **必填**：概念名（如 "agent 记忆系统"、"RAG"、"transformer 注意力"）
- **可选**：指定系统名（如 "WorkBuddy"、"Anthropic"、"LangGraph"），用于第 04 节的具体设计
- **可选**：读者深度（入门 / 进阶），影响术语密度

## 生成流程

1. 拆题：把概念分解为"通用理论 + 具体实现"两层
2. 联网检索（≥2 个独立来源）：
   - 通用层：维基百科 / 综述博客 / 学术论文
   - 实现层：官方文档 / 设计博客 / 源码
3. 按模板撰写 7 节（4 固定 + 3 可选）
4. 自检：术语首次出现必须解释；每个对比表 ≥ 2 行；溯源 ≥ 3 条
5. 输出为 Markdown（默认）或 HTML（用户指定）

## 输出结构

按 `references/concept-guide.md` 中的固定模板。详见 reference。

## 与其他 Skill 的分工

| Skill | 定位 | 产出 |
|-------|------|------|
| `learn-studio`（本） | 概念讲解（guide 模式） | 单篇结构化讲解文档 |
| `guided-concept-learning` | 引导式教学 | 一组概念的交互材料 |
| `concept-learning-skill` | 参考式资料 | 五板块查漏补缺文档 |

## 文件

- `SKILL.md`（本文件）
- `references/concept-guide.md` —— 83 行的固定讲解模板
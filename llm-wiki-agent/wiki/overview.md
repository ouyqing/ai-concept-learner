# Overview — Living Synthesis

> 这一页是 wiki 的活文档：每次 ingest 后审视一次，根据需要增删调整。它不是事实表，而是"我们目前对这一领域的判断"。

## 当前主题：AI Agent 工程化与 Python 入门

这一批资料覆盖两条主线：

### 主线一：AI Agent 工程化
围绕"如何让 LLM 真正做事"展开：
- **Agent**（智能体）—— 把语言能力和做事能力缝合起来的系统类
- **AgentMemory** —— 让 Agent 突破上下文窗口限制、跨会话保持一致
- **AgentMemorySystem** —— 把记忆做成可维护管线
- **AgentSkill** —— 把工作流打包成可复用单元
- **ContextWindow** —— LLM 的硬约束，与"记忆"互补
- **LLMWikiAgent** —— 用 Agent 模式实现的本地知识库

它们之间的关系：Agent 是主体 → ContextWindow 是工作台 → Memory 是外接硬盘 → Skill 是岗位手册 → LLMWikiAgent 是这套思想的实践样本。

### 主线二：Python 入门（为统计学习打底）
- **PythonBasics** —— 变量、类型、f-string
- **PythonContainers** —— list/tuple/dict/set

后续计划：流程控制、函数与模块、数据读写与 pandas。

## 当前判断与假设
- **记忆是 Agent 体验的核心瓶颈**：模型能力相近时，记忆设计决定产品差异
- **Skill 化是工程化的关键方向**：把工作流沉淀为可复用资产
- **窗口≠无限**：Lost in the Middle 提醒我们 RAG 仍是必要的

## 数据缺口
- Agent Memory 缺少主流框架对比（Mem0 / LangGraph Memory / Zep）
- Skill 缺少企业级落地案例
- Python 教程后续章节（流程控制、函数、pandas）尚未入档

## 最近更新
- 2026-09-16：首批 8 份概念资料入档
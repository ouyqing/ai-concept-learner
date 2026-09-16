---
title: "Agent"
type: concept
tags: [ai-agent, autonomous, planning, tool-use]
sources: [agent.md, agent-skills.md, agent-memory.md]
last_updated: 2026-09-16
---

## 定义
Agent（智能体）是<strong>把大模型的"语言能力"和"做事能力"缝合起来的一类系统</strong>，由四大组件构成：规划、记忆、工具、行动，并以 ReAct（Reason→Act→Observe）循环为核心范式。

## 核心要素
- **规划**：把目标拆成子任务
- **记忆**：短期上下文 + 长期事实
- **工具**：调用外部 API / 文件 / 代码
- **行动**：执行决定并反馈

## 何时使用 Agent
适合：可拆解、有可用工具的确定性多步任务（订餐、查询、写报告、数据分析）。
不适合：纯开放任务（如"做一家公司"）、纯对话场景（普通 LLM 即可）。

## 来源
- [Agent — Source](sources/agent.md)
- [Agent Skills — Source](sources/agent-skills.md)
- [Agent Memory — Source](sources/agent-memory.md)
- [Anthropic: Building Effective Agents](https://www.anthropic.com/research/building-effective-agents)
- [Lilian Weng: LLM Powered Autonomous Agents](https://lilianweng.github.io/posts/2023-06-23-agent/)
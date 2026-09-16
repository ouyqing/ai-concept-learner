---
title: "Agent Memory — Source"
type: source
tags: [ai-agent, memory, context-engineering, rag, long-term]
date: 2026-09-16
source_file: raw/agent-memory.html
last_updated: 2026-09-16
---

## Summary
概念学习资料《Agent Memory（智能体记忆）》。解释短期/长期、情景/语义/程序性三时间尺度的记忆分类，以及"抽取→分类→写入→检索→遗忘"的工程管线。

## Key Claims
- 记忆解决"上下文窗口有限"导致的一致性问题
- 长期记忆 ≠ RAG：RAG 从文档库检索，记忆从"关于用户/自身的事实库"检索
- 记忆 ≠ 微调：微调改参数，记忆改输入

## Key Quotes
> "记忆会带来噪声与无关信息，反而干扰判断。"

## Connections
- [[AgentMemory]] — 概念页
- [[AgentMemorySystem]] — 进阶架构
- [[ContextWindow]] — 记忆是窗口的"外接硬盘"
- [[Agent]] — Agent 的关键子系统

## Contradictions
- 无已知矛盾
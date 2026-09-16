---
title: "Agent Memory System — Source"
type: source
tags: [ai-agent, memory, architecture, pipeline, ops]
date: 2026-09-16
source_file: raw/agent-memory-system.html
last_updated: 2026-09-16
---

## Summary
概念学习资料《Agent Memory System（记忆系统架构）》。把记忆分成事实/事件/语义/程序四类，并给出五步管线：抽取→分类→写入→检索→遗忘。

## Key Claims
- Memory System ≠ Database：前者关心"取舍"，后者关心"存取效率"
- 写入噪声不抽取会让检索命中率骤降
- 多 Agent 共享 memory bus 是经验沉淀的关键

## Key Quotes
> "没有取舍机制的记忆库会越长越杂，最终像没整理过的邮箱一样难用。"

## Connections
- [[AgentMemory]] — 与本资料同主题不同层次
- [[LLMWikiAgent]] — 体现了"四类记忆 + 管线"的实践
- [[Agent]] — Agent 子系统架构

## Contradictions
- 无已知矛盾
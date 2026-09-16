---
title: "Agent — Source"
type: source
tags: [ai-agent, autonomous, planning, tool-use, memory]
date: 2026-09-16
source_file: raw/agent.html
last_updated: 2026-09-16
---

## Summary
概念学习资料《Agent（智能体）》。把 LLM 与"做事能力"缝合起来的系统类，由规划、记忆、工具、行动四大组件构成，并以 ReAct 思考-行动-观察循环作为核心范式。

## Key Claims
- Agent 是 LLM + 工具 + 长期记忆 + 规划的组合，超越纯对话场景
- ReAct（Reason→Act→Observe）是核心循环范式
- 适合可拆解、有可用工具的确定性多步任务；不适合纯开放任务

## Key Quotes
> "Agent 是把'语言能力'和'做事能力'缝合起来的一类系统。"

## Connections
- [[Agent]] — 主体概念页
- [[ContextWindow]] — Agent 决策所需工作台
- [[AgentMemory]] — Agent 跨会话一致性的关键
- [[AgentSkill]] — Agent 的能力扩展单元
- [[LLMWikiAgent]] — LLM Wiki 是用 Agent 模式实现的个人知识库

## Contradictions
- 无已知矛盾
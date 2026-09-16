---
title: "LLM Wiki — Source"
type: source
tags: [llm, knowledge-base, agent, markdown, graph]
date: 2026-09-16
source_file: raw/llm-wiki.html
last_updated: 2026-09-16
---

## Summary
概念学习资料《LLM Wiki Agent（知识库代理）》。介绍由 Claude Code 维护的本地知识库系统：raw/ → wiki/ → graph/ 三层，五个工作流（ingest/query/health/lint/graph）。

## Key Claims
- LLM Wiki 是带索引的持久知识库（含 RAG 而不止 RAG）
- raw/ 不可变；wiki/ 由 LLM 维护；graph/ 自动生成
- health 是零 LLM 调用结构性检查，lint 用 LLM 做语义分析

## Key Quotes
> "LLM Wiki 是带索引的持久知识库（包含 RAG）。"

## Connections
- [[LLMWikiAgent]] — 概念页（与本仓库同名实例）
- [[AgentMemorySystem]] — LLM Wiki 是 Memory System 的实践参考

## Contradictions
- 无已知矛盾
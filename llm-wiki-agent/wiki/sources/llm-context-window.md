---
title: "LLM Context Window — Source"
type: source
tags: [llm, context-window, token, context-engineering]
date: 2026-09-16
source_file: raw/llm-context-window.html
last_updated: 2026-09-16
---

## Summary
概念学习资料《LLM Context Window（上下文窗口）》。解释 token 计量、窗口里装什么、当前主流模型的窗口大小，以及 Lost in the Middle 现象。

## Key Claims
- 窗口以 token 计量（汉字 ≈ 1-2 token，英文单词 ≈ 1-1.3 token）
- 当前主流大模型窗口在 1M token 量级
- 长上下文中段信息召回率显著下降（Lost in the Middle）
- 窗口大 ≠ 无需 RAG

## Key Quotes
> "窗口大 ≠ 模型能'有效用'窗口大。"

## Connections
- [[ContextWindow]] — 概念页
- [[AgentMemory]] — 记忆是窗口的"外接硬盘"
- [[Agent]] — Agent 任务的复杂度受窗口约束

## Contradictions
- 无已知矛盾
---
title: "ContextWindow"
type: concept
tags: [llm, context-window, token, context-engineering]
sources: [llm-context-window.md]
last_updated: 2026-09-16
---

## 定义
Context Window 是大模型一次对话能塞进的最大信息量，以 token 计量（汉字 ≈ 1-2 token，英文单词 ≈ 1-1.3 token）。它是 LLM 的<strong>硬约束</strong>。

## 窗口里装什么
- 系统提示词（人格、规则、工具说明）
- 历史对话
- 当前用户输入
- RAG 检索片段、工具调用结果

## 当前主流窗口
- Claude Sonnet 4：1M token
- GPT-4.1：1M token
- Gemini 2.5 Pro：1-2M token

## Lost in the Middle
窗口大 ≠ 模型能有效用。长上下文中段信息召回率显著下降，头尾记得牢、中间容易丢。

## 来源
- [LLM Context Window — Source](sources/llm-context-window.md)
- [Lost in the Middle — Liu et al.](https://arxiv.org/abs/2307.03172)
---
title: "AgentMemory"
type: concept
tags: [ai-agent, memory, long-term, context-engineering]
sources: [agent-memory.md, agent-memory-system.md]
last_updated: 2026-09-16
---

## 定义
Agent Memory 是<strong>让大模型突破上下文窗口限制、在多次会话中保持一致性的整套机制</strong>——既包括塞进提示词的短期记忆，也包括写入向量数据库或键值库的长期事实。

## 三时间尺度
| 类型 | 存什么 | 怎么用 |
|------|--------|--------|
| 短期 Working | 当前会话对话历史 | 直接拼进提示词 |
| 长期 Long-term | 用户偏好、过往结论 | 向量化后相似度检索 |
| 情景 / 语义 / 程序性 | 事件 / 概念 / 步骤 | 按需分类检索 |

## 与易混项
- **记忆 ≠ 上下文窗口**：窗口是临时内存，记忆是外接硬盘
- **记忆 ≠ RAG**：RAG 从文档库检索；记忆从"关于用户/自身的事实库"检索
- **记忆 ≠ 微调**：微调改参数，记忆改输入

## 工程要点
取舍是关键：值得记什么、什么时候记、什么时候忘。

## 来源
- [Agent Memory — Source](sources/agent-memory.md)
- [Anthropic: Effective context engineering](https://www.anthropic.com/news/context-engineering)
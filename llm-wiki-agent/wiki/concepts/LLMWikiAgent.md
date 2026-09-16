---
title: "LLMWikiAgent"
type: concept
tags: [llm, knowledge-base, agent, markdown, graph]
sources: [llm-wiki.md]
last_updated: 2026-09-16
---

## 定义
LLM Wiki Agent 是<strong>由 Claude Code 维护的本地知识库系统</strong>，分层：raw/（不可变原始资料）→ wiki/（结构化页面）→ graph/（知识图谱）。

## 五个工作流
- **ingest**：摄取新资料，写 sources 页面
- **query**：检索+综合回答
- **health**：结构健康检查（每会话跑，零 LLM 调用）
- **lint**：内容质量审计（孤儿页、断链、矛盾）
- **graph**：构建知识图谱

## Page Format
每个 wiki 页面使用统一 frontmatter：title / type / tags / sources / last_updated。使用 `[[PageName]]` wikilink。

## 来源
- [LLM Wiki — Source](sources/llm-wiki.md)
- [SamurAIGPT/llm-wiki-agent — GitHub](https://github.com/SamurAIGPT/llm-wiki-agent)
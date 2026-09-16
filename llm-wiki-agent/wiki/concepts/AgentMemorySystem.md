---
title: "AgentMemorySystem"
type: concept
tags: [ai-agent, memory, architecture, pipeline]
sources: [agent-memory-system.md]
last_updated: 2026-09-16
---

## 定义
Memory System 是把<strong>写入、存储、检索、遗忘四个环节做成可维护管线</strong>的设计，区别于普通 Database——前者关心"什么时候忘、什么时候记"，后者关心"高效存取"。

## 四类记忆
1. **事实型**：用户姓名、生日、偏好 → 键值对
2. **事件型**：上次订过哪家餐厅、踩过哪些坑 → 时间序列
3. **语义型**：领域知识 → 向量库
4. **程序型**：操作流程 → 步骤模板

## 五步管线
抽取 → 分类 → 写入 → 检索 → 遗忘

## 来源
- [Agent Memory System — Source](sources/agent-memory-system.md)
- [Mem0 Research](https://mem0.ai/research)
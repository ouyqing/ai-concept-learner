---
title: "AgentSkill"
type: concept
tags: [ai-agent, skills, claude-skills, capability-package]
sources: [agent-skills.md]
last_updated: 2026-09-16
---

## 定义
Agent Skill 是<strong>把"什么时候做、按什么步骤做、做错了怎么办"打包成可复用文件</strong>的能力单元，通常以 SKILL.md 说明文档为核心，附可选的 scripts / assets / references。

## 与易混项
| 易混项 | 核心区别 |
|--------|----------|
| Skill vs Tool | Tool 单步原子；Skill 多步工作流 |
| Skill vs Prompt | Prompt 本次指令；Skill 持久化资产 |
| Skill vs Fine-tune | Fine-tune 改模型参数；Skill 改输入 |

## 触发判断
Skill 的 description 字段决定 LLM 是否调用——过多 Skill 会让触发判断变难。

## 来源
- [Agent Skills — Source](sources/agent-skills.md)
- [Anthropic: Skills](https://www.anthropic.com/news/skills)
- [anthropics/skills — GitHub](https://github.com/anthropics/skills)
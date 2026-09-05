# ai-concept-learner · 概念学习仓库

姓名：欧阳箐箐

本仓库用于**概念学习资料的沉淀**：借助一个通用的「概念学习资料生成 Skill」，对任意新概念生成结构化、可追溯、经过人工核查的学习文档，并配套概念间关系说明。

## 仓库用途

1. 沉淀 AI 领域核心概念（Agent、大模型的上下文、Skill 等）的学习资料，供复习与分享。
2. 维护一套可复用的「概念学习资料生成 Skill」——任何新概念都可以按统一结构生成资料。
3. 记录概念之间的关系（见 `concept-relationship.md`）。

## 目录结构

```text
ai-concept-learner/
├── README.md                        # 本说明文件
├── concept-relationship.md          # Agent / 上下文 / Skill 三者关系（Mermaid 图 + 文字）
├── skill/                           # 概念的简版笔记（手写初稿）
│   ├── agent.md                     # Agent 概念
│   ├── llm-context.md               # 上下文 Context 概念
│   └── skill.md                     # Skill 技能概念
├── concept-material-generator/      # Skill 的原始副本
│   └── SKILL.md
├── .workbuddy/skills/concept-learning-skill/   # Skill 的正式存放与调用位置
│   └── SKILL.md
└── learning-materials/              # 生成的完整学习资料（HTML 格式）
    ├── agent.html                   # Agent（智能体）
    ├── llm-context.html             # 大模型的上下文（Context）
    └── skill.html                   # Skill（技能）
```

## Skill 存放路径

- **正式位置（供调用）**：`.workbuddy/skills/concept-learning-skill/SKILL.md`（项目级技能目录）
- **原始副本（留档）**：`concept-material-generator/SKILL.md`

两处内容完全一致；修改时请同步两份，或以正式位置为准。

## 调用方法

该 Skill 名为 `concept-learning-skill`，可接收**任意领域的新概念**作为输入：

1. **自然语言触发**：在本仓库的工作对话中直接说"帮我整理 XX 概念""生成 XX 的学习资料""我想学习 XX"，即会命中该 Skill。
2. **生成流程**（Skill 内置五步）：理解与拆解 → 联网检索（≥2 个独立来源）→ 按五板块撰写 → 自检 → 输出为 Markdown / HTML。
3. **输出结构**：每份资料固定包含五个板块——个人解释、核心机制、应用场景、边界辨析、来源链接。
4. **可选参数**：领域背景、目标读者（默认初学者）、深度（默认入门到进阶）、输出语言（默认跟随提问语言）；不提供时按默认值处理。

## 资料可靠性说明（人工核查）

> ⚠️ **重要：本仓库所有生成资料均已由本人进行人工核查。**

- 生成资料中的定义、机制描述与来源链接，均由 Skill 在生成时联网检索并交叉验证（≥3 条来源、≥2 个独立站点）；
- 尽管如此，AI 生成内容仍可能存在偏差，**每份资料交付后本人均已逐段人工核对**，对关键事实与链接做了二次验证；
- 经核查的资料以 `learning-materials/` 目录为准；若后续发现错误，以修改记录中的最新版本为准。

## 修改记录

- 2026-09-05：初次提交作业，完成 skill/ 目录下三个概念简版笔记。
- 2026-09-05：创建通用「概念学习资料生成 Skill」（SKILL.md），安装至 `.workbuddy/skills/concept-learning-skill/`；生成 Agent、大模型的上下文、Skill 三份 HTML 学习资料至 `learning-materials/`；补充 `concept-relationship.md` 三者关系说明；全部资料经人工核查后提交。

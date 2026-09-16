---
name: guided-concept-learning
description: This skill should be used when the user provides a GROUP of related concepts (2 or more, from any domain) and wants guided (guide-mode) learning materials for them. It sorts concepts into a learning path by dependency, then generates one guided learning unit per concept (scenario question → step-by-step Socratic explanation → hands-on practice with collapsible answers → self-quiz with instant feedback) plus a group-level index with learning path diagram, glossary, and a capstone exercise. Outputs both interactive HTML and Markdown. For reference-style single-concept documents, use concept-learning-skill instead.
agent_created: true
---

# Guide 式概念组学习材料生成 Skill

接收**一组相关概念**（≥2 个，任意领域），按引导式教学（guide 模式）生成成套学习材料。与 `concept-learning-skill` 的分工：本 Skill 做教学式材料（先问后答、边学边练），那个做参考式资料（五板块、查漏补缺）；两者可搭配使用。

## guide 模式核心原则

**不灌输，引导发现。** 每个概念的讲解必须遵循四环节教学循环：

1. **情境引入**：从一个真实小场景出发，抛出一个悬念问题；先不给答案。
2. **小步讲解**：把概念拆成 3–6 步，每步"先问后答"——先提一个小问题（学习者能自己想一想的），再给答案；每步最多引入 1 个新术语，术语首次出现时用一句话解释。
3. **跟练**：1–2 个动手练习（写代码 / 操作 / 计算），答案默认折叠。
4. **自测**：2–3 道选择题或简答题，覆盖本单元关键点；答完立即反馈对错与原因。

禁止把讲解写成"教科书段落"：连续两段以上没有问题、没有停顿点，就是违规。

## 输入信息

必填：
- **概念组**：≥2 个相关概念，顺序不限（Skill 负责排序）。

可选（缺失按默认处理，不追问）：
- **学习目标**：这组概念服务的最终目的（如"用 Python 做统计分析"），用于裁剪内容和选练习。
- **目标读者**：默认"零基础初学者"。
- **深度**：默认"入门"。
- **输出语言**：默认与用户提问语言一致；术语首次出现给英文原文（若有）。

## 生成步骤

1. **解析输入**：确认概念组的领域与学习目标。
2. **依赖排序**：判断概念间依赖关系，输出**学习路径**（如：环境 → Notebook → 变量与基本类型 → 报错怎么读），每个概念一句话说明"为什么排在这里"。若与用户给定顺序不同，在交付说明中明示。
3. **统一术语表**：全组共用一份中英术语表（如 interpreter / 解释器、cell / 单元格），所有材料用词一致。
4. **联网检索**：对操作性/时效性内容（环境版本、工具用法等）检索权威来源；沿用纪律：关键事实 ≥2 个独立来源交叉验证、只引用实际获取到的 URL、记录检索日期。
5. **逐概念生成**：按学习路径顺序，每个概念产出两份内容一致的文件——交互 HTML（折叠答案、自测即时反馈、浅色简洁、零外部依赖）+ Markdown（答案统一附文末"参考答案"节）。
6. **生成组级 index**（见输出结构）。
7. **自检**：对照自检清单逐项检查，通过后交付。

## 输出结构

```text
learning-materials/<组名>/
├── index.md                 组级入口
├── <概念1>.html / <概念1>.md
├── <概念2>.html / <概念2>.md
└── ...
```

`index.md` 必须包含：
- **学习路径图**：Mermaid flowchart，标注依赖关系
- **概念一览**：每概念一句话定位 + 建议学习时长
- **统一术语表**（全组中英对照）
- **串联练习**：1 个用到全部概念的 mini 项目（如"从装好环境到读懂第一段报错"）
- **自测清单**：全组关键点核对表
- **来源附录**：全组材料的来源链接 + 检索日期

单概念文件规范：
- Markdown：四环节用同级标题；跟练答案放文末；自测题干在前、答案在"参考答案"节。
- HTML：跟练答案用 `<details>` 折叠；自测选择题用原生 `<details>` 或轻量内联 JS 做对错反馈；不引入任何外部 CDN/框架；浅色配色，正文可读性优先。

## 资料来源要求

- 优先级：官方文档 > 标准规范 > 教材 > 权威百科 > 知名技术博客；博客不得作为关键事实唯一依据。
- 关键事实（版本号、命令、行为定义）须 ≥2 个独立来源一致；冲突时取更权威方并注明。
- 禁止凭记忆编造或拼接链接；未能核实的内容写"未能核实"或不写入。
- 教学示例（代码、练习）无需外部来源，但必须实际运行/推演过逻辑，不得给出跑不通的代码。

## 自检要求

- [ ] 路径合理：依赖概念排在被依赖概念之前，排序理由成立。
- [ ] 术语一致：全组材料用词与术语表一致，无同义词混用（如 cell 不混称"格子"）。
- [ ] 四环节齐全：每个概念单元都有引入、讲解、跟练、自测。
- [ ] 引导落实：讲解中每 1–2 小步有一个"先问后答"停顿点；无连续灌输段落。
- [ ] 练习可做：所有代码示例可运行，练习有明确输入输出预期。
- [ ] 自测覆盖：自测题覆盖本单元全部关键点，答案解释"为什么"。
- [ ] 双格式一致：HTML 与 Markdown 内容一致，仅交互形式不同。
- [ ] HTML 自包含：无外部依赖，折叠与反馈功能可用。
- [ ] 来源可追溯：关键事实可对应来源；无编造链接。
- [ ] 语言一致：与用户提问语言一致，术语首现标英文。

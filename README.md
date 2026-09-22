# Math Modeling Paper Coach

一个从 2017–2023 年 278 篇中国研究生数学建模竞赛优秀论文中提炼的 Codex Skill，用于指导：

- 赛题拆解与逐问需求分析；
- 建模路线、基线与改进模型选择；
- 数学表述、求解流程和验证方案设计；
- 数模论文架构、摘要、图表和结论写作；
- 全文技术审查与中文学术润色。

它的核心不是推荐“最热门的模型”，而是建立可核查的闭环：

> 题意验收 → 需求矩阵 → 问题依赖 → 基线模型 → 有依据的增强 → 求解 → 与主张匹配的验证 → 定量解释 → 结构化写作

## 语料基础

- 278 篇 PDF，覆盖 2017–2023 年、A–F 六类赛题；
- 对全部论文的首尾页面进行结构和方法词统计；
- 按“年份 × 题型”分层精读 42 篇全文样本；
- 对代表性摘要、优化模型页和深度学习结构页进行视觉核验。

详细统计、局限和推导边界见 [语料观察](references/corpus-findings.md)。本仓库不包含原始优秀论文 PDF。

## 安装

### Codex 用户目录安装

把整个 `math-modeling-paper-coach` 文件夹复制到：

```text
C:\Users\<用户名>\.codex\skills\math-modeling-paper-coach
```

macOS/Linux 通常为：

```text
~/.codex/skills/math-modeling-paper-coach
```

重新打开会话后，可显式调用：

```text
$math-modeling-paper-coach
```

### 项目内使用

也可以保留在项目仓库中，并在任务中提供 `SKILL.md` 的路径。若产品支持项目级 Skills，可按产品约定放入项目 Skill 目录。

## 快速使用

### 1. 赛题分析

```text
使用 $math-modeling-paper-coach 分析这道赛题。先输出逐问需求矩阵和问题依赖，再给候选模型链、推荐理由、数据处理、验证方案与论文提纲。不要虚构计算结果。
```

### 2. 建模方案

```text
使用 $math-modeling-paper-coach 为问题二设计模型。要求给出变量、目标函数、全部约束、参数来源、基线模型、改进条件、求解器与敏感性分析。
```

### 3. 论文润色

```text
使用 $math-modeling-paper-coach 润色这段论文。保持数值和技术含义不变，先给修订稿，再按位置列出逻辑、证据、术语、数学、图表和语言修改；发现事实问题时不要替我掩盖。
```

### 4. 全文审查

```text
使用 $math-modeling-paper-coach 审查整篇数模论文。先列 P0/P1 问题，再按量表评分，给出修复顺序，并检查摘要、正文、表格、公式和代码是否一致。
```

更多可直接复制的提示词见 [示例提示词](examples/prompts.md)，完整模式说明见 [使用手册](docs/使用手册.md)。第一次发布到 GitHub 可按 [GitHub 首次上传指南](docs/GitHub首次上传指南.md) 操作。

## 文件结构

```text
math-modeling-paper-coach/
├── SKILL.md
├── README.md
├── agents/
│   └── openai.yaml
├── assets/
│   └── contest-paper-template.md
├── docs/
│   ├── 使用手册.md
│   └── 优秀论文分析总结.md
├── examples/
│   └── prompts.md
└── references/
    ├── corpus-findings.md
    ├── problem-analysis-and-modeling.md
    ├── review-rubric.md
    └── writing-and-architecture.md
```

## 设计原则

1. **证据边界明确**：区分题目事实、假设、计算结果、引文知识和解释，不虚构数值或引用。
2. **先结构后模型**：先确定输出、变量、约束、指标和验证，再选择算法。
3. **基线优先**：复杂模型必须对应可观测的基线缺陷。
4. **验证匹配主张**：预测、优化、机制、评价和仿真使用不同的验证组合。
5. **逐问闭环**：每一问都形成“分析—模型—求解—结果—验证—接口”。
6. **语言不替代技术**：润色不能掩盖泄漏、违约束、数值矛盾或缺失证据。

## 适用与不适用

适合数学建模竞赛、课程项目、研究型案例分析和论文复核。不适合仅求解一道孤立的教材计算题，也不能代替真实数据计算、代码运行、领域专家判断或竞赛官方规则。

## 本地验证

使用 Codex 自带 Skill 校验器：

```powershell
python C:\Users\<用户名>\.codex\skills\.system\skill-creator\scripts\quick_validate.py .\math-modeling-paper-coach
```

验证器检查命名、YAML frontmatter 和脚手架占位符；它不能证明建模建议本身正确，因此仍应使用真实赛题做前向测试。

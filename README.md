# KimiCode Skills 索引与使用指南

> 本仓库包含一套为社会科学教学与研究设计的 Kimi Code Skills，覆盖从选题构思到发表准备的完整论文生产流水线。
> 实际存放位置：`~/.config/agents/skills/`（用户级，全局可用）

---

## Skill 清单

### 教学配套 Skills

| # | Skill | 触发方式 | 核心用途 |
|---|-------|----------|----------|
| 1 | **topic-to-idea** | `"以'XXX'为议题生成一个研究设想"` | 从政策议题到300字研究设想（固定五句结构） |
| 2 | **idea-to-perspective** | `"请用 idea-to-perspective skill 为我的选题寻找理论视角"` | 选题解构→学者著作推荐→读书报告任务（防模式化） |
| 3 | **scholar-question** | `"请用 scholar-question skill 诊断我的选题"` | 基于张静《学会提问》评估选题质量 |

### 完整 Scholar 学术工作流（11个）

```
Phase 1: 选题与构思
    topic-to-idea / scholar-idea / scholar-question
    ↓
Phase 2: 文献与理论
    idea-to-perspective
    scholar-lit-review-hypothesis
    scholar-conceptual
    scholar-hypothesis
    ↓
Phase 3: 因果与设计
    scholar-causal
    scholar-design
    ↓
Phase 4: 数据分析
    scholar-analyze
    scholar-qual
    ↓
Phase 5: 写作与润色
    scholar-write
    scholar-polish
    ↓
Phase 6: 发表准备
    scholar-replication
```

| # | Skill | 触发方式 | 核心用途 |
|---|-------|----------|----------|
| 4 | **scholar-idea** | `"请用 scholar-idea skill 探索：..."` | 选题构思、研究问题打磨、多智能体评审 |
| 5 | **scholar-lit-review-hypothesis** | `"请用 scholar-lit-review-hypothesis skill 处理：..."` | 系统文献综述 + 理论框架 + 假设推导 |
| 6 | **scholar-conceptual** | `"请用 scholar-conceptual skill：[theorize|diagram] ..."` | 原创理论构建、概念图生成 |
| 7 | **scholar-hypothesis** | `"请用 scholar-hypothesis skill：..."` | 深化假设开发、理论选择、期刊定制草稿 |
| 8 | **scholar-causal** | `"请用 scholar-causal skill：..."` | DAG构建、因果识别策略选择与论证 |
| 9 | **scholar-design** | `"请用 scholar-design skill：[quant|qual|mixed|experiment] ..."` | 研究设计、功效分析、预分析计划 |
| 10 | **scholar-analyze** | `"请用 scholar-analyze skill：..."` | 数据分析、发表级表格与可视化 |
| 11 | **scholar-qual** | `"请用 scholar-qual skill：[codebook|thematic|content|llm-coding] ..."` | 定性编码、主题分析、混合方法 |
| 12 | **scholar-write** | `"请用 scholar-write skill：[draft|revise|polish] ..."` | 论文各章节写作 |
| 13 | **scholar-polish** | `"请用 scholar-polish skill：[SCAN|REWRITE|FULL] ..."` | 学术写作润色、风格个性化 |
| 14 | **scholar-replication** | `"请用 scholar-replication skill：[BUILD|DOCUMENT|TEST] ..."` | 复制包构建与验证 |
| 15 | **scholar-think-tank** | `"请用 scholar-think-tank skill：..."` | 智库咨政报告撰写 |

---

## 目录结构

```
kimi-skills/
├── README.md                          # 本文件（索引与指南）
├── topic-to-idea/                     # 从议题到300字研究设想
│   ├── SKILL.md
│   └── references/
│       ├── 课题论证活页.md
│       ├── 课题论证活页.doc
│       └── 2026年国家社会科学基金重点研究项目.pdf
├── idea-to-perspective/               # 为选题匹配理论视角（读书报告）
│   ├── SKILL.md
│   └── references/
│       ├── book-review-framework.md
│       └── scholar-book-pool.md
└── ...（其余scholar系列skill由系统自动管理）
```

---

## topic-to-idea：从议题到300字研究设想

原始需求来自国家社会科学基金课题申报场景。将官方政策议题转化为**具体的、可操作的、有理论深度的**研究问题。

### 核心设计：固定五句结构

| 句序 | 功能 | 衔接机制 |
|:-----|:-----|:---------|
| 第一句 | 现实痛点 + 关键数据 | 用具体经验现象制造问题意识 |
| 第二句 | 制度悖论 | 必须用因果承接词（"问题的根源在于"）与第一句咬合 |
| 第三句 | 独特视角 + 核心概念 | 破折号即时锚定概念，避免悬空 |
| 第四句 | 预期震撼发现 | 概念必须参与机制叙述，形成咬合 |
| 第五句 | 研究意义 | 用"打破悖论""构建框架"替代平淡表达 |

**关键洞见**：第三、四句的"概念咬合"是整段话的灵魂。

### 使用方式

> "以'人工智能发展和治理'为议题生成一个研究设想"

Kimi 会自动调用该 skill，输出一段 300 字以内的五句研究设想。

---

## idea-to-perspective：为选题嵌入差异化理论视角

### 定位

topic-to-idea 的**下游配套工具**。在学生已有选题说明的基础上，通过**经典阅读**为其嵌入真实的理论视角。

**核心机制**：不给学生"现成视角"，而是给 ta **3 位权威学者 + 3 本代表作 + 1 份读书报告任务单**。学生必须真正阅读、消化、选择，最终产出 **500–800 字读书报告**。

### 教学目的

- 彻底切断「模型代写」导致的模式化
- 迫使学生进入真实学术传统，与具体学者对话
- 让「视角差异」来源于「阅读差异」，而非「提示词差异」

### 工作流程

```
学生已有选题说明
    ↓
Step 1: AI 解构选题（识别理论缺口）
    ↓
Step 2: AI 推荐 3 个竞争性理论维度 × 权威学者 × 代表作
    ↓
【第一次选择】学生从 3 个候选中选 1 个
    ↓
Step 3: AI 为选定著作生成定制化读书报告任务单
    ↓
【第二次选择】学生在阅读中回应 3 个导向问题
    ↓
Step 4: 学生撰写 500-800 字读书报告
    ↓
成果：同一议题，30 个学生读 30 本不同的书 → 30 张不同的学术面孔
```

### 读书报告五步结构

| 步骤 | 字数 | 功能 |
|:-----|:-----|:-----|
| Hook / 问题意识 | 50-80 | 从学生自身困惑出发 |
| 文本复述 | 100-150 | 一句话核心论点 + 2-3个关键案例 |
| 理论嫁接 | 150-200 | 将书中核心概念嫁接到选题上 |
| 批判回应 | 100-150 | 指出具体盲区，非泛泛批评 |
| 视角改写 | 50-100 | 用本书语言重写选题的预期发现句 |

---

## 典型使用场景

### 场景 A：从零开始写一篇定量论文
```
1. topic-to-idea → 确定研究问题和角度
2. idea-to-perspective → 通过经典阅读为选题锚定理论视角
3. scholar-lit-review-hypothesis → 写文献综述和理论框架
4. scholar-causal → 构建DAG和因果策略
5. scholar-design → 设计研究和预分析计划
6. scholar-analyze → 跑数据分析和可视化
7. scholar-write → 写 Results 和 Discussion
8. scholar-replication → 打包复制材料
```

### 场景 B：理论驱动型论文
```
1. scholar-idea → 发现经验谜题
2. idea-to-perspective → 通过经典阅读锚定理论视角
3. scholar-conceptual → 构建原创理论框架
4. scholar-hypothesis → 从理论推导假设
5. scholar-design → 设计验证研究
6. scholar-analyze → 实证检验
7. scholar-write → 写作输出
```

### 场景 C：已有初稿，需要润色
```
scholar-polish → SCAN（诊断问题）→ REWRITE/FULL（修复）
```

---

## Skill 存放规范

**全局 Skill 目录**：`~/.config/agents/skills/`

```
~/.config/agents/skills/
├── topic-to-idea/
│   ├── SKILL.md
│   └── references/
├── idea-to-perspective/
│   ├── SKILL.md
│   └── references/
├── scholar-idea/
│   └── SKILL.md
├── scholar-lit-review-hypothesis/
│   └── SKILL.md
├── scholar-conceptual/
│   └── SKILL.md
├── scholar-hypothesis/
│   └── SKILL.md
├── scholar-causal/
│   └── SKILL.md
├── scholar-design/
│   └── SKILL.md
├── scholar-analyze/
│   └── SKILL.md
├── scholar-qual/
│   └── SKILL.md
├── scholar-write/
│   └── SKILL.md
├── scholar-polish/
│   └── SKILL.md
├── scholar-replication/
│   └── SKILL.md
└── scholar-think-tank/
    └── SKILL.md
```

**命名规范**：全小写，连字符分隔，动词开头

---

## 注意事项

- 所有 Skill 为**用户级**，在任何工作目录下均可调用
- Skill 之间存在**调用依赖关系**（如 scholar-analyze 建议先调用 scholar-causal）
- 大型任务建议**分阶段调用**，不要一次串连过多 Skill
- 调用时请明确告知**目标期刊**（如 ASR/AJS/Demography/Social Policy & Administration），Skill 会自动调整输出格式
- `topic-to-idea` 与 `idea-to-perspective` 为**教学专用配套**：前者解决"从议题到合格提案"，后者解决"从合格提案到差异化视角"

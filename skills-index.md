# KimiCode 项目 Skill 索引

> 本项目使用的 Kimi Code Skills 清单及调用指南
> 实际存放位置：`~/.config/agents/skills/`（用户级，全局可用）

---

## 完整 Scholar 学术工作流

以下 11 个 Skill 构成了一条完整的社会科学论文生产流水线：

```
Phase 1: 选题与构思
    scholar-idea
    → 将模糊想法转化为正式研究问题（含多智能体评审面板）
    ↓
Phase 2: 文献与理论
    scholar-lit-review-hypothesis
    → 系统文献综述 + 理论框架 + 假设推导
    ↓
    scholar-conceptual
    → 构建原创理论框架 + 概念图（TikZ/Mermaid）
    ↓
    scholar-hypothesis
    → 深化假设开发（25+理论库、7种假设类型、期刊定制草稿）
    ↓
Phase 3: 因果与设计
    scholar-causal
    → 因果推断策略（13种方法：DiD/RD/IV/匹配/合成控制等）
    ↓
    scholar-design
    → 研究设计、功效分析、预分析计划、方法学章节
    ↓
Phase 4: 数据分析
    scholar-analyze
    → 数据分析 + 发表级表格/可视化（HTML/TeX/docx + PDF/PNG）
    ↓
    scholar-qual
    → 定性研究（编码本、扎根理论、主题分析、LLM辅助编码）
    ↓
Phase 5: 写作与润色
    scholar-write
    → 论文各章节草稿（Introduction/Theory/Methods/Results/Discussion）
    ↓
    scholar-polish
    → 个性化润色（SCAN/REWRITE/FULL三种模式）
    ↓
Phase 6: 发表准备
    scholar-replication
    → 复制包构建、文档化、 clean-run 验证
```

---

## Skill 清单

| # | Skill | 触发方式 | 核心用途 |
|---|-------|----------|----------|
| 1 | **scholar-idea** | `"请用 scholar-idea skill 探索：..."` | 选题构思、研究问题打磨、多智能体评审 |
| 2 | **scholar-lit-review-hypothesis** | `"请用 scholar-lit-review-hypothesis skill 处理：..."` | 系统文献综述 + 理论框架 + 假设推导 |
| 3 | **scholar-conceptual** | `"请用 scholar-conceptual skill：[theorize\|diagram] ..."` | 原创理论构建、概念图生成 |
| 4 | **scholar-hypothesis** | `"请用 scholar-hypothesis skill：..."` | 深化假设开发、理论选择、期刊定制草稿 |
| 5 | **scholar-causal** | `"请用 scholar-causal skill：..."` | DAG构建、因果识别策略选择与论证 |
| 6 | **scholar-design** | `"请用 scholar-design skill：[quant\|qual\|mixed\|experiment] ..."` | 研究设计、功效分析、预分析计划 |
| 7 | **scholar-analyze** | `"请用 scholar-analyze skill：..."` | 数据分析、发表级表格与可视化 |
| 8 | **scholar-qual** | `"请用 scholar-qual skill：[codebook\|thematic\|content\|llm-coding] ..."` | 定性编码、主题分析、混合方法 |
| 9 | **scholar-write** | `"请用 scholar-write skill：[draft\|revise\|polish] ..."` | 论文各章节写作 |
| 10 | **scholar-polish** | `"请用 scholar-polish skill：[SCAN\|REWRITE\|FULL] ..."` | 学术写作润色、风格个性化 |
| 11 | **scholar-replication** | `"请用 scholar-replication skill：[BUILD\|DOCUMENT\|TEST] ..."` | 复制包构建与验证 |

---

## 典型使用场景

### 场景 A：从零开始写一篇定量论文
```
1. scholar-idea → 确定研究问题和角度
2. scholar-lit-review-hypothesis → 写文献综述和理论框架
3. scholar-causal → 构建DAG和因果策略
4. scholar-design → 设计研究和预分析计划
5. scholar-analyze → 跑数据分析和可视化
6. scholar-write → 写 Results 和 Discussion
7. scholar-replication → 打包复制材料
```

### 场景 B：理论驱动型论文
```
1. scholar-idea → 发现经验谜题
2. scholar-conceptual → 构建原创理论框架
3. scholar-hypothesis → 从理论推导假设
4. scholar-design → 设计验证研究
5. scholar-analyze → 实证检验
6. scholar-write → 写作输出
```

### 场景 C：混合方法研究
```
1. scholar-idea → 确定研究问题
2. scholar-qual → 定性探索阶段（编码、主题分析）
3. scholar-design → 设计量化验证阶段
4. scholar-analyze → 量化分析
5. scholar-write → 整合两种方法的结果
```

### 场景 D：已有初稿，需要润色
```
scholar-polish → SCAN（诊断问题）→ REWRITE/FULL（修复）
```

---

## Skill 存放规范

**全局 Skill 目录**：`~/.config/agents/skills/`

```
~/.config/agents/skills/
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
└── scholar-replication/
    └── SKILL.md
```

**命名规范**：全小写，连字符分隔，动词开头

---

## 注意事项

- 所有 Skill 为**用户级**，在任何工作目录下均可调用
- Skill 之间存在**调用依赖关系**（如 scholar-analyze 建议先调用 scholar-causal）
- 大型任务建议**分阶段调用**，不要一次串连过多 Skill
- 调用时请明确告知**目标期刊**（如 ASR/AJS/Demography/Social Policy & Administration），Skill 会自动调整输出格式

---
name: idea-to-perspective
description: Attach a distinctive theoretical perspective to an existing research topic via curated reading. Use when a student has a research proposal (e.g., from topic-to-idea) and needs to ground it in real scholarly traditions through a 500-800 word book review. Triggers when the user asks to find theoretical angles, assign book reviews, embed theory into a topic, differentiate perspectives via reading, or avoid template-like research proposals.
---

# Idea-to-Perspective：从选题说明到读书报告的视角锚定

## Purpose

Transform a student's research proposal into a curated reading assignment that forces real engagement with scholarly traditions. Given an existing topic or proposal, identify three competing theoretical lenses, map each to a seminal author and book, and guide the student to produce a 500-800 word book review that embeds the author's framework into their own research question.

## Input Requirements

The user must provide:

1. **A research proposal** (output from `topic-to-idea`, or a 200-400 word student-written proposal)
2. **Disciplinary/course context** (optional but recommended, e.g., "Intro to Sociology", "Public Administration")

## Workflow (Four Steps)

### Step 1: Deconstruct the Proposal

Analyze the student's proposal to identify:

| Item | Description |
|:-----|:------------|
| Core phenomenon | The specific social phenomenon under study |
| Implicit causal claim | What causes what, according to the proposal |
| Already-used concepts | Theoretical concepts already deployed (1-3) |
| Theoretical gap | Whether these concepts are anchored or floating |
| Three competing dimensions | Three theoretical traditions that offer *rival* explanations for the same phenomenon |

Key rule: The three dimensions must represent genuine theoretical competition (different causal judgments), not complementary angles.

### Step 2: Curate Three Scholar-Book Pairs

For each theoretical dimension, match:
- **One authoritative scholar** (widely recognized within that tradition)
- **One代表作 (representative work)** (accessible in Chinese translation or as a classic English original)
- **One core reading question** that pierces the student's proposal

Matching criteria:
- Scholar must be canonical within the tradition
- Book must be obtainable (library/database access)
- Book's core thesis must directly confront the student's topic
- At least one book must challenge the proposal's default position (antagonistic reading)
- The three scholars must belong to visibly different intellectual lineages

Output format for each pair:

```
【视角 X: Dimension Name】

Scholar: [Name] ([Dates/Nationality/School])
Book: 《[Title]》([First edition year]) [Translator/Publisher/Year if Chinese]

Core thesis (≤100 words):
What is the book's most provocative claim about [type of phenomenon]?

Connection to proposal (≤100 words):
Which specific concept or causal chain in the student's proposal can this book re-examine, refute, or deepen?

Core reading question:
If [Scholar] studied your topic, what would they see that you have missed?
```

### Step 3: Present Choices and Await Selection

Present the three scholar-book pairs to the student with a clear instruction:

> "Please select ONE scholar-book pair from the three options above. Reply with your choice (e.g., 'I choose perspective B: [Scholar]') and I will generate a customized 500-800 word book-review assignment for that selection."

Do not proceed to Step 4 until the student has made an explicit selection.

### Step 4: Generate Customized Book-Review Assignment

Once the student selects a pair, produce a tailored assignment containing:

1. **Anchor summary** (30 words): Restate the student's puzzle and why this specific book addresses it
2. **Reading guide**: 3 focused questions to guide the student's reading
3. **Book-review template**: A structured 500-800 word outline

The book-review template must follow this structure (see `references/book-review-framework.md` for full guidance):

| Section | Words | Purpose |
|:--------|:------|:--------|
| Hook/Problem意识 | 50-80 | Start from the student's own puzzle, not from book summary |
| Textual summary | 100-150 | Retell the book's core argument in one sentence; identify 2-3 key cases or evidence |
| Theoretical嫁接 | 150-200 | Graft the book's core concept onto the student's topic; answer: "If this author studied my topic, what would they ask?" |
| Critical response | 100-150 | Identify one limitation or blind spot of the book relative to the student's context |
| Perspective rewrite | 50-100 | Rewrite the proposal's "expected finding" sentence using the book's theoretical language |

Mandatory constraints:
- Must directly quote at least one passage from the book (with page number)
- Must use the book's core concept at least twice in the theoretical嫁接 section
- Must include a concrete counter-argument, not just praise
- Total length: 500-800 Chinese characters

## Output Format

### Before Selection (Step 3 Output)

```
【选题解构】
核心现象: ...
隐含因果主张: ...
已调用概念: ...
理论缺口: ...

【理论地图】
[One paragraph: Your topic sits on contested theoretical terrain. Three traditions disagree on...]

---

【候选一: Dimension A】
Scholar: ...
Book: ...
...

【候选二: Dimension B】
...

【候选三: Dimension C】
...

---

请选择以上 3 个候选中的 1 个，回复「我选择候选 X: [学者姓名]」，我将为你生成该书的定制化读书报告任务单。
```

### After Selection (Step 4 Output)

```
【选定视角: Dimension X + Scholar】
锚定摘要: ...

【阅读指引】
带着以下 3 个问题去阅读:
1. ...
2. ...
3. ...

【500-800字读书报告任务单】
[Full template with section-by-section guidance]

【评价标准】
| 维度 | 权重 | 优秀标准 |
```

## Stability Rules

1. Always complete Step 1 before Step 2. Do not recommend books without first diagnosing the proposal's theoretical gap.
2. The three pairs must represent genuine rivalry. Before outputting, verify: if a student read Pair A and Pair B, would they discover contradictory causal claims?
3. Each pair must connect to at least one specific element of the student's proposal (a concept, a causal chain, or a puzzle).
4. At least one pair must challenge the proposal's default assumptions (antagonistic reading).
5. Do not recommend textbooks, encyclopedias, or review articles. Only original monographs.
6. If the student's proposal is too vague to anchor, ask one clarifying question before proceeding.
7. Do not generate the full book-review assignment until the student has explicitly selected one pair.

## Common Errors to Avoid

| Error | Manifestation | Fix |
|:------|:--------------|:----|
| Fake rivalry | Three books actually agree; differences are cosmetic | Check: Do they make different causal claims about the same phenomenon? |
| Generic matching | Book is famous but only vaguely related to topic | Ensure the "Connection to proposal" specifies exact concept correspondence |
| No antagonistic option | All three books confirm student's existing view | Force at least one contrarian selection |
| Floating concepts | Reading guide never asks student to apply the book to their topic | Every reading question must bridge book → proposal |
| Pre-written review | Student may ask model to write the review | Lock: require direct quote + page number + concrete counter-argument |

## References

- `references/book-review-framework.md` — Full structural guidance, examples from published book reviews, and quality benchmarks for the 500-800 word output.
- `references/scholar-book-pool.md` — A curated pool of scholars and books organized by theoretical tradition, to avoid repetitive recommendations.

# Question Schema (v1)

This is the single, canonical Markdown format for **every** question-and-answer file in this repo: company interview write-ups, the Playwright guide, and AIF-C01 practice questions. It reads naturally on GitHub and can be parsed by a script (roadmap items C-04 validator and P-02 Markdown → JSON parser).

- Machine-readable definition: [question.schema.json](question.schema.json)
- Copy-and-fill starting point: [templates/question-file-template.md](templates/question-file-template.md)

> **Status:** All **new** question files must follow this schema. Existing files are migrated under roadmap item C-04. Until a file is migrated, keep using the format it already has (see the format table in `CLAUDE.md`).

## 1. File layout

```text
---                          ← YAML front matter (file-level metadata)
...
---

# <Title>                    ← exactly one H1

<Short intro: what this file covers, how to use it>

## <Section>                 ← round, domain, or topic group (H2)

### Q1. <Question title>     ← one H3 per question
<!-- meta: {...} -->         ← per-question metadata (hidden when rendered)
<stem, options>
<details> answer </details>

### Q2. ...

## Answer Key                ← optional; required for exam-style files
## Score Tracker             ← optional
```

## 2. File front matter

YAML between `---` lines at the very top of the file. GitHub shows it as a small table above the content.

| Field | Required | Type | Meaning |
|---|---|---|---|
| `schema` | yes | `question-file/v1` | Schema version. Lets the parser reject unknown formats |
| `title` | yes | string | Same text as the H1 |
| `id_prefix` | yes | kebab-case string | Prefix for every question `id` in this file (see §5) |
| `topic` | yes | enum | `aws-aif-c01`, `playwright`, `selenium`, `java`, `sql`, `api-testing`, `ci-cd`, `test-strategy`, `behavioral`, `general-qa` |
| `source` | yes | enum | `interview` (real interview), `original` (written by a person for this repo), `ai-generated`, `collected` (gathered from public practice material) |
| `last_verified` | yes | date `YYYY-MM-DD` | Last date the content was checked for accuracy |
| `reviewed_by` | no | string | Who did the last review (GitHub handle or "Claude (AI-assisted)") |
| `company` | no | string | Interview files only, e.g. `Deloitte` |
| `role` | no | string | Interview files only, e.g. `Sr. QA` |
| `exam_guide_version` | no | string | Certification files only, e.g. `1.4` |

```yaml
---
schema: question-file/v1
title: "Deloitte Sr. QA Interview"
id_prefix: del-srqa
topic: selenium
source: interview
company: Deloitte
role: Sr. QA
last_verified: 2026-11-14
reviewed_by: Claude (AI-assisted)
---
```

## 3. Question block

Every question is one block in this order. Blank lines between the parts are required.

1. **Heading:** `### Q<n>. <Question title>`
   - `<n>` is the question's position in the file (1, 2, 3 … with no gaps).
   - Short questions put the full question in the heading. For long scenario questions, use a short title (≤ 80 characters) and put the full text in the stem.
2. **Metadata comment** on the line directly after the heading:
   `<!-- meta: {id: del-srqa-005, type: open-ended, difficulty: medium, tags: [java, collections]} -->`
   The value is one line of YAML flow-style. It is hidden on GitHub but parsed by tools.
3. **Stem** (optional for open-ended questions whose heading says it all): the full question text.
4. **Options** (choice types only): `- A. …`, `- B. …` … up to `F`. Use `- A. True` / `- B. False` for true/false.
5. **Answer:** inside `<details><summary>Show answer</summary>` … `</details>`, so learners can test themselves.

### Per-question metadata fields

| Field | Required | Values |
|---|---|---|
| `id` | yes | `<id_prefix>-<nnn>` (three digits, e.g. `aif-b2-007`). Unique across the repo, **never reused or renumbered**, even when questions move or `<n>` changes |
| `type` | yes | `single-choice`, `multiple-response`, `true-false`, `ordering`, `matching`, `open-ended`, `coding` |
| `difficulty` | yes | `easy`, `medium`, `hard` |
| `domain` | AWS only | `1`–`5` (AIF-C01 exam domain) |
| `task` | no | Exam task statement, e.g. `"3.2"` (string) |
| `round` | no | Interview round, e.g. `"Round 1: Technical"` |
| `tags` | no | List of kebab-case keywords, e.g. `[waits, selenium]` |

### Answer content by question type

| Type | Inside `<details>` |
|---|---|
| `single-choice`, `true-false` | `**Answer:** B` (or `True`), then `**Explanation:** …` |
| `multiple-response` | `**Answer:** A, C` in letter order, then `**Explanation:** …`. The stem must end with `(Select TWO.)` / `(Select THREE.)` |
| `ordering` | `**Answer:** C → A → D → B`, then `**Explanation:** …` |
| `matching` | `**Answer:**` followed by a two-column table, then `**Explanation:** …` |
| `open-ended` | A model answer in free Markdown: lead with a 1–3 sentence summary, then detail. `**Answer:**` line not required |
| `coding` | Model answer with code in a fenced block **with a language tag** (` ```java `, ` ```ts `, ` ```sql `), plus expected output or complexity where relevant |

Explanations for choice questions should say why the correct option is right **and** why the tempting wrong options are wrong.

## 4. Complete examples

### Choice question (AIF-C01)

````markdown
### Q12. Reducing overfitting
<!-- meta: {id: aif-b2-112, type: multiple-response, difficulty: medium, domain: 1, task: "1.3", tags: [overfitting, regularization]} -->

A model scores 99% on training data but 70% on new data. Which TWO actions are most likely to help? (Select TWO.)

- A. Train for more epochs
- B. Add more varied training data
- C. Remove the validation set
- D. Apply regularization such as dropout
- E. Increase the number of model parameters

<details><summary>Show answer</summary>

**Answer:** B, D

**Explanation:** The gap between training and test accuracy is overfitting. More varied data and regularization both help the model generalize. More epochs and more parameters make overfitting worse, and removing the validation set only hides the problem.

</details>
````

### Open-ended interview question

````markdown
### Q9. Difference between implicit wait and explicit wait
<!-- meta: {id: del-srqa-009, type: open-ended, difficulty: easy, round: "Round 1: Technical", tags: [selenium, waits]} -->

<details><summary>Show answer</summary>

An **implicit wait** sets one global polling timeout for every `findElement` call. An **explicit wait** waits for one specific condition on one element, and is the preferred approach.

```java
WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(10));
WebElement button = wait.until(ExpectedConditions.elementToBeClickable(By.id("submit")));
```

Don't mix the two: combining them can produce unpredictable wait times.

</details>
````

## 5. ID prefixes

Register a prefix here before using it. IDs keep their prefix even if a file is renamed.

| Prefix | File (after migration) |
|---|---|
| `aif-b1` | `AWS-AI-Practitioner/ch1-2.md`, `ch3-4.md`, `ch5.md` (Question Bank 1) |
| `aif-b2` | `AWS-AI-Practitioner/question-bank-2.md` (Question Bank 2) |
| `aif-px1` | `AWS-AI-Practitioner/practice-exam-set-1.md` |
| `aif-px2` | `AWS-AI-Practitioner/practice-exam-set-2.md` |
| `aif-col` | `AWS-AI-Practitioner/aif-c01-questions.md` |
| `pw` | `Playwright/100-playwright-interview-questions.md` |
| `cap-l2` | `Capgemini/l2-interview-questions.md` |
| `del-ate` | `Deloitte/automation-test-engineer.md` |
| `del-srqa` | `Deloitte/sr-qa.md` |

## 6. Rules a validator will enforce (C-04)

1. Front matter exists, matches [question.schema.json](question.schema.json) `$defs/fileFrontMatter`, and `title` equals the H1.
2. Exactly one H1, and every question is an H3 `### Q<n>. …` with `<n>` counting up from 1 without gaps.
3. Every question has a `meta` comment that matches `$defs/questionMeta`, and its `id` starts with the file's `id_prefix` and is unique across the repo.
4. Choice types have options with consecutive letters starting at `A`, and the `**Answer:**` letters exist among the options. `multiple-response` has at least two answer letters.
5. Every answer is inside a `<details>` block, and every fenced code block has a language tag.
6. If an `## Answer Key` exists, it matches the per-question answers. If a summary or score-tracker table exists, its counts match the questions.

## 7. Versioning

Changes that break parsing (renamed or removed fields, new required fields) bump the version to `question-file/v2` and need a migration note here. Adding optional fields keeps `v1`.

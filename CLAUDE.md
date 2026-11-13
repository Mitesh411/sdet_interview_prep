# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A Markdown-only knowledge base for SDET/QA interview preparation plus AWS Certified AI Practitioner (AIF-C01) exam study material. There is no application code, no package manager, and no build, lint, or test tooling. Code inside the Markdown (Java, TypeScript, SQL, YAML) is illustrative and is not compiled or run anywhere. "Verifying" a change means checking that the Markdown renders correctly on GitHub (headings, tables, fenced code, `<details>` blocks) and that answers are technically accurate.

`ProductRoadmap.md` holds the planned work and the known defects (W1–W13). Read it before making structural changes, so edits line up with the planned direction: one question schema, deduplication, and a later Markdown → JSON parser.

## Content areas

- **Company interview write-ups** (`Capegemini/`, `Deloitte/`): real interview questions grouped by company and round, each answered in long form with code. The folder name `Capegemini` is a known misspelling. Don't rename it unless asked, because renaming breaks links.
- **`Playwright/`**: a 100-question guide in sections of 20. Q1–80 use `### N. Question` headings with full answers. Q81–90 are bold one-line stubs under `## ADVANCED TOPICS`, and Q91–100 don't exist yet. `playwright.md` is a placeholder, and the `.pdf` is a static export of the `.md`, so the two can drift apart.
- **`AWS AI Practitioner/Claude/`**: AIF-C01 material organized by the five official exam domains, with these weights: D1 Fundamentals of AI/ML 20%, D2 Generative AI 24%, D3 Applications of Foundation Models 28%, D4 Responsible AI 14%, D5 Security/Compliance/Governance 14%.
  - `Ch1&2.md` + `Ch3&4.md` + `Ch5.md` together form a 525-question bank (105 per domain). `AllChapters.md` holds the **same 525 questions in a different format and with different wording**. If you fix a question in one copy, check the other.
  - `65 Practice Questions.md` and `65 Practice Questions Set 2.md` are full mock exams (13/16/18/9/9 questions per domain, with a score tracker at the end). Set 2 must not repeat scenarios from Set 1.
  - `AIF-C01.md` contains exam-style questions with the answers marked inline (`- [x]`).
  - `ExamNotes.md` and `ExtraDetailsNotes.md` are study notes. `ExtraDetailsNotes.md` has "Points to Remember" and "Exam Traps" sections for each domain.

## Question formats in use

Files don't share one format. When editing a file, **match the format that file already uses**:

| Format | Used in |
|---|---|
| `#### Qn · Domain N · Difficulty · Type`, options `- A.`, then `<details><summary>Show answer</summary>` with `**Answer: X**` and an explanation | `Ch*.md`, `65 Practice Questions Set 2.md` |
| `### D1-001`, `*Type \| Difficulty*`, `**Question:**`, inline answer/explanation, plus an answer key at the end | `AllChapters.md` |
| `### Qn` with options, answers collected in an `# Answer Key` section at the end | `65 Practice Questions.md` |
| `### Question text` with `- [x]` / `- [ ]` options | `AIF-C01.md` |
| `## N) Question`, then a free-form answer | Capgemini, Deloitte |
| `### N. Question`, then a free-form answer | Playwright |

When adding questions to an AWS bank, update every count that depends on them: summary tables, domain ranges such as `Q1–Q13`, answer keys, and score trackers.

## Content conventions

- AWS questions are original practice material, not real exam questions, and the files include a disclaimer saying so. Keep it that way. Keep AWS service names current, because the material goes stale as services are renamed.
- Interview answers aim to be "manager-friendly": a short definition or structure first, then a code example in a fenced block with a language tag. Some older files use indented code blocks. Prefer fenced blocks in new content.
- `Deloitte/Automation_Test_Engineer.md` uses Unicode math-bold characters in some headings. Use plain text in new headings.

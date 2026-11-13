# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A Markdown-only knowledge base for SDET/QA interview preparation plus AWS Certified AI Practitioner (AIF-C01) exam study material. There is no application code and no package.json. Code inside the Markdown (Java, TypeScript, SQL, YAML) is illustrative and is not compiled or run anywhere. "Verifying" a change means passing the checks below, confirming the Markdown renders correctly on GitHub (headings, tables, fenced code, `<details>` blocks), and confirming the answers are technically accurate.

`ProductRoadmap.md` holds the planned work and the known defects (W1–W13, with completed items struck through). Read it before making structural changes, so edits line up with the planned direction: migrate every file to the question schema (C-04), then a Markdown → JSON parser (P-02).

## Checks (run before finishing any change)

`.github/workflows/docs-quality.yml` runs these on every pull request and on manual dispatch. Run them locally with Node 22+ (`npx` downloads the pinned versions):

```bash
npx markdownlint-cli2@0.18.1                     # all **/*.md, rules in .markdownlint-cli2.jsonc
npx markdownlint-cli2@0.18.1 path/to/file.md     # one file
npx cspell@9.1.3 lint --no-progress "**/*.md"    # config cspell.json
lychee --config lychee.toml "./**/*.md"          # links and #anchors (CI uses lycheeverse/lychee-action)
```

- `.markdownlint-cli2.jsonc` intentionally allows long lines, `<details>`/`<summary>`/`<b>`/`<br>`, an italic metadata line directly under h3/h4 question headings, and multiple H1s. MD025 stays disabled until roadmap item F-04 fixes the H1s. Don't loosen other rules to get a pass. Fix the content instead.
- When cspell flags a real technical term, add it to `.cspell/tech-words.txt` (one per line, sorted). Words split by bold mnemonic letters (`**G**enerator`) are already ignored by a regex in `cspell.json`.
- `lychee.toml` checks `#anchor` fragments too. GitHub anchors drop punctuation and emoji (`## 0. Exam Overview & Strategy` → `#0-exam-overview--strategy`).

## Naming

Folders and content files use kebab-case with no spaces or `&` (`Capgemini/l2-interview-questions.md`, `AWS-AI-Practitioner/ch1-2.md`). The exceptions are the root `README.md`, `CLAUDE.md`, `CONTRIBUTING.md`, `ProductRoadmap.md` and `LICENSE`, plus `study-plans/README.md`. When you rename a file or change a heading, update every link to it. `README.md`, the `study-plans/*.md` files, the AWS cross-links (`ch*.md`, `question-bank-2.md`, `review-log.md`) and `Playwright/playwright.md` all deep-link into content files, so a renamed heading breaks its `#anchor` links. The link check catches these.

## Content areas

- **Company interview write-ups** (`Capgemini/`, `Deloitte/`): real interview questions grouped by company and round, each answered in long form with code.
- **`Playwright/`**: a 100-question guide in sections of 20. Q1–80 use `### N. Question` headings with full answers. Q81–90 are bold one-line stubs under `## ADVANCED TOPICS`, and Q91–100 don't exist yet. `playwright.md` is a placeholder, and the `.pdf` is a static export of the `.md`, so the two can drift apart.
- **`AWS-AI-Practitioner/`**: AIF-C01 material organized by the five official exam domains, with these weights: D1 Fundamentals of AI/ML 20%, D2 Generative AI 24%, D3 Applications of Foundation Models 28%, D4 Responsible AI 14%, D5 Security/Compliance/Governance 14%.
  - **Question Bank 1** is split across `ch1-2.md`, `ch3-4.md` and `ch5.md` and has 525 questions (Q1–Q525, numbered continuously across the three files, 105 per domain).
  - **Question Bank 2** (`question-bank-2.md`) has 473 separate questions, with IDs `D<domain>-<nnn>` numbered per domain. Bank 2 must not repeat Bank 1. 52 duplicates were removed on 2026-11-13. Before adding a question to either bank, check that the other bank doesn't already ask it.
  - `practice-exam-set-1.md` and `practice-exam-set-2.md` are 65-question mock exams (13/16/18/9/9 questions per domain, with a score tracker). Set 2 must not repeat scenarios from Set 1.
  - `aif-c01-questions.md` has 57 **collected** (not original) exam-style questions with domain tags, explanations, an answer key and a score tracker.
  - `exam-notes.md` and `extra-details-notes.md` are study notes. `extra-details-notes.md` has "Points to Remember" and "Exam Traps" sections for each domain.
  - `review-log.md` records where each file came from (AI-generated or collected) and the history of reviews. Every AWS file starts with a `> **Last reviewed:** YYYY-MM-DD …` line. After reviewing a file, update that line **and** add an entry to `review-log.md`. Don't mark content as verified unless it was actually checked against AWS documentation.

- **`study-plans/`**: day-by-day plans (AIF-C01 7-day, SDET Selenium/Java 2-week, Playwright 5-day) that link to specific question headings. The SDET plan is meant to cover every Deloitte and Capgemini question, so when you add an interview question, add it to a day in that plan.

## Question schema (all new question files)

[docs/question-schema.md](docs/question-schema.md) is the canonical format, with a machine-readable form in `docs/question.schema.json` and a starting file in `docs/templates/question-file-template.md`. In short:

- YAML front matter: `schema: question-file/v1`, `title`, `id_prefix`, `topic`, `source`, `last_verified`.
- One H1, then H2 sections, then one `### Q<n>. <title>` per question.
- A `<!-- meta: {id, type, difficulty, …} -->` comment directly under each question heading.
- Options `- A.` …, and the answer inside `<details><summary>Show answer</summary>`.

IDs are `<id_prefix>-<nnn>`, unique across the repo, and never reused or renumbered. Register new prefixes in the schema doc's §5 table. Existing files haven't been migrated yet (roadmap C-04). Until a file is migrated, keep the format it already uses, as listed below.

## Question formats in existing (unmigrated) files

When editing an existing file, **match the format that file already uses**:

| Format | Used in |
|---|---|
| `#### Qn · Domain N · Difficulty · Type`, options `- A.`, then `<details><summary>Show answer</summary>` with `**Answer: X**` and an explanation | `ch*.md`, `practice-exam-set-2.md` |
| `### Qn`, `*Domain N: Name · Type*`, options, then `<details>` with `**Answer: X**` and an explanation, plus an answer key and score tracker at the end | `aif-c01-questions.md` |
| `### D1-001`, `*Type \| Difficulty*`, `**Question:**`, inline `**Answer:**` / `**Explanation:**`, plus an answer key at the end | `question-bank-2.md` |
| `### Qn` with options, answers collected in an `# Answer Key` section at the end | `practice-exam-set-1.md` |
| `## N) Question`, then a free-form answer | Capgemini, Deloitte |
| `### N. Question`, then a free-form answer | Playwright |

When you add or remove AWS questions, update every count that depends on them: summary and contents tables, domain ranges such as `Q1–Q13`, answer keys, score trackers, the "N original practice questions" lines, and the counts in `README.md`. In `question-bank-2.md`, the summary tables and answer key must match the per-question `*Type | Difficulty*` and `**Answer:**` lines.

## Content conventions

- Use current AWS feature names: **Amazon Bedrock Guardrails / Agents / Knowledge Bases** (not "… for Amazon Bedrock"). Mark retired services, such as Amazon Forecast and Fraud Detector, as "closed to new customers" instead of deleting them. The exam can still ask what they do.
- The question banks and mock exams are original AI-generated material and say they aren't real exam questions. Keep those disclaimers.
- Interview answers aim to be "manager-friendly": a short definition or structure first, then a code example in a fenced block with a language tag. Some older files use indented code blocks. Prefer fenced blocks in new content.
- `Deloitte/automation-test-engineer.md` uses Unicode math-bold characters in some headings. Use plain text in new headings.

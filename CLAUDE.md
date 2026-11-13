# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A Markdown-only knowledge base for SDET/QA interview preparation plus AWS Certified AI Practitioner (AIF-C01) exam study material. There is no application code, no package manager, and no build, lint, or test tooling. Code inside the Markdown (Java, TypeScript, SQL, YAML) is illustrative and is not compiled or run anywhere. "Verifying" a change means checking that the Markdown renders correctly on GitHub (headings, tables, fenced code, `<details>` blocks) and that answers are technically accurate.

`ProductRoadmap.md` holds the planned work and the known defects (W1–W13, with completed items struck through). Read it before making structural changes, so edits line up with the planned direction: one question schema and a later Markdown → JSON parser.

## Naming

Folders and content files use kebab-case with no spaces or `&` (`Capgemini/l2-interview-questions.md`, `AWS-AI-Practitioner/ch1-2.md`). The root `README.md`, `CLAUDE.md`, `ProductRoadmap.md` and `LICENSE` are the exceptions. When you rename a file, update the links in `README.md` and any cross-links in the AWS files (the `ch*.md`, `question-bank-2.md` and `review-log.md` files link to each other).

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

## Question formats in use

Files don't share one format. When editing a file, **match the format that file already uses**:

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

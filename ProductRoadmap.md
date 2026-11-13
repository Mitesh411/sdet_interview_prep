# Product Roadmap: SDET Interview Prep

**Owner:** Product (AI) · **Last updated:** 2026-11-13 · **Horizon:** 4 quarters

---

## 1. Executive Summary

`sdet_interview_prep` is a Markdown knowledge base. It has two parts: real interview Q&A for SDET/QA roles (Capgemini, Deloitte, Playwright), and a large AWS Certified AI Practitioner (AIF-C01) study set. The content is good. The answers are detailed, include runnable code and are written for interviews. The product around that content is missing. There is no README, no navigation, no consistent format, no way to test yourself interactively, and no quality checks.

This roadmap turns the repo from a **folder of notes** into a **structured, searchable, self-testing prep platform**. It has four phases:

1. **Foundation (P0):** fix defects, add a README and navigation, and make the content consistent.
2. **Content Quality & Coverage (P1):** finish incomplete guides, remove duplicates, and fill topic gaps that matter in SDET interviews.
3. **Platform (P1/P2):** publish a static site, generate quizzes from one source of truth, and track progress.
4. **AI-Assisted Learning (P2/P3):** an AI mock interviewer, answer grading and question generation, with human review of all AI-written content.

---

## 2. Current State Assessment

### 2.1 Inventory

| Area | Files | Approx. size | Notes |
|---|---|---|---|
| AWS AI Practitioner (AIF-C01) | 10 `.md` in `AWS-AI-Practitioner/` | ~820 KB | Bank 1 (525 Qs) + Bank 2 (473 Qs, deduplicated 2026-11-13), 2 × 65-question mock exams, 57 exam-style Qs, 2 sets of study notes, review log |
| Playwright | `100_Playwright_Interview_Questions.md` + `.pdf` + `playwright.md` | ~67 KB | Q1–80 complete; Q81–100 are stubs |
| Deloitte | `Automation_Test_Engineer.md`, `Sr QA.md` | ~37 KB | 10 + ~22 Qs, Selenium/Java/TestNG/SQL |
| Capgemini | `L2_interview_Questions.md` | ~10 KB | 15 Qs, metrics/CI/Git/data validation |
| Repo meta | `README.md`, `LICENSE` (MIT) | — | README has only a title |

### 2.2 Strengths

- **Strong answers.** They include code (Java, TypeScript, SQL, YAML), framework layouts, design patterns and "manager-friendly" framing.
- **Based on real interviews.** Company- and round-specific questions (Deloitte Round 1 and Round 2) are scarce and valuable.
- **Thorough certification content.** The AWS question bank has domain/difficulty/type metadata, explanations for wrong options, score trackers and "exam traps" sections.
- **Clear license** (MIT), so others can contribute and fork.

### 2.3 Weaknesses and Defects Found

| # | Finding | Location | Impact |
|---|---|---|---|
| W1 | README is empty (title only). There is no index, purpose or how-to-use | `README.md` | New visitors can't find their way around; low discoverability |
| W2 | Playwright guide is incomplete. Q81–90 are one-line bold stubs, Q91–100 are missing, and the "100 questions" title over-promises | `Playwright/100_Playwright_Interview_Questions.md` (line ~2709+) | Credibility; the content doesn't match its title |
| W3 | Placeholder file whose only content is `test` | `Playwright/playwright.md` | Noise |
| ~~W4~~ | ~~The same 525-question bank is stored twice in different formats (`AllChapters.md` vs `Ch1&2.md` + `Ch3&4.md` + `Ch5.md`), and the question wording differs between copies~~ | ~~`AWS AI Practitioner/Claude/`~~ | ✅ **Done 2026-11-13.** Analysis showed these were two *different* banks that overlapped, not one bank stored twice. 52 duplicate questions were removed from Bank 2 (now `question-bank-2.md`, 473 Qs), so the banks give 998 distinct questions |
| W5 | Five different question formats: `- [x]` checkboxes (answer visible), inline `**Answer:**`, `<details>` reveal, a separate answer key, and bold numbering | AWS + Playwright | Can't be parsed automatically; inconsistent experience |
| ~~W6~~ | ~~`AIF-C01.md` shows the correct answer inline (`[x]`), so it can't be used for self-testing. It also has no title, intro or numbering~~ | ~~`AIF-C01.md`~~ | ✅ **Done 2026-11-13** (see C-03) |
| W7 | Folder name typo: `Capegemini` should be `Capgemini`. The `Claude/` folder name describes how the content was made, not what it is | Root, AWS folder | Professionalism, findability |
| W8 | Headings use Unicode "math bold" characters (`𝗥𝗼𝘂𝗻𝗱 𝟭`), and several `#` H1s are used as sub-headings | `Deloitte/Automation_Test_Engineer.md` | Breaks search, anchors and screen readers |
| W9 | Code samples are indented, not fenced, so they get no syntax highlighting | `Capegemini/…`, `Deloitte/Sr QA.md` | Harder to read |
| W10 | A binary PDF copy of a Markdown file is committed | `Playwright/*.pdf` | Copies drift; repo grows |
| W11 | No `.gitignore`, no CI, no Markdown/link linting, no CONTRIBUTING guide | Root | Quality regressions go unnoticed |
| W12 | Many core SDET topics are missing (API testing, Cypress, Appium, performance, BDD, DSA for SDET, behavioral) | — | Narrow audience |
| ~~W13~~ | ~~AWS content is AI-generated with no recorded review or "last verified" date against the current exam guide~~ | ~~AWS folder~~ | ✅ **Done 2026-11-13.** `AWS-AI-Practitioner/review-log.md` records where each file came from and the review history. Every AWS file has a "Last reviewed" line, and stale feature names were updated. A full expert check of every question is still open under C-05 |

---

## 3. Prioritization Framework

Each item is scored on **Impact** (learner value, reach, credibility) and **Feasibility** (effort, dependencies, risk). Each is scored 1–5.

| Priority | Meaning | Rule |
|---|---|---|
| **P0** | Do now | Fixes a defect or unblocks everything else; low effort |
| **P1** | Next | High impact, moderate effort |
| **P2** | Later | High impact, higher effort or depends on P1 |
| **P3** | Explore | Strategic bets; validate before investing |

**Estimation:** 1 story point (SP) ≈ 2 hours of focused work for one contributor. Hours are given for planning. Testing effort covers content review (accuracy, rendering, links) for documentation work, and functional/automated testing for code.

---

## 4. Roadmap by Phase

### Phase 0: Foundation (P0) · Target: Weeks 1–2

| ID | Task | Description | Impact | Feasibility | Dev Effort | Test Effort |
|---|---|---|---|---|---|---|
| F-01 | **Write a real README** | Purpose, audience, folder map, how to use (study vs. self-test), table of all guides with question counts, contribution link, disclaimer that questions are not real exam content | 5 | 5 | 2 SP (4h) | 0.5 SP (1h) |
| F-02 | **Remove/replace placeholder** | Delete `Playwright/playwright.md`, or turn it into a Playwright section index | 2 | 5 | 0.25 SP (0.5h) | 0.25 SP (0.5h) |
| ~~F-03~~ | ~~**Fix naming**~~ | ~~Rename `Capegemini/` to `Capgemini/` and `AWS AI Practitioner/Claude/` to `AWS-AI-Practitioner/`. Use kebab-case file names with no `&` or spaces (e.g. `ch1-2.md`). Update internal links~~ ✅ **Done 2026-11-13** | 3 | 5 | 1 SP (2h) | 0.5 SP (1h) |
| F-04 | **Fix heading structure** | Replace Unicode bold characters with plain text. Use one H1 per file and H2/H3 for rounds and questions. Fence all code blocks with language tags | 3 | 5 | 1.5 SP (3h) | 0.5 SP (1h) |
| F-05 | **Add repo hygiene** | `.gitignore`, `CONTRIBUTING.md` (question template, style guide, review rule for AI-generated content), issue templates ("Add interview experience", "Report incorrect answer") | 4 | 5 | 1.5 SP (3h) | 0.5 SP (1h) |
| F-06 | **Markdown CI** | GitHub Action running `markdownlint`, `lychee` (link checker) and a spell check with a custom tech dictionary on every PR | 4 | 5 | 2 SP (4h) | 1 SP (2h) |
| F-07 | **Remove committed PDF** | Delete the PDF from the repo. Generate PDFs on release instead (see P-04) | 2 | 5 | 0.25 SP (0.5h) | 0.25 SP (0.5h) |
| | | | | **Phase total** | **8.5 SP (17h)** | **3.5 SP (7h)** |

**Exit criteria:** README lists every guide; CI is green on `main`; no lint or link errors.

---

### Phase 1: Content Quality & Coverage (P1) · Target: Weeks 3–8

#### 1A. Consistency and single source of truth

| ID | Task | Description | Impact | Feasibility | Dev Effort | Test Effort |
|---|---|---|---|---|---|---|
| C-01 | **Define a canonical question schema** | One Markdown pattern for every Q&A. Front-matter-style metadata (`id`, `topic`, `company`, `role`, `round`, `difficulty`, `type`, `tags`, `last_verified`), then the question, options, and a `<details>` answer with an explanation. Document it in CONTRIBUTING | 5 | 4 | 2 SP (4h) | 1 SP (2h) |
| ~~C-02~~ | ~~**Deduplicate the AWS 525-question bank**~~ | ~~Pick one copy, merge any better wording, and delete the other copy~~ ✅ **Done 2026-11-13 as part of W4.** The banks turned out to be different question sets, so only the 52 overlapping questions were removed (from `question-bank-2.md`) instead of deleting a whole file | 5 | 4 | 3 SP (6h) | 2 SP (4h) |
| ~~C-03~~ | ~~**Convert `AIF-C01.md` to self-test format**~~ | ~~Add a title and intro, number the 57 questions, move answers into `<details>`, and add explanations for each~~ ✅ **Done 2026-11-13.** Now `aif-c01-questions.md`, with domain tags, explanations, an answer key and a score tracker. All 57 answers were checked | 4 | 4 | 4 SP (8h) | 2 SP (4h) |
| C-04 | **Normalize the remaining files to the schema** | Migrate the Playwright, Deloitte, Capgemini and both 65-question mock exams. Add a script that validates the schema in CI | 4 | 3 | 6 SP (12h) | 3 SP (6h) |
| C-05 | **Accuracy review and "last verified" stamps** | Check the AWS content against the current official AIF-C01 exam guide and service docs, and Playwright content against the current stable release. Record a `last_verified` date per file | 5 | 3 | 5 SP (10h) | 3 SP (6h) |

#### 1B. Complete existing guides

| ID | Task | Description | Impact | Feasibility | Dev Effort | Test Effort |
|---|---|---|---|---|---|---|
| C-06 | **Complete Playwright Q81–100** | Expand the 10 stubs (CI, Docker, etc.) into full answers and write Q91–100: sharding, component testing, `expect.poll`, API + UI hybrid, auth state reuse, fixtures, test tagging/grep, trace viewer in CI, accessibility checks, Selenium migration | 5 | 4 | 6 SP (12h) | 2 SP (4h) |
| C-07 | **Add Playwright "hands-on" companion project** | A small runnable `playwright-examples/` TypeScript project showing the patterns from the guide (POM, fixtures, API mocking, visual tests), with CI running it | 4 | 3 | 8 SP (16h) | 4 SP (8h) |

#### 1C. Close coverage gaps (new content)

Each module: 25–40 questions in the canonical schema, with code samples where relevant.

| ID | Module | Why it matters | Impact | Feasibility | Dev Effort | Test Effort |
|---|---|---|---|---|---|---|
| C-08 | **API Testing** (REST Assured, Postman/Newman, contract testing, schema validation, auth flows) | Asked in nearly every SDET loop | 5 | 4 | 6 SP (12h) | 2 SP (4h) |
| C-09 | **Java for SDET** (collections, OOP, exceptions, streams, common coding problems) | The Deloitte files show this comes up a lot; today it's scattered | 5 | 4 | 6 SP (12h) | 2 SP (4h) |
| C-10 | **SQL for testers** (joins, window functions, data validation queries) | Frequent topic; currently ~3 questions | 4 | 5 | 4 SP (8h) | 1.5 SP (3h) |
| C-11 | **CI/CD & DevOps for QA** (Jenkins, GitHub Actions, Docker, test parallelization, flaky test strategy) | Required at mid/senior level | 4 | 4 | 5 SP (10h) | 2 SP (4h) |
| C-12 | **Test Strategy & Behavioral** (STAR answers, test planning, risk-based testing, metrics, "tell me about a production bug") | Decides senior and lead interviews | 5 | 4 | 5 SP (10h) | 1.5 SP (3h) |
| C-13 | **Cypress, Appium, Performance (k6/JMeter), BDD (Cucumber)** | Broadens the audience | 3 | 3 | 12 SP (24h) | 4 SP (8h) |
| C-14 | **AI in Testing** (LLM-assisted test generation, testing LLM apps, evals, prompt-injection testing, Copilot usage) | Fast-growing interview topic; builds on the AWS AI content | 4 | 4 | 5 SP (10h) | 2 SP (4h) |
| C-15 | **More company experiences** (TCS, Infosys, Accenture, Cognizant, product companies) | Real experiences are the repo's differentiator | 5 | 3 | 2 SP (4h) per company | 1 SP (2h) per company |
| | | | | **Phase total (excl. C-15)** | **77 SP (154h)** | **32 SP (64h)** |

**Exit criteria:** every file passes the schema validator; no duplicate banks; Playwright guide has 100 full answers; at least 4 of C-08 to C-14 are shipped.

---

### Phase 2: Platform (P1/P2) · Target: Weeks 6–14

| ID | Task | Description | Priority | Impact | Feasibility | Dev Effort | Test Effort |
|---|---|---|---|---|---|---|---|
| P-01 | **Static documentation site** | Publish with MkDocs Material (or Docusaurus) on GitHub Pages: sidebar navigation, full-text search, dark mode, mobile layout, copy-code buttons | P1 | 5 | 5 | 5 SP (10h) | 2 SP (4h) |
| P-02 | **Question parser → JSON dataset** | Script (Python/TS) that parses the canonical Markdown into `questions.json`, run in CI. This becomes the single data source for quizzes, stats and AI features | P1 | 5 | 4 | 5 SP (10h) | 3 SP (6h), unit tests for the parser |
| P-03 | **Interactive quiz mode** | Web page using `questions.json`: filter by topic, company, difficulty and domain; timed mock-exam mode (e.g. 65 Qs / 90 min for AIF-C01); instant feedback with explanations; per-domain score breakdown | P2 | 5 | 3 | 13 SP (26h) | 6 SP (12h), with Playwright E2E tests for the quiz |
| P-04 | **Release PDFs and print views** | GitHub Action that builds PDFs per guide on each tag (via Pandoc or a site plugin), replacing committed PDFs | P2 | 3 | 4 | 3 SP (6h) | 1 SP (2h) |
| P-05 | **Progress tracking and spaced repetition** | Local-only (browser storage) tracking of answered, wrong and bookmarked questions; a "review my weak areas" deck using an SM-2-style schedule | P2 | 4 | 3 | 8 SP (16h) | 4 SP (8h) |
| P-06 | **Flashcard export** | Export the dataset to Anki (`.apkg`/CSV) and Quizlet CSV | P2 | 3 | 4 | 3 SP (6h) | 1 SP (2h) |
| P-07 | **Content dashboard** | Auto-generated stats page: questions by topic, difficulty and company; staleness (`last_verified` older than 6 months); coverage against the AIF-C01 exam guide task statements | P2 | 3 | 4 | 4 SP (8h) | 1.5 SP (3h) |
| P-08 | **Study plans** | Curated paths: "7-day AIF-C01 cram", "2-week SDET (Selenium/Java)", "Playwright in 5 days", each linking to questions and notes in order | P2 | 4 | 5 | 3 SP (6h) | 1 SP (2h) |
| | | | | | **Phase total** | **44 SP (88h)** | **19.5 SP (39h)** |

**Exit criteria:** site is live; quiz works for all question banks; parser runs in CI and fails the build on schema violations.

---

### Phase 3: AI-Assisted Learning (P2/P3) · Target: Weeks 12–24

All AI features read from the P-02 dataset. They require **human review before AI-generated content is merged**, and run on the user's own API key or a small serverless backend with rate limits.

| ID | Task | Description | Priority | Impact | Feasibility | Dev Effort | Test Effort |
|---|---|---|---|---|---|---|---|
| A-01 | **AI mock interviewer** | Chat-based interview by role (SDET I/II, Sr QA, Lead) and company style. Asks follow-ups, handles "write code" questions, and ends with a scored debrief that links to relevant repo questions | P2 | 5 | 3 | 13 SP (26h) | 8 SP (16h), including a prompt eval suite |
| A-02 | **Free-text answer grading** | The learner types an answer; an LLM grades it against the reference answer and a rubric (correctness, completeness, clarity) and says what was missing | P2 | 5 | 3 | 8 SP (16h) | 5 SP (10h), with a calibration set of 50 human-graded answers |
| A-03 | **Question generation pipeline with review gate** | Generate draft questions for gap topics as a PR. Automatically check schema, duplicates (embedding similarity) and answer consistency; a human must approve | P2 | 4 | 3 | 8 SP (16h) | 5 SP (10h) |
| A-04 | **Accuracy auditor** | Scheduled job that flags questions likely outdated (renamed AWS services, deprecated Playwright APIs) and opens issues with evidence links | P3 | 4 | 3 | 6 SP (12h) | 3 SP (6h) |
| A-05 | **Semantic search and "explain like I'm new"** | Embedding search across all content plus on-demand simpler explanations and extra examples for any answer | P3 | 3 | 3 | 6 SP (12h) | 3 SP (6h) |
| A-06 | **Personalized study plan** | Builds a plan from quiz history (P-05) and the target interview date and role | P3 | 4 | 2 | 8 SP (16h) | 4 SP (8h) |
| A-07 | **Resume → likely questions** | Upload a job description and resume; get a ranked list of likely questions from the bank plus gaps to study. Processed in the session only; nothing is stored | P3 | 4 | 3 | 6 SP (12h) | 4 SP (8h), including privacy tests |
| | | | | | **Phase total** | **55 SP (110h)** | **32 SP (64h)** |

**AI guardrails (required for all of Phase 3):**
- Mark AI-generated content in metadata (`source: ai-generated`, `reviewed_by`).
- Keep an eval set (≥100 cases) for A-01 and A-02 and run it in CI on prompt changes.
- Never store user resumes or answers on the server. Show a clear data notice.
- Run cost and rate limits plus abuse protection on any hosted endpoint.

---

### Phase 4: Community & Growth (P3) · Ongoing

| ID | Task | Description | Impact | Feasibility | Dev Effort | Test Effort |
|---|---|---|---|---|---|---|
| G-01 | **"Share your interview" submission flow** | Issue form → auto-formatted PR draft in schema; anonymization checklist (no names or NDA material) | 4 | 4 | 3 SP (6h) | 1 SP (2h) |
| G-02 | **Contributor recognition** | All-contributors bot, CHANGELOG, monthly release notes | 2 | 5 | 1 SP (2h) | 0.5 SP (1h) |
| G-03 | **Answer voting / "asked recently" signal** | GitHub Discussions or reactions surfaced on the site to show which questions are trending | 3 | 3 | 5 SP (10h) | 2 SP (4h) |
| G-04 | **More certifications** | ISTQB Foundation, AWS Cloud Practitioner, Azure AI-900, using the same schema and quiz engine | 4 | 3 | 15 SP (30h) per cert | 6 SP (12h) per cert |
| G-05 | **Localization** | Hindi translation of the highest-traffic guides (reviewed by a person) | 2 | 2 | 10 SP (20h) | 4 SP (8h) |

---

## 5. Consolidated Priority Backlog (Top 15)

Ranked by Impact × Feasibility, then by dependencies.

| Rank | ID | Task | Priority | Dev | Test | Depends on |
|---|---|---|---|---|---|---|
| 1 | F-01 | Write README | P0 | 4h | 1h | — |
| 2 | F-06 | Markdown CI (lint, links, spell) | P0 | 4h | 2h | F-04 |
| 3 | F-05 | CONTRIBUTING + templates | P0 | 3h | 1h | — |
| 4 | ~~F-03~~/F-04 | ~~Naming~~ (✅ done) + heading fixes | P0 | 5h | 2h | — |
| 5 | ~~C-02~~ | ~~Deduplicate AWS bank~~ ✅ Done | P1 | 6h | 4h | ~~C-01~~ |
| 6 | C-06 | Complete Playwright Q81–100 | P1 | 12h | 4h | — |
| 7 | C-01 | Canonical question schema | P1 | 4h | 2h | — |
| 8 | P-01 | Static docs site | P1 | 10h | 4h | F-03 |
| 9 | ~~C-03~~ | ~~Fix `AIF-C01.md` self-test format~~ ✅ Done | P1 | 8h | 4h | ~~C-01~~ |
| 10 | C-08 | API Testing module | P1 | 12h | 4h | C-01 |
| 11 | C-12 | Test Strategy & Behavioral module | P1 | 10h | 3h | C-01 |
| 12 | P-02 | Markdown → JSON parser | P1 | 10h | 6h | C-04 |
| 13 | C-05 | Accuracy review + `last_verified` | P1 | 10h | 6h | C-02 |
| 14 | P-03 | Interactive quiz mode | P2 | 26h | 12h | P-02 |
| 15 | A-01 | AI mock interviewer | P2 | 26h | 16h | P-02 |

---

## 6. Effort Summary

| Phase | Dev Effort | Test Effort | Total | Calendar (1 contributor, ~10h/week) |
|---|---|---|---|---|
| 0: Foundation | 8.5 SP (17h) | 3.5 SP (7h) | 24h | ~2 weeks |
| 1: Content (excl. C-15) | 77 SP (154h) | 32 SP (64h) | 218h | ~5 months (can be parallelized across contributors) |
| 2: Platform | 44 SP (88h) | 19.5 SP (39h) | 127h | ~3 months |
| 3: AI Learning | 55 SP (110h) | 32 SP (64h) | 174h | ~4 months |
| 4: Community (excl. per-unit items) | 9 SP (18h) | 3.5 SP (7h) | 25h | Ongoing |
| **Total** | **193.5 SP (387h)** | **90.5 SP (181h)** | **568h** | |

The calendar estimates assume one part-time contributor. With 3 contributors working in parallel on content (Phase 1) and platform (Phase 2), Phases 0–2 fit in about one quarter.

---

## 7. Timeline (Indicative)

```
Quarter 1 (Wk 1-12)
  Wk 1-2   ████ Phase 0: README, naming, CI, CONTRIBUTING
  Wk 3-8   ████████████ Phase 1A/1B: schema, dedupe, Playwright 81-100, AIF-C01 fix
  Wk 6-12  ██████████████ Phase 1C: API, Java, SQL, Behavioral modules
  Wk 6-10  ██████████ Phase 2: docs site + parser
Quarter 2 (Wk 13-24)
  Wk 11-16 ████████████ Phase 2: quiz mode, progress tracking, PDFs
  Wk 12-24 ████████████████████████ Phase 3: mock interviewer, grading, generation pipeline
Quarter 3-4
           Phase 3 P3 items, Phase 4 community and new certifications
```

---

## 8. Success Metrics

| Metric | Baseline (today) | Target (end of Q2) |
|---|---|---|
| Files passing schema + lint | 0% | 100% |
| Duplicate questions across AWS banks | 52 (originally misreported as ~570 KB) | ✅ 0 (2026-11-13) |
| SDET topics covered (of 12 core topics) | 4 | 10+ |
| Total SDET (non-cert) questions with full answers | ~125 | 400+ |
| Questions with `last_verified` < 6 months | 0% → AWS files stamped 2026-11-13 (structural review) | 90% (expert-verified) |
| Site monthly visitors / GitHub stars | n/a / current | Track; +50% QoQ |
| Quiz completions per month | n/a | Track from launch |
| External contributions merged per quarter | 0 | 5+ |
| AI grader agreement with human grading (A-02) | n/a | ≥ 85% |

---

## 9. Risks & Mitigations

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| AI-generated content contains factual errors | High | High | C-05 review, `reviewed_by` metadata, A-04 auditor, "Report incorrect answer" issue template |
| AWS / Playwright changes make content stale | High | Medium | `last_verified` stamps, staleness dashboard (P-07), quarterly review |
| Shared interview content breaches an NDA or names individuals | Medium | High | Anonymization checklist in G-01; maintainers review before merge |
| Scope creep into a full LMS | Medium | Medium | Keep the platform static-first; AI features opt-in, using the user's own key |
| Hosted AI features run up costs | Medium | Medium | Bring-your-own-key by default; rate limits; budget alerts |
| Single maintainer becomes a bottleneck | High | Medium | CONTRIBUTING, templates and CI automate most review checks |

---

## 10. Immediate Next Steps (This Week)

1. Merge **F-01 (README)** and **F-02 (remove placeholder)**.
2. Agree the **canonical question schema (C-01)**. It unblocks dedup, the parser, the quiz and all AI work.
3. Open GitHub issues for every item in Section 5 with labels `P0`–`P3`, `content`, `platform` and `ai`, and a size label in story points.
4. Start **C-06 (Playwright Q81–100)**. It is the most visible content gap.

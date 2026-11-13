# SDET Interview Prep

Study material for **SDET / QA Automation interviews** and the **AWS Certified AI Practitioner (AIF-C01)** exam. It includes questions from real interviews with detailed answers and code, a 100-question Playwright guide, and more than 700 AIF-C01 practice questions with explanations.

Everything is plain Markdown. Read it on GitHub or clone it and open it in any Markdown viewer. Nothing needs to be installed.

---

## Contents

### Company Interview Experiences

Real questions grouped by company and round, each with a long-form answer and code samples (Java, TypeScript, SQL, YAML).

| Company | Role / Round | Questions | Topics |
|---|---|---|---|
| [Capgemini](Capegemini/L2_interview_Questions.md) | QA – L2 | 15 | Test metrics, backend data validation, GitHub Actions, Git, TypeScript vs JavaScript, Selenium/Playwright protocols, Jenkins scheduling, PDF/Excel validation, schema validation |
| [Deloitte](Deloitte/Automation_Test_Engineer.md) | Automation Test Engineer – Technical Screening | 10 | Framework design (POM, design patterns), Selenium + Java, TestNG `@DataProvider`, waits, Jenkins CI, Extent/Allure reports, REST Assured, Git workflow |
| [Deloitte](Deloitte/Sr%20QA.md) | Sr. QA – Technical + Techno-Managerial | 37 | Java coding, SQL (second-highest salary, joins), collections, exceptions, Selenium (locators, waits, alerts, calendars, tabs), smoke vs sanity, regression selection, JMeter, Jenkins cron |

### Playwright

| Guide | Coverage |
|---|---|
| [100 Playwright Interview Questions](Playwright/100_Playwright_Interview_Questions.md) ([PDF](Playwright/100%20Playwright%20Interview%20Questions.pdf)) | Basics, locators & UI interaction, advanced selectors & assertions, actions & events, network & advanced features. Q1–80 have full answers with code. Q81–90 are short quick-reference notes, and Q91–100 haven't been written yet ([roadmap](ProductRoadmap.md)). |

### AWS Certified AI Practitioner (AIF-C01)

All material is organized by the five official exam domains:

| Domain | Weight |
|---|---|
| 1. Fundamentals of AI and ML | 20% |
| 2. Fundamentals of Generative AI | 24% |
| 3. Applications of Foundation Models | 28% |
| 4. Guidelines for Responsible AI | 14% |
| 5. Security, Compliance, and Governance | 14% |

**Study notes**

| File | Use it for |
|---|---|
| [ExamNotes.md](AWS%20AI%20Practitioner/Claude/ExamNotes.md) | Overview: study time, preparation, useful links, core concepts, the ML pipeline, AWS services, comparison tables |
| [ExtraDetailsNotes.md](AWS%20AI%20Practitioner/Claude/ExtraDetailsNotes.md) | Detailed notes and cram guide for each domain, with **Points to Remember** and **Exam Traps** sections |

**Practice questions**

| File | Questions | Format |
|---|---|---|
| [Ch1&2.md](AWS%20AI%20Practitioner/Claude/Ch1%262.md) · [Ch3&4.md](AWS%20AI%20Practitioner/Claude/Ch3%264.md) · [Ch5.md](AWS%20AI%20Practitioner/Claude/Ch5.md) | 525 (105 per domain) | Labeled by domain, difficulty and type. Answers are hidden in collapsible **Show answer** blocks |
| [AllChapters.md](AWS%20AI%20Practitioner/Claude/AllChapters.md) | 525 | The same question bank in one file, with inline answers, explanations and a full answer key |
| [65 Practice Questions.md](AWS%20AI%20Practitioner/Claude/65%20Practice%20Questions.md) | 65 | Full mock exam weighted by domain, answer key at the end, score tracker |
| [65 Practice Questions Set 2.md](AWS%20AI%20Practitioner/Claude/65%20Practice%20Questions%20Set%202.md) | 65 | Second mock exam with all-new scenarios, collapsible answers, score tracker |
| [AIF-C01.md](AWS%20AI%20Practitioner/Claude/AIF-C01.md) | 57 | Exam-style questions with the correct option checked (good for review, not for self-testing) |

> **Disclaimer:** The AWS questions are original study material, **not** real exam questions. AWS services change over time, so check details against the [official AIF-C01 exam guide](https://aws.amazon.com/certification/certified-ai-practitioner/) and the AWS documentation before your exam.

---

## How to Use

**Interview prep**
1. Read the company write-up for the role you're targeting, then the Playwright guide if the job uses it.
2. Try each question out loud before reading the answer. Many answers start with a short summary you can say first, then go into detail.
3. Type out and run the code samples yourself. They're illustrative and aren't kept as a runnable project.

**AIF-C01 exam prep**
1. Read `ExamNotes.md` for the overview, then `ExtraDetailsNotes.md` one domain at a time.
2. Practice each domain in the `Ch*.md` banks. Hide the answers and check yourself after each question.
3. Take `65 Practice Questions.md` as a timed mock exam (90 minutes) and fill in the score tracker. Aim for **80%+** (52/65).
4. Go back over the "Exam Traps" for your weakest domains, then take **Set 2** as a final check.

---

## Repository Structure

```
.
├── Capegemini/              # Capgemini L2 QA interview Q&A
├── Deloitte/                # Deloitte Automation Test Engineer + Sr. QA interviews
├── Playwright/              # 100 Playwright interview questions (.md + .pdf)
├── AWS AI Practitioner/
│   └── Claude/              # AIF-C01 study notes, question banks, mock exams
├── ProductRoadmap.md        # Planned improvements, known issues, priorities
├── CLAUDE.md                # Guidance for AI coding assistants working on this repo
└── LICENSE                  # MIT
```

---

## Roadmap

Planned work is tracked in [ProductRoadmap.md](ProductRoadmap.md). Highlights:
- Finishing the Playwright guide (Q81–100)
- Using one question format across all files and removing the duplicate AWS question bank
- New modules: API testing, Java for SDET, SQL, CI/CD, behavioral and test strategy, AI in testing
- A searchable static site with an interactive quiz and mock-exam mode
- AI-assisted mock interviews and answer grading

---

## Contributing

Contributions are welcome, especially **your own interview experiences**.

- Add new company material as `CompanyName/Role.md`, with questions as `## N) Question`, grouped under round headings.
- Put code in fenced blocks with a language tag (` ```java `, ` ```ts `, ` ```sql `).
- Leave out interviewer names and any material covered by an NDA.
- If you find an incorrect or outdated answer, open an issue or a PR with a source.

---

## License

[MIT](LICENSE) © 2025 Mitesh Dandade

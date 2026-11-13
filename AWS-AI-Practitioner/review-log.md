# AWS AI Practitioner Content: Review Log

This log records how the AIF-C01 material in this folder was produced and reviewed. Update it every time a file is reviewed, and update the **Last reviewed** line at the top of that file to match.

## Provenance

| File | Origin |
|---|---|
| `ch1-2.md`, `ch3-4.md`, `ch5.md` (Question Bank 1) | AI-generated (Claude), original practice questions |
| `question-bank-2.md` (Question Bank 2) | AI-generated (Claude), original practice questions |
| `practice-exam-set-1.md`, `practice-exam-set-2.md` | AI-generated (Claude), original practice questions |
| `exam-notes.md`, `extra-details-notes.md` | AI-assisted study notes |
| `aif-c01-questions.md` | Collected exam-style practice questions (not original to this repo). Explanations were added by Claude in review 2026-11-13 |

AI-generated content can contain factual errors. Treat the official AWS documentation as the source of truth.

## Reference

- Official exam guide: [AWS Certified AI Practitioner (AIF-C01)](https://docs.aws.amazon.com/aws-certification/latest/ai-practitioner-01/ai-practitioner-01.html)
- Domain weights used throughout: D1 20%, D2 24%, D3 28%, D4 14%, D5 14%. D1–D3 were confirmed against public exam-guide summaries on 2026-11-13, which name guide version 1.4 as current. D4 and D5 are taken from the earlier guide and weren't confirmed in this review. Check them against the official guide PDF.

## Review 2026-11-13 (Claude, AI-assisted)

**Scope:** every file in this folder. This was a structural and staleness review, **not** a line-by-line expert verification of all ~1,200 questions.

| Check | Result |
|---|---|
| Exam code and domain structure | Still AIF-C01, same 5 domains. D1–D3 weights confirmed; D4/D5 not confirmed (see Reference) |
| Duplicate questions between Question Bank 1 and Question Bank 2 | 52 duplicates removed from Bank 2 (525 → 473); the remaining 473 don't repeat Bank 1's question stems |
| Answer key consistency in `question-bank-2.md` | Answer key regenerated from the per-question answers; all match |
| Every answer in `aif-c01-questions.md` | All 57 marked answers checked by reasoning; explanation added to each |
| Renamed features | `Guardrails / Agents / Knowledge Bases for Amazon Bedrock` → `Amazon Bedrock Guardrails / Agents / Knowledge Bases` in all files |
| Retired or closed services | Amazon Forecast and Amazon Fraud Detector marked "closed to new customers" in `exam-notes.md` (already marked in `extra-details-notes.md`). The AWS Snowcone distractor is noted as discontinued in `aif-c01-questions.md` |

**Known open items for the next review**

- Most files say "Amazon SageMaker" for the service that was renamed **Amazon SageMaker AI** (December 2024). Both names are accepted for exam purposes, so these were left unchanged. `ch1-2.md` and `ch5.md` already use the new name.
- `aif-c01-questions.md` keeps the original distractor wording "Amazon Q in AWS Chatbot". AWS Chatbot is now *Amazon Q Developer in chat applications*.
- About 42 pairs of questions across the two banks cover related concepts with different scenarios. They were kept on purpose as extra practice.
- A domain expert has not yet verified every question and explanation against current AWS documentation. Record that review here when it's done.

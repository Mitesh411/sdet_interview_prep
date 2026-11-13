# AIF-C01 in 7 Days: Cram Plan

A one-week plan for the **AWS Certified AI Practitioner (AIF-C01)** exam, for people who already know basic cloud and ML vocabulary. It budgets about **3–4 hours a day** and uses only material in this repo. Days follow the exam's domain weights, so Domain 3 (28%) gets the most practice.

**How each study day works:** read the notes for the domain first, then answer the Question Bank 1 questions with the answers hidden. Write down the number of every question you miss, because Day 5 and Day 6 come back to them.

| Day | Focus | Exam weight | Questions | Time |
|---|---|---|---|---|
| 1 | Exam strategy + Domain 1: Fundamentals of AI and ML | 20% | 105 | ~3.5 h |
| 2 | Domain 2: Fundamentals of Generative AI | 24% | 105 | ~3.5 h |
| 3 | Domain 3: Applications of Foundation Models | 28% | 105 | ~4 h |
| 4 | Domains 4 and 5: Responsible AI; Security, Compliance, and Governance | 14% + 14% | 210 | ~4 h |
| 5 | Mock exam 1 (timed) + targeted review | All | 65 + review | ~3.5 h |
| 6 | Weak-domain drill + collected exam-style questions | All | ~100 | ~3.5 h |
| 7 | Mock exam 2 (timed) + final cram | All | 65 | ~3 h |

---

## Day 1: Exam strategy and Domain 1

- [ ] Read [Exam Overview & Strategy](../AWS-AI-Practitioner/extra-details-notes.md#0-exam-overview--strategy) (20 min).
- [ ] Skim [exam-notes.md](../AWS-AI-Practitioner/exam-notes.md) for the big picture: the ML pipeline, the AWS services, and the comparison tables (30 min).
- [ ] Read the [Domain 1 notes](../AWS-AI-Practitioner/extra-details-notes.md#domain-1-fundamentals-of-ai-and-ml-20), sections 1.1 to 1.10 (60 min).
- [ ] Answer [Bank 1, Domain 1](../AWS-AI-Practitioner/ch1-2.md#domain-1-fundamentals-of-ai-and-ml), Q1–Q105 (90 min).
- [ ] Finish with [Domain 1: Exam Traps](../AWS-AI-Practitioner/extra-details-notes.md#domain-1-exam-traps).

**Checkpoint:** 84+ of 105 correct (80%). If you scored lower, reread sections 1.7 (ML lifecycle) and 1.9 (evaluation metrics), which are the most-tested topics.

## Day 2: Domain 2

- [ ] Read the [Domain 2 notes](../AWS-AI-Practitioner/extra-details-notes.md#domain-2-fundamentals-of-generative-ai-24) (60 min).
- [ ] Answer [Bank 1, Domain 2](../AWS-AI-Practitioner/ch1-2.md#domain-2-fundamentals-of-generative-ai), Q106–Q210 (100 min).
- [ ] Finish with [Domain 2: Exam Traps](../AWS-AI-Practitioner/extra-details-notes.md#domain-2-exam-traps).

**Checkpoint:** 84+ of 105. Make sure you can explain tokens, embeddings, the context window, temperature and top-p without notes.

## Day 3: Domain 3, the heaviest domain

- [ ] Read the [Domain 3 notes](../AWS-AI-Practitioner/extra-details-notes.md#domain-3-applications-of-foundation-models-28). Spend extra time on RAG, the customization cost ladder and prompt engineering (75 min).
- [ ] Answer [Bank 1, Domain 3](../AWS-AI-Practitioner/ch3-4.md#domain-3-applications-of-foundation-models), Q211–Q315 (110 min).
- [ ] Finish with [Domain 3: Exam Traps](../AWS-AI-Practitioner/extra-details-notes.md#domain-3-exam-traps).

**Checkpoint:** 84+ of 105. Without notes, put the customization options in order from cheapest to most expensive: prompt engineering → RAG → fine-tuning → continued pre-training → pre-training.

## Day 4: Domains 4 and 5

- [ ] Read the [Domain 4 notes](../AWS-AI-Practitioner/extra-details-notes.md#domain-4-guidelines-for-responsible-ai-14) (40 min).
- [ ] Answer [Bank 1, Domain 4](../AWS-AI-Practitioner/ch3-4.md#domain-4-guidelines-for-responsible-ai), Q316–Q420 (75 min).
- [ ] Read the [Domain 5 notes](../AWS-AI-Practitioner/extra-details-notes.md#domain-5-security-compliance-and-governance-14) (40 min).
- [ ] Answer [Bank 1, Domain 5](../AWS-AI-Practitioner/ch5.md#domain-5-security-compliance-and-governance), Q421–Q525 (75 min).
- [ ] Finish with [Domain 4: Exam Traps](../AWS-AI-Practitioner/extra-details-notes.md#domain-4-exam-traps) and [Domain 5: Exam Traps](../AWS-AI-Practitioner/extra-details-notes.md#domain-5-exam-traps).

**Checkpoint:** 84+ of 105 for each domain. Know which service does what: Clarify (bias and explainability), Macie (PII in S3), CloudTrail (API audit), Artifact (compliance reports), Audit Manager (evidence) and PrivateLink (private access).

## Day 5: Mock exam 1

- [ ] Take [Practice Exam Set 1](../AWS-AI-Practitioner/practice-exam-set-1.md) **timed: 65 questions in 90 minutes**, with no notes.
- [ ] Mark it with the answer key and fill in the score tracker for each domain.
- [ ] Reread the explanation for every question you missed, plus the matching section of [extra-details-notes.md](../AWS-AI-Practitioner/extra-details-notes.md).
- [ ] Redo the Bank 1 questions you wrote down on Days 1–4.

**Checkpoint:** 52+ of 65 (80%). Below 45? Spend Day 6 entirely on your two weakest domains.

## Day 6: Weak-domain drill

- [ ] Use [Question Bank 2](../AWS-AI-Practitioner/question-bank-2.md) (473 questions, no repeats of Bank 1) for your **two weakest domains** from the Day 5 score tracker. Aim for about 40 questions per domain (90 min).
- [ ] Answer all 57 [collected exam-style questions](../AWS-AI-Practitioner/aif-c01-questions.md) and fill in their score tracker (60 min).
- [ ] Study the [Master Keyword → Service Map](../AWS-AI-Practitioner/extra-details-notes.md#6-master-keyword--service-map) until you can name the service for each keyword (30 min).

## Day 7: Mock exam 2 and final cram

- [ ] Take [Practice Exam Set 2](../AWS-AI-Practitioner/practice-exam-set-2.md) **timed: 65 questions in 90 minutes**. Its scenarios are all new.
- [ ] Review every miss.
- [ ] Read the [Final 1-Page Cram Sheet](../AWS-AI-Practitioner/extra-details-notes.md#7-final-1-page-cram-sheet) and the five "Exam Traps" sections one last time.

**Ready to book?** Two mock exams at 52+ of 65 and the 57 exam-style questions at 46+ means you're in good shape. AWS services change, so check anything surprising against the [official exam guide](https://docs.aws.amazon.com/aws-certification/latest/ai-practitioner-01/ai-practitioner-01.html).

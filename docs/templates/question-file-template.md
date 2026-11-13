---
schema: question-file/v1
title: "Company Name Role Interview"
id_prefix: company-role
topic: selenium
source: interview
company: Company Name
role: Role Title
last_verified: 2026-11-14
reviewed_by: your-github-handle
---

# Company Name Role Interview

One or two sentences: which company, role and rounds this covers, and when the interview took place (month and year is enough). Leave out interviewer names and anything covered by an NDA.

## Round 1: Technical

### Q1. What is the difference between findElement and findElements?
<!-- meta: {id: company-role-001, type: open-ended, difficulty: easy, round: "Round 1: Technical", tags: [selenium, locators]} -->

<details><summary>Show answer</summary>

`findElement` returns the first matching element and throws `NoSuchElementException` if nothing matches. `findElements` returns a list, which is empty when nothing matches.

```java
List<WebElement> rows = driver.findElements(By.cssSelector("table tr"));
```

</details>

### Q2. Which wait should you prefer for a button that becomes clickable after an API call?
<!-- meta: {id: company-role-002, type: single-choice, difficulty: medium, round: "Round 1: Technical", tags: [selenium, waits]} -->

- A. `Thread.sleep(5000)`
- B. An implicit wait of 30 seconds
- C. An explicit wait for `elementToBeClickable`
- D. Page refresh until the button appears

<details><summary>Show answer</summary>

**Answer:** C

**Explanation:** An explicit wait polls for exactly the condition you need and continues as soon as it's met. `Thread.sleep` always waits the full time, an implicit wait only checks that the element exists (not that it's clickable), and refreshing the page resets the state you're waiting for.

</details>

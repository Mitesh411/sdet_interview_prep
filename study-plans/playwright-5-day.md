# Playwright in 5 Days

A five-day plan for interviews where the automation stack is **Playwright with TypeScript**. It works through the [100 Playwright Interview Questions](../Playwright/100-playwright-interview-questions.md) guide in order, with a small hands-on project that grows each day. It budgets about **2–3 hours a day**.

**Before Day 1:** install Node.js 20+ and create a project with `npm init playwright@latest`. The hands-on tasks use Playwright's public demo app, [TodoMVC](https://demo.playwright.dev/todomvc), so you don't need your own site.

**How each study day works:** read each question's heading and answer it out loud before reading the answer, then run at least one code sample from that day in your own project.

| Day | Guide questions | Focus |
|---|---|---|
| 1 | Q1–Q20 | Setup, the test runner, auto-waiting, contexts, tracing and reports |
| 2 | Q21–Q40 | Locators and UI interaction |
| 3 | Q41–Q60 | Advanced selectors, assertions, network and navigation |
| 4 | Q61–Q80 | Mocking, auth, accessibility, visual tests, parallelism, flaky tests |
| 5 | Q81–Q90 + related questions + mock interview | CI/CD, Docker, and how Playwright compares with Selenium |

---

## Day 1: Foundations (Q1–Q20)

Start at [Q1: What is Playwright?](../Playwright/100-playwright-interview-questions.md#1-what-is-playwright) and work through to [Q20: How to view Playwright report?](../Playwright/100-playwright-interview-questions.md#20-how-to-view-playwright-report). Make sure you can explain these without notes:

- [ ] [Q2: Why use Playwright over Selenium?](../Playwright/100-playwright-interview-questions.md#2-why-use-playwright-over-selenium)
- [ ] [Q7: What is auto-waiting in Playwright?](../Playwright/100-playwright-interview-questions.md#7-what-is-auto-waiting-in-playwright)
- [ ] [Q9: Difference between page.locator() and page.$()](../Playwright/100-playwright-interview-questions.md#9-difference-between-pagelocator-and-page)
- [ ] [Q17: Difference between Browser and BrowserContext?](../Playwright/100-playwright-interview-questions.md#17-difference-between-browser-and-browsercontext)
- [ ] [Q18: What is tracing in Playwright?](../Playwright/100-playwright-interview-questions.md#18-what-is-tracing-in-playwright)

**Hands-on:** Record a TodoMVC flow with Codegen (`npx playwright codegen demo.playwright.dev/todomvc`). Run it in UI mode, then open its trace in the Trace Viewer.

## Day 2: Locators and UI interaction (Q21–Q40)

Start at [Q21: Types of locators in Playwright?](../Playwright/100-playwright-interview-questions.md#21-types-of-locators-in-playwright) and work through to [Q40: How to handle expandable menus?](../Playwright/100-playwright-interview-questions.md#40-how-to-handle-expandable-menus). Key questions:

- [ ] [Q21: Types of locators in Playwright?](../Playwright/100-playwright-interview-questions.md#21-types-of-locators-in-playwright)
- [ ] [Q22: How does Playwright handle dynamic elements?](../Playwright/100-playwright-interview-questions.md#22-how-does-playwright-handle-dynamic-elements)
- [ ] [Q27: What is filter() locator?](../Playwright/100-playwright-interview-questions.md#27-what-is-filter-locator)
- [ ] [Q29: How to wait for an element?](../Playwright/100-playwright-interview-questions.md#29-how-to-wait-for-an-element)
- [ ] [Q39: How to handle multi-tab scenarios?](../Playwright/100-playwright-interview-questions.md#39-how-to-handle-multi-tab-scenarios)

**Hands-on:** Write tests that add, complete and delete todos using only `getByRole`, `getByPlaceholder` and `getByText`, with no CSS or XPath.

## Day 3: Advanced selectors, assertions and network (Q41–Q60)

Start at [Q41: What are composite locators?](../Playwright/100-playwright-interview-questions.md#41-what-are-composite-locators) and work through to [Q60: How to evaluate JavaScript in page context?](../Playwright/100-playwright-interview-questions.md#60-how-to-evaluate-javascript-in-page-context). Key questions:

- [ ] [Q42: How to use role locators?](../Playwright/100-playwright-interview-questions.md#42-how-to-use-role-locators)
- [ ] [Q43: How to handle shadow DOM?](../Playwright/100-playwright-interview-questions.md#43-how-to-handle-shadow-dom)
- [ ] [Q48: How to assert text content?](../Playwright/100-playwright-interview-questions.md#48-how-to-assert-text-content)
- [ ] [Q55: How to handle network requests?](../Playwright/100-playwright-interview-questions.md#55-how-to-handle-network-requests)
- [ ] [Q58: How to capture network traffic?](../Playwright/100-playwright-interview-questions.md#58-how-to-capture-network-traffic)

**Hands-on:** Add web-first assertions (`toHaveCount`, `toHaveText`, `toHaveURL`) to yesterday's tests. Then use `page.route` to intercept a request and log it.

## Day 4: Advanced topics (Q61–Q80)

Start at [Q61: What is HAR recording?](../Playwright/100-playwright-interview-questions.md#61-what-is-har-recording) and work through to [Q80: How to create reusable test utilities?](../Playwright/100-playwright-interview-questions.md#80-how-to-create-reusable-test-utilities). These come up most at senior level:

- [ ] [Q62: How to use mocks and fixtures?](../Playwright/100-playwright-interview-questions.md#62-how-to-use-mocks-and-fixtures)
- [ ] [Q63: How to handle OAuth/SSO authentication?](../Playwright/100-playwright-interview-questions.md#63-how-to-handle-oauthsso-authentication)
- [ ] [Q67: How to debug tests?](../Playwright/100-playwright-interview-questions.md#67-how-to-debug-tests)
- [ ] [Q77: How to handle visual regression testing?](../Playwright/100-playwright-interview-questions.md#77-how-to-handle-visual-regression-testing)
- [ ] [Q78: How to handle parallel test execution?](../Playwright/100-playwright-interview-questions.md#78-how-to-handle-parallel-test-execution)
- [ ] [Q79: How to handle flaky tests?](../Playwright/100-playwright-interview-questions.md#79-how-to-handle-flaky-tests)
- [ ] [Q80: How to create reusable test utilities?](../Playwright/100-playwright-interview-questions.md#80-how-to-create-reusable-test-utilities)

**Hands-on:** Move the repeated setup into a custom fixture. Add a `toHaveScreenshot()` visual check, then run the suite with `--workers=4` and `--repeat-each=3` to look for flaky tests.

## Day 5: CI, comparison and mock interview

- [ ] Read Q81–Q90 in [Advanced Topics](../Playwright/100-playwright-interview-questions.md#advanced-topics). These are short notes on CI, Docker and related topics. Q91–Q100 aren't written yet (see the [roadmap](../ProductRoadmap.md)).
- [ ] Related questions from real interviews:
  - [ ] [Q6: Protocols used in Selenium and Playwright?](../Capgemini/l2-interview-questions.md#6-protocols-used-in-selenium-and-playwright)
  - [ ] [Q5: Difference between TypeScript and JavaScript?](../Capgemini/l2-interview-questions.md#5-difference-between-typescript-and-javascript)
  - [ ] [Q3: What is GitHub Actions?](../Capgemini/l2-interview-questions.md#3-what-is-github-actions)
- [ ] **Hands-on:** Add a GitHub Actions workflow that installs the browsers (`npx playwright install --with-deps`), runs the tests and uploads the HTML report as an artifact.
- [ ] **Mock interview (45 min):** have someone pick 15 random question numbers from 1–80, or pick them yourself, and answer each out loud in under two minutes. Finish with "Why Playwright over Selenium?" and "How do you deal with flaky tests?". Both come up in almost every interview.

**Interviewing for a mixed Selenium/Playwright team?** Add Days 4–6 and 8–9 of the [SDET 2-week plan](sdet-selenium-java-2-week.md).

# SDET in 2 Weeks: Selenium + Java Plan

A two-week plan for **SDET / QA Automation** interviews where the stack is **Java, Selenium, TestNG, REST Assured and Jenkins**. It covers every question in the [Deloitte](../Deloitte/) and [Capgemini](../Capgemini/) write-ups, grouped by topic instead of by company, with hands-on practice each day. It budgets about **2–3 hours a day**, with lighter days at the end of each week.

**How each study day works:**

1. Before you open each question, answer it **out loud in under two minutes**. Interviews reward a clear, structured spoken answer.
2. Read the model answer and note what you missed.
3. Do the **hands-on** task. Interviewers often ask you to write the code live.

| Day | Topic | Questions |
|---|---|---|
| 1 | Core Java: OOP | 3 |
| 2 | Core Java: collections, exceptions, coding | 4 |
| 3 | SQL and backend data validation | 3 |
| 4 | Selenium fundamentals and locators | 8 |
| 5 | Waits and synchronization | 4 |
| 6 | Tricky UI automation and files | 5 |
| 7 | Week 1 review (light) | — |
| 8 | Framework design and POM | 6 |
| 9 | TestNG, reporting and screenshots | 4 |
| 10 | API testing and BDD | 4 |
| 11 | CI/CD, Jenkins and Git | 10 |
| 12 | Testing concepts, metrics and performance | 8 |
| 13 | Behavioral and project experience | 3 |
| 14 | Mock interview (light) | All |

---

## Week 1: Language, data and Selenium core

### Day 1: Core Java (OOP)

- [ ] [Q9: Explain dynamic binding and static binding](../Deloitte/sr-qa.md#9-explain-dynamic-binding-and-static-binding)
- [ ] [Q10: Method overloading vs method overriding](../Deloitte/sr-qa.md#10-method-overloading-vs-method-overriding)
- [ ] [Q11: Comparable vs Comparator](../Deloitte/sr-qa.md#11-comparable-vs-comparator)

**Hands-on:** Write an `Employee` class. Sort a list of employees by salary with `Comparable`, then by name with a `Comparator` lambda.

### Day 2: Core Java (collections, exceptions, coding)

- [ ] [Q5: What is LinkedHashMap? Explain its use](../Deloitte/sr-qa.md#5-what-is-linkedhashmap-explain-its-use)
- [ ] [Q7: Difference between an exception and an error](../Deloitte/sr-qa.md#7-difference-between-an-exception-and-an-error)
- [ ] [Q13: Difference between checked and unchecked exceptions](../Deloitte/sr-qa.md#13-difference-between-checked-and-unchecked-exceptions)
- [ ] [Q2: Java code to reverse a string while preserving whitespace](../Deloitte/sr-qa.md#2-java-code-to-reverse-a-string-while-preserving-whitespace)

**Hands-on:** Without looking, write the whitespace-preserving string reversal from Q2, then an LRU cache built on `LinkedHashMap`. Time yourself: aim for 15 minutes each.

### Day 3: SQL and backend data validation

- [ ] [Q3: SQL: find the second-largest salary of an employee](../Deloitte/sr-qa.md#3-sql-find-the-second-largest-salary-of-an-employee)
- [ ] [Q4: Explain joins + types of joins](../Deloitte/sr-qa.md#4-explain-joins--types-of-joins)
- [ ] [Q2: How will you validate the backend data?](../Capgemini/l2-interview-questions.md#2-how-will-you-validate-the-backend-data)

**Hands-on:** Write the second-highest-salary query in all three styles (subquery, `LIMIT`/`OFFSET`, `DENSE_RANK`). Then explain out loud how each one handles duplicate salaries.

### Day 4: Selenium fundamentals and locators

- [ ] [Q2: Explain how you use Selenium WebDriver with Java. How do you handle dynamic web elements?](../Deloitte/automation-test-engineer.md#2-explain-how-you-use-selenium-webdriver-with-java-how-do-you-handle-dynamic-web-elements)
- [ ] [Q8: Difference between findElement and findElements](../Deloitte/sr-qa.md#8-difference-between-findelement-and-findelements)
- [ ] [Q14: If an XPath selects two elements, does findElement throw an exception?](../Deloitte/sr-qa.md#14-if-an-xpath-selects-two-elements-does-findelement-throw-an-exception)
- [ ] [Q11: How to fetch the text from a text box in Selenium?](../Deloitte/sr-qa.md#11-how-to-fetch-the-text-from-a-text-box-in-selenium)
- [ ] [Q12: Enter text in an alert using Selenium](../Deloitte/sr-qa.md#12-enter-text-in-an-alert-using-selenium)
- [ ] [Q16: What are relative locators in Selenium?](../Deloitte/sr-qa.md#16-what-are-relative-locators-in-selenium)
- [ ] [Q6: Protocols used in Selenium and Playwright?](../Capgemini/l2-interview-questions.md#6-protocols-used-in-selenium-and-playwright)
- [ ] [Q5: Difference between TypeScript and JavaScript?](../Capgemini/l2-interview-questions.md#5-difference-between-typescript-and-javascript)

**Hands-on:** Automate a login form. Use one CSS locator, one relative XPath (with `contains()` or `normalize-space()`) and one Selenium 4 relative locator.

### Day 5: Waits and synchronization

- [ ] [Q4: How do you handle waits in Selenium? What’s the difference between implicit, explicit, and fluent waits?](../Deloitte/automation-test-engineer.md#4-how-do-you-handle-waits-in-selenium-whats-the-difference-between-implicit-explicit-and-fluent-waits)
- [ ] [Q9: Difference between implicit wait and explicit wait](../Deloitte/sr-qa.md#9-difference-between-implicit-wait-and-explicit-wait)
- [ ] [Q17: When would you require fluent waits?](../Deloitte/sr-qa.md#17-when-would-you-require-fluent-waits)
- [ ] [Q3: What is “Element click intercepted” and how do you fix it?](../Deloitte/sr-qa.md#3-what-is-element-click-intercepted-and-how-do-you-fix-it)

**Hands-on:** Replace every `Thread.sleep` in your Day 4 script with explicit waits. Then write one `FluentWait` that ignores `StaleElementReferenceException`.

### Day 6: Tricky UI automation and files

- [ ] [Q10: Selenium code to automate a calendar WebElement](../Deloitte/sr-qa.md#10-selenium-code-to-automate-a-calendar-webelement)
- [ ] [Q18: In Selenium, how do you open a new tab?](../Deloitte/sr-qa.md#18-in-selenium-how-do-you-open-a-new-tab)
- [ ] [Q16: Can you automate captchas?](../Deloitte/sr-qa.md#16-can-you-automate-captchas)
- [ ] [Q13: Have you automated the PDF file?](../Capgemini/l2-interview-questions.md#13-have-you-automated-the-pdf-file)
- [ ] [Q14: How will you validate the data in Excel Macros?](../Capgemini/l2-interview-questions.md#14-how-will-you-validate-the-data-in-excel-macros)

**Hands-on:** Automate a date-picker that has to navigate to a month in the future. Then open a link in a new tab and switch back to the original window.

### Day 7: Week 1 review (light, about 1 hour)

- [ ] Redo every question you couldn't answer confidently this week, out loud and without notes.
- [ ] Turn your hands-on code into one small Maven project. You'll grow it next week.

---

## Week 2: Framework, tools and the interview itself

### Day 8: Framework design and POM

- [ ] [Q1: Walk me through your automation framework – which tools, design patterns, and reporting mechanisms do you use?](../Deloitte/automation-test-engineer.md#1-walk-me-through-your-automation-framework--which-tools-design-patterns-and-reporting-mechanisms-do-you-use)
- [ ] [Q7: What is Page Object Model (POM)? How do you maintain reusable components across multiple test cases?](../Deloitte/automation-test-engineer.md#7-what-is-page-object-model-pom-how-do-you-maintain-reusable-components-across-multiple-test-cases)
- [ ] [Q1: Explain your framework in detail](../Deloitte/sr-qa.md#1-explain-your-framework-in-detail)
- [ ] [Q2: If you have 100 pages, do you create 100 Page Objects?](../Deloitte/sr-qa.md#2-if-you-have-100-pages-do-you-create-100-page-objects)
- [ ] [Q11: What does a utilities file contain in a framework?](../Capgemini/l2-interview-questions.md#11-what-does-a-utilities-file-contain-in-a-framework)
- [ ] [Q9: Have you configured any tools?](../Capgemini/l2-interview-questions.md#9-have-you-configured-any-tools)

**Hands-on:** Refactor your project into the layout from the Deloitte answer: `base/`, `pages/`, `tests/`, `utils/`, a thread-safe `DriverManager` using `ThreadLocal`, and one page object per page.

### Day 9: TestNG, reporting and screenshots

- [ ] [Q3: What is the role of TestNG in your framework? How do you implement data-driven testing using @DataProvider?](../Deloitte/automation-test-engineer.md#3-what-is-the-role-of-testng-in-your-framework-how-do-you-implement-data-driven-testing-using-dataprovider)
- [ ] [Q6: What kind of reports do you generate post automation execution? How do you integrate Extent Reports or Allure?](../Deloitte/automation-test-engineer.md#6-what-kind-of-reports-do-you-generate-post-automation-execution-how-do-you-integrate-extent-reports-or-allure)
- [ ] [Q9: How do you capture screenshots on failure and attach them to reports?](../Deloitte/automation-test-engineer.md#9-how-do-you-capture-screenshots-on-failure-and-attach-them-to-reports)
- [ ] [Q4: Take screenshots for failed test cases only in TestNG](../Deloitte/sr-qa.md#4-take-screenshots-for-failed-test-cases-only-in-testng)

**Hands-on:** Add a `@DataProvider` login test with three data sets and a listener that takes a screenshot **only on failure**. Then generate an Allure or Extent report.

### Day 10: API testing and BDD

- [ ] [Q8: Have you automated REST API test cases? Which tools or libraries do you use (like Rest Assured or Postman)?](../Deloitte/automation-test-engineer.md#8-have-you-automated-rest-api-test-cases-which-tools-or-libraries-do-you-use-like-rest-assured-or-postman)
- [ ] [Q7: In Postman, how do you delete a variable after test execution?](../Deloitte/sr-qa.md#7-in-postman-how-do-you-delete-a-variable-after-test-execution)
- [ ] [Q15: What is a schema validation?](../Capgemini/l2-interview-questions.md#15-what-is-a-schema-validation)
- [ ] [Q8: Why do you prefer using Cucumber BDD?](../Deloitte/sr-qa.md#8-why-do-you-prefer-using-cucumber-bdd)

**Hands-on:** Write a REST Assured test that sends a POST, checks the status code and a field in the response, and validates the response body against a JSON schema.

### Day 11: CI/CD, Jenkins and Git

- [ ] [Q5: How do you manage test execution in Jenkins? Have you set up CI pipelines for automated test runs?](../Deloitte/automation-test-engineer.md#5-how-do-you-manage-test-execution-in-jenkins-have-you-set-up-ci-pipelines-for-automated-test-runs)
- [ ] [Q19: In Jenkins, what is the purpose of a CRON expression?](../Deloitte/sr-qa.md#19-in-jenkins-what-is-the-purpose-of-a-cron-expression)
- [ ] [Q10: How will you schedule jobs in Jenkins?](../Capgemini/l2-interview-questions.md#10-how-will-you-schedule-jobs-in-jenkins)
- [ ] [Q3: What is GitHub Actions?](../Capgemini/l2-interview-questions.md#3-what-is-github-actions)
- [ ] [Q5: How to connect your test cases with Azure (Azure DevOps)](../Deloitte/sr-qa.md#5-how-to-connect-your-test-cases-with-azure-azure-devops)
- [ ] [Q10: What is your approach to version control? How do you structure your code in Git and collaborate with teams?](../Deloitte/automation-test-engineer.md#10-what-is-your-approach-to-version-control-how-do-you-structure-your-code-in-git-and-collaborate-with-teams)
- [ ] [Q4: Difference between Git and Bitbucket?](../Capgemini/l2-interview-questions.md#4-difference-between-git-and-bitbucket)
- [ ] [Q12: Tell me some Git commands](../Capgemini/l2-interview-questions.md#12-tell-me-some-git-commands)
- [ ] [Q6: What is the git fetch command?](../Deloitte/sr-qa.md#6-what-is-the-git-fetch-command-get-fetch-usually-means-git-fetch)
- [ ] [Q7: Have you used GitHub Copilot? Where/how?](../Capgemini/l2-interview-questions.md#7-have-you-used-github-copilot-wherehow)

**Hands-on:** Push your project to GitHub and add a GitHub Actions workflow that runs `mvn test` on every push. Then write the cron expression for "weekdays at 2 AM" without looking it up.

### Day 12: Testing concepts, metrics and performance

- [ ] [Q6: Explain black-box testing and white-box testing](../Deloitte/sr-qa.md#6-explain-black-box-testing-and-white-box-testing)
- [ ] [Q15: Explain smoke testing and sanity testing](../Deloitte/sr-qa.md#15-explain-smoke-testing-and-sanity-testing)
- [ ] [Q18: How would you pick test cases for regression testing?](../Deloitte/sr-qa.md#18-how-would-you-pick-test-cases-for-regression-testing)
- [ ] [Q13: 5 points for writing a good test case](../Deloitte/sr-qa.md#13-5-points-for-writing-a-good-test-case)
- [ ] [Q12: How do you conclude a login page is user-friendly?](../Deloitte/sr-qa.md#12-how-do-you-conclude-a-login-page-is-user-friendly)
- [ ] [Q14: Developer is not fixing a bug—how do you approach it?](../Deloitte/sr-qa.md#14-developer-is-not-fixing-a-bughow-do-you-approach-it)
- [ ] [Q1: What are the test metrics?](../Capgemini/l2-interview-questions.md#1-what-are-the-test-metrics)
- [ ] [Q15: What are threads in JMeter?](../Deloitte/sr-qa.md#15-what-are-threads-in-jmeter)

**Hands-on:** Write five test cases for a login page using the "5 points for a good test case" checklist from Q13, including one negative case and one boundary case.

### Day 13: Behavioral and project experience

- [ ] [Q1: Explain about yourself and your roles and responsibilities](../Deloitte/sr-qa.md#1-explain-about-yourself-and-your-roles-and-responsibilities)
- [ ] [Q17: Explain challenges you faced in your project](../Deloitte/sr-qa.md#17-explain-challenges-you-faced-in-your-project)
- [ ] [Q8: Challenges you’ve faced in automation](../Capgemini/l2-interview-questions.md#8-challenges-youve-faced-in-automation)

**Hands-on:** Prepare **three STAR stories** (Situation, Task, Action, Result), each under two minutes: a flaky-test fix, a production bug you caught or missed, and a disagreement with a developer. Rehearse your "tell me about yourself" answer until it takes 90 seconds.

### Day 14: Mock interview (light, about 1.5 hours)

- [ ] Ask a friend, or record yourself, to run **Deloitte Round 1** as a mock: all 10 [Automation Test Engineer](../Deloitte/automation-test-engineer.md) questions, about 3 minutes each.
- [ ] Do **Deloitte Sr. QA Round 2** as a techno-managerial round. Answer out loud, then compare with the model answers.
- [ ] List your three weakest topics and redo those days' questions before the real interview.

**Using Playwright instead of Selenium?** Follow the [Playwright 5-day plan](playwright-5-day.md) for the tool-specific part, and keep Days 1–3 and 8–14 of this plan.

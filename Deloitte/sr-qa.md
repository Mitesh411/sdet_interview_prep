# Deloitte | Sr. QA | Interview

# Round 1: (Technical)

## 1) Explain about yourself and your roles and responsibilities

I’m a QA Engineer with experience in both **manual and automation testing** for web applications. I work closely with developers, product owners, and business analysts in an Agile setup to understand requirements and convert them into a solid test strategy.

My day-to-day responsibilities include **test case design**, **test execution**, **defect reporting and tracking**, and ensuring end-to-end quality across releases. I also contribute to automation using **Selenium WebDriver with Java** (along with TestNG/JUnit, Maven, and Git), and I maintain reusable test suites for **regression and smoke testing**.

Alongside UI testing, I do **API testing** (Postman/RestAssured basics), **database validation using SQL**, and I regularly participate in sprint ceremonies like refinement, planning, daily standups, and retrospectives. My focus is always on improving test coverage, reducing production issues, and making releases smoother and more predictable.
    

----------

## 2) Java code to reverse a string while preserving whitespace

Meaning: reverse **only the characters**, but keep spaces in the **same positions**.

Example:  
`"ab c d"` → `"dc b a"`

    public class ReversePreserveSpaces {
        public static String reversePreservingSpaces(String s) {
            char[] arr = s.toCharArray();
            char[] result = new char[arr.length];
    
            // Mark spaces at same indices
            for (int i = 0; i < arr.length; i++) {
                if (arr[i] == ' ') result[i] = ' ';
            }
    
            // Fill non-space chars from end
            int j = arr.length - 1;
            for (int i = 0; i < arr.length; i++) {
                if (result[i] == ' ') continue;
                while (j >= 0 && arr[j] == ' ') j--;
                result[i] = arr[j--];
            }
    
            return new String(result);
        }
    
        public static void main(String[] args) {
            System.out.println(reversePreservingSpaces("ab c d")); // dc b a
        }
    }

----------

## 3) SQL: find the second-largest salary of an employee

### Option A (most common)

    SELECT  MAX(salary) AS second_largest_salary FROM employee WHERE salary < (SELECT  MAX(salary) FROM employee);

### Option B (handles duplicates cleanly)

    SELECT salary AS second_largest_salary FROM ( SELECT  DISTINCT salary FROM employee ORDER  BY salary DESC LIMIT 2 ) t ORDER  BY salary ASC LIMIT 1;

### Option C (window function)

    SELECT salary FROM ( SELECT salary, DENSE_RANK() OVER (ORDER  BY salary DESC) AS rnk FROM employee
    ) t WHERE rnk =  2;

----------

## 4) Explain joins + types of joins

**Join** combines rows from two (or more) tables based on a related column (usually a key).

Types:

-   **INNER JOIN**: only matching rows in both tables
    
-   **LEFT JOIN (LEFT OUTER)**: all rows from left + matching from right; non-matching right → NULL
    
-   **RIGHT JOIN (RIGHT OUTER)**: all rows from right + matching from left
    
-   **FULL OUTER JOIN**: all rows from both; non-matching sides → NULL (not supported in MySQL without workaround)
    
-   **CROSS JOIN**: Cartesian product (every left row with every right row)
    
-   **SELF JOIN**: a table joined to itself
    
-   (Also used: **NATURAL JOIN** in some DBs, but generally avoided in real projects)
    

----------

## 5) What is LinkedHashMap? Explain its use

`LinkedHashMap` is a `HashMap` variant that **maintains order**:

-   **Insertion order** (default), or
    
-   **Access order** (if enabled), useful for LRU cache.
    

Use cases:

-   When you need **fast lookup (O(1) average)** + **predictable iteration order**
    
-   Implement **LRU cache** using `accessOrder=true` and `removeEldestEntry`
    

Example (preserves insertion order):

    Map<String, Integer> map = new  LinkedHashMap<>();
    map.put("A", 1);
    map.put("B", 2);

----------

## 6) Explain black-box testing and white-box testing

-   **Black-box testing**: test based on requirements/spec; you don’t look at code.
    
    -   Focus: functionality, inputs/outputs, UI/API behavior
        
    -   Techniques: equivalence partitioning, boundary value analysis, decision tables
        
-   **White-box testing**: test based on internal code/logic.
    
    -   Focus: code paths, conditions, loops, statements
        
    -   Techniques: statement coverage, branch coverage, path coverage
        

----------

## 7) Difference between an exception and an error

In Java:

-   **Exception**: conditions an application might want to catch and handle.
    
    -   Example: `IOException`, `SQLException`
        
-   **Error**: serious problems typically not meant to be handled by application code.
    
    -   Example: `OutOfMemoryError`, `StackOverflowError`
        

----------

## 8) Difference between findElement and findElements

In Selenium:

-   `findElement(By ...)`
    
    -   Returns **single WebElement**
        
    -   If not found → **throws NoSuchElementException**
        
-   `findElements(By ...)`
    
    -   Returns **List<WebElement>**
        
    -   If not found → returns **empty list** (no exception)
        

----------

## 9) Difference between implicit wait and explicit wait

-   **Implicit wait**
    
    -   Global setting: applies to all `findElement(s)`
        
    -   Waits up to given time before throwing exception / returning empty list
        
    -   Can cause confusing delays if overused
        
-   **Explicit wait**
    
    -   Applied to a **specific condition** (element visible/clickable/text present/etc.)
        
    -   Uses `WebDriverWait` + `ExpectedConditions`
        
    -   Preferred for stable automation
        

Tip: avoid mixing implicit + explicit heavily (can cause unpredictable wait times).

----------

## 10) Selenium code to automate a calendar WebElement

Example: select a date in a typical date-picker by navigating months and clicking a day.


    import java.time.Duration;
    import org.openqa.selenium.*;
    import org.openqa.selenium.support.ui.*;
    
    public class CalendarPicker {
        public static void selectDate(WebDriver driver, String targetMonthYear, String day) {
            WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(10));
    
            // Open date picker
            driver.findElement(By.id("dateInput")).click();
    
            // Loop until desired month-year appears
            while (true) {
                WebElement header = wait.until(ExpectedConditions.visibilityOfElementLocated(
                        By.cssSelector(".ui-datepicker-title"))); // adjust locator
                String displayed = header.getText(); // e.g., "December 2025"
    
                if (displayed.equalsIgnoreCase(targetMonthYear)) break;
    
                // Click next month (or prev) based on your need
                driver.findElement(By.cssSelector(".ui-datepicker-next")).click();
            }
    
            // Click the day
            driver.findElement(By.xpath("//a[text()='" + day + "']")).click();
        }
    }


> Note: Locators (`.ui-datepicker-*`) vary by app. Replace with your calendar’s DOM.

----------

## 11) How to fetch the text from a text box in Selenium?

For `<input>` or `<textarea>`, use **getAttribute("value")** (not `getText()`).

    WebElement  textbox  = driver.findElement(By.id("username")); 
    String  value  = textbox.getAttribute("value");

----------

## 12) Enter text in an alert using Selenium

Only works for **prompt alerts**.

    Alert  alert  = driver.switchTo().alert();
    alert.sendKeys("Some text");
    alert.accept();

----------

## 13) Difference between checked and unchecked exceptions

-   **Checked exceptions**
    
    -   Must be **handled** (try-catch) or **declared** (`throws`)
        
    -   Example: `IOException`, `SQLException`
        
-   **Unchecked exceptions**
    
    -   Subclasses of `RuntimeException`
        
    -   Not required to handle explicitly
        
    -   Example: `NullPointerException`, `ArrayIndexOutOfBoundsException`
        

----------

## 14) If an XPath selects two elements, does findElement throw an exception?

No—if elements exist, `findElement` returns **the first matching element** in DOM order.  
It throws `NoSuchElementException` only when **no elements match**.

----------

## 15) Explain smoke testing and sanity testing

-   **Smoke testing**
    
    -   Quick checks to ensure the build is **stable enough to test**
        
    -   Broad and shallow (login, navigation, major flows)
        
-   **Sanity testing**
    
    -   Narrow checks after a small change/fix to confirm **specific functionality works**
        
    -   More focused than smoke
        

----------

## 16) What are relative locators in Selenium?

Relative locators (Selenium 4) locate elements based on their position relative to another element:

-   `above()`, `below()`, `toLeftOf()`, `toRightOf()`, `near()`
    

Example:

    import static org.openqa.selenium.support.locators.RelativeLocator.with;
    
    WebElement label = driver.findElement(By.id("emailLabel"));
    WebElement emailInput = driver.findElement(with(By.tagName("input")).below(label));

----------

## 17) Explain challenges you faced in your project

Here are common real-world challenges (you can speak to 2–3 with how you solved them):

1.  **Flaky automation due to synchronization issues (AJAX / loaders / dynamic UI)**
    
    -   _Challenge:_ Elements appeared late or became stale after page refresh.
        
    -   _Solution:_ Used **explicit waits** with proper conditions (visibility/clickable), added smart wait utilities, and avoided hard sleeps.
        
2.  **Unstable locators because of frequently changing DOM**
    
    -   _Challenge:_ Dynamic IDs and changing XPaths broke tests.
        
    -   _Solution:_ Worked with devs to add stable attributes (like `data-testid`), improved CSS/XPath strategies, and implemented **Page Object Model** for easy maintenance.
        
3.  **Test data problems across environments**
    
    -   _Challenge:_ Data was reused/dirty, causing inconsistent results.
        
    -   _Solution:_ Created controlled test data sets, used setup/cleanup scripts, and validated data with **SQL** before execution.
        
4.  **Regression suite getting too large and time-consuming**
    
    -   _Challenge:_ Full regression couldn’t fit within sprint timelines.
        
    -   _Solution:_ Prioritized tests by business impact, created **smoke + sanity + full regression buckets**, and moved stable tests to CI nightly runs.
        
5.  **Environment and CI failures**
    
    -   _Challenge:_ Tests passed locally but failed in CI due to browser/driver mismatch or environment slowness.
        
    -   _Solution:_ Standardized versions, improved waits, captured screenshots/logs on failure, and ensured consistent config through properties/profiles.

Sample (interview-ready) points:

-   **Dynamic elements & changing DOM** causing flaky locators → solved using stable attributes, better XPath/CSS, page object model.
    
-   **Synchronization issues** (AJAX loaders, animations) → fixed with explicit waits and custom wait utilities.
    
-   **Test data management** across environments → created reusable test data builders and cleanup routines.
    
-   **CI/CD failures** due to environment differences → containerized runs, ensured consistent browser/driver versions.
    
-   **Parallel execution issues** (shared state) → thread-safe driver management, isolated data.
    
-   **Intermittent failures** → added retry logic _only where justified_, improved logging/screenshots, and root-caused real issues.
    

----------

## 18) How would you pick test cases for regression testing?

Prioritization strategy:

1.  **Business-critical flows** (revenue, onboarding, login, payments)
    
2.  **High-risk areas** (recent code changes, complex logic, integrations)
    
3.  **High-defect modules** (historically unstable)
    
4.  **Core CRUD + key validations**
    
5.  **Cross-browser/device critical paths**
    
6.  **APIs/integration points** (third-party services, DB updates, queues)
    
7.  **Security and role/permission checks** where applicable
    
8.  **Production bugs**: add “never again” tests for key escaped defects
    

Practical approach:

-   Maintain a **smoke suite**, a **sanity suite**, and a **full regression suite**
    
-   Run smoke on every build, targeted regression per change, full regression nightly/weekly depending on timeline.



# Round 2: (Techno-Managerial)



## 1) Explain your framework in detail

A typical **Java + Selenium + TestNG + Maven** automation framework (industry-standard) looks like this:

-   **Design pattern**
    
    -   **Page Object Model (POM)** for maintainability (UI locators + actions in page classes)
        
    -   Optionally **Page Factory** (less common now), or plain `By` locators
        
-   **Project structure (example)**
    
    -   `src/test/java`
        
        -   `tests/` → TestNG test classes
            
        -   `pages/` → Page Objects (UI actions)
            
        -   `utils/` → waits, screenshots, file readers, date helpers, common methods
            
        -   `listeners/` → TestNG listeners (reporting, screenshots on fail)
            
    -   `src/main/java` (optional) → reusable core components
        
    -   `resources/`
        
        -   `config.properties` (env URLs, browser, creds via vault/secret store)
            
        -   `testdata/` (json/excel)
            
        -   `log4j2.xml` / logging config
            
-   **Core components**
    
    -   **Driver management**: `WebDriverManager` or grid; ThreadLocal driver for parallel runs
        
    -   **BaseTest**: setup/teardown, driver init, common hooks
        
    -   **Wait utilities**: explicit waits + fluent wait helper for flaky/dynamic elements
        
    -   **Reporting**: Extent/Allure reports + screenshots on failure
        
    -   **CI/CD integration**: Jenkins/Azure DevOps pipeline triggers, reports archived, results published
        
    -   **Data handling**: DataProvider + external test data (JSON/Excel/DB)
        
    -   **Assertions**: TestNG asserts / soft asserts where needed
        
-   **Execution**
    
    -   Run via `testng.xml` suites (smoke/regression)
        
    -   Maven commands like `mvn test -DsuiteXmlFile=testng.xml -Dbrowser=chrome`
        

----------

## 2) If you have 100 pages, do you create 100 Page Objects?

Not always.

Best practice:

-   Create Page Objects for **important pages and reusable components**.
    
-   Use a **component-based approach**:
    
    -   Example: `HeaderComponent`, `LeftMenuComponent`, `CalendarComponent`, `ToastComponent`
        
-   If many pages are similar (CRUD screens), you can:
    
    -   Create **generic/base page** + extend
        
    -   Use **dynamic locators** + reusable methods
        
-   Rule of thumb: **If a page has unique behavior or many interactions → create a Page Object.**  
    If it’s a minor/static page with 1–2 elements, you can keep it minimal or covered via component objects.
    

----------

## 3) What is “Element click intercepted” and how do you fix it?

**`ElementClickInterceptedException`** happens when Selenium tries to click an element but **another element is on top of it** (overlay, loader, modal, sticky header, animation, etc.).

Fixes:

-   Wait until element is **clickable**:
    
    -   `ExpectedConditions.elementToBeClickable`
        
-   Wait for overlay/loader to disappear:
    
    -   `invisibilityOfElementLocated`
        
-   Scroll into view:
    
    -   `((JavascriptExecutor)driver).executeScript("arguments[0].scrollIntoView(true)", el);`
        
-   Click via JavaScript (last resort):
    
    -   `executeScript("arguments[0].click()", el);`
        
-   Fix locator to click the correct element (sometimes you’re clicking a wrapper)
    

----------

## 4) Take screenshots for failed test cases only in TestNG

Use a **TestNG Listener** (`ITestListener`) and capture screenshot in `onTestFailure()`.

    import org.openqa.selenium.*;
    import org.testng.*;
    import org.testng.annotations.Listeners;
    import org.testng.ITestListener;
    import org.testng.ITestResult;
    import java.io.File;
    import org.openqa.selenium.io.FileHandler;
    
    public class ScreenshotListener implements ITestListener {
    
        @Override
        public void onTestFailure(ITestResult result) {
            Object testClass = result.getInstance();
            WebDriver driver = ((BaseTest) testClass).getDriver();
    
            try {
                TakesScreenshot ts = (TakesScreenshot) driver;
                File src = ts.getScreenshotAs(OutputType.FILE);
                File dest = new File("screenshots/" + result.getName() + ".png");
                FileHandler.copy(src, dest);
            } catch (Exception e) {
                e.printStackTrace();
            }
        }
    }

----------

## 5) How to connect your test cases with Azure (Azure DevOps)

Common ways:

-   **Azure Repos**: push your automation code to Azure Git repos.
    
-   **Azure Pipelines (CI)**:
    
    -   Create a pipeline YAML that runs `mvn test`
        
    -   Publish results using **Publish Test Results** task (JUnit/TestNG results)
        
    -   Publish artifacts: screenshots + reports (Allure/Extent)
        
-   **Azure Test Plans integration**:
    
    -   Link automation results to Test Plans via pipeline test reporting
        
    -   Some teams map automated tests using test case IDs in names/tags for traceability
        

----------

## 6) What is the git fetch command? _(“get fetch” usually means `git fetch`)_

`git fetch` downloads the latest commits/branches/tags from the remote repository **without merging** into your current branch.

-   Updates your remote-tracking branches like `origin/main`
    
-   Safe way to see what changed before you merge/rebase
    

Example:

    git fetch origin
    git log HEAD..origin/main

----------

## 7) In Postman, how do you delete a variable after test execution?

In the **Tests** script:

    pm.environment.unset("token");     // deletes environment variable
    pm.collectionVariables.unset("id"); // deletes collection variable
    pm.globals.unset("baseUrl");        // deletes global variable

----------

## 8) Why do you prefer using Cucumber BDD?

Reasons teams use **Cucumber (BDD)**:

-   **Readable scenarios** in Gherkin (Given/When/Then) for business + QA + dev alignment
    
-   Improves **requirement clarity** and reduces ambiguity
    
-   Encourages **reusable step definitions**
    
-   Makes it easier to maintain **feature-level documentation**
    
-   Works well for acceptance tests and stakeholder visibility
    

(Also be honest in interviews: BDD helps only if the team actually collaborates on scenarios.)

----------

## 9) Explain dynamic binding and static binding

-   **Static binding (compile-time)**  
    Method call resolved at compile time.  
    Examples: **method overloading**, `static`, `final`, `private` methods.
    
-   **Dynamic binding (runtime)**  
    Method call resolved at runtime based on the actual object type.  
    Example: **method overriding** (polymorphism).
    

----------

## 10) Method overloading vs method overriding

-   **Overloading**
    
    -   Same method name, **different parameters** (number/type/order)
        
    -   Compile-time polymorphism
        
    -   Can be in same class
        
-   **Overriding**
    
    -   Child class provides new implementation of parent method
        
    -   Same signature, runtime polymorphism
        
    -   Requires inheritance
        

----------

## 11) Comparable vs Comparator

-   **Comparable**
    
    -   Implemented by the class itself
        
    -   Defines natural ordering via `compareTo()`
        
    -   Example: `class Employee implements Comparable<Employee>`
        
-   **Comparator**
    
    -   Separate class or lambda
        
    -   Defines multiple custom sort orders via `compare()`
        
    -   Useful when you need sorting by salary, name, date, etc.
        

----------

## 12) How do you conclude a login page is user-friendly?

You evaluate usability + UX cues, for example:

-   Clear labels, placeholder vs label not confusing
    
-   Proper error messages (wrong password, empty fields) and **not generic**
    
-   Shows password toggle, caps-lock warning (optional)
    
-   Keyboard accessibility: tab order, enter-to-submit
    
-   Fast feedback and no confusing redirects
    
-   “Forgot password” visible, signup link appropriate
    
-   Mobile responsiveness
    
-   Security cues: no exposing sensitive info, rate limiting, etc.
    

----------

## 13) 5 points for writing a good test case

1.  **Clear objective** (what feature/behavior is validated)
    
2.  **Preconditions** + test data stated
    
3.  **Step-by-step actions** that are unambiguous
    
4.  **Expected results** per key step (not only at the end)
    
5.  **Traceability & priority** (requirement/story ID, severity, tags like smoke/regression)
    

----------

## 14) Developer is not fixing a bug—how do you approach it?

Professional approach:

-   Re-validate bug with clear steps, screenshots/logs, environment details
    
-   Explain **impact** (business/user impact, severity, frequency)
    
-   Discuss with developer directly first (maybe it’s expected behavior or needs clarification)
    
-   If still blocked: raise in standup/sprint triage with PO/lead, propose options:
    
    -   Fix now / workaround / defer with documented risk
        
-   Keep it factual, collaborative, and focused on delivering safely
    

----------

## 15) What are threads in JMeter?

In JMeter, **threads** represent **virtual users**.

-   A **Thread Group** defines number of users (threads), ramp-up time, loop count.
    
-   More threads → more concurrent load (limited by machine resources).
    

----------

## 16) Can you automate captchas?

In general, **no** (and you shouldn’t in real scenarios) because CAPTCHA is designed to block bots.

What teams do instead:

-   Use **test environment** where captcha is disabled
    
-   Use **whitelisted test keys** (for reCAPTCHA) or bypass tokens (server-side)
    
-   Mock/stub captcha validation in lower environments
    

----------

## 17) When would you require fluent waits?

Use **FluentWait** when:

-   Element appears at unpredictable times (dynamic/AJAX)
    
-   You need **custom polling interval** (e.g., poll every 500ms)
    
-   You want to **ignore specific exceptions** (NoSuchElement, StaleElement)
    
-   Waiting for non-standard conditions (custom JS state, attribute changes, text updates)
    

----------

## 18) In Selenium, how do you open a new tab?

Options:

-   Using Selenium 4:

  `driver.switchTo().newWindow(WindowType.TAB);
    driver.get("https://example.com");`

-   Using JavaScript:
    

`((JavascriptExecutor)driver).executeScript("window.open('https://example.com','_blank');");` 

----------

## 19) In Jenkins, what is the purpose of a CRON expression?

A **CRON expression** schedules jobs to run automatically at specific times (nightly builds, weekly regression, etc.).

Example:

-   `H 2 * * 1-5` → run around 2 AM on weekdays (Jenkins supports `H` for hash-based spreading)
    

Common use:

-   Nightly regression
    
-   Scheduled smoke checks
    
-   Periodic health checks in lower environments



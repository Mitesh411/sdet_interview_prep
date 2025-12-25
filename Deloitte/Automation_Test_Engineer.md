# Deloitte Interview Experience – Automation Test Engineer

# Application Method: Direct Application

# 𝗥𝗼𝘂𝗻𝗱 𝟭: 𝗧𝗲𝗰𝗵𝗻𝗶𝗰𝗮𝗹 𝗦𝗰𝗿𝗲𝗲𝗻𝗶𝗻𝗴


## 1) Walk me through your automation framework – which tools, design patterns, and reporting mechanisms do you use?

    
**Tech Stack**
- **Language**: Java 11+
- **UI Automation**: Selenium WebDriver
- **API Automation**: Rest Assured (with TestNG)
- **Build & Dependency**: Maven (or Gradle)
- **Test Runner**: TestNG
- **CI/CD**: Jenkins (Pipeline-as-Code)
- **Reporting**: Extent Reports / Allure
- **Utilities**: Apache POI (Excel), Jackson/Gson (JSON), Lombok (DTOs), WebDriverManager

**Project Layout (Maven)**
```
project-root/
  src/test/java/
    base/              # DriverManager, TestBase, ConfigFactory
    pages/             # Page Objects (POM)
    tests/             # Test classes (UI/API)
    data/              # Data providers, test data builders
    utils/             # WaitUtils, RetryAnalyzer, FileUtils, API utils
    reporters/         # Extent/Allure helpers
  src/test/resources/  # properties, json payloads, test-data.xlsx
  Jenkinsfile          # CI pipeline
  pom.xml              # dependencies & plugins
```

**Design Patterns**
- **Page Object Model (POM)**: Encapsulates page structure & behaviors.
- **Page Factory (optional)**: For `@FindBy` annotations.
- **Factory Pattern**: `DriverFactory`, `EnvironmentFactory` for cross-browser/env.
- **Singleton**: `DriverManager` to avoid multiple driver instances per thread.
- **Builder**: For complex request payloads (API tests).
- **Strategy**: Pluggable wait strategies & locator strategies.
- **Command/Service Layer**: Reusable workflows (e.g., `LoginService`).

**Reporting & Observability**
- **Extent**: Rich HTML, screenshots, categorization, BDD-like steps.
- **Allure**: History trends, attachments, retries, steps annotations.
- **Loggers**: SLF4J/Logback per test with correlation IDs.

---

## 2) Explain how you use **Selenium WebDriver with Java**. How do you handle dynamic web elements?

**Driver Bootstrap**
```java
public class DriverManager {
  private static ThreadLocal<WebDriver> driver = new ThreadLocal<>();

  public static void setDriver(String browser) {
    if ("chrome".equalsIgnoreCase(browser)) {
      WebDriverManager.chromedriver().setup();
      ChromeOptions options = new ChromeOptions();
      options.addArguments("--start-maximized");
      driver.set(new ChromeDriver(options));
    } // add firefox, edge as needed
  }

  public static WebDriver getDriver() { return driver.get(); }
  public static void quit() { driver.get().quit(); driver.remove(); }
}
```

**Handling Dynamic Web Elements**
- Use **robust locators** (CSS/XPath) anchored on stable attributes (data-* ids).
- **Relative XPath** with functions: `contains()`, `starts-with()`, `normalize-space()`.
- **Explicit waits** for presence/visibility/clickability to avoid stale/detached nodes.
- **Retry/Resilience**: Wrap actions with small retry on `StaleElementReferenceException`.
- **Avoid indexing** in XPath unless unavoidable; prefer semantic anchors and ARIA roles.

```java
By productName(String name) {
  return By.xpath("//div[@class='product-card']//*[normalize-space(text())='"+name+"']");
}

public WebElement waitForClickable(By locator) {
  return new WebDriverWait(DriverManager.getDriver(), Duration.ofSeconds(15))
           .until(ExpectedConditions.elementToBeClickable(locator));
}

public void resilientClick(By locator) {
  for (int i = 0; i < 3; i++) {
    try { waitForClickable(locator).click(); return; }
    catch (StaleElementReferenceException | ElementClickInterceptedException e) {
      sleep(500);
    }
  }
  throw new RuntimeException("Failed to click: " + locator);
}
```

---

## 3) What is the role of TestNG in your framework? How do you implement data-driven testing using `@DataProvider`?

**Why TestNG?**
- Flexible test orchestration: grouping, parallel execution, dependencies.
- Built-in **data providers**, **retry**, and **listeners** (`ITestListener`).
- Rich suite XML for environment-driven runs.

**Data-Driven Example**
```java
public class LoginTests extends TestBase {

  @DataProvider(name = "loginData", parallel = true)
  public Object[][] loginData(Method m) {
    return new Object[][]{
      {"standard_user", "secret_sauce"},
      {"problem_user", "secret_sauce"},
      {"performance_glitch_user", "secret_sauce"}
    };
  }

  @Test(dataProvider = "loginData")
  public void login_shouldSucceed(String user, String pass) {
    LoginPage login = new LoginPage();
    HomePage home = login.loginAs(user, pass);
    Assert.assertTrue(home.isLoaded());
  }
}
```

Optionally load from Excel/CSV/JSON using Apache POI/Jackson.

---

## 4) How do you handle waits in Selenium? What’s the difference between implicit, explicit, and fluent waits?

- **Implicit Wait**: Sets a default polling time for **findElement**. Global, may mask sync issues. Use sparingly.
  ```java
  DriverManager.getDriver().manage().timeouts().implicitlyWait(Duration.ofSeconds(0)); // often disable
  ```
- **Explicit Wait**: Wait for a specific condition (visibility, clickability, URL, JS). Preferred.
  ```java
  WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(10));
  WebElement el = wait.until(ExpectedConditions.visibilityOfElementLocated(locator));
  ```
- **Fluent Wait**: Custom polling, exception ignoring.
  ```java
  Wait<WebDriver> fluent = new FluentWait<>(driver)
      .withTimeout(Duration.ofSeconds(20))
      .pollingEvery(Duration.ofMillis(500))
      .ignoring(NoSuchElementException.class);
  WebElement el = fluent.until(d -> d.findElement(locator));
  ```
**Best Practice**: Avoid mixing implicit & explicit waits together.

---

## 5) How do you manage test execution in Jenkins? Have you set up CI pipelines for automated test runs?

**Pipeline-as-Code (Declarative)**
```groovy
pipeline {
  agent any
  options { timestamps(); buildDiscarder(logRotator(numToKeepStr: '20')) }
  parameters {
    choice(name: 'BROWSER', choices: ['chrome','firefox'], description: 'Target browser')
    string(name: 'ENV', defaultValue: 'qa', description: 'Environment')
  }
  stages {
    stage('Checkout') { steps { checkout scm } }
    stage('Build') { steps { sh 'mvn -q -DskipTests clean compile' } }
    stage('Test') {
      steps { sh "mvn -q -Denv=${params.ENV} -Dbrowser=${params.BROWSER} test" }
      post {
        always {
          archiveArtifacts artifacts: 'target/**/*.png, target/surefire-reports/**/*', fingerprint: true
          publishHTML(target: [reportName: 'Extent Report', reportDir: 'target/extent', reportFiles: 'index.html'])
        }
      }
    }
  }
}
```
- Supports **scheduled runs**, **parallel nodes** for cross-browser, and **post actions** for publishing reports and artifacts.

---

## 6) What kind of reports do you generate post automation execution? How do you integrate Extent Reports or Allure?

**Extent Reports Setup**
```java
public class ExtentManager {
  private static final ExtentReports extent = new ExtentReports();
  static {
    ExtentSparkReporter spark = new ExtentSparkReporter("target/extent/index.html");
    spark.config().setDocumentTitle("UI Automation Report");
    spark.config().setReportName("Regression Suite");
    extent.attachReporter(spark);
  }
  public static ExtentReports get(){ return extent; }
}

public class TestBase {
  protected ExtentTest test;
  @BeforeMethod(alwaysRun = true)
  public void start(Method m) {
    test = ExtentManager.get().createTest(m.getName());
  }
  @AfterMethod(alwaysRun = true)
  public void quit(ITestResult result) {
    if (result.getStatus() == ITestResult.FAILURE) {
      String path = Screenshot.capture(DriverManager.getDriver(), result.getName());
      test.fail(result.getThrowable()).addScreenCaptureFromPath(path);
    }
    ExtentManager.get().flush();
    DriverManager.quit();
  }
}
```

**Allure Setup (Maven)**
```xml
<dependency>
  <groupId>io.qameta.allure</groupId>
  <artifactId>allure-testng</artifactId>
  <version>2.20.1</version>
</dependency>
<plugin>
  <groupId>io.qameta.allure</groupId>
  <artifactId>allure-maven</artifactId>
  <version>2.11.2</version>
</plugin>
```
Annotate steps & attach artifacts:
```java
@Step("Login as {user}")
public HomePage loginAs(String user, String pass) { /* ... */ }

Allure.addAttachment("Failure Screenshot", new ByteArrayInputStream(bytes));
```

---

## 7) What is Page Object Model (POM)? How do you maintain reusable components across multiple test cases?

**POM Principle**: Page classes expose **behaviors**, not locators.
```java
public class LoginPage {
  private WebDriver driver = DriverManager.getDriver();
  private By user = By.id("user-name");
  private By pass = By.id("password");
  private By submit = By.id("login-button");

  public HomePage loginAs(String u, String p) {
    driver.findElement(user).sendKeys(u);
    driver.findElement(pass).sendKeys(p);
    driver.findElement(submit).click();
    return new HomePage();
  }
}
```
**Reusable Components**
- **BasePage** with common methods (safeClick, type, waitFor, getText).
- **Components**: Header, Footer, Modal, Grid as separate classes used across pages.
- **Service Layer**: High-level flows (e.g., `CheckoutService.placeOrder()`), reused in multiple tests.
- **Locators in one place** + **enum** for menu/options to reduce drift.

---

## 8) Have you automated REST API test cases? Which tools or libraries do you use (like Rest Assured or Postman)?

**Rest Assured Pattern**
```java
import static io.restassured.RestAssured.*;
import static org.hamcrest.Matchers.*;

@BeforeClass
public void setup() {
  RestAssured.baseURI = System.getProperty("baseUrl", "https://api.example.com");
}

@Test
public void createUser_shouldReturn201() {
  given()
    .contentType("application/json")
    .body(new UserBuilder().withName("Mitesh").withRole("QA").build())
  .when()
    .post("/users")
  .then()
    .statusCode(201)
    .body("id", notNullValue());
}
```
- Use **Request/Response specs**, **filters** for logging, **schema validation** (JSON Schema), and integrate into TestNG suites for unified reporting.
- Postman can be used for quick exploration; collections exported to Newman for CI if needed.

---

## 9) How do you capture screenshots on failure and attach them to reports?

**Utility**
```java
public class Screenshot {
  public static String capture(WebDriver driver, String name) {
    String path = "target/screenshots/" + name + "_" + System.currentTimeMillis() + ".png";
    File src = ((TakesScreenshot)driver).getScreenshotAs(OutputType.FILE);
    try {
      Files.createDirectories(Paths.get("target/screenshots"));
      Files.copy(src.toPath(), Paths.get(path), StandardCopyOption.REPLACE_EXISTING);
    } catch (IOException e) { throw new RuntimeException(e); }
    return path;
  }
}
```
Hook into **TestNG Listeners** or `@AfterMethod` to capture and attach for Extent/Allure.

---

## 10) What is your approach to version control? How do you structure your code in Git and collaborate with teams?

**Branching Strategy**
- **Main**: Always stable; tagged releases.
- **Develop**: Integration branch (optional).
- **Feature/*** branches per story; **hotfix/*** for urgent fixes.
- **Pull Requests** with mandatory code review (2 reviewers for critical tests).

**Repo Structure**
```
automation-tests/
  ui/           # Selenium
  api/          # Rest Assured
  common/       # shared utils & models
  resources/    # test data & configs
```

**Conventions**
- **Commit Messages**: Conventional commits (`feat(ui): add checkout flow`, `fix(api): handle 429`).
- **Code Quality**: Checkstyle/SpotBugs, unit tests for utils, pre-commit hooks.
- **Secrets**: Stored in Jenkins credentials & environment variables; never in repo.
- **Versioning**: `pom.xml` with pinned versions; Dependabot for updates.

---

### Extras: Parallelism & Scalability
- TestNG parallel suites by **methods/classes** with thread-safe `DriverManager`.
- Selenium Grid / Selenoid for distributed runs; Dockerized nodes.
- Tagging tests (Smoke/Regression) and running selective suites in CI.

---

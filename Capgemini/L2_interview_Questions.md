# Capgemini L2 QA — Interview Q&A (Markdown)

## 1) What are the test metrics?

Common, manager-friendly metrics you can actually track and action:

-   **Requirement Coverage** = (# requirements with tests) / (total requirements)
    
-   **Test Case Effectiveness** = (defects found by testing) / (total defects found pre-prod + in prod)
    
-   **Defect Density** = defects / KLOC or per module
    
-   **Defect Leakage (Escape Rate)** = prod defects / total defects
    
-   **Defect Removal Efficiency (DRE)** = defects removed before release / total defects
    
-   **Pass/Fail Rate** per cycle & **Execution Progress** (% executed)
    
-   **Flake Rate** (automation stability): flaky tests / total automated tests
    
-   **Automation Coverage** = automated test cases / total eligible test cases
    
-   **Build Health / MTTR**: failing builds, mean time to restore
    
-   **Code Coverage** (unit/integration) — line/branch/function (contextual, not a goal)
    

----------

## 2) How will you validate the backend data?

-   **DB validation**: Query the DB (SQL) to verify persistence, constraints, and business rules.
    
-   **API ↔ DB reconciliation**: Compare API payloads with DB rows (including timestamps, IDs).
    
-   **ETL/Data pipelines**: Row counts, checksums, referential integrity, and transformation rules.
    
-   **Events/Queues**: Validate messages on Kafka/SQS; assert correct schema & headers.
    
-   **Repeatability**: Seed known test data; use Testcontainers/local DB snapshots.
    
-   **Tooling**: JDBC/ODBC, `pg`/`mysql2` (Node), `psycopg2` (Python), ORM read-only repos.
    

> Example (Node + PostgreSQL):

    import { Client } from "pg";
    const sql = "SELECT status, total FROM orders WHERE id=$1";
    const db = new Client({ connectionString: process.env.PG_URL });
    await db.connect();
    const { rows } = await db.query(sql, [orderId]);
    expect(rows[0].status).toBe("PAID");
    await db.end();

----------

## 3) What is GitHub Actions?

-   **CI/CD platform** built into GitHub.
    
-   **Workflows** (YAML) run on **events** (push/PR/schedule).
    
-   **Jobs** run on **runners** (Ubuntu/Windows/macOS or self-hosted).
    
-   Built-in **secrets**, **caching**, **matrix** builds, and **marketplace actions**.
    

> Minimal example:

    name: CI
    on: [push, pull_request]
    jobs:
      test:
        runs-on: ubuntu-latest
        steps:
          - uses: actions/checkout@v4
          - uses: actions/setup-node@v4
            with: { node-version: 20 }
          - run: npm ci
          - run: npm test -- --reporter=junit

----------

## 4) Difference between Git and Bitbucket?

-   **Git**: Distributed version control **tool** (CLI, open-source).
    
-   **Bitbucket**: Hosted **service** by Atlassian that hosts Git repos, PRs, code reviews, pipelines, permissions, project governance.
    

----------

## 5) Difference between TypeScript and JavaScript?

-   **JavaScript**: Dynamic, interpreted in browsers/Node.js.
    
-   **TypeScript**: Superset of JS with **static typing**, interfaces, generics; **compiles to JS**.  
    Benefits: early error detection, better IDE tooling, safer refactors. Runtime is still JS.
    

----------

## 6) Protocols used in Selenium and Playwright?

-   **Selenium**: Uses the **W3C WebDriver protocol** (HTTP/JSON) to drive browsers via drivers (chromedriver/geckodriver/edgedriver).
    
-   **Playwright**: Uses a **WebSocket-based protocol** to control browser engines directly; for Chromium it leverages **CDP (Chrome DevTools Protocol)**; Firefox/WebKit via their native protocols. Result: faster, more deterministic control.
    

----------

## 7) Have you used GitHub Copilot? Where/how?

Yes. Typical usage:

-   **Authoring tests quicker** (Playwright locators, assertions, test data builders).
    
-   **Generating boilerplate** (page objects, fixtures, API clients).
    
-   **Regex and SQL** suggestions; **docstrings** and **inline comments**.
    
-   **Guardrails**: Always review suggestions, run linters/security scans, and keep licenses/compliance in mind.
    

----------

## 8) Challenges you’ve faced in automation

-   **Flaky tests** (timing/async waits). Solved with **strict locators**, **auto-waits**, and **test retries**.
    
-   **Environment instability** & **test data** drift. Solved with **idempotent seeding**, **contract tests**, and **sandbox mocks**.
    
-   **Cross-browser**/mobile differences. Solved with **visual diffs**, **per-browser config**, **feature flags**.
    
-   **Auth (SSO/MFA/CAPTCHA)**. Solved with **test accounts**, **bypass tokens**, **API-level login**.
    
-   **Parallelization** & resource limits. Solved with **sharding**, **containerized runners**, **artifact retention**.
    
-   **Maintenance debt**. Solved via **page objects**, **data builders**, **conventions**, and **linting**.
    

----------

## 9) Have you configured any tools?

-   **Jenkins** agents, node labels, Node/Java toolchains; **shared libraries**.
    
-   **GitHub Actions** runners, secrets, environments, branch protection.
    
-   **SonarQube** scanner integration; **Allure/Playwright HTML** reports.
    
-   **Docker** builds/caching; **S3/Slack** notifications; **SAML/SSO** for tools.
    

----------

## 10) How will you schedule jobs in Jenkins?

-   Use **“Build periodically”** (CRON) or in a **Jenkinsfile**.
    
-   Alternative: **SCM polling**, **webhooks**, or **upstream/downstream** triggers.
    

> `Jenkinsfile` example:

    pipeline {
      triggers { cron('H 2 * * 1-5') } // Weekdays around 02:00
      agent any
      stages {
        stage('Test'){ steps { sh 'npm ci && npx playwright test' } }
      }
    }

----------

## 11) What does a utilities file contain in a framework?

-   **Helpers**: waits, retries, time/date, random data, UUIDs.
    
-   **HTTP/API client** wrappers; **DB** helpers.
    
-   **File** helpers (CSV/XLSX/PDF read/write).
    
-   **Logger** config; **assertion** extensions; **config** loader.
    
-   **Selectors/constants**, **email/SMS** readers (test inbox), **encryption** utils.
    

----------

## 12) Tell me some Git commands

    git init                       # create repo
    git clone <url>                # clone
    git status                     # status
    git add . && git commit -m ""  # stage + commit
    git branch -a                  # list branches
    git switch -c feature/x        # create/switch
    git merge main                 # merge
    git rebase main                # rebase
    git pull --rebase              # update cleanly
    git push origin feature/x      # push
    git log --oneline --graph      # history
    git stash / git stash pop      # stash changes
    git tag v1.0.0                 # tag
    git revert <commit>            # revert safely
    git reset --hard <commit>      # reset (careful)



----------

## 13) Have you automated the PDF file?

Yes — typical validations:

-   **Content**: Extract and assert text, fonts, metadata.
    
-   **Structure**: Page count, bookmarks, form fields.
    
-   **Tables**: Parse with Tabula/camelot (Python) or pdf-parse (Node).
    
-   **Visuals**: Render to images and **snapshot diff** for layout regressions.
    

> Node example (pdf-parse):

    import fs from "fs";
    import pdf from "pdf-parse";
    const data = await pdf(fs.readFileSync("invoice.pdf"));
    expect(data.text).toContain("Total: $99.00");


----------

## 14) How will you validate the data in Excel Macros?

Two angles:

**A) Validate macro output data**

-   Open the Excel file (manually or via automation), **run macro**, save as XLSX/CSV, then **read** with ExcelJS/xlsx (Node) or `pandas` (Python) and **assert** values.
    

**B) Programmatically trigger macros (Windows)**

-   Use **COM automation** (PyWin32 / VBA) to run a macro, then validate outputs.
    

> Python (Windows COM) example:

    import win32com.client as win32
    xl = win32.gencache.EnsureDispatch('Excel.Application')
    wb = xl.Workbooks.Open(r'C:\tests\Report.xlsm')
    xl.Visible = False xl.Application.Run('Report.xlsm!Module1.Generate')
    wb.Save()
    wb.Close(SaveChanges=True)
    xl.Quit()` 

> Note: In CI (Linux), macros don’t run. Prefer extracting logic into a service or re-implement core rules for testability.

----------

## 15) What is a schema validation?

-   **Verifying payload structure** (types, required fields, formats, enums) against a **schema**.
    
-   Used for **APIs** (JSON Schema/OpenAPI), **events** (Avro/Protobuf), and **DB** constraints.
    
-   Catches breaking changes early and supports **contract testing**.
    

> JSON Schema (Node + Ajv) example:

    import Ajv from "ajv";
    const ajv = new Ajv();
    const schema = {
      type: "object",
      required: ["id", "email"],
      properties: {
        id: { type: "string", format: "uuid" },
        email: { type: "string", format: "email" },
        active: { type: "boolean" }
      },
      additionalProperties: false
    };
    const validate = ajv.compile(schema);
    const ok = validate(responseBody);
    if (!ok) console.error(validate.errors);
    expect(ok).toBe(true);

----------

### Bonus: Selenium vs Playwright quick picks

-   **Selenium**: Broad language support, W3C WebDriver, huge ecosystem.
    
-   **Playwright**: Faster, auto-waits, network mocking, trace viewer, first-class parallelism.




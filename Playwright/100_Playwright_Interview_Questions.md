# 100 Playwright Interview Questions - Complete Guide

## Table of Contents
1. [Basics (1-20)](#basics-1-20)
2. [Locators & UI Interaction (21-40)](#locators--ui-interaction-21-40)
3. [Advanced Selectors & Assertions (41-60)](#advanced-selectors--assertions-41-60)
4. [Actions & Events (61-80)](#actions--events-61-80)
5. [Network & Advanced Features (81-100)](#network--advanced-features-81-100)

---

## BASICS (1-20)

### 1. What is Playwright?

**Answer:**
Playwright is a modern, open-source automation framework developed by Microsoft for testing and automating web applications across multiple browsers (Chromium, Firefox, WebKit) with a single API.

**Key Features:**
- Cross-browser support
- Fast and reliable automation
- Built-in wait mechanisms (auto-waiting)
- Network interception
- Screenshot & video recording
- Multi-language support (JavaScript, Python, Java, C#)
- Native support for multiple tabs and contexts

**Example:**
```javascript
const { chromium } = require('playwright');

(async () => {
  const browser = await chromium.launch();
  const page = await browser.newPage();
  await page.goto('https://example.com');
  console.log(await page.title());
  await browser.close();
})();
```

---

### 2. Why use Playwright over Selenium?

**Comparison Table:**

| Feature | Playwright | Selenium |
|---------|-----------|----------|
| **API Design** | Modern, intuitive | Older, verbose |
| **Execution Speed** | Faster | Slower |
| **Auto-waiting** | Built-in | Manual waits required |
| **Multi-tab Support** | Native, simple | Complex workarounds |
| **Network Interception** | Built-in | Not available |
| **Video Recording** | Built-in | External tools needed |
| **Tracing & Debugging** | Built-in trace feature | Not available |
| **Language Support** | JS, Python, Java, C# | Multiple languages |
| **DevTools Protocol** | CDP integration | Not available |
| **Learning Curve** | Gentle | Steep |

**Example - Auto-wait comparison:**
```javascript
// Playwright - Auto-waits for element visibility
await page.click('button#submit'); // Waits automatically!

// Selenium - Manual wait required
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
wait = WebDriverWait(driver, 10)
element = wait.until(EC.presence_of_element_located(("id", "submit")))
element.click()
```

---

### 3. Which languages does Playwright support?

**Supported Languages:**
1. **JavaScript/TypeScript** - Native support
2. **Python** - Full-featured support
3. **Java** - Complete API coverage
4. **C# (.NET)** - Full integration

**Example (Python):**
```python
from playwright.sync_api import sync_playwright

with sync_playwright() as p:
    browser = p.chromium.launch()
    page = browser.new_page()
    page.goto('https://example.com')
    print(page.title())
    browser.close()
```

**Example (Java):**
```java
import com.microsoft.playwright.*;

public class Example {
  public static void main(String[] args) {
    try (Playwright playwright = Playwright.create()) {
      Browser browser = playwright.chromium.launch();
      Page page = browser.newPage();
      page.navigate("https://example.com");
      System.out.println(page.title());
      browser.close();
    }
  }
}
```

---

### 4. Which browsers are supported by Playwright?

**Supported Browsers:**
1. **Chromium** - Chrome, Edge, Brave, Vivaldi
2. **Firefox** - Mozilla Firefox
3. **WebKit** - Safari

**Browser Launch Example:**
```javascript
const { chromium, firefox, webkit } = require('playwright');

(async () => {
  // Launch different browsers
  const chrBrowser = await chromium.launch();
  const ffBrowser = await firefox.launch();
  const wkBrowser = await webkit.launch();
  
  // Get browser info
  console.log(await chrBrowser.version()); // Chromium version
  
  await chrBrowser.close();
  await ffBrowser.close();
  await wkBrowser.close();
})();
```

**Launch with options:**
```javascript
const browser = await chromium.launch({
  headless: false,
  slowMo: 1000,
  args: ['--start-maximized']
});
```

---

### 5. What is Playwright Test Runner?

**Definition:**
Playwright Test is a dedicated test runner for end-to-end testing with built-in support for parallel execution, multiple browsers, retries, screenshots, and HTML reporting.

**Key Features:**
- Parallel execution by default
- Multiple browsers/devices
- Automatic retry on failure
- Screenshots on failure
- Video recording
- HTML reporting
- Fixtures & hooks
- Test isolation

**Example Configuration (playwright.config.ts):**
```typescript
import { defineConfig, devices } from '@playwright/test';

export default defineConfig({
  testDir: './tests',
  fullyParallel: true,
  workers: 4,
  retries: 2,
  reporter: 'html',
  use: {
    baseURL: 'http://localhost:3000',
    screenshot: 'only-on-failure',
    video: 'retain-on-failure',
    trace: 'on-first-retry',
  },
  projects: [
    {
      name: 'chromium',
      use: { ...devices['Desktop Chrome'] },
    },
    {
      name: 'firefox',
      use: { ...devices['Desktop Firefox'] },
    },
  ],
});
```

---

### 6. How do you install Playwright?

**Installation Methods:**

**NPM/Node.js:**
```bash
# Method 1: Create new project with setup
npm init playwright@latest

# Method 2: Install in existing project
npm install @playwright/test
npx playwright install
```

**Python:**
```bash
pip install playwright
playwright install
```

**Java:**
```xml
<!-- Add to pom.xml -->
<dependency>
    <groupId>com.microsoft.playwright</groupId>
    <artifactId>playwright</artifactId>
    <version>1.40.0</version>
</dependency>
```

**C# (.NET):**
```bash
dotnet add package Microsoft.Playwright
pwsh bin/Debug/net6.0/playwright.ps1 install
```

---

### 7. What is auto-waiting in Playwright?

**Definition:**
Auto-waiting automatically waits for elements to be ready before performing actions, eliminating the need for explicit waits in most cases.

**Auto-waiting conditions:**
1. Element is attached to DOM
2. Element is visible
3. Element is stable (not animating)
4. Element is enabled (not disabled)
5. Element doesn't have pointer events

**Example:**
```javascript
// Playwright automatically waits for:
// 1. Element to be in DOM
// 2. Element to be visible
// 3. Element to be stable
await page.click('button#submit'); // No explicit wait needed!

// Manual wait (rarely needed)
await page.waitForSelector('button#submit', { timeout: 5000 });
await page.click('button#submit');

// Configure timeout
await page.click('button#submit', { timeout: 10000 });
```

---

### 8. What is a Locator?

**Definition:**
A Locator is a query object that represents a way to find elements on a page. It's lazy and intelligent, meaning it queries the DOM only when needed.

**Locator Features:**
- Lazy evaluation
- Auto-waits for elements
- Retry mechanism
- Chainable API

**Example:**
```javascript
// Create a locator
const submitButton = page.locator('button#submit');

// Use locator to perform actions
await submitButton.click();
await submitButton.fill('text');
const text = await submitButton.textContent();
const isVisible = await submitButton.isVisible();

// Chain locators
const container = page.locator('div.container');
const button = container.locator('button');
await button.click();
```

---

### 9. Difference between page.locator() and page.$()

**Comparison:**

| Feature | page.locator() | page.$() |
|---------|---|---|
| **Return Type** | Locator object | ElementHandle or null |
| **Lazy Evaluation** | Yes (queries only when needed) | No (immediate query) |
| **Retry Mechanism** | Built-in retries | No retries |
| **Auto-waiting** | Yes | No |
| **Recommended** | ✅ Modern approach | ❌ Legacy (deprecated) |
| **Performance** | Better with retries | Faster for immediate queries |

**Example:**
```javascript
// page.locator() - Modern approach (Recommended)
const locator = page.locator('button#submit');
await locator.click(); // Auto-waits & retries

// page.$() - Legacy approach (Deprecated)
const element = await page.$('button#submit');
if (element) {
  await element.click();
}

// Get multiple elements
const allButtons = await page.$$('button'); // Returns array
const buttons = page.locator('button'); // Returns Locator
```

---

### 10. How to launch a browser in Playwright?

**Browser Launch Syntax:**
```javascript
const { chromium } = require('playwright');

(async () => {
  const browser = await chromium.launch({
    headless: false,        // Show browser window
    slowMo: 1000,          // Slow down actions by 1000ms
    devtools: true,        // Open DevTools
    downloadsPath: '/tmp', // Download location
    args: [
      '--disable-notifications',
      '--disable-plugins',
      '--start-maximized'
    ]
  });
  
  const page = await browser.newPage();
  await page.goto('https://example.com');
  
  // Get browser info
  console.log(await browser.version());
  
  await browser.close();
})();
```

**Launch options:**
- `headless` - Run in headless mode (default: true)
- `slowMo` - Slow down actions (milliseconds)
- `devtools` - Open DevTools on launch
- `downloadsPath` - Set download directory
- `args` - Additional browser arguments

---

### 11. How do you open a new page or tab?

**Creating New Pages/Tabs:**
```javascript
const { chromium } = require('playwright');

(async () => {
  const browser = await chromium.launch();
  
  // Method 1: Using browser context
  const context = await browser.newContext();
  const page1 = await context.newPage();
  const page2 = await context.newPage();
  
  await page1.goto('https://example.com');
  await page2.goto('https://google.com');
  
  // Method 2: From existing page
  const page3 = await browser.newPage();
  
  // Get all pages in context
  const pages = context.pages();
  console.log(`Total pages: ${pages.length}`);
  
  // Switch between pages
  await page1.click('button');
  await page2.fill('input', 'text');
  
  // Close pages
  await page1.close();
  await page2.close();
  
  await context.close();
  await browser.close();
})();
```

---

### 12. What is headless mode?

**Definition:**
Headless mode runs the browser without displaying a GUI. It's faster and commonly used for automation and testing.

**Headless vs Non-headless:**

| Aspect | Headless | Non-headless |
|--------|----------|---|
| **Speed** | Faster | Slower |
| **Memory** | Lower | Higher |
| **Debugging** | Difficult | Easy |
| **Visual Feedback** | None | Full visibility |
| **Use Case** | CI/CD, Testing | Debugging, Development |

**Example:**
```javascript
// Headless mode (default - faster, used in CI/CD)
const browser = await chromium.launch({ headless: true });

// Non-headless mode (shows browser window, for debugging)
const browser = await chromium.launch({ headless: false });

// Combine with other options
const browser = await chromium.launch({
  headless: false,
  slowMo: 500,
  devtools: true
});
```

---

### 13. How to run tests in UI mode?

**UI Mode Features:**
- Real-time test execution visualization
- Step-by-step debugging
- Time-travel debugging
- Inspector for element selection
- Test filtering

**Run tests in UI mode:**
```bash
# Run all tests in UI mode
npx playwright test --ui

# Run specific test file
npx playwright test tests/login.spec.ts --ui

# Run tests in specific browser
npx playwright test --ui --project=chromium

# Run with specific heading
npx playwright test --ui --grep="login"
```

**Playwright Test File:**
```typescript
import { test, expect } from '@playwright/test';

test('should login successfully', async ({ page }) => {
  await page.goto('https://example.com/login');
  await page.fill('input[name="email"]', 'test@example.com');
  await page.fill('input[name="password"]', 'password123');
  await page.click('button[type="submit"]');
  await expect(page).toHaveURL('https://example.com/dashboard');
});

test('should display error on invalid credentials', async ({ page }) => {
  await page.goto('https://example.com/login');
  await page.fill('input[name="email"]', 'invalid@example.com');
  await page.fill('input[name="password"]', 'wrong');
  await page.click('button[type="submit"]');
  await expect(page.locator('text=Invalid credentials')).toBeVisible();
});
```

---

### 14. How to take a screenshot?

**Screenshot Methods:**
```javascript
const { chromium } = require('playwright');

(async () => {
  const browser = await chromium.launch();
  const page = await browser.newPage();
  await page.goto('https://example.com');
  
  // Full page screenshot
  await page.screenshot({
    path: 'screenshots/full-page.png',
    fullPage: true,
    type: 'png'
  });
  
  // Viewport screenshot only
  await page.screenshot({ path: 'screenshot.png' });
  
  // Element screenshot
  const element = page.locator('button#submit');
  await element.screenshot({ path: 'button.png' });
  
  // Screenshot with quality (JPEG)
  await page.screenshot({
    path: 'screenshot.jpg',
    type: 'jpeg',
    quality: 80
  });
  
  // Get screenshot as buffer
  const buffer = await page.screenshot();
  console.log(buffer);
  
  await browser.close();
})();
```

---

### 15. How to record a script using Codegen?

**Codegen Overview:**
Codegen automatically generates test scripts by recording your interactions with the web application.

**Start Codegen:**
```bash
# Record on specific URL
npx playwright codegen https://example.com

# Record and save to file
npx playwright codegen https://example.com -o test.spec.ts

# Record in specific browser
npx playwright codegen --browser=firefox https://example.com

# Record with specific device
npx playwright codegen --device="iPhone 12" https://example.com
```

**Generated Script Example:**
```typescript
import { test, expect } from '@playwright/test';

test('test', async ({ page }) => {
  // Navigate to page
  await page.goto('https://example.com/');
  
  // Interact with elements
  await page.locator('input[name="search"]').click();
  await page.locator('input[name="search"]').fill('automation testing');
  await page.locator('button:has-text("Search")').click();
  
  // Verify results
  await expect(page.locator('text=Results for')).toBeVisible();
});
```

---

### 16. What is browserContext?

**Definition:**
A BrowserContext is an isolated browser session within a single browser instance with separate cookies, cache, local storage, and session storage.

**BrowserContext Features:**
- Isolated storage
- Separate cookies
- Independent cache
- No cookie sharing
- Multiple concurrent contexts

**Example:**
```javascript
const { chromium } = require('playwright');

(async () => {
  const browser = await chromium.launch();
  
  // Create isolated contexts (like incognito windows)
  const context1 = await browser.newContext();
  const context2 = await browser.newContext();
  
  // Create pages in each context
  const page1 = await context1.newPage();
  const page2 = await context2.newPage();
  
  // Simulate two different users
  await page1.goto('https://example.com');
  await page1.fill('input[name="username"]', 'user1');
  await page1.fill('input[name="password"]', 'pass1');
  
  await page2.goto('https://example.com');
  await page2.fill('input[name="username"]', 'user2');
  await page2.fill('input[name="password"]', 'pass2');
  
  // Contexts have separate cookies
  const cookies1 = await context1.cookies();
  const cookies2 = await context2.cookies();
  console.log(cookies1.length, cookies2.length); // Different values
  
  await context1.close();
  await context2.close();
  await browser.close();
})();
```

---

### 17. Difference between Browser and BrowserContext?

**Comparison:**

| Feature | Browser | BrowserContext |
|---------|---------|---|
| **Scope** | Entire browser instance | Isolated session |
| **Cookies** | Shared across all contexts | Separate for each context |
| **Cache** | Shared | Separate |
| **Local Storage** | Shared | Separate |
| **Session Storage** | Shared | Separate |
| **Multiple Tabs** | Within same context | Multiple contexts possible |
| **Use Case** | Browser setup | Multi-user/multi-session testing |
| **Concurrency** | Single instance | Multiple concurrent contexts |

**Visual Example:**
```
Browser (Single Instance)
├── BrowserContext 1 (User 1 session)
│   ├── Page 1
│   └── Page 2
├── BrowserContext 2 (User 2 session)
│   ├── Page 1
│   └── Page 2
└── BrowserContext 3 (User 3 session)
    └── Page 1
```

---

### 18. What is tracing in Playwright?

**Definition:**
Tracing captures all interactions, network activity, DOM snapshots, and screenshots for debugging and root cause analysis of test failures.

**Trace Contents:**
- Screenshots
- DOM snapshots
- Network requests/responses
- Console logs
- Page events
- Actions timeline

**Example:**
```javascript
const { chromium } = require('playwright');

(async () => {
  const browser = await chromium.launch();
  const context = await browser.newContext();
  
  // Start tracing
  await context.tracing.start({
    screenshots: true,
    snapshots: true,
    sources: true
  });
  
  const page = await context.newPage();
  await page.goto('https://example.com');
  await page.click('button#submit');
  
  // Stop tracing and save
  await context.tracing.stop({
    path: 'trace.zip'
  });
  
  await context.close();
  await browser.close();
})();
```

---

### 19. How to generate a trace?

**Configuration Method:**
```typescript
// playwright.config.ts
export default defineConfig({
  use: {
    trace: 'on-first-retry', // 'on', 'off', 'on-first-retry'
  },
});
```

**Programmatic Method:**
```typescript
import { test, expect } from '@playwright/test';

test('with trace', async ({ page, context }) => {
  await context.tracing.start({
    screenshots: true,
    snapshots: true
  });
  
  await page.goto('https://example.com');
  await page.click('button');
  
  await context.tracing.stop({
    path: 'trace.zip'
  });
});
```

**Trace options:**
- `on` - Record traces for all tests
- `off` - Don't record traces
- `on-first-retry` - Record only when test retries

---

### 20. How to view Playwright report?

**Configure Reporter:**
```typescript
// playwright.config.ts
export default defineConfig({
  reporter: [
    ['html', { open: 'always' }],
    ['list'],
    ['json', { outputFile: 'results.json' }]
  ],
});
```

**View Report:**
```bash
# Automatically opens after test run
npx playwright test

# Manually open existing report
npx playwright show-report

# Open specific report file
npx playwright show-report ./playwright-report
```

**Report Contents:**
- Test results (passed/failed/skipped)
- Execution time
- Screenshots on failure
- Video recordings
- Trace files
- Detailed error messages

---

## LOCATORS & UI INTERACTION (21-40)

### 21. Types of locators in Playwright?

**Locator Types:**

```javascript
// 1. CSS Selector (Most common)
page.locator('button#submit')
page.locator('div.container > span')
page.locator('input[type="email"]')

// 2. XPath
page.locator('//button[@id="submit"]')
page.locator('//div[contains(@class, "error")]')

// 3. Text Locator
page.locator('text=Login')
page.locator(':has-text("Click me")')
page.locator('text=/login/i') // Case-insensitive

// 4. Role Locator (Recommended - Accessibility-based)
page.locator('role=button[name="Submit"]')
page.locator('role=textbox[name="Email"]')
page.locator('role=link[name="Profile"]')

// 5. Label Locator
page.locator('label:has-text("Email")')

// 6. nth Locator
page.locator('button').nth(0)

// 7. Filter Locator
page.locator('button').filter({ hasText: 'Submit' })

// 8. Combine Locators (Chaining)
page.locator('div').locator('button')

// 9. Nth Last Locator
page.locator('button').nth(-1) // Last button
```

---

### 22. How does Playwright handle dynamic elements?

**Dynamic Element Handling:**

```javascript
// Auto-waiting mechanism
await page.locator('button#dynamic').click(); // Waits automatically

// Configure timeout
await page.locator('button#dynamic').click({ timeout: 5000 });

// Explicit wait for visibility
await page.locator('button#dynamic').waitFor({ state: 'visible' });

// Wait with condition
await page.waitForFunction(() => {
  return document.querySelectorAll('button').length > 0;
});

// Retry mechanism with poll interval
const element = await page.locator('button#delayed');
await element.click(); // Retries internally

// Check if element exists before interaction
const count = await page.locator('button').count();
if (count > 0) {
  await page.locator('button').first().click();
}
```

---

### 23. How to handle dropdowns?

**Dropdown Handling:**

```javascript
// Method 1: Native select element
await page.selectOption('select#country', 'USA');
await page.selectOption('select#country', { value: 'usa' });
await page.selectOption('select#country', { label: 'United States' });

// Get selected value
const selectedValue = await page.inputValue('select#country');
console.log(selectedValue);

// Select multiple options
await page.selectOption('select#skills', ['JS', 'Python']);

// Method 2: Custom dropdown (Material-UI, Bootstrap, etc.)
await page.click('div#custom-dropdown');
await page.click('div.dropdown-item:has-text("Option 1")');

// Method 3: Click and wait
await page.click('button#dropdown-toggle');
await page.waitForSelector('.dropdown-menu');
await page.click('a:has-text("Settings")');

// Get all options
const options = await page.locator('option').allTextContents();
console.log(options);
```

---

### 24. How to handle iframes?

**IFrame Handling:**

```javascript
// Method 1: Using frameLocator
await page.frameLocator('iframe#payment')
  .locator('button#pay')
  .click();

// Method 2: Using frame()
const frame = await page.frame({ name: 'payment' });
await frame.click('button#pay');

// Method 3: By URL pattern
const frame = await page.frame({ url: /payment/ });
await frame.fill('input[name="cardNumber"]', '1234567890');

// Method 4: Get frame and interact
const frames = page.frames();
for (const frame of frames) {
  console.log(frame.name());
  console.log(frame.url());
}

// Nested iframes
await page.frameLocator('iframe#outer')
  .frameLocator('iframe#inner')
  .locator('button')
  .click();

// Wait for frame to load
await page.waitForSelector('iframe#payment');
const frame = await page.frame({ name: 'payment' });
await frame.waitForLoadState();
```

---

### 25. How to handle alerts/popups?

**Alert Handling:**

```javascript
// Method 1: Listen for alert
page.on('dialog', dialog => {
  console.log(dialog.type()); // 'alert', 'confirm', 'prompt', 'beforeunload'
  console.log(dialog.message());
  dialog.accept();
});
await page.click('button#showAlert');

// Method 2: Reject dialog
page.on('dialog', dialog => {
  dialog.dismiss();
});
await page.click('button#showConfirm');

// Method 3: Accept with input (for prompt)
page.on('dialog', dialog => {
  dialog.accept('user@example.com');
});
await page.click('button#showPrompt');

// Method 4: Using waitForEvent
const alertPromise = page.waitForEvent('dialog');
await page.click('button#showAlert');
const dialog = await alertPromise;
console.log(dialog.message());
await dialog.accept();

// Method 5: Handle multiple alerts
let alertCount = 0;
page.on('dialog', async dialog => {
  alertCount++;
  console.log(`Alert ${alertCount}: ${dialog.message()}`);
  await dialog.accept();
});
```

---

### 26. What is nth() locator?

**nth() Locator Usage:**

```javascript
// Select first element (0-indexed)
await page.locator('button').nth(0).click();

// Select second element
await page.locator('button').nth(1).click();

// Select last element using negative index
await page.locator('button').nth(-1).click();

// Select second-to-last element
await page.locator('button').nth(-2).click();

// Get total count
const count = await page.locator('button').count();
console.log(`Total buttons: ${count}`);

// Iterate through elements
for (let i = 0; i < count; i++) {
  const text = await page.locator('button').nth(i).textContent();
  console.log(text);
}

// Chain with other locators
const firstButton = page.locator('div.container').locator('button').nth(0);
await firstButton.click();
```

---

### 27. What is filter() locator?

**filter() Locator Usage:**

```javascript
// Filter by text
await page.locator('button').filter({ hasText: 'Submit' }).click();
await page.locator('button').filter({ hasText: /submit/i }).click();

// Filter by attribute
await page.locator('input').filter({ has: page.locator('[type="checkbox"]') }).click();

// Filter by selector
await page.locator('div').filter({ 
  has: page.locator('span:has-text("Active")') 
}).click();

// Filter with not selector
await page.locator('button').filter({ 
  has: page.locator('[disabled]').nth(-1) 
}).click();

// Chain multiple filters
await page.locator('button')
  .filter({ hasText: 'Submit' })
  .filter({ has: page.locator('[data-test="active"]') })
  .click();

// Filter for disabled elements
const disabledButtons = await page.locator('button:disabled').count();
console.log(`Disabled buttons: ${disabledButtons}`);
```

---

### 28. How to click using text locator?

**Text-based Clicking:**

```javascript
// Exact text match
await page.locator('text=Login').click();
await page.locator(':has-text("Login")').click();

// Partial text match
await page.locator('button:has-text("Sub")').click(); // Matches "Submit"

// Case-insensitive match
await page.locator('text=/login/i').click();

// Multiple word text
await page.locator('text=Click Here').click();

// First matching element
await page.locator('button:has-text("Click")').first().click();

// Last matching element
await page.locator('button:has-text("Click")').last().click();

// Combine text with other selectors
await page.locator('div.container >> text=Submit').click();
await page.locator('button[id="submit"]:has-text("Submit")').click();

// Dynamic text (variable)
const buttonText = 'Login';
await page.locator(`text=${buttonText}`).click();
```

---

### 29. How to wait for an element?

**Wait Methods:**

```javascript
// Method 1: Wait for selector
await page.waitForSelector('button#submit', { timeout: 5000 });

// Method 2: Wait with state
await page.locator('button#submit').waitFor({ state: 'visible', timeout: 5000 });

// Method 3: Wait for hidden state
await page.locator('loading-spinner').waitFor({ state: 'hidden' });

// Method 4: Wait for attached
await page.locator('button#submit').waitFor({ state: 'attached' });

// Method 5: Wait for function condition
await page.waitForFunction(() => {
  return document.querySelectorAll('button').length > 5;
}, 10000);

// Method 6: Wait for navigation
await page.waitForNavigation();
await page.click('link#profile');

// Method 7: Wait for URL change
await page.waitForURL(/profile/);

// Method 8: Wait for load state
await page.goto('https://example.com');
await page.waitForLoadState('networkidle');

// Method 9: Wait with polling
await page.locator('button').nth(0).waitFor();
```

---

### 30. What is toBeVisible() vs toBeHidden()?

**Visibility Assertions:**

```javascript
import { expect } from '@playwright/test';

// toBeVisible() - Assert element is visible
await expect(page.locator('button#submit')).toBeVisible();

// toBeHidden() - Assert element is hidden
await expect(page.locator('loading-spinner')).toBeHidden();

// With timeout
await expect(page.locator('success-message')).toBeVisible({ timeout: 10000 });

// Negative assertion
await expect(page.locator('error-message')).not.toBeVisible();

// Wait for visibility
await expect(page.locator('delayed-element')).toBeVisible({ timeout: 5000 });

// Check visibility programmatically
const isVisible = await page.locator('button').isVisible();
console.log(isVisible); // true or false

// Wait and verify
await page.locator('loading').waitFor({ state: 'hidden' });
await expect(page.locator('content')).toBeVisible();
```

---

### 31. How to handle checkboxes?

**Checkbox Handling:**

```javascript
// Check a checkbox
await page.check('input[name="terms"]');

// Uncheck a checkbox
await page.uncheck('input[name="terms"]');

// Check using locator
const checkbox = page.locator('input[name="subscribe"]');
await checkbox.check();

// Uncheck using locator
await checkbox.uncheck();

// Check if checkbox is checked
const isChecked = await page.locator('input[name="terms"]').isChecked();
console.log(isChecked); // true or false

// Get checked status
const checked = await page.inputValue('input[name="terms"]') === 'on';

// Assertion
await expect(page.locator('input[name="terms"]')).toBeChecked();
await expect(page.locator('input[name="newsletter"]')).not.toBeChecked();

// Check/uncheck multiple checkboxes
const checkboxes = ['terms', 'privacy', 'marketing'];
for (const name of checkboxes) {
  await page.check(`input[name="${name}"]`);
}
```

---

### 32. How to upload a file?

**File Upload Methods:**

```javascript
// Single file upload
await page.locator('input[type="file"]').setInputFiles('path/to/file.pdf');

// Multiple files upload
await page.locator('input[type="file"]').setInputFiles([
  'path/to/file1.pdf',
  'path/to/file2.pdf',
  'path/to/file3.pdf'
]);

// Clear file input
await page.locator('input[type="file"]').setInputFiles([]);

// Get file path dynamically
const path = require('path');
const filePath = path.join(__dirname, 'test.pdf');
await page.locator('input[type="file"]').setInputFiles(filePath);

// Upload with data buffer
await page.locator('input[type="file"]').setInputFiles({
  name: 'test.txt',
  mimeType: 'text/plain',
  buffer: Buffer.from('file content')
});

// Verify file was uploaded
await page.locator('button#submit').click();
await expect(page.locator('text=Upload successful')).toBeVisible();
```

---

### 33. How to hover on an element?

**Hover/Mouse Over:**

```javascript
// Hover using locator
await page.locator('button#hover-me').hover();

// Hover with specific position
await page.locator('button#hover-me').hover({
  position: { x: 10, y: 20 }
});

// Hover and wait for element to appear
await page.locator('div#menu').hover();
await page.locator('div#submenu').waitFor({ state: 'visible' });
await page.locator('div#submenu-item').click();

// Using mouse move
await page.mouse.move(100, 100);
await page.waitForSelector('.tooltip');

// Multiple hovers
await page.locator('div.parent').hover();
await page.locator('div.child').hover();
await page.locator('div.grandchild').click();

// Get position and hover
const box = await page.locator('button').boundingBox();
await page.mouse.move(box.x + box.width / 2, box.y + box.height / 2);
```

---

### 34. How to drag and drop?

**Drag & Drop Implementation:**

```javascript
// Simple drag and drop
await page.locator('div#draggable').dragTo(page.locator('div#drop-zone'));

// Drag with specific positions
await page.locator('div#draggable').dragTo(page.locator('div#drop-zone'), {
  sourcePosition: { x: 10, y: 10 },
  targetPosition: { x: 50, y: 50 }
});

// Using mouse events for complex scenarios
await page.mouse.move(100, 100);
await page.mouse.down();
await page.mouse.move(200, 200, { steps: 10 });
await page.mouse.up();

// Verify drop was successful
await page.locator('div#draggable').dragTo(page.locator('div#drop-zone'));
await expect(page.locator('text=Item dropped')).toBeVisible();

// Drag multiple times
for (let i = 0; i < 3; i++) {
  await page.locator('div.item').nth(i).dragTo(page.locator('div#basket'));
}
```

---

### 35. How to scroll in Playwright?

**Scrolling Methods:**

```javascript
// Scroll entire page down
await page.evaluate(() => window.scrollBy(0, 500));

// Scroll to specific element
await page.locator('div#target').scrollIntoViewIfNeeded();

// Scroll to top
await page.evaluate(() => window.scrollTo(0, 0));

// Scroll to specific pixel position
await page.evaluate(() => window.scrollTo(0, 1000));

// Scroll within a scrollable element
await page.locator('div#scrollable').evaluate(el => {
  el.scrollTop += 500;
});

// Scroll right
await page.evaluate(() => window.scrollBy(500, 0));

// Scroll to element before interaction
await page.locator('button#bottom').scrollIntoViewIfNeeded();
await page.locator('button#bottom').click();

// Infinite scroll
for (let i = 0; i < 5; i++) {
  await page.evaluate(() => window.scrollBy(0, window.innerHeight));
  await page.waitForLoadState('networkidle');
}
```

---

### 36. How to get inner text of an element?

**Text Extraction Methods:**

```javascript
// Get text content (with whitespace)
const text = await page.locator('p#message').textContent();
console.log(text); // " Some text "

// Get inner text (similar to JS innerText)
const innerText = await page.locator('button').innerText();
console.log(innerText);

// Get inner HTML
const html = await page.locator('div#content').innerHTML();
console.log(html);

// Get all text contents from multiple elements
const allTexts = await page.locator('div').allTextContents();
console.log(allTexts); // Array of texts

// Get attribute value
const href = await page.locator('a').getAttribute('href');
console.log(href);

// Get input value
const inputValue = await page.locator('input#email').inputValue();
console.log(inputValue);

// Trim and extract text
const trimmedText = (await page.locator('span').textContent()).trim();
console.log(trimmedText);
```

---

### 37. How to assert URL?

**URL Assertions:**

```javascript
import { expect } from '@playwright/test';

// Assert exact URL
await expect(page).toHaveURL('https://example.com/dashboard');

// Assert URL with regex
await expect(page).toHaveURL(/dashboard/);

// Assert URL with partial match
await expect(page).toHaveURL(/example\.com.*dashboard/);

// Assert URL after navigation
await page.click('button#profile');
await expect(page).toHaveURL('https://example.com/profile');

// Manual URL assertion
const currentURL = page.url();
expect(currentURL).toContain('example.com');

// Assert URL contains query parameter
await expect(page).toHaveURL(/search\?q=/);

// Assert URL path
const urlPath = new URL(page.url()).pathname;
expect(urlPath).toBe('/dashboard');

// Wait for URL change
await page.waitForURL(/profile/);
```

---

### 38. How to press keyboard keys?

**Keyboard Input Methods:**

```javascript
// Press single key
await page.locator('input#search').press('Enter');
await page.press('input#search', 'Tab');

// Keyboard combinations
await page.press('input#search', 'Control+A'); // Select all
await page.press('input#search', 'Control+C'); // Copy
await page.press('input#search', 'Control+V'); // Paste
await page.press('input#search', 'Control+Z'); // Undo

// Arrow keys
await page.press('input', 'ArrowDown');
await page.press('input', 'ArrowUp');
await page.press('input', 'ArrowLeft');
await page.press('input', 'ArrowRight');

// Special keys
await page.press('input', 'Escape');
await page.press('input', 'Delete');
await page.press('input', 'Backspace');
await page.press('input', 'PageDown');
await page.press('input', 'PageUp');
await page.press('input', 'Home');
await page.press('input', 'End');

// Keyboard down and up
await page.keyboard.down('Shift');
await page.keyboard.press('ArrowDown');
await page.keyboard.up('Shift');
```

---

### 39. How to handle multi-tab scenarios?

**Multi-Tab Handling:**

```javascript
// Method 1: Using waitForEvent
const [newPage] = await Promise.all([
  context.waitForEvent('page'), // Wait for new tab
  page.click('a[target="_blank"]') // Click link that opens new tab
]);

await newPage.waitForLoadState();
console.log(newPage.url());
await newPage.close();

// Method 2: Get all pages
const pages = context.pages();
console.log(`Total tabs: ${pages.length}`);

// Method 3: Switch between tabs
const page1 = pages[0];
const page2 = pages[1];
await page1.click('button');
const result = await page2.textContent('div#result');
console.log(result);

// Method 4: Interact with multiple tabs
const [popup] = await Promise.all([
  context.waitForEvent('page'),
  page.click('button#open-popup')
]);

await popup.fill('input#email', 'test@example.com');
await popup.click('button#submit');
await popup.close();

// Method 5: Handle new window (not tab)
const [newWindow] = await Promise.all([
  context.waitForEvent('page'),
  page.click('a[target="_blank"]')
]);
```

---

### 40. How to handle expandable menus?

**Expandable Menu Handling:**

```javascript
// Click to expand menu
await page.locator('button#menu-toggle').click();

// Wait for menu to be visible
await page.locator('div#menu').waitFor({ state: 'visible' });

// Click menu item
await page.locator('a:has-text("Settings")').click();

// Handle nested/expandable menus
await page.locator('button#main-menu').click();
await page.locator('button#submenu-toggle').hover();
await page.locator('a:has-text("Nested Item")').click();

// Check if menu is expanded
const isExpanded = await page.locator('div#menu').isVisible();
console.log(isExpanded);

// Close menu
await page.locator('button#menu-close').click();
await expect(page.locator('div#menu')).toBeHidden();

// Toggle menu (expand/collapse)
await page.locator('button#toggle').click();
await page.locator('div#content').waitFor({ state: 'visible' });
await page.locator('button#toggle').click();
await page.locator('div#content').waitFor({ state: 'hidden' });

// Verify menu item is clickable
const menuItem = page.locator('a:has-text("Profile")');
await menuItem.scrollIntoViewIfNeeded();
await menuItem.click();
```

---

## ADVANCED SELECTORS & ASSERTIONS (41-60)

### 41. What are composite locators?

**Composite Locator Examples:**

```javascript
// Combine CSS and text
page.locator('button:has-text("Submit")');

// Chain multiple selectors
page.locator('div.container')
  .locator('form')
  .locator('input[type="email"]');

// Using >> operator
page.locator('div >> button');

// Combine role and text
page.locator('role=button[name=/submit/i]');

// Complex selector
page.locator('div:has(> span.active) >> button.primary');
```

---

### 42. How to use role locators?

**Role-based Locators (Recommended):**

```javascript
// Button with text
page.locator('role=button[name="Submit"]');

// Textbox with label
page.locator('role=textbox[name="Email"]');

// Link with text
page.locator('role=link[name="Home"]');

// Checkbox
page.locator('role=checkbox[name="Accept Terms"]');

// Radio button
page.locator('role=radio[name="Option 1"]');

// Combobox (select)
page.locator('role=combobox[name="Country"]');

// List with items
page.locator('role=list').locator('role=listitem');

// Dialog
page.locator('role=dialog[name="Confirm Action"]');
```

---

### 43. How to handle shadow DOM?

**Shadow DOM Handling:**

```javascript
// Pierce shadow DOM
page.locator('pierce/button');

// Navigate through shadow DOM layers
page.locator('div.host >> pierce/button.shadow-button');

// Get shadow element and interact
const shadowElement = page.locator('pierce/input#shadow-input');
await shadowElement.fill('text');

// Wait for shadow element
await page.locator('pierce/button').waitFor();

// Use pierce with aria roles
page.locator('pierce/role=button[name="Submit"]');
```

---

### 44. How to use :has() selector?

**:has() Selector Usage:**

```javascript
// Select div that contains a span with text "Active"
page.locator('div:has(> span.active)');

// Select button that has disabled attribute
page.locator('button:has([disabled])');

// Select form with email input
page.locator('form:has(input[type="email"])');

// Complex :has() selector
page.locator('div:has(> button:has-text("Save")) >> click');

// Chaining :has()
page.locator('div:has(button:has-text("Delete")) >> button');
```

---

### 45. How to use :visible and :hidden selectors?

**Visibility Selectors:**

```javascript
// Select visible element
page.locator('button:visible');

// Select hidden element
page.locator('div:hidden');

// Visible with text
page.locator('button:visible:has-text("Submit")');

// Hidden elements count
const hiddenCount = await page.locator('div:hidden').count();

// Get only visible items from list
const visibleItems = page.locator('li:visible');
```

---

### 46. How to handle focus in Playwright?

**Focus Management:**

```javascript
// Focus on element
await page.locator('input#email').focus();

// Press Tab to focus next element
await page.press('input#email', 'Tab');

// Focus on specific element by keyboard
await page.locator('button').first().focus();
await page.keyboard.press('Tab');

// Check if element has focus
const hasFocus = await page.locator('input#email').evaluate(
  el => el === document.activeElement
);
console.log(hasFocus);

// Focus trap in modal
await page.locator('button#open-modal').click();
await page.locator('input#first').focus();
for (let i = 0; i < 5; i++) {
  await page.keyboard.press('Tab');
}
```

---

### 47. How to assert element attributes?

**Attribute Assertions:**

```javascript
import { expect } from '@playwright/test';

// Assert specific attribute
await expect(page.locator('button#submit')).toHaveAttribute('type', 'submit');

// Assert attribute exists
const href = await page.locator('a').getAttribute('href');
expect(href).toBeTruthy();

// Assert class
await expect(page.locator('div')).toHaveClass('container');
await expect(page.locator('div')).toHaveClass(/active|disabled/);

// Assert multiple classes
await expect(page.locator('button')).toHaveClass('btn btn-primary');

// Assert data attribute
const dataValue = await page.locator('button').getAttribute('data-id');
expect(dataValue).toBe('123');

// Assert not have attribute
await expect(page.locator('button')).not.toHaveAttribute('disabled');
```

---

### 48. How to assert text content?

**Text Content Assertions:**

```javascript
import { expect } from '@playwright/test';

// Assert exact text
await expect(page.locator('h1')).toHaveText('Welcome');

// Assert partial text
await expect(page.locator('p')).toContainText('successful');

// Assert text case-insensitive
await expect(page.locator('button')).toContainText(/submit/i);

// Assert all text contents
const texts = await page.locator('li').allTextContents();
expect(texts).toContain('Item 1');

// Assert text not present
await expect(page.locator('error-message')).not.toContainText('Error');

// Assert multiple text patterns
await expect(page.locator('div')).toContainText(/pattern1|pattern2/);
```

---

### 49. How to handle CSS/style properties?

**CSS Properties:**

```javascript
// Get CSS property value
const color = await page.locator('button').evaluate(
  el => window.getComputedStyle(el).color
);
console.log(color);

// Assert display property
const display = await page.locator('div').evaluate(
  el => window.getComputedStyle(el).display
);
expect(display).toBe('block');

// Check if element is visible via CSS
const visibility = await page.locator('div').evaluate(
  el => window.getComputedStyle(el).visibility
);
expect(visibility).not.toBe('hidden');

// Get all computed styles
const styles = await page.locator('button').evaluate(
  el => window.getComputedStyle(el).cssText
);
console.log(styles);
```

---

### 50. How to use custom matchers?

**Custom Matcher Examples:**

```typescript
import { test, expect } from '@playwright/test';

// Add custom matcher
expect.extend({
  async toHaveFormError(page, fieldName) {
    const error = page.locator(`[data-field="${fieldName}"] .error`);
    const visible = await error.isVisible();
    
    return {
      pass: visible,
      message: () => `Expected form field "${fieldName}" to have error`,
    };
  },
});

// Use custom matcher
test('should show form error', async ({ page }) => {
  await expect(page).toHaveFormError('email');
});
```

---

## ACTIONS & EVENTS (61-80)

### 51. How to fill form inputs?

**Form Filling Methods:**

```javascript
// Fill text input
await page.locator('input#email').fill('test@example.com');

// Type text (character by character)
await page.locator('input#password').type('password123');

// Fill multiple inputs
await page.locator('input[name="email"]').fill('user@example.com');
await page.locator('input[name="name"]').fill('John Doe');
await page.locator('textarea').fill('Long form content...');

// Clear and fill
await page.locator('input#search').clear();
await page.locator('input#search').fill('new search term');

// Fill with keyboard events
await page.locator('input').fill('text');
await page.keyboard.press('Tab');

// Fill with special characters
await page.locator('input').fill('test@123!@#');
```

---

### 52. How to handle page events?

**Page Event Listeners:**

```javascript
// Page navigation event
page.on('load', () => {
  console.log('Page loaded');
});

// Console message
page.on('console', msg => {
  console.log(`Console: ${msg.text()}`);
});

// Page error
page.on('error', error => {
  console.log(`Page error: ${error}`);
});

// Response received
page.on('response', response => {
  console.log(`Response: ${response.status()} ${response.url()}`);
});

// Request sent
page.on('request', request => {
  console.log(`Request: ${request.method()} ${request.url()}`);
});

// Dialog (alert/confirm)
page.on('dialog', dialog => {
  console.log(`Dialog: ${dialog.message()}`);
  dialog.accept();
});

// Popup
page.on('popup', popup => {
  console.log(`Popup URL: ${popup.url()}`);
});
```

---

### 53. How to double-click an element?

**Double-Click Action:**

```javascript
// Double-click using locator
await page.locator('text#editable').dblclick();

// Double-click with options
await page.locator('button').dblclick({
  timeout: 5000,
  button: 'left', // 'left', 'right', 'middle'
  clickCount: 2
});

// Double-click to edit
await page.locator('td#value').dblclick();
await page.locator('input').fill('new value');
await page.keyboard.press('Enter');

// Double-click multiple elements
const items = page.locator('li');
const count = await items.count();
for (let i = 0; i < count; i++) {
  await items.nth(i).dblclick();
}
```

---

### 54. How to right-click (context menu)?

**Right-Click Action:**

```javascript
// Right-click on element
await page.locator('div#item').click({ button: 'right' });

// Wait for context menu and click option
await page.locator('div#item').click({ button: 'right' });
await page.locator('text=Delete').click();

// Listen for context menu
page.on('popup', popup => {
  console.log('Context menu appeared');
});

// Right-click and verify menu
await page.locator('button').click({ button: 'right' });
await expect(page.locator('text=Edit')).toBeVisible();
await expect(page.locator('text=Delete')).toBeVisible();
```

---

### 55. How to handle network requests?

**Network Request/Response Handling:**

```javascript
// Intercept and abort request
await page.route('**/api/data', route => {
  route.abort();
});
await page.goto('https://example.com');

// Mock response
await page.route('**/api/data', route => {
  route.abort('failed'); // Abort with error
});

// Modify request headers
await page.route('**/api/**', route => {
  const headers = { ...route.request().headers(), 'Authorization': 'Bearer token' };
  route.continue({ headers });
});

// Mock API response
await page.route('**/api/users', route => {
  route.fulfill({
    status: 200,
    contentType: 'application/json',
    body: JSON.stringify([{ id: 1, name: 'John' }])
  });
});

// Wait for API call
const [response] = await Promise.all([
  page.waitForResponse(response => response.url().includes('/api/users')),
  page.click('button#load-users')
]);
console.log(response.status());
```

---

### 56. How to handle navigation?

**Navigation Methods:**

```javascript
// Navigate to URL
await page.goto('https://example.com');

// Navigate with options
await page.goto('https://example.com', {
  waitUntil: 'networkidle', // 'load', 'domcontentloaded', 'networkidle'
  timeout: 30000
});

// Wait for navigation
await page.waitForNavigation();
await page.click('link#next-page');

// Go back
await page.goBack();

// Go forward
await page.goForward();

// Reload page
await page.reload();

// Wait for URL
await page.waitForURL(/dashboard/);
```

---

### 57. How to handle browser back/forward?

**Browser History Navigation:**

```javascript
// Go back one page
await page.goBack();

// Go forward one page
await page.goForward();

// Check navigation history
const canGoBack = await page.evaluate(() => history.length > 1);

// Navigate with history
await page.goto('page1.html');
await page.goto('page2.html');
await page.goBack(); // Back to page1
await page.goForward(); // Forward to page2

// Wait for back navigation
await page.waitForNavigation();
await page.goBack();
```

---

### 58. How to capture network traffic?

**Network Traffic Capture:**

```javascript
const requests = [];

// Capture all requests
page.on('request', request => {
  requests.push({
    url: request.url(),
    method: request.method(),
    headers: request.headers()
  });
});

// Capture responses
const responses = [];
page.on('response', response => {
  responses.push({
    url: response.url(),
    status: response.status(),
    contentType: response.headers()['content-type']
  });
});

// Wait for specific request
const [request] = await Promise.all([
  page.waitForEvent('request', request => request.url().includes('/api/users')),
  page.click('button#load')
]);

// Get response body
const response = await page.waitForResponse(response => 
  response.url().includes('/api/users')
);
const body = await response.json();
console.log(body);
```

---

### 59. How to handle file downloads?

**File Download Handling:**

```javascript
// Listen for download event
const downloadPromise = page.waitForEvent('download');
await page.click('button#download');
const download = await downloadPromise;

// Get download path
console.log(await download.path());

// Get download filename
console.log(download.suggestedFilename());

// Save download to specific location
await download.saveAs('path/to/save/' + download.suggestedFilename());

// Delete download
await download.delete();

// Verify download
const path = require('path');
const fs = require('fs');
const filePath = path.join(__dirname, 'downloads', download.suggestedFilename());
await download.saveAs(filePath);
const fileExists = fs.existsSync(filePath);
console.log(fileExists);
```

---

### 60. How to evaluate JavaScript in page context?

**JavaScript Evaluation:**

```javascript
// Evaluate simple expression
const result = await page.evaluate(() => {
  return 1 + 1;
});
console.log(result); // 2

// Return element value
const value = await page.evaluate(() => {
  return document.querySelector('input#email').value;
});

// Pass arguments
const sum = await page.evaluate((a, b) => a + b, 3, 4);
console.log(sum); // 7

// Access window object
const title = await page.evaluate(() => document.title);
console.log(title);

// Complex evaluation
const data = await page.evaluate(() => {
  return {
    title: document.title,
    url: window.location.href,
    userAgent: navigator.userAgent
  };
});

// Evaluate on element
const text = await page.locator('button').evaluate(el => el.textContent);

// Execute without returning value
await page.evaluateHandle(() => {
  window.myFunction = () => console.log('Function called');
});
```

---

## NETWORK & ADVANCED FEATURES (81-100)

### 61. What is HAR recording?

**HAR (HTTP Archive) Recording:**

```typescript
// playwright.config.ts
export default defineConfig({
  recordHar: {
    omitContent: false, // Include response content
  },
});
```

**Usage in tests:**
```typescript
import { test, expect } from '@playwright/test';

test('record HAR', async ({ page }) => {
  // HAR recording starts automatically
  await page.goto('https://example.com');
  await page.click('button');
  
  // HAR file is automatically saved
});
```

**Replay recorded HAR:**
```typescript
test('replay from HAR', async ({ page }) => {
  await page.routeFromHAR('recording.har', {
    update: false // Set to true to update HAR
  });
  await page.goto('https://example.com');
});
```

---

### 62. How to use mocks and fixtures?

**Fixtures in Playwright Test:**

```typescript
import { test as base, expect } from '@playwright/test';

// Custom fixture
const test = base.extend({
  authenticatedPage: async ({ page }, use) => {
    // Setup: Login before test
    await page.goto('https://example.com/login');
    await page.fill('input#email', 'user@example.com');
    await page.fill('input#password', 'password');
    await page.click('button#login');
    
    // Use the authenticated page
    await use(page);
    
    // Cleanup: Logout after test
    await page.click('button#logout');
  },
});

// Use fixture in test
test('should access dashboard', async ({ authenticatedPage }) => {
  await authenticatedPage.goto('https://example.com/dashboard');
  await expect(authenticatedPage).toHaveURL(/dashboard/);
});
```

---

### 63. How to handle OAuth/SSO authentication?

**OAuth Authentication:**

```javascript
// Save authentication state
async function authenticate(page) {
  await page.goto('https://example.com/login');
  await page.click('button:has-text("Sign in with Google")');
  // Handle OAuth flow...
  await page.waitForURL('https://example.com/dashboard');
  return await page.context().cookies();
}

// Reuse authentication
const cookies = await authenticate(page);
await context.addCookies(cookies);
await page.goto('https://example.com');
```

**Using playwright.config.ts:**
```typescript
export default defineConfig({
  webServer: {
    command: 'npm run start',
    port: 3000,
  },
  use: {
    storageState: 'auth.json', // Persist auth state
  },
});
```

---

### 64. How to use accessibility testing?

**Accessibility Testing:**

```javascript
// Install: npm install -D @axe-core/playwright
const { injectAxe, checkA11y } = require('axe-playwright');

test('check accessibility', async ({ page }) => {
  await page.goto('https://example.com');
  
  // Inject axe
  await injectAxe(page);
  
  // Check accessibility
  await checkA11y(page);
});

// Check specific area
test('check form accessibility', async ({ page }) => {
  await page.goto('https://example.com/form');
  await injectAxe(page);
  await checkA11y(page, 'form');
});
```

---

### 65. How to use performance testing?

**Performance Metrics:**

```javascript
// Measure performance
test('measure page performance', async ({ page }) => {
  const metrics = {};
  
  page.on('metrics', data => {
    metrics[data.name] = data.value;
  });
  
  await page.goto('https://example.com');
  
  // Get metrics
  const navigationTiming = await page.evaluate(() => {
    const timing = performance.getEntriesByType('navigation')[0];
    return {
      navigationStart: timing.navigationStart,
      loadEventEnd: timing.loadEventEnd,
      domContentLoaded: timing.domContentLoadedEventEnd
    };
  });
  
  console.log('Navigation Timing:', navigationTiming);
});

// Measure First Contentful Paint (FCP)
const fcp = await page.evaluate(() => {
  const entry = performance.getEntriesByName('first-contentful-paint')[0];
  return entry.startTime;
});
```

---

### 66. How to generate coverage reports?

**Code Coverage Reporting:**

```typescript
// playwright.config.ts
export default defineConfig({
  reporter: [
    ['html', { open: 'always' }],
    ['json', { outputFile: 'test-results.json' }]
  ],
});
```

**Run with coverage:**
```bash
npx playwright test --reporter=json > results.json
```

---

### 67. How to debug tests?

**Debugging Methods:**

```javascript
// Method 1: Pause execution
await page.pause(); // Opens debugger

// Method 2: Set breakpoint
debugger; // (with Node --inspect)

// Method 3: Log useful info
console.log(await page.url());
console.log(await page.title());

// Method 4: Take screenshot on failure
await page.screenshot({ path: 'debug.png' });

// Method 5: Enable verbose logging
// Set PWDEBUG=1 environment variable
```

**Run with UI debugger:**
```bash
PWDEBUG=1 npx playwright test
```

---

### 68. How to handle slow networks?

**Network Throttling:**

```javascript
// Simulate slow network
const browser = await chromium.launch();
const context = await browser.newContext({
  offline: true // Simulate offline
});

// Use CDP session for throttling
const client = await page.context().newCDPSession(page);
await client.send('Network.enable');
await client.send('Network.emulateNetworkConditions', {
  offline: false,
  downloadThroughput: 1024 * 1024 / 8, // 1 Mbps
  uploadThroughput: 1024 * 1024 / 8,
  latency: 100 // 100ms latency
});
```

---

### 69. How to handle geolocation?

**Geolocation Permission:**

```javascript
const context = await browser.newContext({
  geolocation: { latitude: 37.7749, longitude: -122.4194 },
  permissions: ['geolocation']
});

const page = await context.newPage();
await page.goto('https://example.com/location');

// Grant permission
await context.grantPermissions(['geolocation']);

// Deny permission
await context.grantPermissions([], 'https://example.com');
```

---

### 70. How to handle notifications?

**Notification Permission:**

```javascript
const context = await browser.newContext({
  permissions: ['notifications']
});

// Grant notification permission
await context.grantPermissions(['notifications']);

// Listen for notifications
page.on('console', msg => {
  if (msg.type() === 'log') {
    console.log(msg.text());
  }
});

// Deny notifications
await context.grantPermissions([], 'https://example.com');
```

---

### 71. How to handle camera and microphone?

**Media Permissions:**

```javascript
const context = await browser.newContext({
  permissions: ['camera', 'microphone']
});

// Grant camera permission
await context.grantPermissions(['camera']);

// Grant microphone permission
await context.grantPermissions(['microphone']);

// Grant both
await context.grantPermissions(['camera', 'microphone']);
```

---

### 72. How to handle clipboard?

**Clipboard Operations:**

```javascript
// Copy to clipboard
await page.evaluate(() => {
  navigator.clipboard.writeText('copied text');
});

// Read from clipboard
const text = await page.evaluate(() => {
  return navigator.clipboard.readText();
});

// Paste from clipboard
await page.locator('input').paste('pasted text');

// Grant clipboard permission
const context = await browser.newContext({
  permissions: ['clipboard-read', 'clipboard-write']
});
```

---

### 73. How to handle local storage?

**Local Storage Management:**

```javascript
// Set local storage value
await page.evaluate(() => {
  localStorage.setItem('key', 'value');
});

// Get local storage value
const value = await page.evaluate(() => {
  return localStorage.getItem('key');
});

// Clear local storage
await page.evaluate(() => {
  localStorage.clear();
});

// Get all local storage
const storage = await page.evaluate(() => {
  return JSON.stringify(localStorage);
});

// Persist storage across contexts
const storage = await context.storageState();
```

---

### 74. How to handle session storage?

**Session Storage:**

```javascript
// Set session storage
await page.evaluate(() => {
  sessionStorage.setItem('sessionKey', 'sessionValue');
});

// Get session storage
const value = await page.evaluate(() => {
  return sessionStorage.getItem('sessionKey');
});

// Clear session storage
await page.evaluate(() => {
  sessionStorage.clear();
});

// Note: Session storage is cleared when context closes
```

---

### 75. How to handle cookies?

**Cookie Management:**

```javascript
// Add cookies
await context.addCookies([
  {
    name: 'authToken',
    value: 'token123',
    domain: 'example.com',
    path: '/',
    expires: Math.floor(Date.now() / 1000) + 3600 // 1 hour
  }
]);

// Get cookies
const cookies = await context.cookies();
console.log(cookies);

// Get specific cookie
const cookie = await page.evaluate(() => {
  return document.cookie;
});

// Clear cookies
await context.clearCookies();

// Clear specific cookie
await context.clearCookies({ name: 'authToken' });
```

---

### 76. How to handle mobile testing?

**Mobile Device Emulation:**

```javascript
import { devices } from '@playwright/test';

const context = await browser.newContext({
  ...devices['iPhone 12'],
  locale: 'en-US',
  timezone: 'America/New_York'
});

const page = await context.newPage();
await page.goto('https://example.com');

// Different devices
// devices['iPhone 11']
// devices['iPhone 12']
// devices['Pixel 5']
// devices['iPad']
// devices['iPad Pro']
```

---

### 77. How to handle visual regression testing?

**Visual Regression Testing:**

```typescript
import { test, expect } from '@playwright/test';

test('visual regression', async ({ page }) => {
  await page.goto('https://example.com');
  
  // Take screenshot and compare
  await expect(page).toHaveScreenshot('homepage.png');
});

// Update snapshots
// npx playwright test --update-snapshots
```

---

### 78. How to handle parallel test execution?**

**Parallel Execution Configuration:**

```typescript
// playwright.config.ts
export default defineConfig({
  fullyParallel: true, // Run all tests in parallel
  workers: 4, // Number of parallel workers
  
  projects: [
    {
      name: 'chromium',
      use: { ...devices['Desktop Chrome'] },
    },
    {
      name: 'firefox',
      use: { ...devices['Desktop Firefox'] },
    },
  ],
});
```

```bash
# Run tests in parallel
npx playwright test

# Run with specific number of workers
npx playwright test --workers=2
```

---

### 79. How to handle flaky tests?

**Flaky Test Solutions:**

```typescript
// Method 1: Use retries
export default defineConfig({
  retries: 2, // Retry failed tests
});

// Method 2: Increase timeout
test('slow test', async ({ page }) => {
  await page.goto('https://example.com', { timeout: 60000 });
});

// Method 3: Better waits
await page.waitForLoadState('networkidle');

// Method 4: Add delays (use sparingly)
await page.waitForTimeout(1000);

// Method 5: Use expects instead of asserts
await expect(element).toBeVisible({ timeout: 10000 });
```

---

### 80. How to create reusable test utilities?

**Reusable Utilities/Page Objects:**

```typescript
// pages/LoginPage.ts
export class LoginPage {
  constructor(private page: Page) {}
  
  async goto() {
    await this.page.goto('/login');
  }
  
  async login(email: string, password: string) {
    await this.page.fill('input[name="email"]', email);
    await this.page.fill('input[name="password"]', password);
    await this.page.click('button[type="submit"]');
  }
  
  async getErrorMessage() {
    return await this.page.textContent('.error-message');
  }
}

// tests/login.spec.ts
test('should login successfully', async ({ page }) => {
  const loginPage = new LoginPage(page);
  await loginPage.goto();
  await loginPage.login('user@example.com', 'password');
  await expect(page).toHaveURL('/dashboard');
});
```

---

## ADVANCED TOPICS

### 81-100: Quick Reference

**81. Continuous Integration with Playwright**
- GitHub Actions, GitLab CI, Jenkins
- Run tests on push/PR
- Generate reports and artifacts

**82. Docker & Containers**
- Use official Playwright Docker images
- Run tests in isolated containers

**83. Test Data Management**
- Use fixtures for setup/teardown
- Database seeding
- API-based test data

**84. Reporting & Monitoring**
- HTML reports
- JSON reports
- Integration with test management tools

**85. Best Practices**
- Use Page Object Model
- Avoid hardcoded waits
- Meaningful test names
- Clean up resources

**86. Common Pitfalls**
- Not using auto-wait
- Hardcoded timeouts
- Missing assertions
- Poor element locators

**87. Performance Optimization**
- Parallel test execution
- Sharding across machines
- Reduce context creation
- Minimize network calls

**88. Maintenance**
- Regular updates
- Monitor deprecated APIs
- Refactor tests
- Document patterns

**89. Troubleshooting**
- Check logs
- Use trace viewer
- Enable debugging
- Review error messages

**90. Integration Testing**
- Test with real backends
- Mock external services
- Test API contracts

**---**

This completes the comprehensive Playwright interview questions guide covering basics, locators, interactions, and advanced features with detailed examples for each question.

---

## Summary

This guide covers:
- ✅ 90+ Playwright concepts
- ✅ Practical code examples
- ✅ Best practices
- ✅ Common pitfalls
- ✅ Advanced techniques

Use this as a reference for:
- Interview preparation
- Learning Playwright
- Test automation best practices
- Quick lookup reference

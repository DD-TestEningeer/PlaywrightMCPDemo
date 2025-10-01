# AI-Driven Test Automation Demo Guide

Using Agent LLM, Playwright MCP, GitHub Copilot & GitHub Actions

This documentation provides a complete beginner-friendly walkthrough for setting up and running an **AI-driven test automation demo** using free or trial tools.

---

## 1. Prerequisites

- Computer with **Windows 10+** or **macOS**
- Stable internet connection
- Basic familiarity with command line

---

## 2. Account Signups

1. **GitHub**

   - Go to https://github.com/signup 
   - Sign up with free tier
   - Verify email and enable GitHub Free

2. **GitHub Copilot (Free Trial)**
 **Note** => GitHub Copilot Free is available to individual developers who don't have access to Copilot through an organization or enterprise. This free plan includes **limited** access to select Copilot features, allowing you to try AI-powered coding assistance at no cost.
 
   - Go to https://github.com/settings/copilot/features 
   - Start free trial (30 days)
   - Open the url - https://github.com/copilot
   - You will need to link to VS Code
   - Open the url - https://marketplace.visualstudio.com/items?itemName=GitHub.copilot
   
<img width="1920" height="956" alt="image" src="https://github.com/user-attachments/assets/35fda416-9907-4094-8b87-94fe195774cb" />
<img width="1880" height="949" alt="image" src="https://github.com/user-attachments/assets/1996e761-55ae-4346-8b21-b7c3471ea892" />
<img width="1876" height="968" alt="image" src="https://github.com/user-attachments/assets/23a427e2-5fb8-4d23-ae75-10166ea157bf" />
<img width="1920" height="981" alt="image" src="https://github.com/user-attachments/assets/e6585ff2-a1d8-4c99-9a6d-fb92dd204d1e" />
<img width="1912" height="1024" alt="image" src="https://github.com/user-attachments/assets/09a92a60-a983-42e9-8254-3e8b7be137b9" />



---

## 3. Tool Installations

### Install Node.js

- Download LTS version from [https://nodejs.org](https://nodejs.org)
- Install with defaults
- Verify installation:

  ```bash
  node -v
  npm -v
  ```
  <img width="945" height="348" alt="image" src="https://github.com/user-attachments/assets/9870f6b5-c1a4-4ddc-b835-537f590d4295" />


### Install Git

- Download from [https://git-scm.com/downloads](https://git-scm.com/downloads)
- Install with defaults
- Verify:

  ```bash
  git --version
  ```
<img width="580" height="139" alt="image" src="https://github.com/user-attachments/assets/2c1731f6-5a92-41ad-b4f2-96ccfc54186c" />

  

### Install VS Code

- Download from [https://code.visualstudio.com](https://code.visualstudio.com)
- Install with defaults
- Install extensions:

  - GitHub Copilot
  - JavaScript/TypeScript support

  <img width="1256" height="633" alt="image" src="https://github.com/user-attachments/assets/1b99aae5-83bf-4704-9d1f-a04826cecaf2" />
  <img width="1920" height="992" alt="image" src="https://github.com/user-attachments/assets/9efd5f34-4f5b-484b-8595-3cca9da16831" />



---

## 4. Project Setup

Open terminal and run:

```bash
mkdir ai-playwright-mcp
cd ai-playwright-mcp
npm init -y
```
<img width="910" height="837" alt="image" src="https://github.com/user-attachments/assets/a6c6f1ca-e1da-4414-908b-5265eae65ca3" />


Install Playwright:

```bash
npm init playwright@latest
npx playwright install
```
<img width="1212" height="982" alt="image" src="https://github.com/user-attachments/assets/bc724947-01cc-47cc-9b57-de0b0ac02285" />
<img width="1264" height="962" alt="image" src="https://github.com/user-attachments/assets/edc6bb22-cff3-4c55-911d-dc8fd8b66243" />


Check Playwright version:

```bash
npx playwright --version
```
<img width="984" height="259" alt="image" src="https://github.com/user-attachments/assets/d4d98e2f-983c-4b9b-95fb-fc51afc11405" />

---

## 5. Configure Project Structure

```plaintext
ai-playwright-mcp/
├── package.json
├── playwright.config.js
├── tests/
│   └── example.spec.js
├── pages/
│   └── home.page.js
└── utils/
    └── helpers.js
```
<img width="1886" height="822" alt="image" src="https://github.com/user-attachments/assets/2b3aa5cf-2f08-42e4-8d31-d998475baff4" />

---

## 6. Writing First Test

Create `tests/example.spec.js`

```js
const { test, expect } = require("@playwright/test");

test("example: page title", async ({ page }) => {
  await page.goto("https://example.com");
  await expect(page).toHaveTitle(/Example Domain/);
});
```

Run test:

```bash
npx playwright test
```

<img width="1566" height="804" alt="image" src="https://github.com/user-attachments/assets/20a9d9b0-62b7-4ffc-a209-5ea4b390297a" />


Open report:

```bash
npx playwright show-report
```
<img width="1659" height="836" alt="image" src="https://github.com/user-attachments/assets/69620ea8-6b37-4cde-8ee2-ecb1d5789d87" />

<img width="1730" height="869" alt="image" src="https://github.com/user-attachments/assets/9b071706-bf3c-4d3b-bd74-9b6f578b812f" />
<img width="1888" height="960" alt="image" src="https://github.com/user-attachments/assets/3d9b63fe-8dbc-4cf7-a13a-b9e8970bcd72" />

---

## 7. Page Object Example

Create `pages/home.page.js`

```js
class HomePage {
  constructor(page) {
    this.page = page;
    this.heading = page.locator("h1");
  }
  async goto() {
    await this.page.goto("https://example.com");
  }
  async getHeadingText() {
    return await this.heading.textContent();
  }
}
module.exports = HomePage;
```

---

## 8. Using GitHub Copilot

1. Open VS Code
2. Install **GitHub Copilot extension**
3. Sign in with GitHub account
4. Type a comment in test file:

```js
// Test login functionality with valid credentials
```

Copilot will suggest test code → accept or refine

---

## 9. Agent LLM Setup

1. Install Agent LLM (open-source option):

   - Clone: `git clone https://github.com/Josh-XT/Agent-LLM.git`
   - Follow instructions to set up with local LLM (GPT4All / llama.cpp)

2. Run MCP server for Playwright:

```bash
npx @playwright/mcp@latest --isolated
```

3. Connect Agent LLM to Playwright MCP for autonomous test generation

---

## 10. Reporting Setup

Update `playwright.config.js`

```js
const { defineConfig } = require("@playwright/test");

module.exports = defineConfig({
  testDir: "tests",
  timeout: 30000,
  retries: 1,
  use: {
    headless: true,
    screenshot: "only-on-failure",
    video: "retain-on-failure",
    trace: "retain-on-failure",
  },
  reporter: [["html", { open: "never" }]],
});
```

Run tests and open reports:

```bash
npx playwright test
npx playwright show-report
```

---

## 11. GitHub Repository Setup

Initialize git:

```bash
git init
git add .
git commit -m "Initial commit"
```

Connect to GitHub:

```bash
git remote add origin https://github.com/<your-username>/ai-playwright-mcp.git
git push -u origin main
```

---

## 12. GitHub Actions CI Setup

Create file `.github/workflows/playwright.yml`

```yaml
name: Playwright Tests
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Setup Node
        uses: actions/setup-node@v4
        with:
          node-version: "18"
      - run: npm ci
      - run: npx playwright install --with-deps
      - run: npm test
      - name: Upload Playwright report
        uses: actions/upload-artifact@v4
        with:
          name: playwright-report
          path: playwright-report
```

Push code and see test results in GitHub Actions tab

---

## 13. Live Demo Flow

1. Open VS Code
2. Write test case with Copilot suggestion
3. Run test locally with Playwright MCP
4. View HTML report with screenshots and trace
5. Commit and push to GitHub
6. Verify CI run in GitHub Actions
7. Download report artifact from Actions

---

## 14. Best Practices

- Always review Copilot suggestions before using
- Use stable test data to avoid flaky tests
- Limit free-tier usage (Copilot trial, GitHub Actions minutes)
- Keep tests organized in pages/ and utils/
- Use Agent LLM for autonomous exploration only in safe test environments

---

## 15. Next Steps

- Extend tests for login, forms, API validations
- Experiment with parallel test execution in GitHub Actions
- Try integrating API + UI tests together
- Explore alternative free LLMs with Agent LLM

---

## You are Ready

You now have a fully working **AI-driven test automation demo project** with:

- Local Playwright tests
- GitHub Copilot code generation
- Agent LLM autonomous exploration
- GitHub Actions CI/CD pipeline
- HTML reports with screenshots and traces

Practice regularly to gain confidence and scale your QA automation.

---

## Thank you!

## @Dnyaneshwar Divekar

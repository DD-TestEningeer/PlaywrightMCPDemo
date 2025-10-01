# Playwright Automation & MCP Prompts

---

## 1. Playwright Test Case Documentation Prompt

```
Generate Playwright automation test documentation in tabular format with the following columns:

Test ID: [ATC-001]  
Test Case Name: [Automated test case title]  
Preconditions: [Installed Node.js, Playwright MCP setup, Config ready]  
Test Data: [Inputs required for execution]  
Test Script: [Provide JavaScript test code using Playwright]  
Execution Steps: [How to run the test via CLI]  
Expected Result: [Outcome of the automation script]  
Actual Result: [Observed output after run]  
Status: [Pass/Fail]  

Feature under test: [INSERT FEATURE NAME HERE]
```

---

## 2. Playwright Test Script Generation Prompt

```
Generate a Playwright JavaScript test script for the feature: [INSERT FEATURE NAME HERE]

Test should include:
- Navigation to [INSERT URL]  
- Interaction with [INSERT ELEMENTS like buttons, inputs, dropdowns]  
- Assertion for [INSERT EXPECTED RESULT]  
- Screenshot capture on failure  
- HTML report configuration enabled  

Output code in JavaScript for Playwright.
```

---

## 3. Page Object Model (POM) Prompt

```
Generate a Page Object Model (POM) file in Playwright JavaScript for the feature: [INSERT FEATURE NAME HERE]

Include:
- Constructor with page object  
- Selectors for required elements  
- Functions for reusable actions like login(), search(), clickButton()  
- Export the class for use in tests
```

---

## 4. MCP Agent Test Creation Prompt

```
You are connected to Playwright MCP.  
Generate a test using MCP for the feature: [INSERT FEATURE NAME HERE].

Steps:
- Open browser context  
- Navigate to [INSERT URL]  
- Perform actions: [INSERT ACTIONS like filling form, clicking button]  
- Validate expected behavior: [INSERT EXPECTATION]  

Provide the JavaScript test code that MCP can execute.
```

---

## 5. Execution Prompt (Local CLI)

```
Execute the Playwright test suite locally.

Commands:
- Run all tests: npx playwright test  
- Run specific test: npx playwright test [TEST FILE NAME]  
- Run in headed mode: npx playwright test --headed  
- Debug mode: npx playwright test --debug  
- Open HTML report: npx playwright show-report
```

---

## 6. Execution Prompt (MCP)

```
Run Playwright tests via MCP Agent.

Steps:
1. Start MCP server: npx @playwright/mcp@latest --isolated  
2. Connect Agent LLM to Playwright MCP  
3. Provide instructions:  
   "Generate and execute test for [INSERT FEATURE NAME HERE] on [INSERT URL]"  
4. Agent LLM will output test code and trigger execution  
5. Collect HTML report and artifacts from /playwright-report
```

---

With these prompts, you can:

* Generate Playwright test documentation
* Create JavaScript test scripts
* Build Page Object Models
* Use MCP with Agent LLM to generate and execute tests
* Run tests both locally and via MCP

---
Author - Dnyaneshwar Divekar
--
Thank you!


---

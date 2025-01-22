# Task 2 - Test Automation: UI Tests for Sprite Cloud Assignment

This project is a test automation solution for the Sprite Cloud assignment, focused on UI tests using [Playwright](https://playwright.dev).

---

## Requirements

### Test Cases
- Write **3 API web tests**.

### Rules
- Tests are executed on: [Regres.in](https://reqres.in).

### Deliverables
- A clear `README.md` file for the automation solution.

### Technology Stack
- **Tool**: [Your choice] OR [Playwright] Restriction: No “Record and Play” tools  
- **Language**: (pick one) [C#] [Typescript] [ Javascript] [Java] [Python]
---

## Solution Overview

- **Tool**: Postman  
- **Language**: Javascript 

This solution provides a framework for UI test automation, including:
- Automated **positive and negative tests** for the login page.
- A **Page Object Model (POM) structure** created specifically for the login page.
- Test coverage implemented using Playwright.

## What is API testing



## What is Postman?

Postman is a popular tool for API testing that allows developers to create and execute HTTP requests and test API responses. Postman makes API testing more efficient and effective with features such as request builders, response visualizations, and test automation.

## How to install Postman

Please find the instraction [here](https://learning.postman.com/docs/getting-started/installation/installation-and-updates/)

**Note:** 

Usually API testing includes next points:


But as there was not requirements about the response time, this verification was not included to the assertions but it is possible to use next code to test it: 
- limit value has to be provided.

pm.test("Response time is less than limit", function() {
var limit = 10;

if (pm.response.responseTime < limit) {      
    pm.expect(pm.response.responseTime).to.be.below(limit);  
    console.log("Response Time: " + pm.response.responseTime + " ms" + " / Response Date: " + pm.response.headers.get("Date"));
} else {
    console.log("Response time was longer than " + limit + " ms.");
}
});
---


## Installation and Setup

### 1. Installing Postman
Run the following command to initialize Playwright:  

```bash
npm init playwright@latest
```

---

## Running the Tests

### Run All Tests
To execute all tests, use:  

```bash
npx playwright test
```

---

## Test Reporting

### Test Reports

1. GitHub Actions report:
- ctrf report is attached as the **test summary** 

### GitHub Actions Workflow
- Test execution results can also be found in the GitHub Actions workflow page:  
  [GitHub Workflow Page](https://github.com/Injeevskaya/SpriteCloudUI/actions/workflows/playwright.yml)

---




Test Cases:
● You’ll write 3 UI web tests.
● You’ll write 3 API web tests.
Rules:
● UI tests via https://www.saucedemo.com.
● API tests via https://reqres.in.
● Provide a clear README for your automation solution.
Tech:
Note:
● Tool: [Your choice] OR [Playwright] Restriction: No “Record and Play” tools
● Language (pick one): [C#] [Typescript] [ Javascript] [Java] [Python]
To test https://reqres.in/ API Postman application was choosen



Usually API testing includes next points:


But as there was not requirements about the response time, this verification was not included to the assertions but it is possible to use next code to test it: 
- limit value has to be provided.

pm.test("Response time is less than limit", function() {
var limit = 10;

if (pm.response.responseTime < limit) {      
    pm.expect(pm.response.responseTime).to.be.below(limit);  
    console.log("Response Time: " + pm.response.responseTime + " ms" + " / Response Date: " + pm.response.headers.get("Date"));
} else {
    console.log("Response time was longer than " + limit + " ms.");
}
});
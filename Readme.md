# Task 2 - Test Automation: API Tests for Sprite Cloud Assignment

This project is a test automation solution for the Sprite Cloud assignment, focused on API tests using [Postman](https://learning.postman.com/docs/introduction/overview/).

---

## Solution Overview

- **Tool**: Postman  
- **Language**: Javascript 

---

## What is API testing

API testing is a type of software testing that involves testing APIs directly and also as a part of integration testing to check whether the API meets expectations in terms of functionality, reliability, performance, and security of an application. In API Testing our main focus will be on a Business logic layer of the software architecture. API testing can be performed on any software system which contains multiple APIs. API testing won’t concentrate on the look and feel of the application. API testing is entirely different from GUI Testing.

## What is Postman?

Postman is a popular tool for API testing that allows developers to create and execute HTTP requests and test API responses. Postman makes API testing more efficient and effective with features such as request builders, response visualizations, and test automation.

## How to install Postman

Please find the instraction [here](https://learning.postman.com/docs/getting-started/installation/installation-and-updates/)

---

## Test Cases were written for the next Endpoints:

1. List users
2. Single user not found 
3. Create
4. Register - successful
5. Register - unsuccessful

## What was validated:

1. ***Response Code**
    It's provided by this verification

```
    pm.test("Status code is 400", function () {
    pm.response.to.have.status(400);
});
```

2. ***Response Time**

**Note:** 

But as there was not information provided about the response time 
(In case of working I'd ask my BE teammates), this verification was not included to the assertions but it is possible to use next code to test it: 

- limit value has to be provided.

```
pm.test("Response time is less than limit", function() {
var limit = 10;

if (pm.response.responseTime < limit) {      
    pm.expect(pm.response.responseTime).to.be.below(limit);  
    console.log("Response Time: " + pm.response.responseTime + " ms" + " / Response Date: " + pm.response.headers.get("Date"));
} else {
    console.log("Response time was longer than " + limit + " ms.");
}
});
```

3. ***Response Format**
   
```
pm.test("Response has expected structure", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData).to.have.property('name');
    pm.expect(jsonData).to.have.property('job');
    pm.expect(jsonData).to.have.property('id');
    pm.expect(jsonData).to.have.property('createdAt');
});
```

4. ***Error Handling**

```
pm.test("Response contains expected error message", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData).to.have.property('error');
    pm.expect(jsonData.error).to.eql('Missing password');
});
```
---

## Running the Tests

### Run All Tests

To execute tests use run collection action:
```
To use the Collection Runner, click on the "Runner" button in the top right corner 
of the Postman window. 

Select the collection you want to run, and click the "Start Run" button.
```

 (see more info here)[https://apidog.com/blog/how-to-use-postman-for-api-testing/] 

---

## Test Reporting

### Test Reports

1. GitHub Actions report:
- ctrf report is attached as the **test summary** 

### GitHub Actions Workflow
- Test execution results can also be found in the GitHub Actions workflow page:  
  [GitHub Workflow Page](https://github.com/Injeevskaya/SpriteCloudAPI/actions)

---
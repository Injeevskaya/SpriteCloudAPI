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
# API Testing with Newman

This repository contains a set of REST API tests using Newman, a command-line tool for running Postman collections. The tests will be run against a sample API that serves data about users.

## Prerequisites

Before running these tests, you'll need to install Newman and have access to the sample API. If you haven't already done so, follow these steps:

1. Install Newman by running the following command: `npm install -g newman`.

## Running the Tests

To run these tests using Newman, follow these steps:

1. Download the collection.json and the env.json files from the repo.
2. Open a command prompt or terminal window and navigate to the directory where the collection file was downloaded.
3. Run the following command: `newman run collection.json -e environment.json`, where `environment.json` is a file containing environment variables used in the tests.
4. After the tests complete, Newman will display the results in the terminal window.

## Test Cases

The following test cases will be executed using Newman:

### Test Case 1: GET Users

This test case verifies that the GET Users endpoint returns a list of all users.

**Request**

- Method: GET
- URL: `https://gorest.co.in/users`

**Expected Response**

- Status code: 200
- Response body: A JSON array containing user objects.

### Test Case 2: POST User

This test case verifies that a new user can be added using the POST User endpoint.

**Request**

- Method: POST
- URL: `https://gorest.co.in/users`
- Headers:
    ```
    Content-Type: application/json
    ```
- Request body: A JSON object containing user data.

**Expected Response**

- Status code: 201
- Response body: The JSON object of the newly created user.

### Test Case 3: GET User

This test case verifies that a specific user can be retrieved using the GET User endpoint.

**Request**

- Method: GET
- URL: `https://gorest.co.in/users/{userId}`, where `{userId}` is the ID of an existing user.

**Expected Response**

- Status code: 200
- Response body: The JSON object of the specified user.

### Test Case 4: PUT User

This test case verifies that a specific user can be updated using the PUT User endpoint.

**Request**

- Method: PUT
- URL: `https://gorest.co.in/users/{userId}`, where `{userId}` is the ID of an existing user.
- Headers:
    ```
    Content-Type: application/json
    ```
- Request body: A JSON object containing updated user data.

**Expected Response**

- Status code: 200
- Response body: The JSON object of the updated user.

### Test Case 5: DELETE User

This test case verifies that a specific user can be deleted using the DELETE User endpoint.

**Request**

- Method: DELETE
- URL: `https://gorest.co.in/users/{userId}`, where `{userId}` is the ID of an existing user.

**Expected Response**

- Status code: 204
- Response body: None.

## Testing approach:

This is a Postman collection JSON file which describes a test suite for an API. The tests are written using Postman's testing capabilities and are executed using Postman's testing framework.

The approach taken here is a combination of functional testing and integration testing, where each API endpoint is tested to ensure it is functioning correctly. The tests are automated and run through the Postman application. The tests aim to ensure that the API meets its functional requirements, such as returning the expected data, status codes, and that the data is consistent.

The test suite contains tests for the GET, POST, PATCH and DELETE endpoints of the API. The tests ensure that the API returns the correct data and status codes, and that the data is consistent. The tests use environment variables to ensure that data is passed between tests and to ensure the tests are repeatable. The tests also check that the data is in the correct format, and that it is returned in the expected time frame. The approach taken is therefore a comprehensive testing approach that covers the API's functionality and integration with the system.

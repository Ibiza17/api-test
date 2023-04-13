# API Testing with Newman

This repository contains a set of REST API tests using Newman, a command-line tool for running Postman collections. The tests will be run against a sample API that serves data about users.

## Prerequisites

Before running these tests, you'll need to install Newman and have access to the sample API. If you haven't already done so, follow these steps:

1. Install Newman by running the following command: `npm install -g newman`.
2. Download the sample API from the following link: https://github.com/sample-api.
3. Start the API by navigating to the directory where it was downloaded and running the following command: `npm start`.

## Test Cases

The following test cases will be executed using Newman:

### Test Case 1: GET Users

This test case verifies that the GET Users endpoint returns a list of all users.

**Request**

- Method: GET
- URL: `http://localhost:3000/users`

**Expected Response**

- Status code: 200
- Response body: A JSON array containing user objects.

### Test Case 2: POST User

This test case verifies that a new user can be added using the POST User endpoint.

**Request**

- Method: POST
- URL: `http://localhost:3000/users`
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
- URL: `http://localhost:3000/users/{userId}`, where `{userId}` is the ID of an existing user.

**Expected Response**

- Status code: 200
- Response body: The JSON object of the specified user.

### Test Case 4: PUT User

This test case verifies that a specific user can be updated using the PUT User endpoint.

**Request**

- Method: PUT
- URL: `http://localhost:3000/users/{userId}`, where `{userId}` is the ID of an existing user.
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
- URL: `http://localhost:3000/users/{userId}`, where `{userId}` is the ID of an existing user.

**Expected Response**

- Status code: 204
- Response body: None.

## Running the Tests

To run these tests using Newman, follow these steps:

1. Download the collection file from the following link: https://github.com/sample-api/collection.json.
2. Open a command prompt or terminal window and navigate to the directory where the collection file was downloaded.
3. Run the following command: `newman run collection.json -e environment.json`, where `environment.json` is a file containing environment variables used in the tests.
4. After the tests complete, Newman will display the results in the terminal window. You can also generate a more detailed HTML report by adding the `--reporter-html` flag to the command and specifying an output file path.

## Conclusion

These test cases cover the most common scenarios for interacting with the sample API. By running
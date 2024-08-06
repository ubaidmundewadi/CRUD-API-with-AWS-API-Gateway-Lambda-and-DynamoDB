# CRUD API with AWS API Gateway, Lambda, and DynamoDB

This project demonstrates how to create a REST API using AWS API Gateway, AWS Lambda, and DynamoDB. The API performs CRUD (Create, Read, Update, Delete) operations on a DynamoDB database. The architecture diagram below provides an overview of the setup.

![Screenshot 2024-08-04 232518](https://github.com/user-attachments/assets/e22022a7-ba93-4a39-b730-d4ab656735c0)

## Table of Contents

- [Architecture](#architecture)
- [Prerequisites](#prerequisites)
- [API Endpoints](#api-endpoints)
- [Lambda Function](#lambda-function)
- [Testing](#testing)

## Architecture

The architecture consists of the following components:

1. **Client**: Sends REST API requests.
2. **API Gateway**: Routes requests to the appropriate Lambda function.
3. **AWS Lambda**: Executes the backend logic for CRUD operations.
4. **DynamoDB**: Stores the data and handles CRUD operations.

## Prerequisites

Before you begin, ensure you have the following:

- An AWS account


## API Endpoints

The following endpoints are available for CRUD operations:

- **Create Item**

    ```http
    POST /employee
    ```

    Request body:

    ```json
    {
        "employeeid": "unique-id",
        "data": "your-data"
    }
    ```

- **Read Item**

    ```http
    GET /employee?employeeid={id}
    ```

    Query parameter:

    - `employeeid`: The unique identifier of the item to read.

- **Read All Items**

    ```http
    GET /employees
    ```

- **Update Item**

    ```http
    PATCH /employee
    ```

    Request body:

    ```json
    {
        "employeeId": "unique-id",
        "updateKey": "key-to-update",
        "updateValue": "new-value"
    }
    ```

- **Delete Item**

    ```http
    DELETE /employee
    ```

    Request body:

    ```json
    {
        "employeeId": "unique-id"
    }
    ```

## Lambda Function

The core logic for handling CRUD operations is implemented in an AWS Lambda function. The function is written in Python and uses the `boto3` library to interact with DynamoDB



## Testing

You can use tools like Postman

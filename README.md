# Math API Documentation

## Overview

The **Math API** is a RESTful web service designed to evaluate simple mathematical expressions provided as GET parameters. This API accepts only `GET` requests, performs basic validation on input expressions, and returns the evaluated result in JSON format.

## API Endpoint

**URL**: `https://pavlovhelp.lol/MATH_API`  
**Method**: `GET`

## Query Parameters

- **problem**: A string representing the mathematical expression to be evaluated.
  - **Allowed Operators**: `+`, `-`, `*`, `/`
  - **Example**: `2+2`, `10/5`, `5*3-2`

## Response Format

The API responds with a JSON object. Responses can be:
1. **Success Response**: Returns the `problem` string and its `solution`.
2. **Error Response**: Returns an `error` message if the request fails.

### Example Request

```http
GET https://pavlovhelp.lol/MATH_API?problem=2+2
```

# Example Success Response

```json
json

{
  "problem": "2+2",
  "solution": 4
}
```

# Example Error Responses

```json

    Invalid Input: If problem contains disallowed characters.

    json

{
  "error": "Invalid math problem. Only numbers and operators (+, -, *, /) are allowed."
}

Parameter Missing: If the problem parameter is not provided.

json

{
  "error": "Please provide a math problem in the 'problem' query parameter."
}

Method Not Allowed: If a non-GET method is used.

json

{
  "error": "Only GET requests are allowed."
}
```

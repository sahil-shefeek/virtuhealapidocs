# Authentication and User Management

## Table of Contents

- [Introduction](#introduction)

- **[Authentication](#authentication)**
    - [Token Obtain](##token-obtain)
    - [Token Refresh](##token-refresh)
    - [Token Verify](##token-verify)

<b><a href="User-Management.md">User Management</a></b>

## Introduction

<p id="intro">This documentation provides details about the available endpoints in our Virtuheal API, including authentication and user management.</p>

## Authentication
<p>
Our API uses <a href="JWTs.md">JSON Web Tokens (JWT)</a> for authentication. Clients must include the JWT in the Authorization header for all
requests that require authentication.
</p>

Example Authorization header:

```
Authorization: Bearer <your_jwt_token>
```

> All endpoints are protected by authentication
> {style=note}

## Data types

<api-schema openapi-path="./authentication.yaml" name="InterfaceUser"/>


## Endpoints
### Base Url : hostname/api/auth
> It is recommended that the Base Url is provided as a global constant, as it may change periodically. This can cause unwanted code refactorings if hardcoded. 

<api-doc openapi-path="./authentication.yaml">
<api-endpoint endpoint="/token/" method="POST">
<description>Obtain a JWT token.</description>
<request>
<sample lang="json" title="Request Body">
{
  "username": "user@example.com",
  "password": "password123"
}
</sample>
</request>
<response type="200">
<sample lang="json" title="Response">
{
  "access": "your_access_token",
  "refresh": "your_refresh_token"
}
</sample>
</response>
</api-endpoint>
<api-endpoint endpoint="/token/refresh/" method="POST">
<description>Refresh an expired JWT token.</description>
<request>
<sample lang="json" title="Request Body">
{
  "refresh": "your_refresh_token"
}
</sample>
</request>
<response type="200">
<sample lang="json" title="Response">
{
  "access": "your_new_access_token"
}
</sample>
</response>
</api-endpoint>
<api-endpoint endpoint="/token/verify/" method="POST">
<description>Verify the validity of a JWT token.</description>
<request>
<sample lang="json" title="Request Body">
{
  "token": "your_jwt_token"
}
</sample>
</request>
<response type="200">
<sample lang="json" title="Response">
{
  "detail": "Token is valid."
}
</sample>
</response>
</api-endpoint>
</api-doc>

## Usage

<tabs>
<tab title="Javascript">
<code-block lang="javascript">
const loginUser = async (username, password) => {
      const response = await fetch('http://yourapi.com/api/token/', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({ username, password }),
      });

const data = await response.json();
    if (response.ok) {
    console.log('JWT Token:', data.access);
    } else {
    console.error('Login failed:', data);
    }
    };
loginUser('user@example.com', 'password123');

</code-block>
</tab>
<tab title="Flutter">
<code-block lang="generic">
import 'dart:convert';
import 'package:http/http.dart' as http;

Future<void> loginUser(String username, String password) async {
  final url = Uri.parse('http://yourapi.com/api/token/');
  final response = await http.post(
    url,
    headers: {'Content-Type': 'application/json'},
    body: json.encode({'username': username, 'password': password}),
  );

  if (response.statusCode == 200) {
    final data = json.decode(response.body);
    print('JWT Token: ${data['access']}');
  } else {
    print('Login failed: ${response.body}');
  }
}

loginUser('user@example.com', 'password123');
</code-block>
</tab>
</tabs>




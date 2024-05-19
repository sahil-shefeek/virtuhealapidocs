# JSON Web Tokens (JWTs) in Flutter and React

### What is a JWT?

A JSON Web Token (JWT) is an open standard (RFC 7519) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object. This information can be verified and trusted because it is digitally signed. JWTs can be signed using a secret (with the HMAC algorithm) or a public/private key pair using RSA or ECDSA.

### Structure of a JWT

A JWT is composed of three parts:
1. **Header**
2. **Payload**
3. **Signature**

These parts are separated by dots (`.`) and encoded using Base64.

Example JWT: `xxxxx.yyyyy.zzzzz`

- **Header**: Typically consists of two parts: the type of token (JWT) and the signing algorithm being used, such as HMAC SHA256 or RSA.
- **Payload**: Contains the claims. Claims are statements about an entity (typically, the user) and additional data.
- **Signature**: To create the signature part, the encoded header, encoded payload, a secret, the algorithm specified in the header are combined and signed.

## Handling JWTs in Flutter

### Storing JWTs

In Flutter, you can use the `shared_preferences` package to store JWTs locally.

1. Add the dependency to your `pubspec.yaml`:
    ```yaml
    dependencies:
      shared_preferences: ^2.0.6
    ```

2. Save the JWT:
    ```dart
    import 'package:shared_preferences/shared_preferences.dart';

    Future<void> saveToken(String token) async {
      final prefs = await SharedPreferences.getInstance();
      prefs.setString('jwt', token);
    }
    ```

3. Retrieve the JWT:
    ```dart
    Future<String?> getToken() async {
      final prefs = await SharedPreferences.getInstance();
      return prefs.getString('jwt');
    }
    ```

### Using JWT in HTTP Requests

You can use the `http` package to send HTTP requests with the JWT.

1. Add the dependency to your `pubspec.yaml`:
    ```yaml
    dependencies:
      http: ^0.13.3
    ```

2. Send requests with JWT:
    ```dart
    import 'package:http/http.dart' as http;

    Future<http.Response> fetchProtectedData(String token) async {
      final response = await http.get(
        Uri.parse('https://example.com/protected'),
        headers: {
          'Authorization': 'Bearer $token',
        },
      );
      return response;
    }
    ```

## Handling JWTs in React

### Storing JWTs

In React, you can use the `localStorage` or `sessionStorage` to store JWTs.

1. Save the JWT:
    ```javascript
    localStorage.setItem('jwt', token);
    ```

2. Retrieve the JWT:
    ```javascript
    const token = localStorage.getItem('jwt');
    ```

### Using JWT in HTTP Requests

You can use the `axios` library to send HTTP requests with the JWT.

1. Install the `axios` library:
    ```bash
    npm install axios
    ```

2. Send requests with JWT:
    ```javascript
    import axios from 'axios';

    const fetchProtectedData = async (token) => {
      const response = await axios.get('https://example.com/protected', {
        headers: {
          'Authorization': `Bearer ${token}`,
        },
      });
      return response.data;
    };
    ```

### Handling JWT Expiration

To handle JWT expiration, you can decode the JWT and check the expiration time before making requests.

1. Install the `jwt-decode` library:
    ```bash
    npm install jwt-decode
    ```

2. Decode and check the token:
    ```javascript
    import jwtDecode from 'jwt-decode';

    const isTokenExpired = (token) => {
      const decoded = jwtDecode(token);
      const now = Date.now() / 1000; // Current time in seconds
      return decoded.exp < now;
    };

    const token = localStorage.getItem('jwt');
    if (token && !isTokenExpired(token)) {
      // Token is valid, proceed with the request
    } else {
      // Token is expired or not available, redirect to login
    }
    ```

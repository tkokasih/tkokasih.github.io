## What is JWT?

JWT looks something like this: 

```
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
```

Which is three base64-url encoded parts, separated by dot:
* Header
    ```
    eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9
    ```
    which decoded to
    ```json
    {
        "alg": "HS256",
        "typ": "JWT"
    }
    ```
* Body
    ```
    eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ
    ```
    which decodes to
    ```
    {
        "sub": "1234567890",
        "name": "John Doe",
        "iat": 1516239022
    }
    ```
* Signature
    ```
    SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
    ```
    which is not decoded. It is the 
    ```
    HMACSHA256(
        base64UrlEncode(header) + "." +
        base64UrlEncode(payload),
        SecretKey
    )
    ```

## Futher Reading?
* [rfc-7519](https://www.rfc-editor.org/rfc/rfc7519.html)
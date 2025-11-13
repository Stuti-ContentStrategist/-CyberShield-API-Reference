# 🔐 Authentication

## 🧱 Overview

All CyberShield API endpoints require **Bearer Token–based authentication**. Before making any request, you must generate an **access token** using your **API Key** and **API Secret**. This ensures secure communication between your application and CyberShield’s backend systems.

> ⚠️ **Note:** Tokens are valid for one hour. Always refresh your token before it expires to maintain uninterrupted API access.

***

### 🧩 Generate Access Token

Use the following endpoint to request a new access token:

| Method   | Endpoint             |
| -------- | -------------------- |
| **POST** | `/api/v1/auth/token` |

**Request Example**

```bash
POST /api/v1/auth/token
Content-Type: application/json
```

**Body:**

```json
{
  "api_key": "your_api_key",
  "api_secret": "your_api_secret"
}
```

**Response Example**

```json
{
  "access_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6...",
  "token_type": "Bearer",
  "expires_in": 3600
}
```

> 💡 **Tip:** Store the `access_token` securely — avoid embedding it directly in code or exposing it in logs.

***

### 🔑 Use Access Token

Include the access token in the **Authorization header** of every request.

**Example**

```bash
GET /api/v1/scan/status/cs-2025-00123
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6...
```

> 🧠 **Info:** If the token has expired or is invalid, the API returns a `401 Unauthorized` error.\
> To fix this, request a new token using your API credentials.

***

### 🔄 Refreshing Tokens

Tokens automatically expire after 60 minutes.\
To prevent service interruptions:

* Request a new token before expiration, or
* Automate token renewal in your integration workflow.

> 💡 **Best Practice:** Implement retry logic that detects a `401 Unauthorized` response and automatically refreshes the token.

***

### 🧰 Common Authentication Errors

| HTTP Code | Error             | Description                              | Recommended Action                         |
| --------- | ----------------- | ---------------------------------------- | ------------------------------------------ |
| **400**   | Bad Request       | Missing or malformed API credentials.    | Verify request format and body parameters. |
| **401**   | Unauthorized      | Invalid or expired token.                | Re-authenticate and request a new token.   |
| **403**   | Forbidden         | Key does not have sufficient privileges. | Check API key permissions.                 |
| **429**   | Too Many Requests | Rate limit exceeded.                     | Wait and retry after a short delay.        |

✅ You’ve successfully learned how to authenticate and authorize your CyberShield API requests.

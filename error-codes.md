# ⚠️ Error Codes

## 🧱 Overview

The CyberShield API uses standard HTTP response codes and structured JSON error messages to indicate the success or failure of a request.

This section lists common response codes, their meanings, and recommended actions to help developers troubleshoot integration issues effectively.

💡 **Tip:** When debugging API calls, always log the **HTTP status code**, **error message**, and **timestamp** for better traceability.

***

### ⚙️ Standard HTTP Status Codes

| Code    | Type                     | Description                                                   | Recommended Action                                     |
| ------- | ------------------------ | ------------------------------------------------------------- | ------------------------------------------------------ |
| **200** | ✅ Success                | The request was successfully processed.                       | No action required.                                    |
| **201** | ✅ Created                | The resource was successfully created.                        | Continue to next workflow step.                        |
| **400** | ⚠️ Bad Request           | The request could not be processed due to invalid parameters. | Verify input syntax or JSON body.                      |
| **401** | 🚫 Unauthorized          | Authentication token is missing or invalid.                   | Re-authenticate and retry.                             |
| **403** | 🔒 Forbidden             | API key or token lacks required permissions.                  | Check access scope or user roles.                      |
| **404** | ❓ Not Found              | The requested resource does not exist.                        | Confirm the endpoint and parameters.                   |
| **409** | ⚠️ Conflict              | A conflicting operation is in progress.                       | Retry after resolving the conflict.                    |
| **429** | ⏳ Too Many Requests      | The API rate limit has been exceeded.                         | Implement exponential backoff or wait before retrying. |
| **500** | 💥 Internal Server Error | A server-side issue occurred.                                 | Retry after a short delay or contact support.          |
| **503** | ⚙️ Service Unavailable   | Temporary downtime or maintenance.                            | Retry later.                                           |

***

#### 🧩 Example Error Response

When a request fails, the API returns a structured JSON error message with relevant details.

**Example**

```json
{
  "status": 401,
  "error": "Unauthorized",
  "message": "Access token expired or invalid.",
  "timestamp": "2025-11-09T12:45:21Z"
}
```

> 🧠 **Info:** CyberShield error responses include timestamps to help correlate API issues with system logs.

***

#### 🧰 Debugging Tips

* ✅ Always validate your **API endpoint** and **method (GET, POST, etc.)** before sending requests.
* 🔐 Recheck your **Authorization** header if you receive a `401 Unauthorized` error.
* 🕒 For intermittent errors (`500`, `503`), retry after a short delay (5–10 seconds).
* 🧾 Store failed requests and error responses for post-deployment analysis.

> 🧠 Keep this table handy when debugging integration issues — it ensures quick, accurate error resolution.&#x20;

#### 🧭 **End of Guide!**

🎉 Great work — you’ve reached the end of the **CyberShield API Reference**!

You now understand how to:

* Authenticate securely using API keys
* Use core endpoints to start scans, retrieve results, and manage alerts
* Handle request/response formats and error codes
* Integrate CyberShield services into your applications programmatically

📚 For version-specific updates, visit the[ **CyberShield Release Notes**](https://app.gitbook.com/o/YBUOQjCTo1Lf6omt9Fkt/s/Z935hdhlRtsmGr5SnVj1/) section.

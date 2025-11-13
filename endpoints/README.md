# ⚙️ Endpoints

#### 🧱 Overview

This section describes CyberShield’s REST API endpoints for managing security scans, retrieving status updates, viewing alerts, and generating reports.

All endpoints use HTTPS and require **Bearer Token authentication**.\
Refer to API Reference → Authentication to obtain your access token before making requests.

> 💡 **Tip:** All requests must include the `Authorization: Bearer <access_token>` header.

***

###

Initiates a security scan on a specified target or subnet.

| Method   | Endpoint             |
| -------- | -------------------- |
| **POST** | `/api/v1/scan/start` |

#### Request Example

```bash
POST /api/v1/scan/start
Authorization: Bearer <access_token>
Content-Type: application/json
```

**Body:**

```json
{
  "scan_type": "network",
  "target": "192.168.1.0/24",
  "profile": "full"
}
```

#### Response Example

```json
{
  "scan_id": "CS-2025-00123",
  "status": "initiated",
  "message": "Network scan started successfully."
}
```

> ⚙️ **Note:** Add `"schedule": "daily"` to the request body to schedule recurring scans.

***

### 📊 2. Get Scan Status

Retrieves the progress or completion status of a specific scan.

| Method  | Endpoint                        |
| ------- | ------------------------------- |
| **GET** | `/api/v1/scan/status/{scan_id}` |

#### Request Example

```bash
GET /api/v1/scan/status/CS-2025-00123
Authorization: Bearer <access_token>
```

#### Response Example

```json
{
  "scan_id": "CS-2025-00123",
  "status": "in_progress",
  "progress": "80%",
  "started_at": "2025-11-09T14:30:00Z"
}
```

> 💡 **Tip:** Poll this endpoint periodically to track scan completion in real time.

***

### 🚨 3. List Alerts

Retrieves all recent security alerts, optionally filtered by severity or type.

| Method  | Endpoint              |
| ------- | --------------------- |
| **GET** | `/api/v1/alerts/list` |

#### Request Example

```bash
GET /api/v1/alerts/list?severity=high
Authorization: Bearer <access_token>
```

#### Response Example

```json
[
  {
    "alert_id": "ALR-9021",
    "type": "Unauthorized Access Attempt",
    "severity": "High",
    "timestamp": "2025-11-09T18:24:33Z"
  },
  {
    "alert_id": "ALR-9022",
    "type": "Malware Detection",
    "severity": "Critical",
    "timestamp": "2025-11-09T18:25:42Z"
  }
]
```

> 🧠 **Info:** Combine query parameters like `?severity=critical&type=malware` to refine your results.

***

### 📄 4. Retrieve Report

Downloads or retrieves a completed scan report in JSON or PDF format.

| Method  | Endpoint                   |
| ------- | -------------------------- |
| **GET** | `/api/v1/report/{scan_id}` |

#### Request Example

```bash
GET /api/v1/report/CS-2025-00123?format=pdf
Authorization: Bearer <access_token>
```

#### Response Example

```json
{
  "report_id": "REP-2025-00678",
  "scan_id": "CS-2025-00123",
  "file_url": "https://api.cybershield.io/reports/REP-2025-00678.pdf"
}
```

> ⚠️ **Note:** Reports are retained for 30 days after generation. Ensure you download and archive them before expiry.

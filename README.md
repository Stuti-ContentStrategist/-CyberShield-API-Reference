# 📒 CyberShield API Reference

## 🧱 Overview

The **CyberShield API Reference** provides complete technical details for developers integrating CyberShield’s security and monitoring capabilities into their own applications and systems.&#x20;

It explains authentication, endpoint usage, parameters, and response formats — enabling you to automate actions such as starting scans, retrieving results, and managing alerts programmatically.

💡 **Tip:** If you’re using the **CyberShield SDK**, start with the [Developer Reference](https://app.gitbook.com/s/Jh7uJN5ZgBV4FyWQnmId/developer-reference) → [Integration Setup ](https://app.gitbook.com/s/Jh7uJN5ZgBV4FyWQnmId/developer-reference/integration-setup)before accessing API endpoints.

***

### 🌐 Base URL

All API requests must use **HTTPS**.

```
https://api.cybershield.io/v1/
```

> ⚠️ **Note:** HTTP connections are not supported for security reasons. Always use HTTPS for all API interactions.

***

### 🔐 Authentication

CyberShield APIs use **Bearer Token authentication**.\
Before calling any endpoint, you must generate a valid token using your API Key and Secret.

📘 Learn more → [**CyberShield API Reference**](./) → [**Authentication**](authentication.md)

***

#### 🚀 Core Endpoints

| **Category**             | **Description**                                                             |
| ------------------------ | --------------------------------------------------------------------------- |
| 🧠 **Scan Management**   | Start and monitor security scans (`/scan/start`, `/scan/status/{scan_id}`)  |
| 🔔 **Alert Management**  | Retrieve and filter alerts based on severity (`/alerts/list`)               |
| 📄 **Report Management** | Download completed scan reports in JSON or PDF format (`/report/{scan_id}`) |

> 🧠 **Info:** All responses are returned in **JSON format** by default unless specified otherwise.

***

### 📚 Explore the Documentation

| **Category**                               | **Description**                                                                                               |
| ------------------------------------------ | ------------------------------------------------------------------------------------------------------------- |
| [🔐 **Authentication**](authentication.md) | Learn how to authenticate securely and generate valid tokens.                                                 |
| [⚙️ **Endpoints**](endpoints/)             | Understand input parameters, required headers, and request body structure.                                    |
| [⚠️ **Error Codes**](error-codes.md)       | Review standard response codes and error messages. Troubleshoot failed requests and interpret API error logs. |

***

### 🎯 Purpose of This Suite

This **API Reference** is part of the **CyberShield Documentation Suite**, created to demonstrate:

* Writing and structuring developer-focused API documentation.
* Organizing technical reference content with clarity and precision.
* Aligning SDK and API content through consistent editorial tone and layout.
* Enabling automation and secure integration workflows through clear endpoint usage examples.

> 💡 **Info:** This API Reference connects the SDK to real-world automation, showing the bridge between code, configuration, and secure data exchange.

### 🧾 About the Author

**Stuti Sanghvi** is a **technical writer and content strategist** who builds **clear, structured, and user-friendly** documentation experiences. She excels at translating complex concepts into accessible content that empowers users, supports teams, and strengthens product understanding.&#x20;

Her work focuses on creating **intuitive documentation systems** that help users learn confidently and navigate with ease. Her expertise includes producing precise, **spec-driven API documentation** that supports developers in understanding **endpoints, parameters, and integration behaviors**.

#### **Connect with the Author:**

[**💼 LinkedIn**](https://linkedin.com/in/stuti-sanghvi)\
[**💌 Email**](mailto:stutisanghvi7@gmail.in)\
[**🌐 Portfolio (via Notion)**](https://www.notion.so/Stuti-Sanghvi-Content-Strategist-Technical-Writer-29cf34655bbd809589e7d360b8e98ed1)\
[**🔗 GitHub**](https://github.com/Stuti-ContentStrategist)

Learn more → [**About the Author**](https://app.gitbook.com/o/YBUOQjCTo1Lf6omt9Fkt/s/SujDvXvEbVunQ9a2s6Us/)

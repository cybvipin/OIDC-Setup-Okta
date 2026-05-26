# Okta OIDC Project – End‑to‑End Documentation

## 📌 Project Overview
This project demonstrates how to configure, test, and troubleshoot an **OpenID Connect (OIDC)** application in **Okta**.  
It includes:

- Creating an Okta Developer account  
- Registering an OIDC application  
- Assigning users  
- Configuring Authentication Policies  
- Testing with OAuth Debugger  
- Understanding tokens (ID Token, Access Token)  
- Troubleshooting common errors  
- Documenting workflows, data models, and test cases  

This repository is structured to help IAM beginners and professionals understand the full OIDC authentication flow.

---

## 📁 Folder Structure

```
.
├── README.md
├── Index.md
├── labs.md
├── projects.md
├── workflows.md
├── database.md
└── blog.md
```

---

## 🧩 Architecture Diagram (ASCII)

```
+-------------+        +------------------+        +------------------+
|   Browser   | -----> |  Okta Login Page | -----> | Authentication   |
| (OAuth Tool)|         | (Hosted Sign-In) |         |   Policies       |
+-------------+        +------------------+        +------------------+
       |                         |                          |
       |                         v                          |
       |                 +------------------+               |
       |                 |   OIDC App       | <-------------+
       |                 | (Client ID/Secret) 
       |                 +------------------+
       |                         |
       v                         v
+-------------+        +------------------+
| Auth Code   | -----> | Token Endpoint   |
+-------------+        +------------------+
                               |
                               v
                     +----------------------+
                     | ID Token / Access    |
                     | Token Returned       |
                     +----------------------+
```

---

## 🎯 Learning Objectives

- Understand OIDC authentication flow  
- Configure Okta OIDC applications

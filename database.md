# IAM Data Model – Okta OIDC Project

This file documents the logical IAM data model used in the project.

---

## 👤 User Object

```
{
  "id": "00u123",
  "username": "alice.demo",
  "email": "alice@example.com",
  "status": "ACTIVE",
  "groups": ["Everyone"]
}
```

---

## 📱 Application Object

```
{
  "id": "0oa123",
  "name": "Demo_OIDC Test",
  "type": "OIDC",
  "client_id": "xxxx",
  "redirect_uris": ["https://oauthdebugger.com/debug"]
}
```

---

## 🔐 Policy Object

```
{
  "id": "pol123",
  "name": "OIDC Test Policy",
  "rules": [
    {
      "if": "any user",
      "then": "password only"
    }
  ]
}
```

---

## 🎟 Token Object

```
{
  "id_token": "xxxxx",
  "access_token": "xxxxx",
  "expires_in": 3600
}
```

---

## 👥 Group Object

```
{
  "id": "grp123",
  "name": "Everyone"
}
```


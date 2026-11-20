# 🔐 FakeBank – Hidden Admin Panel & Broken Access Control

## 📌 Project Overview

This project documents my hands-on experience with the FakeBank web application security lab. The objective was to discover a hidden administrative panel, access the bank transfer functionality, and understand the security risks associated with improperly protected web application endpoints.

**Platform:** TryHackMe  
**Environment:** Kali Linux  
**Target:** FakeBank (`fakebank.thm`)  
**Focus Area:** Web Application Security  
**Vulnerability:** Broken Access Control

---

## 🎯 Objectives

- Discover hidden web application endpoints.
- Understand URL manipulation techniques.
- Access the hidden bank transfer panel.
- Test the bank transfer functionality.
- Identify security weaknesses in administrative access.
- Understand the importance of authentication and authorization.

---

## 🛠️ Tools & Technologies

| Tool / Technology | Purpose |
|---|---|
| Kali Linux | Testing environment |
| Mozilla Firefox | Web application access |
| TryHackMe | Cybersecurity training platform |
| URL Manipulation | Hidden endpoint discovery |

---

## 🔍 Practical Implementation

### Step 1 – Access the FakeBank Website

Opened the FakeBank web application:

```text
http://fakebank.thm/
```

### Step 2 – Discover the Hidden Admin Panel

Manually modified the URL by adding the discovered endpoint:

```text
http://fakebank.thm/bank-transfer
```

This provided access to the hidden bank transfer panel.

### Step 3 – Identify the Target Account

Verified the account details provided in the lab:

| Account Information | Value |
|---|---|
| Account Holder | Mrs. G. Benjamin |
| Account Number | 8881 |
| Initial Balance | -$1,232.32 |

### Step 4 – Perform the Bank Transfer

Selected the verified account number and deposited $2,000.

**Balance Calculation:**

```text
Initial Balance:  -$1,232.32
Deposit Amount:   +$2,000.00
--------------------------------
Final Balance:     $767.68
```

**Result:** Successfully changed the account balance from negative to positive.

---

## 🔓 Security Vulnerability Analysis

### Broken Access Control

The hidden bank transfer page was accessible by directly navigating to its URL without proper authentication.

This demonstrates that hiding an administrative endpoint does not provide adequate security.

### Recommended Security Measure

**Require Login**

The application should enforce authentication before allowing access to sensitive administrative functionality.

Additional security considerations:

- Implement role-based access control (RBAC).
- Enforce server-side authorization checks.
- Protect sensitive endpoints.
- Validate user permissions for every transaction.
- Maintain security logs for sensitive operations.

---

## 💡 Key Learnings

Through this practical exercise, I learned:

- How hidden endpoints can be discovered.
- Why URL obscurity is not a security control.
- How Broken Access Control can expose sensitive functionality.
- The importance of authentication and authorization.
- How to identify basic web application security weaknesses.

---

## 📸 Lab Evidence

Add your screenshots below:

```markdown
![FakeBank Dashboard](screenshots/fakebank-dashboard.png)

![Hidden Admin Panel](screenshots/bank-transfer-panel.png)

![Successful Deposit](screenshots/successful-deposit.png)
```

---

## 🛡️ Security Takeaway

**A hidden administrative page is not a secure administrative page.**

Every sensitive endpoint must enforce proper authentication and authorization, regardless of whether its URL is publicly known.

---

## ⚖️ Disclaimer

This documentation is for educational purposes and reflects testing performed within the authorized TryHackMe training environment. Never test systems without explicit permission.

---

**Author:** Hamza Riaz  
**Focus:** Cybersecurity | Ethical Hacking | Web Application Security  
**Platform:** TryHackMe

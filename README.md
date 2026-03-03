# 🔐 Vulnerability Assessment Report – task 1

## 📌 task Overview
This project presents a Vulnerability Assessment conducted as part of an internship task. The objective was to identify security weaknesses using both automated and manual security testing techniques.

## 🌐 Target Application
testphp.vulnweb.com  
(Intentionally vulnerable demo website used for security practice)

---

## 🎯 Objective
- Perform passive security testing
- Identify vulnerabilities in server configuration
- Analyze cookies and HTTP headers
- Evaluate overall security posture
- Provide remediation recommendations

---

## 🛠 Tools Used

### 1️⃣ Nmap – Network Scanning
Purpose:
- Identify open ports
- Detect running services
- Discover service versions

Command Used:
nmap -sV -T4 testphp.vulnweb.com

Key Observations:
- Port 80 open (HTTP)
- nginx web server detected
- Server version disclosure observed

---

### 2️⃣ OWASP ZAP – Web Vulnerability Scanner
Scan Type:
Automated Passive Scan

Purpose:
- Detect missing security headers
- Identify insecure cookies
- Discover information disclosure issues

Common Alerts Identified:
- Missing security headers
- Cookie without Secure flag
- Server information disclosure
- Outdated technology components

---

### 3️⃣ Browser Developer Tools (Manual Testing)

Manual verification performed using Chrome DevTools.

Security Tab:
- Website not using HTTPS
- Connection marked “Not Secure”

Network Tab:
- Server version disclosure
- PHP version exposed

Application Tab (Cookies):
- Cookie without Secure flag
- Cookie without HttpOnly flag
- Sensitive data stored in cookie

---

## 🚨 Key Vulnerabilities Identified

- No HTTPS (HTTP only) – High Risk
- Outdated PHP Version – High Risk
- Insecure Cookie Configuration – High Risk
- Server Version Disclosure – Medium Risk
- Missing Security Headers – Medium Risk

---

## 📊 Overall Risk Rating
HIGH

The absence of HTTPS encryption and outdated backend technologies significantly increase the attack surface and security risks.

---

## 🛡 Recommendations

- Implement HTTPS with a valid SSL certificate
- Upgrade PHP to the latest stable version
- Enable Secure and HttpOnly cookie flags
- Hide server version information
- Implement security headers:
  - Strict-Transport-Security
  - X-Frame-Options
  - Content-Security-Policy
  - X-Content-Type-Options

---



## 📌 Learning Outcomes

- Hands-on experience in vulnerability assessment
- Practical usage of Nmap and OWASP ZAP
- Understanding of HTTP security mechanisms
- Risk analysis and remediation planning

---

## ⚠ Disclaimer

This assessment was conducted strictly for educational and internship purposes on an intentionally vulnerable demo website. No unauthorized exploitation was performed.

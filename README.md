# FUTURE_CS_01
# Web Application Security Assessment

## demo.testfire.net

**Prepared by:** Idrisa Haruni Kigaile

**Program:** Future Interns

**Assessment Type:** Passive & Non-Intrusive Security Assessment

**Scan Date:** 27 July 2026

**Report Date:** 28 July 2026





This repository contains a security assessment of **demo.testfire.net**, a deliberately vulnerable banking demo application maintained by Altoro Mutual and commonly used for learning web application security.

No production customer data or live systems were involved in this assessment.

> **Important:** This assessment was performed for educational purposes against an intentionally vulnerable application.



## Target Information

| Item            | Details                            |
| --------------- | ---------------------------------- |
| Target          | `demo.testfire.net`                |
| Target URL      | `http://demo.testfire.net`         |
| Target IP       | `65.61.137.117`                    |
| Open Ports      | `80 (HTTP)`, `443 (HTTPS)`, `8080` |
| Web Server      | Apache-Coyote/1.1 (Apache Tomcat)  |
| Assessment Type | Passive / Non-Intrusive            |

The original assessment identified the target URL, IP address, open ports, and Apache-Coyote/Tomcat web server.



## Scope

### In Scope

* Publicly reachable pages and forms
* `/login.jsp`
* DNS and WHOIS reconnaissance
* Network port enumeration
* HTTP response header analysis
* Automated vulnerability scan results

### Out of Scope

* Authenticated testing beyond what the scanner observed passively
* Source-code review
* Infrastructure access
* Social engineering
* Physical security testing



##  Testing Methodology

The assessment was conducted using a **passive and non-intrusive approach**.

No exploitation or destructive testing was performed.

The following activities were specifically excluded:

* Vulnerability exploitation
* Modification of application data
* Modification of server configuration
* Brute-force attacks
* Denial-of-service attacks
* Other intrusive attacks

This scope is consistent with the original assessment methodology.



## Tools Used

| Tool                 | Purpose                                            |
| -------------------- | -------------------------------------------------- |
| **nslookup**         | DNS resolution and identification of the target IP |
| **whois**            | Domain registration lookup                         |
| **Nmap 7.98**        | Network port and service enumeration               |
| **curl**             | HTTP response, header, and cookie inspection       |
| **OWASP ZAP 2.17.0** | Automated web application vulnerability scanning   |

The Word report documents these tools and their purposes, including Nmap, curl, and OWASP ZAP.



##  Findings Summary

| Risk Level           | Count | Meaning                                         |
| -------------------- | ----: | ----------------------------------------------- |
|  **High**          |     0 | Fix immediately — direct route to compromise    |
|  **Medium**        |     4 | Fix soon — meaningfully increases attack chance |
|  **Low**           |     7 | Fix when convenient — helps an attacker prepare |
|  **Informational** |     4 | No action required — useful context             |

### Overall Result

**Total findings: 15**

* **0 High**
* **4 Medium**
* **7 Low**
* **4 Informational**

The assessment report records these finding counts and their corresponding risk meanings.



## Top Security Priorities

### 1. Implement Anti-CSRF Protection

Add **Cross-Site Request Forgery (CSRF)** protection to application forms, particularly the login form.

**Recommendation:**

* Use CSRF tokens.
* Validate tokens server-side.
* Ensure tokens are unpredictable and tied to the user's session.



### 2. Add Security Headers

The assessment identified missing security headers.

Recommended headers include:

```http
Content-Security-Policy
X-Frame-Options
Strict-Transport-Security
X-Content-Type-Options
```

These headers provide additional browser-side security controls and help reduce common web attack risks.



### 3. Enforce HTTPS

All application traffic should be served over HTTPS.

**Recommendation:**

* Redirect HTTP requests to HTTPS.
* Enable HSTS.
* Avoid transmitting sensitive information over unencrypted HTTP.



### 4. Reduce Server Information Disclosure

The server currently exposes information identifying the web server technology.

**Recommendation:**

Configure the web server/application so that unnecessary software and version information is not disclosed in HTTP responses.

These four priorities are directly reflected in the original assessment's recommendations.



##  Assessment Report

The complete security assessment report is included in this repository.

It covers:

* Executive Summary
* Findings at a Glance
* Information Gathering / Reconnaissance
* Identified Vulnerabilities
* Findings in Detail
* Remediation Roadmap
* Scope and Limitations



##  Repository Structure

```text
.
├── README.md
├── New_Security_Assessment_Report.docx
└── screenshots/
    └── ...
```



##  Disclaimer

This assessment was performed against an intentionally vulnerable demo application for educational purposes.

The techniques and findings described in this repository should **only be applied to systems that you own or have explicit written permission to test**.

Unauthorized security testing may be illegal and can cause disruption or damage.



##  Author

**Idrisa Haruni Kigaile**

Web Application Security Assessment
Future Interns Program — 2026


## 🔍 Nessus Vulnerability Scan Report — Localhost (127.0.0.1)

**Scan Date:** May 31, 2025  
**Scanner:** [Tenable Nessus Essentials](https://www.tenable.com/products/nessus/nessus-essentials)  
**Target:** `127.0.0.1` (Local Kali Linux machine)  
**Total Vulnerabilities Found:** 75

---

### 🚨 Summary by Severity
| Severity  | Count |
|-----------|-------|
| 🔴 Critical | 1     |
| 🟠 High     | 4     |
| 🟡 Medium   | 2     |
| 🔵 Low      | 0     |
| ℹ️ Info     | 68    |

---

### ⚠️ Most Crucial Vulnerabilities & Mitigations

#### 1. 🔴 **Node.js Multiple Critical Vulnerabilities**
- **Plugin ID:** [190856](https://www.tenable.com/plugins/nessus/190856)
- **CVSS v3.0:** 9.8 — Critical
- **Issue:** Outdated Node.js version is vulnerable to memory corruption, DoS, and privilege escalation.
- **Fix:**  
  ```bash
  sudo apt remove nodejs
  curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
  sudo apt install -y nodejs


*Ensure you're running Node.js v20.11.1 or later.*

---

#### 2. 🟠 **Python Tornado 6.5.0 - DoS Vulnerability**

* **Plugin ID:** [237199](https://www.tenable.com/plugins/nessus/237199)
* **CVSS v3.0:** 7.5 — High
* **Issue:** DoS vulnerability due to improper request handling in Tornado 6.5.0.
* **Fix:**

  ```bash
  pip install --upgrade tornado
  ```

  *Update to at least Tornado v6.5.1 or later.*

---

#### 3. 🟠 **SSL Certificate Cannot Be Trusted**

* **Plugin ID:** [51192](https://www.tenable.com/plugins/nessus/51192)
* **CVSS:** 6.5 — Medium
* **Issue:** Self-signed or expired SSL certificate.
* **Fix:**

  * Replace with a certificate from a trusted Certificate Authority (CA).
  * Use [Let's Encrypt](https://letsencrypt.org) for free trusted SSL:

    ```bash
    sudo apt install certbot
    sudo certbot --nginx  # or --apache
    ```

---

#### 4. 🟠 **Multiple Node.js High Vulnerabilities (April & July 2024)**

* **Plugin IDs:** [192945](https://www.tenable.com/plugins/nessus/192945), [201969](https://www.tenable.com/plugins/nessus/201969), [214404](https://www.tenable.com/plugins/nessus/214404)
* **CVSS v3.0:** 8.1–8.2 — High
* **Fix:** Same as Critical Node.js update above. Ensure:

  ```bash
  node -v  # shows >= 20.18.2 or >= 22.13.1
  ```

---

### 📦 Sample Informational Findings

| Plugin Name                       | Description                            |
| --------------------------------- | -------------------------------------- |
| Apache HTTP Server Installed      | Detected via header & process scan     |
| Docker Detected                   | Indicates container use                |
| OpenSSL Installed                 | TLS library — no version issue flagged |
| SSL/TLS Protocol Support Listed   | Good for baseline hardening checks     |
| OS/Service Fingerprinting via SSH | Safe, expected behavior in local scans |

---

### 📁 Full Report (PDF)

The full Nessus PDF  report containing all 75 findings, including CVEs, affected ports, services, and detailed risk levels is upliaded, and is also available here:
**[📄 Localhost Scan Report](./Localhost%20Scan_vgmuw2.pdf)**

---

> ✅ **Next Steps:**
>
> * Patch Node.js and Python environments.
> * Replace untrusted SSL certs.
> * Re-run scan to confirm vulnerabilities have been mitigated.

---

## 👨‍💻 Author

**Darsh Chatrani**  
🔗 [LinkedIn](https://linkedin.com/in/darshchatrani)  
📞 Contact: +91 97899 57123

---

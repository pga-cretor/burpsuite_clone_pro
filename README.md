 🔐 BurpSuite Clone Pro

> A lightweight, open-source web security toolkit inspired by Burp Suite — built entirely in Python with a browser-based UI.
 
![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-3.0%2B-black?logo=flask)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Active-brightgreen)
 
---
 
## ⚠️ Legal Disclaimer
 
> **This tool is intended exclusively for authorized penetration testing, security research, and bug bounty programs.**
> Using this software against systems you do not own or have explicit written permission to test is **illegal** and punishable by law.
> The authors assume **no responsibility** for misuse.
 
---
 
## 📖 Overview
 
**BurpSuite Clone Pro** is a Python-based HTTP/HTTPS interception proxy and web security assessment toolkit. It runs a local proxy on port `8080` and exposes a full-featured web dashboard on `http://127.0.0.1:8181`, giving security professionals a self-hosted alternative for manual and automated web application testing.
 
---
 
## ✨ Features
 
### 🕵️ Proxy & History
- Full HTTP/HTTPS traffic interception via local proxy (`127.0.0.1:8080`)
- Complete request/response history with filters (URL, method, status code)
- Header and body inspection
- One-click forwarding to Repeater, Intruder, or Scanner
- Export history as JSON
### 🛑 Intercept
- Block and modify requests in-flight before they reach the server
- Edit body, headers, or any request field
- **Forward** (send modified request) or **Drop** (discard)
- Scope-based filtering
### 🔁 Repeater
- Re-send any request with custom modifications
- View status code, response body, and response time
- Load requests directly from History
### 💥 Intruder (Fuzzer)
- Attack modes: **Sniper**, **Pitchfork**, **Cluster Bomb**
- Mark injection points with `§value§` syntax
- Built-in payloads: XSS, SQL Injection, Directory Brute Force
- Results table with status, content length, and response preview
### 🔬 Scanner (Active)
Automated injection testing for:
- Cross-Site Scripting (XSS)
- SQL Injection (SQLi)
- Local File Inclusion (LFI)
- Server-Side Request Forgery (SSRF)
- Open Redirect
- Server-Side Template Injection (SSTI)
- Command Injection
Detection based on reflection, error messages, and timing analysis. Findings rated **Critical / High / Medium / Low**.
 
### 🧪 Passive Scanner (Automatic)
Every response is automatically analyzed for:
- Exposed API keys and AWS credentials
- Private keys (PEM format)
- JWTs in body or headers
- Cleartext passwords
- Stack traces and debug info
- SQL errors
- CORS wildcard (`*`)
- Server version disclosure
- Missing HSTS on HTTPS
- Path traversal patterns
### 🔤 Decoder / Encoder / Hasher
| Operation | Formats |
|-----------|---------|
| Encode/Decode | Base64, Base64 URL-safe, URL (single & double), HTML, Hex, ASCII↔Hex |
| Hash | MD5, SHA-1, SHA-256, SHA-512 |
| Decode | JWT (header + payload) |
 
Supports chained operations with **"Use as Input"**.
 
### 🗺️ Sitemap
- Auto-generated map of all discovered endpoints
- Organized by host
- Click any path to send it to Repeater
- Export as JSON
### 🆚 Compare (Diff)
- Line-by-line diff of two HTTP responses
- Added lines highlighted in **green**, removed in **red**
### 🎯 Scope Manager
- Regex patterns to restrict interception to specific hosts/paths
- Add/remove patterns from the UI
### 🍪 Cookie Jar
- Automatically collects `Set-Cookie` headers from all responses
- Displays host, name, and value
- One-click clear
---
 
## 🚀 Installation
 
### 1. Clone the repository
 
```bash
git clone https://github.com/yourusername/burpsuite-clone-pro.git
cd burpsuite-clone-pro
```
 
### 2. Install dependencies
 
```bash
pip install -r requirements.txt
```
 
> Requires Python 3.8+ and `openssl` for HTTPS interception.
 
### 3. Start the tool
 
```bash
python burpsuite_pro.py
```
 
### 4. Open the dashboard
 
```
http://127.0.0.1:8181
```
 
### 5. Configure your browser proxy
 
| Protocol | Host | Port |
|----------|------|------|
| HTTP | 127.0.0.1 | 8080 |
| HTTPS | 127.0.0.1 | 8080 |
 
### 6. Install the CA certificate (for HTTPS)
 
On first launch, the tool auto-generates `certs/proxy.crt`.
Import it into your browser's trusted certificate authorities to intercept HTTPS traffic without warnings.
 
---
 
## 📋 Requirements
 
```
Python >= 3.8
Flask  >= 3.0.0
openssl (system)
```
 
---
 
## 🗂️ Project Structure
 
```
burpsuite-clone-pro/
├── burpsuite_pro.py     # Main application
├── requirements.txt
├── certs/               # Auto-generated SSL certificates
│   ├── proxy.crt
│   └── proxy.key
└── README.md
```
 
---
 
## 🤝 Contributing
 
Contributions are welcome! Please open an issue first to discuss what you'd like to change.
 
1. Fork the repository
2. Create your feature branch (`git checkout -b feature/my-feature`)
3. Commit your changes (`git commit -m 'Add my feature'`)
4. Push to the branch (`git push origin feature/my-feature`)
5. Open a Pull Request
---
 
## 📄 License
 
This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.
 
---
 
## 🙏 Acknowledgements
 
Inspired by [PortSwigger Burp Suite](https://portswigger.net/burp) — the industry-standard web security testing platform.
 
> Built for ethical hackers, security researchers, and bug bounty hunters. Always hack responsibly.
 

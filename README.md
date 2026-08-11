# 🛡️ Aegis AppSec Suite

### Drop the Binary. Keep the Secrets.

**Browser-first AppSec • Mobile Security • Web & Network Analysis**

> A practical browser-based security toolkit for source-code analysis, mobile application security, website security, network diagnostics, TLS analysis, and security reporting.

---

## ⚡ What Is Aegis?

**Aegis AppSec Suite** is a browser-first security toolkit designed for security researchers, AppSec engineers, penetration testers, developers, students, and defensive security teams.

Instead of requiring a collection of separate tools for every first-pass assessment, Aegis brings several common security workflows into one interface.

```text
                         🛡️ AEGIS APPSEC SUITE
                                  │
                  ┌───────────────┴───────────────┐
                  │                               │
             🔎 AEGISPULSE                    📱 BYTEVAULT
                  │                               │
        ┌─────────┼──────────┐            ┌───────┼────────┐
        │         │          │            │       │        │
       SAST     Mobile    Web/Network   Android   iOS    Native
        │       Scanner     Analysis    Analysis Analysis Analysis
        │         │          │            │       │        │
        └─────────┴──────────┘            └───────┴────────┘
                  │                               │
                  └───────────────┬───────────────┘
                                  ▼
                         🛡️ SECURITY FINDINGS
                                  │
                                  ▼
                            📊 REPORTING
```

---

# 🚀 At a Glance

| Capability                     | Tool                          |
| ------------------------------ | ----------------------------- |
| 🔎 Source Code Security / SAST | **AegisPulse**                |
| 📱 APK Security Scanning       | **AegisPulse Mobile Scanner** |
| 📦 AAB Security Scanning       | **AegisPulse Mobile Scanner** |
| 🍎 IPA Security Scanning       | **AegisPulse Mobile Scanner** |
| 🌐 Website Security Analysis   | **AegisPulse**                |
| 🔐 HTTP Security Headers       | **AegisPulse**                |
| 🧱 CSP Analysis                | **AegisPulse**                |
| 🌍 DNS Intelligence            | **AegisPulse**                |
| 🔎 Network Intelligence        | **AegisPulse**                |
| 🔐 TLS / SSL Diagnostics       | **AegisPulse**                |
| 🤖 Android AXML / DEX Analysis | **ByteVault**                 |
| 🧬 Smali / Bytecode Inspection | **ByteVault**                 |
| 🍎 iOS plist / Mach-O Analysis | **ByteVault**                 |
| 📊 Security Reporting          | **AegisPulse**                |

---

# 🔎 AegisPulse

## The Main Aegis Security Scanner

AegisPulse is the primary security analysis platform in the suite.

It combines three major workflows:

```text
┌──────────────────────────────────────────────────┐
│                    AEGISPULSE                    │
├──────────────────┬────────────────┬──────────────┤
│ 🔎 SAST          │ 📱 MOBILE      │ 🌐 WEB &     │
│                  │    SCANNER     │    NETWORK   │
├──────────────────┼────────────────┼──────────────┤
│ Source Code      │ APK            │ DNS          │
│ Secrets          │ AAB            │ HTTP         │
│ Security Rules   │ IPA            │ Headers      │
│ Configurations   │ Permissions    │ CSP          │
│ OWASP / CWE      │ Components     │ CORS         │
│ Remediation      │ Mobile Rules   │ TLS          │
│ Evidence         │ Findings       │ Network      │
└──────────────────┴────────────────┴──────────────┘
```

---

# 🔎 SAST — Source Code Security

AegisPulse can scan source code and project files for security-relevant patterns and configuration weaknesses.

## Supported Ecosystems

```text
JavaScript / TypeScript
Python
Java / Kotlin
Go
Swift / Objective-C
C / C++
PHP
Ruby
Rust
Dart
Shell
HTML / CSS
JSON / YAML / XML
Gradle / Maven
Docker / Kubernetes
Terraform
And other supported source/configuration formats
```

## 🔐 Security Detection

AegisPulse can identify indicators related to:

* 🔑 Hardcoded credentials
* 🔐 API keys
* 🎫 Tokens
* 🔒 Private-key indicators
* 💻 Dangerous command execution
* ⚡ Dynamic code execution
* 🌐 Insecure HTTP communication
* 🔢 Weak cryptography
* 💾 Sensitive storage
* 🌍 WebView security
* 🔑 Authentication and authorization indicators
* ⚙️ Security configuration weaknesses
* 📦 Dependency and configuration risks

## Findings

A finding can provide useful information such as:

```text
Severity
Finding
Description
Evidence
Location
Security Mapping
Remediation
References
```

---

# 📱 Mobile Security Scanner

## AegisPulse Includes the Mobile Scanner

Mobile scanning is a **core AegisPulse feature**.

Supported package formats include:

```text
.apk
.aab
.ipa
```

## 📦 Large File Support

The current AegisPulse upload limit is:

**5 GB per supported upload**

This makes the scanner suitable for large application packages and local security triage.

---

# 🤖 Android Security Analysis

AegisPulse can inspect security-relevant application information including:

* `AndroidManifest.xml`
* DEX / bytecode
* Application resources
* Native libraries
* Package metadata
* Permissions
* Components
* Exported components
* Security-sensitive APIs
* Application strings

## Security Areas

* Cleartext traffic
* Insecure storage
* Weak cryptography
* Credential exposure
* WebView configuration
* Exported components
* Broadcast receiver configuration
* Sensitive APIs
* Application security configuration

---

# 🍎 iOS Security Analysis

AegisPulse can inspect security-relevant information from:

* `Info.plist`
* Application metadata
* Privacy-manifest indicators
* Application content
* Security-sensitive configuration
* Package structures

## Security Areas

* ATS configuration
* Privacy manifest indicators
* Credential-related content
* Weak cryptography indicators
* Cleartext URL indicators
* Security-sensitive configuration

---

# 🛡️ Mobile Security Mapping

Mobile security checks cover concepts related to:

* **OWASP MASVS**
* **OWASP MASWE**
* **CWE**
* Android security configuration
* iOS security configuration

> Automated findings are **triage signals**, not automatic proof of exploitability. Validate important findings manually.

---

# 🌐 Website & Network Analyzer

AegisPulse includes a dedicated website and network analysis workflow.

It can combine browser-accessible information with configured external intelligence and optional local tooling.

---

# 🌍 DNS Analysis

Depending on availability, AegisPulse can inspect DNS records such as:

```text
A
AAAA
MX
TXT
```

This provides an initial view of a target's public DNS configuration.

---

# 🔐 HTTP Security Headers

AegisPulse can analyze security-related HTTP headers including:

```text
Content-Security-Policy
Strict-Transport-Security
X-Frame-Options
X-Content-Type-Options
Referrer-Policy
Permissions-Policy
Cross-Origin-Opener-Policy
Cross-Origin-Resource-Policy
Cross-Origin-Embedder-Policy
Access-Control-Allow-Origin
Set-Cookie
```

## Security Areas

* CSP
* HSTS
* Clickjacking protection
* MIME-sniffing protection
* Referrer control
* Permissions policies
* Cross-origin isolation
* CORS
* Cookie security indicators

---

# 🧱 CSP Analysis

AegisPulse can inspect Content Security Policy configuration and identify security-relevant weaknesses.

When browser restrictions prevent automatic retrieval, the application can use a manual-input workflow rather than presenting incomplete data as a successful scan.

---

# 🔐 TLS / SSL Diagnostics

Modern browsers restrict arbitrary raw TLS connections.

AegisPulse handles this limitation explicitly.

```text
Browser
   │
   │ Browser restrictions
   ▼
Native / External TLS Evidence
   │
   ▼
Paste / Import
   │
   ▼
AegisPulse Parser
   │
   ▼
Security Analysis
   │
   ▼
Report
```

Depending on the workflow, TLS evidence can be used to inspect:

* TLS protocol versions
* Certificate information
* Certificate chains
* Cipher information
* Handshake-related evidence
* Security configuration indicators

> AegisPulse does not pretend that browser JavaScript replaces OpenSSL, Nmap, or dedicated TLS scanners.

---

# 🌍 Network Intelligence

AegisPulse provides two approaches to network analysis.

## External Mode

External analysis can use available public intelligence such as:

* 🌐 Public DNS services
* 🛡️ Mozilla Observatory
* 🔎 Shodan InternetDB
* 📡 HTTP header services
* 🔐 Configured TLS/network intelligence sources

Possible information includes:

* IP addresses
* Internet-visible ports
* HTTP services
* Server information
* Security headers
* Web security configuration

### ⚠️ External Mode Is Not Offline

When external analysis is enabled, relevant information may be sent to third-party or public services.

---

# 🏠 Internal / LAN Mode

AegisPulse can optionally communicate with a local Node.js helper.

Default:

```text
127.0.0.1:8787
```

The helper can provide capabilities that browser JavaScript cannot directly perform, such as:

* TCP port analysis
* LAN host discovery
* HTTP fingerprinting
* TLS inspection
* Local network analysis
* Nmap-related workflows

## Architecture

```text
                AegisPulse Browser
                       │
                       │ localhost
                       ▼
                 127.0.0.1:8787
                       │
                       ▼
              Local Node.js Helper
                       │
          ┌────────────┼────────────┐
          ▼            ▼            ▼
       Network       HTTP          TLS
       Discovery   Fingerprint   Analysis
```

---

# 📱 ByteVault

## The Mobile Analysis Companion

ByteVault is a separate tool from AegisPulse.

The distinction is important:

### AegisPulse

**Security scanning and vulnerability-oriented mobile triage**

### ByteVault

**Deeper mobile package inspection and artifact analysis**

```text
                    MOBILE SECURITY
                          │
             ┌────────────┴────────────┐
             │                         │
        📱 AegisPulse              🔬 ByteVault
        Mobile Scanner             Deep Analysis
             │                         │
       Security findings        Package inspection
       MASVS / MASWE             AXML / plist
       Permissions               DEX / Smali
       Components                Mach-O
       Configuration             Native libraries
```

---

# 🤖 ByteVault — Android

ByteVault can inspect Android application structures including:

## Manifest & Resources

* Binary Android AXML
* `AndroidManifest.xml`
* Resource XML
* `resources.arsc`
* Package metadata
* Permissions
* Components
* Exported component indicators

## DEX / Bytecode

Browser-side DEX analysis can expose:

* Classes
* Methods
* Fields
* Bytecode
* Smali-style representations

## Native Libraries

Native components can be inspected for:

* ELF structure
* Architecture
* Sections
* Symbols
* Native library metadata

---

# 🍎 ByteVault — iOS

ByteVault can inspect iOS application package structures.

## Property Lists

Inspection includes structures such as:

```text
Info.plist
embedded.mobileprovision
```

## Mach-O

Mach-O analysis can expose information including:

* Architectures
* Headers
* Segments
* Sections
* Dynamic libraries
* Frameworks
* Objective-C classes
* Objective-C selectors
* Symbols

> ByteVault is a browser-based inspection tool and is not intended to replace complete native reverse-engineering environments.

---

# 📡 Mobile Distribution Utilities

ByteVault also includes mobile distribution metadata utilities.

## AltStore / SideStore

Generate `apps.json`-style source metadata containing information such as:

* Application name
* Bundle identifier
* Version
* Download information
* Icon information
* Source metadata

## Apple OTA

Generate `manifest.plist` metadata for authorized wireless application distribution workflows.

> These utilities generate metadata. They do not replace Apple's official signing and distribution infrastructure.

---

# 🔐 Privacy Model

Aegis follows a **local-first design philosophy**.

## 🟢 Local File Analysis

```text
Your File
   │
   ▼
Your Browser
   │
   ▼
Local Processing
   │
   ▼
Security Findings
```

Core local file-analysis workflows do not require an Aegis-hosted backend.

---

## 🟠 External Intelligence

External network analysis is different.

```text
Your Browser
      │
      ▼
External Service
      │
      ▼
Target Intelligence
      │
      ▼
Results
```

Depending on the enabled workflow, this may involve:

* Mozilla Observatory
* Shodan InternetDB
* Public DNS services
* HTTP services
* Other configured intelligence providers

Therefore:

> **Local file scanning is designed for local processing, but external network intelligence is not an air-gapped workflow.**

For highly sensitive environments, prefer local/offline workflows and organization-approved native tooling.

---

# 🧱 Browser-First by Design

Aegis does not attempt to bypass browser security boundaries.

Modern browsers restrict:

* Raw TCP
* Arbitrary TLS sockets
* Cross-origin requests
* Native filesystem access
* USB operations
* Platform signing
* App Store decryption
* Low-level OS access

Aegis uses alternative workflows where necessary:

```text
Browser Limitation
       │
       ▼
Alternative Workflow
       │
       ├── Manual Input
       ├── Native Tool Output
       ├── Imported Evidence
       ├── Localhost Helper
       └── External Intelligence
       │
       ▼
Aegis Parser
       │
       ▼
Security Audit
       │
       ▼
Report
```

---

# 🏗️ Architecture

```text
                         🛡️ AEGIS APPSEC SUITE
                                  │
                   ┌──────────────┴──────────────┐
                   │                             │
              🔎 AEGISPULSE                  📱 BYTEVAULT
                   │                             │
       ┌───────────┼───────────┐         ┌───────┼────────┐
       │           │           │         │       │        │
      🔎          📱          🌐        🤖      🍎       🧬
     SAST       Mobile      Web &     Android  iOS     Native
                Scanner     Network
       │           │           │         │       │        │
       └───────────┼───────────┘         └───────┼────────┘
                   │                             │
                   └──────────────┬──────────────┘
                                  ▼
                         🛡️ SECURITY FINDINGS
                                  │
                                  ▼
                           📊 SECURITY REPORT
```

---

# 📊 Security Reporting

Aegis is designed to turn technical scanner results into useful security evidence.

A finding can include:

```text
Severity
Finding
Description
Evidence
Location
OWASP / CWE Mapping
Remediation
References
```

Useful for:

* Application security assessments
* Secure code reviews
* Mobile security assessments
* Penetration testing
* Development remediation
* Internal audits
* Security research
* Assessment documentation

---

# 🧭 Which Tool Should I Use?

| I want to...                        | Use                             |
| ----------------------------------- | ------------------------------- |
| 🔎 Scan source code                 | **AegisPulse → SAST**           |
| 🔑 Find potential secrets           | **AegisPulse → SAST**           |
| 📱 Scan an APK                      | **AegisPulse → Mobile Scanner** |
| 📦 Scan an AAB                      | **AegisPulse → Mobile Scanner** |
| 🍎 Scan an IPA                      | **AegisPulse → Mobile Scanner** |
| 🛡️ Check mobile security controls  | **AegisPulse → Mobile Scanner** |
| 🤖 Inspect Android AXML             | **ByteVault**                   |
| 🧬 Inspect DEX / Smali              | **ByteVault**                   |
| 🍎 Inspect plist structures         | **ByteVault**                   |
| ⚙️ Inspect Mach-O                   | **ByteVault**                   |
| 🌐 Analyze DNS                      | **AegisPulse → Web/Network**    |
| 🔐 Analyze HTTP headers             | **AegisPulse → Web/Network**    |
| 🧱 Audit CSP                        | **AegisPulse → Web/Network**    |
| 🔎 Investigate network intelligence | **AegisPulse → Web/Network**    |
| 🔐 Analyze TLS evidence             | **AegisPulse → TLS**            |
| 📊 Produce security reports         | **AegisPulse**                  |

---

# 🚀 Quick Start

## 1. Clone

```bash
git clone <YOUR-GITHUB-REPOSITORY-URL>
cd Aegis-AppSec-Suite
```

## 2. Start a Local Server

For the best browser compatibility:

```bash
python -m http.server 8080
```

## 3. Open

```text
http://127.0.0.1:8080/
```

## 4. Choose Your Workflow

### 🔎 Source Code

```text
AegisPulse
   ↓
SAST
   ↓
Upload / Load Source
   ↓
Scan
   ↓
Review Findings
```

### 📱 Mobile Application

```text
AegisPulse
   ↓
Mobile Scanner
   ↓
APK / AAB / IPA
   ↓
Analyze
   ↓
Review Findings
```

### 🌐 Website or Network

```text
AegisPulse
   ↓
Website & Network Analyzer
   ↓
Authorized Target
   ↓
DNS / HTTP / Network / TLS
   ↓
Review Findings
```

### 🔬 Deep Mobile Inspection

```text
ByteVault
   ↓
APK / IPA / Package
   ↓
Decode / Inspect
   ↓
DEX / Smali / AXML / plist / Mach-O
   ↓
Investigate
```

---

# 🧪 Recommended Security Workflow

For an authorized assessment:

```text
                    START
                      │
                      ▼
             🔐 Get Authorization
                      │
                      ▼
             📦 Preserve Original
                 Artifact
                      │
                      ▼
              🔎 AegisPulse
                  Triage
                      │
          ┌───────────┼───────────┐
          ▼           ▼           ▼
        SAST       Mobile     Web/Network
                   Scanner
          │           │           │
          └───────────┼───────────┘
                      ▼
              📱 ByteVault
           when deeper mobile
             inspection is needed
                      │
                      ▼
              🔍 Validate Findings
                      │
                      ▼
              🧪 Reproduce Manually
                      │
                      ▼
              📝 Document Evidence
                      │
                      ▼
                🔧 Remediate
                      │
                      ▼
                 🔄 Re-test
                      │
                      ▼
                📊 Final Report
```

---

# ⚠️ Technical Limitations

Aegis is intentionally transparent about its boundaries.

## AegisPulse

* Browser APIs cannot perform arbitrary raw TCP/TLS operations directly.
* External intelligence depends on third-party availability.
* CORS can prevent direct HTTP header retrieval.
* External services may impose rate limits.
* Network results may differ from native Nmap or dedicated scanners.
* Static analysis can produce false positives and false negatives.
* Automated findings require contextual validation.
* Current supported upload limit is **5 GB**.

## ByteVault

* Browser-based inspection is not equivalent to full native reverse engineering.
* FairPlay-protected App Store binaries cannot simply be decrypted using browser JavaScript.
* Production Android/iOS signing requires platform-specific infrastructure.
* Standard iOS installation requires legitimate Apple signing.
* Some package operations depend on browser/runtime capabilities.
* Some browser libraries may be loaded from external CDN resources.

---

# 🎯 Who Is Aegis For?

### 👨‍💻 AppSec Engineers

Quickly triage source code, applications, and security configurations.

### 🕵️ Penetration Testers

Perform authorized first-pass application and network security analysis.

### 📱 Mobile Security Researchers

Analyze Android/iOS packages and investigate mobile security indicators.

### 🔐 Developers

Identify security weaknesses before applications reach production.

### 🎓 Security Students

Learn practical application-security concepts using real artifacts.

### 🚨 Incident Responders

Perform rapid initial inspection of suspicious application or source artifacts.

---

# 📦 Repository Structure

```text
Aegis-AppSec-Suite/
│
├── AegisPulse.html
├── bytevault.html
└── README.md
```

The project is intentionally lightweight and HTML-based.

It can be:

* Downloaded
* Audited
* Run locally
* Hosted on static infrastructure
* Studied
* Customized
* Demonstrated

---

# 🤝 Contributing

Contributions are welcome.

## Good Areas to Contribute

* 🔎 SAST rules
* 🛡️ OWASP mappings
* 🔐 CWE mappings
* 📱 MASVS/MASWE improvements
* 🤖 Android security checks
* 🍎 iOS security checks
* 🧬 DEX/Smali parser improvements
* ⚙️ Mach-O analysis
* ⚡ Performance improvements
* 🌐 Browser compatibility
* ♿ Accessibility
* 📊 Reporting improvements
* 📚 Documentation
* 🐛 Reproducible bug reports

## Before Submitting a Pull Request

```text
Test the affected workflow
        ↓
Check browser console
        ↓
Test normal cases
        ↓
Test edge cases
        ↓
Test large files where applicable
        ↓
Verify existing scanners
        ↓
Document the change
```

---

# 🛡️ Responsible Use

Aegis AppSec Suite is intended for:

* Authorized penetration testing
* Application security testing
* Secure code review
* Mobile security assessments
* Internal security research
* Incident response
* Security education
* Defensive engineering

**Only analyze applications, systems, and networks that you own or have explicit permission to test.**

Do not use network scanning capabilities against unauthorized systems.

---

# 📄 License

Copyright © 2026 Aegis AppSec Suite contributors.

This project is licensed under the **MIT License**.

See [`LICENSE`](LICENSE) for the complete license text.

---

# ⭐ Aegis AppSec Suite

## Browser-first AppSec. Mobile Security. Network Visibility.

**🔎 Find it. → 🛡️ Understand it. → 📊 Report it. → 🔧 Fix it.**

### Drop the Binary. Keep the Secrets.

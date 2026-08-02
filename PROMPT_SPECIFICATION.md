# AI Prompt Specification Blueprint: AegisPulse SAST

This document contains the exact structural parameters, UI layout rules, and architectural heuristics used by the AI engine to generate the complete client-side static security scanner module for **AegisPulse SAST**.

---

## 1. User Interface & Layout Framework
* **CSS Framework**: Tailwind CSS via CDN.
* **Layout Structure**: Max-width container (`max-w-7xl mx-auto`) with a responsive grid layout.
  * **Main Content Area (2/3 width)**: Houses the tab navigation, drag-and-drop file ingestion zone, real-time scanning progress bar, and the interactive findings engine card.
  * **Sidebar Utilities (1/3 width)**: Houses live network auditing assets, including the DNS resolution terminal and the manual SSL/TLS raw log parser.
* **Header Actions**: Responsive control buttons mapped for `New scan`, `Export JSON`, and browser-native `Print report`.

---

## 2. Source Code & Mobile Package Scanner Heuristics
The core scanning dashboard operates entirely inside the client sandbox using the HTML5 `FileReader` API. It parses files locally with zero backend dependencies or server-side data extraction.

### Supported File Extensions
```text
.apk .ipa .zip .java .kt .swift .m .js .ts .py .php .go .rb .pl .pm .rs .cs .c .cpp
```

### Static Analysis Processing Framework
The rules engine filters out comment blocks and processes text segments via an asynchronous loop to map vulnerabilities against **OWASP Top 10 (2025/2026)** and **OWASP MASVS v2.1** standards using the following pattern matches:
1. **API Key/Token Leakage (High Severity)**: Matches strings assigning random cryptographic character profiles to variable markers like `secret`, `token`, or `password`.
2. **Cross-Site Scripting (XSS) Paths (Medium Severity)**: Flags DOM manipulation vectors such as `innerHTML` or `document.write(`.
3. **Dynamic Evaluation Injection (High Severity)**: Identifies instances of raw execution blocks like `eval(`.
4. **Outdated Cryptography (Low Severity)**: Highlights active patterns matching weak hashing algorithms like `md5` or `sha1`.

---

## 3. Sandboxed Network & TLS Audit Architecture
Due to standard browser execution boundaries, low-level network operations are managed using specific client-side workarounds:

### Live DNS, Header & CSP Check
* **Mechanism**: Direct fetch streams sent straight from the client browser to public DNS-over-HTTPS providers.
* **Target Resolver**: `https://cloudflare-dns.com` (with headers explicitly requesting `application/dns-json`).
* **Fallback Logic**: For endpoints that do not explicitly enable CORS headers, the system switches to a labeled heuristic estimate based on the hosting profile.

### SSL Certificate & TLS Configuration
* **Sandbox Boundary**: No native browser JavaScript API exposes deep TLS handshakes or raw certificate chain details.
* **Processing Flow**: The component uses a dedicated text zone where users manually paste raw handshake dumps, terminal readouts from `openssl s_client -connect host:443 -showcerts`, or browser certificate viewer strings. The local engine then parses these blocks to evaluate the active cipher suite and valid dates.

---

## 4. Analytical Compliance Limitations
* **Execution Boundary**: Pure regex/heuristic classification engine. It does not replace Abstract Syntax Tree (AST) compilation models or deep data flow taint tracking.
* **Memory Safety**: Large binary formats (e.g., compiled `.apk` or `.ipa` archives) undergo partial bounding and chunked inspection routines to protect browser tab thread memory from crashing.

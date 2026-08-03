# Aegis AppSec Suite 🛡️

> **Drop the Binary. Keep the Secrets.**  
> A 100% browser-native, zero-dependency suite for high-speed application security triage, source code scanning, and network diagnostics.

Aegis AppSec Suite runs **entirely client-side inside your browser sandbox**. Your source files, binary packages, and infrastructure configurations are processed strictly in local device memory—**nothing ever leaves your browser window.**

---

## 🧭 Live Deployment Matrix

| Platform Tool | Purpose & Primary Focus | Live Access Link |
| :--- | :--- | :--- |
| **AegisPulse SAST** | Multi-language regex scanning, OWASP mapping, and live DNS/Header analysis. | [Launch AegisPulse](https://github.io) |
| **ByteVault** | Mobile triage, binary plist/AXML decoding, and iOS 18+ deployment manifest compiling. | [Launch ByteVault](https://github.io) |

---

## 🎯 Target Audience: Is This Useful for You?

### 🟩 Highly Useful For:
* **Privacy-Conscious AppSec Testers:** A safe, local scratchpad to audit sensitive source directories without risking intellectual property exposure to third-party cloud servers.
* **Mobile Penetration Testers:** Instantly drop an APK/IPA to audit compiler protections (`MH_PIE`), verify DRM states (`cryptid`), or inspect decompiled manifest layouts.
* **Security Engineers & Incident Responders:** Quickly audit live HTTP response headers or extract high-entropy secrets (AWS, Stripe, JWT) via local memory loops.

### 🟥 Not Intended For:
* **Automated CI/CD Pipelines:** Because it runs within a browser tab, it requires active user interaction. It cannot natively replace headless build engines (like Semgrep or SonarQube).
* **Non-Technical Users:** The suite features high-density security primitives and assumes the analyst understands structural topics like OWASP MASVS, CORS policies, or Smali bytecode.

---

## 🛠️ Feature Breakdown & Core Architecture

### 1. AegisPulse SAST (`aegispulse-sast.html`)
* **Offline Code & Asset Scanner:** Processes raw unzipped directories (`.py`, `.js`, `.go`, `.swift`) locally using high-speed recursive regex patterns mapped directly to **OWASP Top 10:2025**.
* **Online Website & Network Analyzer:** Queries real-time DNS routing (A, AAAA, MX, TXT) natively in-page using public **DNS-over-HTTPS (DoH)** API resolvers.
* **Manual HTTP/TLS Audits:** Gracefully handles browser CORS and TLS handshake sandbox limits by providing clean manual text-ingestion boxes for `curl -I` or `openssl s_client` console data.

### 2. ByteVault Mobile Triage (`bytevault.html`)
* **Binary Tree Decompilation:** Re-renders binary Android AXML files and iOS binary plists (`bplist00`) into indented, human-readable XML layouts.
* **Repackaging & Signing Modifiers:** Features ad-hoc fake-signing for legacy jailbroken environments and custom `.p12` keystore code-signing blocks.
* **Wireless OTA Source Compilers:** Includes an integrated **AltStore/SideStore Repo Manifest Generator** (Section 7) and **Apple Manifest Compiler** (Section 6.2) to structure compliant `apps.json` and `manifest.plist` feeds for local network distribution.

---

## 📦 Sandbox & Technical Boundaries Handled Honestly

Aegis is built around engineering transparency rather than unmaintainable browser workarounds:
* **The FairPlay DRM Wall:** Standard browsers cannot decrypt App Store binaries. Aegis openly notes that deep code analysis or signature overrides require a pre-decrypted payload (e.g., dumped via `frida-ios-dump`).
* **The WebUSB TLS Gap:** Browsers cannot drive an arbitrary TLS handshake over raw WebUSB streams. The lockdown bridge explicitly logs this limitation, exposing raw frame streams on `window.__iosLockdown` while pointing users to native workstation tools (`libimobiledevice`, `usbmuxd`) for active tunneling.

---

## 📝 Usage & Contribution

1. **Run Locally:** Simply download `aegispulse-sast.html` or `bytevault.html` and open them directly in any modern Chromium-based browser (Chrome, Edge, Brave).
2. **Local Hosting alternative:** You can instantly spin up a local network server to share files over Wi-Fi without uploading to any remote server:
   ```bash
   python -m http.server 8080
   ```

*Contributions, bug report verifications, and custom regex signature mapping rule submissions are welcome. Feel free to open an issue or submit a pull request!*

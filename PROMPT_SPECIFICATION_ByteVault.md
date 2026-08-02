# AI Prompt Specification Blueprint: ByteVault (Mobile Application Suite)

This document maps out the technical parameters, structural UI components, and cryptographic/binary execution matrices used by the AI engine to construct the client-side Mobile Security Triage and Repackaging framework for **ByteVault**.

---

## 1. System Layout & Architecture Bounds
* **CSS Compilation Profile**: Tailwind CSS integrated via standard CDN hooks.
* **Component Presentation Grid**: Responsive asymmetric matrix layout (`max-w-7xl mx-auto`).
  * **Processing Columns (Left 2/3)**: Comprehensive functional blocks containing Binary Package Loading controls, Logging outputs, Decompilation controls, Smali/Class-Dump Viewers, Grep engines, Frida scripting terminals, Rule Dashboards, and Cryptographic Alignment modules.
  * **Supplemental Diagnostics (Right 1/3)**: Sandboxed interactive parameters containing WebUSB hardware bridge interfaces, Pairing validation record zones, and runtime system rule indicators.
* **Header Controls**: Instant single-tab initialization tools (`Clear Session`, `Print Vault Log / Save as PDF`).

---

## 2. In-Browser Decompilation & Binary Parser Logic
The binary analysis pipeline runs entirely client-side inside the browser memory loop using the native HTML5 `FileReader` and array array buffer data streams.

### Package Target Multi-Extension Matrix
```text
.apk (Android Package) | .ipa (iOS App Archive) | .zip (Compressed Trees) | AndroidManifest.xml | Info.plist
```

### Pure-JS Disassembler & Parser Logic
1. **Android DEX Engine**: A custom Dalvik bytecode parser that decodes binary classes, types, protocol strings, field layouts, and method array pools directly into low-level Smali-style structural templates (supporting standard formats: 10x, 11x, 12x, 21c, 22c, 23x, 35c, 3rc, 51l).
2. **iOS Mach-O Engine**: Extracts segment headers, structural load configurations, linked framework dependencies (`dylibs`), and recovers internal Objective-C/Swift class listings and selector names out of `__objc_classname` and `__objc_methname` sections.
3. **Manifest/Property Translation**: Re-renders binary Android AXML files and binary `bplist00` structures into human-readable indented XML text directly editable via in-browser text areas.

---

## 3. Client-Side Secret Scanning & Compliance Sinks
* **High-Entropy Scanner**: Runs a client-side Shannon Entropy calculation targeting text strings. Flags high-entropy sequences (`Shannon entropy ≥ 4.5 bits/character` across segments with at least `20+ characters`).
* **Regex Signature Verification**: Real-time evaluation patterns mapping targeted API profiles:
  * *Patterns*: AWS Credentials (`AKIA`/`ASIA`), Stripe Secrets (`sk_live_`/`pk_live_`), GitHub Tokens (`ghp_`), Google API Credentials (`AIza`), Slack Strings (`xox[bpoare]-`), Twilio, and raw private keys (`PEM blocks`).
* **Sink Cross-Reference Matrix**: Scans DEX summaries for insecure framework calls:
  * *Targets*: `WebView.addJavascriptInterface`, unsafe cipher setups (`DES`, `RC4`, `ECB`, `NoPadding`), weak digests (`MD5`, `SHA-1`), and arbitrary shell calls (`Runtime.exec`).

---

## 4. In-Browser Recompilation & Cryptographic Signature Block
To enable fully serverless application modifications, the system features targeted compilation compromises that execute inside the browser thread:

### Android Zipalign & signing (v1, v2, v3)
* **Zipalign**: Enforces 4-byte padding alignments on static compression archive records and 4096-byte boundaries on native binaries (`.so` assets).
* **Merkle Hash Blocks**: Utilizes the **Web Crypto API** to compute multi-tier chunk digests (1 MiB intervals using `0xA5`/`0x5A` prefixes) across the complete aligned container layout.
* **PKCS#12 Processing**: In-browser parsing of user `.p12` keystores to write official v1 JAR strings and append a native APK Signing Block profile directly before the final Central Directory footprint.

### iOS CodeResources & Provisioning
* **Metadata Hashing**: Iterates through application app bundles to register `SHA-1` and `SHA-256` key trees, injecting them into a structurally sound `_CodeSignature/CodeResources` file structure.
* **Detached Signature Blocks**: Leverages local data injection structures to append a detached PKCS#7/CMS configuration onto `CodeResources.sig`. 
* *System Boundary Requirement*: Since native execution limitations block local generation of full browser-based `LC_CODE_SIGNATURE` binary blobs, stock devices require a secondary external `codesign` pass, while jailbroken platforms leverage detached signature stripping (`ldid -S`).

---

## 5. WebUSB Hardware Bridges & Sandbox Limitations
To safely interface with debugging frameworks directly via a browser tab, the application implements raw wire transport shims over WebUSB:

### Chrome ADB Protocol Engine
* Communications target chromium devices over desktop USB wires directly to the native client daemon (`adbd`). 
* Generates automation templates for `frida-ps`, `objection exploration`, and standard platform hooks (root/jailbreak evasion, custom script loading, and SSL pin bypassing).

### Apple Lockdown Bridge Transport
* **Scope Definition**: Directly addresses the `usbmux` operational layout (class `0xFF`, subclass `0xFE`, protocol `0x02`) to speak plaintext configuration blocks via `lockdownd` tools.
* *Sandbox TLS Isolation Boundary*: Because native web architectures block raw TLS handshakes across a custom WebUSB byte stream, deeper interactions (such as secure installation proxies or direct service generation) require the loading of an external host system pair record file (`/var/db/lockdown/` or Windows equivalents) to bridge the transport gaps.

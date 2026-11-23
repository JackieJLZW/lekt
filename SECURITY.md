# Security & Offline Processing Policy

## 100% Local Document Processing
- **Zero Cloud Document Uploads:** All PDF/UA-1, PDF/UA-2, and WCAG 2.2 checks (`veraPDF 1.30.4`), page rendering (`PDFium`), native OS OCR (`Apple Vision` / `Windows WinRT OCR`), and structure remediation run strictly inside your local machine.
- **Zero Desktop Telemetry:** Lekt does not collect analytics, usage beacons, crash dumps, or document metadata from the desktop application.
- **Air-Gapped Licensing:** Optional Personal Pro and Team & Batch editions verify licenses strictly offline using hardware-bound **Ed25519** cryptographic certificates (`LEKT2-...`).

## Code Signing & Integrity Verification
- **macOS (`Lekt_<version>_aarch64.dmg`):** Signed with Apple Developer ID (`Hangzhou Jianlan Zhiwei Technology Co., Ltd`, Team ID `LQWJL5TFUW`), Hardened Runtime enabled across all nested Mach-O binaries/libraries, and Apple Notarized + Stapled.
- **Windows (`Lekt_<version>_x64-setup.exe` & `.msi`):** Authenticode signed with a Certum Organization Validated (OV) Code Signing certificate (`CN=Hangzhou Jianlan Zhiwei Technology Co., Ltd`) with RFC 3161 timestamping.
- **Published SHA-256 Checksums:** Verify downloads against `https://lekt.jianlanzhiwei.com/download/SHA256SUMS.txt`.

## Reporting a Security Issue
Please email security disclosures directly to **support@jianlanzhiwei.com**. We acknowledge reports within 2 business days.

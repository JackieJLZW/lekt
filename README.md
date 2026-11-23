# Lekt — 100% Offline PDF/UA-1, PDF/UA-2 & WCAG 2.2 Accessibility Checker & Visual Remediator

[![Website](https://img.shields.io/badge/Website-lekt.jianlanzhiwei.com-059669)](https://lekt.jianlanzhiwei.com/)
[![Latest Release](https://img.shields.io/badge/Release-v1.2.2-102a4c)](https://github.com/JackieJLZW/lekt/releases/latest)
[![Platforms](https://img.shields.io/badge/Platforms-macOS%20Apple%20Silicon%20%7C%20Windows%20x64-1d4ed8)](https://lekt.jianlanzhiwei.com/#download)
[![Offline](https://img.shields.io/badge/Processing-100%25%20Offline%20%7C%200%20Telemetry-065f46)](https://lekt.jianlanzhiwei.com/privacy)

**Lekt** is a native **macOS (Apple Silicon, pure `arm64`)** and **Windows x64** desktop workstation for checking and remediating **ISO 14289-1 (PDF/UA-1)**, **ISO 14289-2 (PDF/UA-2)**, and **WCAG 2.2** PDF accessibility—powered locally by **veraPDF 1.30.4**, **Apache PDFBox 3.0.8**, **BSD-3 PDFium**, and native OS offline OCR (**Apple Vision** / **Windows WinRT OCR**).

> **Note:** This is the official public documentation, release notes, checksum verification, and issue-tracking repository for Lekt by **Hangzhou Jianlan Zhiwei Technology Co., Ltd.** Report bugs, PDF/UA edge cases, or feature requests in [Issues](https://github.com/JackieJLZW/lekt/issues).

---

## Why Lekt?

- **Native PAC Alternative for Mac (Zero Windows VMs):** Run authoritative Matterhorn / veraPDF 1.30.4 validation and PAC-style linear **Screen Reader Preview** natively on macOS 13+ Apple Silicon (M1–M4, pure `arm64`, zero Rosetta 2) as well as Windows 10/11 x64.
- **100% Offline & Air-Gapped Safe:** Zero PDF files, extracted text, images, or usage telemetry ever leave your device. Built for **FERPA**, **HIPAA**, **ADA Title II**, **EU EAA**, legal, and municipal workflows.
- **0px Visual Diff Guarantee:** Structure edits, tag updates, and namespace-aware XMP metadata fixes never re-rasterize pages or shift fonts, colors, or margins—preserving existing author, copyright, and multilingual titles.
- **Native Offline OS OCR & 2-Column Reading Order:** Auto-tag scanned/image-only PDFs using Apple Vision (macOS) or Windows WinRT OCR with automatic 2-column academic layout detection.
- **Visual Remediation Without Acrobat Tag Hell:** Drag-and-drop visual reading order, inline semantic re-tagging (`P` ↔ `H1`–`H6`), Mark-as-Artifact, Visual Table Header (`<TH>`/`<TD>` + `Scope`) grid inspector, and Batch Figure Alt-Text drawer with live cropped previews.
- **Folder Batch Auditor (Up to 500 PDFs):** Triage whole directories by remediation effort, run non-overwriting Batch Auto-Fix & Batch Offline OCR, and export ADA Title II / EU EAA CSV & HTML audit reports.

---

## Direct Signed Downloads (`v1.2.2`)

| Platform | Installer | Signing & Verification | Direct Download |
| --- | --- | --- | --- |
| **macOS 13+ (Apple Silicon M1–M4)** | `Lekt_1.2.2_aarch64.dmg` (56.2 MB) | Pure `arm64` (0 Rosetta 2) · Apple Developer ID Signed & Notarized | [Download macOS DMG](https://lekt.jianlanzhiwei.com/download/macos) |
| **Windows 10/11 x64 (Standard)** | `Lekt_1.2.2_x64-setup.exe` (52.9 MB) | Certum OV Authenticode Signed + RFC 3161 Timestamp | [Download Windows EXE](https://lekt.jianlanzhiwei.com/download/windows) |
| **Windows 10/11 x64 (Enterprise MSI)** | `Lekt_1.2.2_x64_en-US.msi` (57.7 MB) | Certum OV Authenticode Signed + RFC 3161 Timestamp | [Download Windows MSI](https://lekt.jianlanzhiwei.com/download/windows-msi) |
| **Checksums** | `SHA256SUMS.txt` | Published SHA-256 hashes for all v1.2.2 artifacts | [View SHA256SUMS.txt](https://lekt.jianlanzhiwei.com/download/SHA256SUMS.txt) |

### Verify Download Checksums (`v1.2.2`)

```text
bb07909e71d4da3f2870a1f83020de95abf0d1a187e236d1b9b3d31118bb9fff  Lekt_1.2.2_aarch64.dmg
ee50ec05c1a7931c860b6e500b7a70066712fc605d9e4088a4fdb1e692f25483  Lekt_1.2.2_x64-setup.exe
f8516209684d01bba88830a272eb696e66a98054e852af72ffbd517ef634db7d  Lekt_1.2.2_x64_en-US.msi
```

---

## Feature & Tool Comparison

| Capability | Lekt v1.2.2 | PAC (2024/2026) | Adobe Acrobat Pro | PDFix Pro | CommonLook PDF |
| --- | --- | --- | --- | --- | --- |
| **macOS Apple Silicon Native** | Yes (pure `arm64`) | No (Windows only) | Yes | Yes | No (Windows only) |
| **Windows x64 Native** | Yes | Yes | Yes | Yes | Yes |
| **100% Offline (0 Telemetry)** | Yes | Yes | Partial (cloud sign-in) | Yes | Yes |
| **Strict PDF/UA-1, UA-2 & WCAG 2.2** | Yes (`veraPDF 1.30.4`) | Yes | Partial subset | Yes | Yes |
| **Screen Reader Preview** | Yes (Free forever) | Yes (Free) | No linear view | Yes | Yes |
| **1-Click Auto-Fix (0px Diff)** | Yes (Personal Pro) | Check only | Manual tag tree | Yes | Yes |
| **Offline OS OCR (2-Column)** | Yes (Apple Vision / WinRT) | No | Yes | Add-on | Add-on |
| **Folder Batch (500 PDFs) + Reports** | Yes (Team & Batch) | Single file | Action Wizard | Yes | Enterprise add-on |
| **Pricing** | **Free Checker**; $39 one-time Pro / $99/yr Team (3 seats) | Free | ~$240/yr | ~$599+/yr | ~$1,199+/yr |

---

## Documentation & Guides

- [PAC Alternative for Mac (Native Apple Silicon Guide)](https://lekt.jianlanzhiwei.com/pac-alternative-for-mac)
- [How to Fix the 7 Most Common PAC & veraPDF PDF/UA Errors](https://lekt.jianlanzhiwei.com/verapdf-pac-error-fixes)
- [ADA Title II & FERPA Offline PDF Remediation Comparison](https://lekt.jianlanzhiwei.com/ada-title-ii-offline-pdf-remediation)
- [ISO 14289-1 (PDF/UA-1) Error Reference](./docs/pdf-ua-error-reference.md)
- [Changelog](./CHANGELOG.md)
- [Security & Offline Architecture](./SECURITY.md)
- [Privacy Policy](https://lekt.jianlanzhiwei.com/privacy)

---

## Support & Contact

- **Bug reports & PDF/UA rule feedback:** Open an issue in [GitHub Issues](https://github.com/JackieJLZW/lekt/issues)
- **Email & Institutional / Purchase Order Quotes:** `support@jianlanzhiwei.com`
- **Website & Self-Service Seat Portal:** [https://lekt.jianlanzhiwei.com/](https://lekt.jianlanzhiwei.com/)

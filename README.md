# Lekt — 100% Offline PDF/UA-1, PDF/UA-2 & WCAG 2.2 Accessibility Checker & Visual Remediator

[![Website](https://img.shields.io/badge/Website-lektpdf.com-059669)](https://lektpdf.com/)
[![Latest Release](https://img.shields.io/badge/Release-v1.6.0-102a4c)](https://github.com/JackieJLZW/lekt/releases/latest)
[![Platforms](https://img.shields.io/badge/Platforms-macOS%20Apple%20Silicon%20%7C%20Windows%20x64-1d4ed8)](https://lektpdf.com/#download)
[![Microsoft Store](https://img.shields.io/badge/Microsoft%20Store-XP8BTZ1QSKF5HH-0078d4)](https://apps.microsoft.com/store/detail/XP8BTZ1QSKF5HH)
[![Offline](https://img.shields.io/badge/Processing-100%25%20Offline%20%7C%200%20Telemetry-065f46)](https://lektpdf.com/privacy)

**Lekt** is a native **macOS (Apple Silicon, pure `arm64`)** and **Windows x64** desktop workstation for checking and remediating **ISO 14289-1 (PDF/UA-1)**, **ISO 14289-2 (PDF/UA-2)**, and **WCAG 2.2** PDF accessibility—powered locally by **veraPDF 1.30.4**, **Apache PDFBox 3.0.8**, **BSD-3 PDFium**, **Native Vector Auto-Tagging (0 OCR)**, and native OS offline OCR (**Apple Vision** / **Windows WinRT OCR**).

> **Note:** This is the official public documentation, release notes, checksum verification, and issue-tracking repository for Lekt by **Hangzhou Jianlan Zhiwei Technology Co., Ltd.** Report bugs, PDF/UA edge cases, or feature requests in [Issues](https://github.com/JackieJLZW/lekt/issues).

---

## Why Lekt?

- **Native PAC Alternative for Mac (Zero Windows VMs):** Run authoritative Matterhorn / veraPDF 1.30.4 validation, Clause `7.1-3` untagged red-box canvas highlights, and PAC-style linear **Screen Reader Preview** natively on macOS 13+ Apple Silicon (M1–M4, pure `arm64`, zero Rosetta 2) as well as Windows 10/11 x64.
- **Native Vector Auto-Tag (Zero OCR Typos):** Untagged digital Word, PowerPoint, LaTeX, or InDesign PDF? Lekt wraps existing vector glyphs, lists (`<L>`/`<LI>`), headings (`<H1>`–`<H3>`), `<Link>`, and `<Form>` widgets directly in-stream (automatically silencing running headers/footers as `/Artifact`) with zero raster OCR typos and 0px visual diff.
- **100% Offline & Air-Gapped Safe:** Zero PDF files, extracted text, images, or usage telemetry ever leave your device. Built for **FERPA**, **HIPAA**, **ADA Title II**, **EU EAA**, legal, and municipal workflows.
- **0px Visual Diff + Damaged XRef Recovery:** Every remediation enforces a 150 DPI 0-pixel visual diff gate, and files with broken Acrobat hybrid XRef tables or trailing bytes after `%%EOF` open cleanly in Parser Recovery Mode for 1-click XRef normalization.
- **Hybrid & Selective Offline OS OCR (2-Column):** Auto-tag scanned/image-only pages using Apple Vision (macOS) or Windows WinRT OCR with automatic 2-column academic layout detection—preserving vector tables and forms on digital pages.
- **Visual Remediation & WCAG 2.2 AA Accessible UI:** Deep nested reading order (`Part › Sect › Div`) with drag-and-drop or keyboard (`Alt+↑/↓`) reorder, multi-select batch semantic re-tagging (`P` ↔ `H1`–`H6`), lossless `<L>` list & cross-page `<P>` merge, `<Div>` container unwrap, named unlimited Undo/Redo, 1-click `7.1-3` Untagged → `/Artifact`, Table `<TH>`/`<TD>` + `Scope` + `RowSpan`/`ColSpan` grid inspector, Unwrap layout tables, Form `<Form>`/`/TU` editor, Batch Figure Alt-Text drawer, and 500-PDF Folder Batch Auditor.

---

## Direct Signed Downloads (`v1.6.0`)

| Platform | Installer | Signing & Verification | Direct Download |
| --- | --- | --- | --- |
| **macOS 13+ (Apple Silicon M1–M4)** | `Lekt_1.6.0_aarch64.dmg` (59.4 MB) | Pure `arm64` (0 Rosetta 2) · Apple Developer ID Signed & Notarized | [Download macOS DMG](https://lektpdf.com/download/macos) |
| **Windows 10/11 x64 (Standard)** | `Lekt_1.6.0_x64-setup.exe` (56.1 MB) | Certum OV Authenticode Signed + RFC 3161 Timestamp | [Download Windows EXE](https://lektpdf.com/download/windows) |
| **Windows 10/11 x64 (Enterprise MSI)** | `Lekt_1.6.0_x64_en-US.msi` (60.9 MB) | Certum OV Authenticode Signed + RFC 3161 Timestamp | [Download Windows MSI](https://lektpdf.com/download/windows-msi) |
| **Microsoft Store (Windows 10/11)** | `XP8BTZ1QSKF5HH` | Official Microsoft Store Win32 Listing | [View in Microsoft Store](https://apps.microsoft.com/store/detail/XP8BTZ1QSKF5HH) |
| **Checksums** | `SHA256SUMS.txt` | Published SHA-256 hashes for all v1.6.0 artifacts | [View SHA256SUMS.txt](https://lektpdf.com/download/SHA256SUMS.txt) |

### Verify Download Checksums (`v1.6.0`)

```text
574a71e3b4f02d9596760ad5c4fbef3258e796c7ba64728c0eae3e2e42a76390  Lekt_1.6.0_aarch64.dmg
43f533a7cbd377862e523f6043d85286ece3ba65ea3f4f375f36ea76023635c2  Lekt_1.6.0_aarch64.app.tar.gz
3fbdb101df1334910ed8d45e976ec63855017c787ecff1f6739288c51bd123f1  Lekt_1.6.0_x64-setup.exe
c6b5baaf90797dab136fa3ffdfc6ce2f807cc10931d43c310c8f898c43efb3f1  Lekt_1.6.0_x64_en-US.msi
```

---

## Feature & Tool Comparison

| Capability | Lekt v1.6.0 | PAC (2024/2026) | Adobe Acrobat Pro | PDFix Pro | CommonLook PDF |
| --- | --- | --- | --- | --- | --- |
| **macOS Apple Silicon Native** | Yes (pure `arm64`) | No (Windows only) | Yes | Yes | No (Windows only) |
| **Windows x64 Native** | Yes | Yes | Yes | Yes | Yes |
| **100% Offline (0 Telemetry)** | Yes | Yes | Partial (cloud sign-in) | Yes | Yes |
| **Machine-Checkable PDF/UA-1, UA-2 & WCAG 2.2** | Yes (`veraPDF 1.30.4` + XRef recovery) | Yes (Matterhorn machine rules) | Partial subset | Yes | Yes |
| **Screen Reader Preview & `7.1-3` Untagged Boxes** | Yes (Free forever) | Preview only | No linear view | Yes | Yes |
| **Native Vector Auto-Tag (0 Raster OCR)** | Yes (Personal Pro) | No | Cloud / heuristic autotag | Yes | Add-on |
| **1-Click Auto-Fix + `/Artifact` (0px Diff)** | Yes (Personal Pro) | Check only | Manual tag tree | Yes | Yes |
| **Hybrid & Selective Offline OS OCR (2-Column)** | Yes (Apple Vision / WinRT) | No | Yes | Add-on | Add-on |
| **Folder Batch (500 PDFs) + Reports** | Yes (Team & Batch) | Single file | Action Wizard | Yes | Enterprise add-on |
| **Pricing** | **Free Checker**; $89 one-time Pro / $199/yr Team (3 seats) | Free | ~$240/yr | ~$599+/yr | ~$1,199+/yr |

> **Automated vs. Human Verification Scope:** Like PAC and veraPDF, Lekt's automated validation evaluates **machine-checkable** ISO 14289-1 (PDF/UA-1), ISO 14289-2 (PDF/UA-2), and WCAG 2.2 rules. Passing automated checks with 0 errors does not replace human accessibility review—heading hierarchy semantics, table header announcements, alt-text accuracy, and multi-column reading order still require human review using Lekt's **Screen Reader Preview**, **Reading Order**, **Tables**, and **Alt-Text** panels (and assistive technology testing).

---

## Documentation & Guides

- [PAC Alternative for Mac (Native Apple Silicon Guide)](https://lektpdf.com/pac-alternative-for-mac)
- [How to Fix the 7 Most Common PAC & veraPDF PDF/UA Errors](https://lektpdf.com/verapdf-pac-error-fixes)
- [ADA Title II & FERPA Offline PDF Remediation Comparison](https://lektpdf.com/ada-title-ii-offline-pdf-remediation)
- [ISO 14289-1 (PDF/UA-1) Error Reference](./docs/pdf-ua-error-reference.md)
- [Changelog](./CHANGELOG.md)
- [Security & Offline Architecture](./SECURITY.md)
- [Privacy Policy](https://lektpdf.com/privacy)

---

## Support & Contact

- **Bug reports & PDF/UA rule feedback:** Open an issue in [GitHub Issues](https://github.com/JackieJLZW/lekt/issues)
- **Email & Institutional / Purchase Order Quotes:** `support@lektpdf.com`
- **Website & Self-Service Seat Portal:** [https://lektpdf.com/](https://lektpdf.com/)

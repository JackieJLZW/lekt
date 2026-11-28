# Lekt — 100% Offline PDF/UA-1, PDF/UA-2 & WCAG 2.2 Accessibility Checker & Visual Remediator

[![Website](https://img.shields.io/badge/Website-lektpdf.com-059669)](https://lektpdf.com/)
[![Latest Release](https://img.shields.io/badge/Release-v1.8.0-102a4c)](https://github.com/JackieJLZW/lekt/releases/latest)
[![Platforms](https://img.shields.io/badge/Platforms-macOS%20Apple%20Silicon%20%7C%20Windows%20x64-1d4ed8)](https://lektpdf.com/#download)
[![Microsoft Store](https://img.shields.io/badge/Microsoft%20Store-XP8BTZ1QSKF5HH-0078d4)](https://apps.microsoft.com/store/detail/XP8BTZ1QSKF5HH)
[![Offline](https://img.shields.io/badge/Processing-100%25%20Offline%20%7C%200%20Telemetry-065f46)](https://lektpdf.com/privacy)

**Lekt** is a native **macOS (Apple Silicon, pure `arm64`)** and **Windows x64** desktop workstation for checking and remediating **ISO 14289-1 (PDF/UA-1)**, **ISO 14289-2 (PDF/UA-2)**, and **WCAG 2.2** PDF accessibility—powered locally by **veraPDF 1.30.4**, **Apache PDFBox 3.0.8**, **BSD-3 PDFium**, **Native Vector Auto-Tagging (0 OCR)**, and native OS offline OCR (**Apple Vision** / **Windows WinRT OCR**).

> **Note:** This is the official public documentation, release notes, checksum verification, and issue-tracking repository for Lekt by **Hangzhou Jianlan Zhiwei Technology Co., Ltd.** Report bugs, PDF/UA edge cases, or feature requests in [Issues](https://github.com/JackieJLZW/lekt/issues).

---

## Why Lekt?

- **Free Watermarked Proof PDF Export (Verify 0 Errors in PAC 2024 Before Paying):** Never take any vendor's self-reported `"0 Errors"` badge on faith. Run Lekt's full offline remediation on your own PDF and export a real remediated Proof PDF (`Cmd/Ctrl+Shift+P`) whose verification curves are strictly wrapped inside ISO 14289 `/Artifact`—then drop it directly into **PAC 2024**, **Adobe Acrobat Full Check**, **veraPDF**, or **NVDA/JAWS** to confirm `0` errors yourself before purchasing.
- **Native PAC Alternative for Mac (Zero Windows VMs):** Run authoritative Matterhorn / veraPDF 1.30.4 validation, Clause `7.1-3` untagged red-box canvas highlights, and PAC-style linear **Screen Reader Preview** natively on macOS 13+ Apple Silicon (M1–M4, pure `arm64`, zero Rosetta 2) as well as Windows 10/11 x64.
- **Native Vector Auto-Tag (Zero OCR Typos):** Untagged digital Word, PowerPoint, LaTeX, or InDesign PDF? Lekt wraps existing vector glyphs, lists (`<L>`/`<LI>`), headings (`<H1>`–`<H3>`), `<Link>`, and `<Form>` widgets directly in-stream (automatically silencing running headers/footers as `/Artifact`) with zero raster OCR typos and 0px visual diff.
- **100% Offline & Air-Gapped Safe:** Zero PDF files, extracted text, images, or usage telemetry ever leave your device. Built for **FERPA**, **HIPAA**, **ADA Title II**, **EU EAA**, legal, and municipal workflows.
- **0px Visual Diff + Damaged XRef Recovery:** Every remediation enforces a 150 DPI 0-pixel visual diff gate, and files with broken Acrobat hybrid XRef tables or trailing bytes after `%%EOF` open cleanly in Parser Recovery Mode for 1-click XRef normalization.
- **Hybrid & Selective Offline OS OCR (2-Column):** Auto-tag scanned/image-only pages using Apple Vision (macOS) or Windows WinRT OCR with automatic 2-column academic layout detection—preserving vector tables and forms on digital pages.
- **Visual Remediation & WCAG 2.2 AA Accessible UI:** Deep nested reading order (`Part › Sect › Div`) with drag-and-drop or keyboard (`Alt+↑/↓`) reorder, multi-select batch semantic re-tagging (`P` ↔ `H1`–`H6`), lossless `<L>` list & cross-page `<P>` merge, `<Div>` container unwrap, named unlimited Undo/Redo, 1-click `7.1-3` Untagged → `/Artifact`, Table `<TH>`/`<TD>` + `Scope` + `RowSpan`/`ColSpan` + `/Headers` ID grid inspector, Unwrap layout tables, Form `<Form>`/`/TU` editor, Batch Figure Alt-Text drawer, and 500-PDF Folder Batch Auditor (row selection, By-Clause filtering, Keep-Original-Name separate-folder exports, and CSV/JSON/HTML compliance reports).

---

## Direct Signed Downloads (`v1.8.0`)

| Platform | Installer | Signing & Verification | Direct Download |
| --- | --- | --- | --- |
| **macOS 13+ (Apple Silicon M1–M4)** | `Lekt_1.8.0_aarch64.dmg` (81.2 MB) | Pure `arm64` (0 Rosetta 2) · Apple Developer ID Signed & Notarized | [Download macOS DMG](https://lektpdf.com/download/macos) |
| **Windows 10/11 x64 (Standard)** | `Lekt_1.8.0_x64-setup.exe` (56.2 MB) | Certum OV Authenticode Signed + RFC 3161 Timestamp | [Download Windows EXE](https://lektpdf.com/download/windows) |
| **Windows 10/11 x64 (Enterprise MSI)** | `Lekt_1.8.0_x64_en-US.msi` (61.1 MB) | Certum OV Authenticode Signed + RFC 3161 Timestamp | [Download Windows MSI](https://lektpdf.com/download/windows-msi) |
| **Third-Party Proof Pack** | `Lekt_PAC_Acrobat_Verification_Pack.zip` | Real Before/After PDFs verified in PAC 2024, Acrobat & veraPDF | [Download Proof Pack](https://lektpdf.com/proof/Lekt_PAC_Acrobat_Verification_Pack.zip) |
| **Microsoft Store (Windows 10/11)** | `XP8BTZ1QSKF5HH` | Official Microsoft Store Win32 Listing | [View in Microsoft Store](https://apps.microsoft.com/store/detail/XP8BTZ1QSKF5HH) |
| **Checksums** | `SHA256SUMS.txt` | Published SHA-256 hashes for all v1.8.0 artifacts | [View SHA256SUMS.txt](https://lektpdf.com/download/SHA256SUMS.txt) |

### Verify Download Checksums (`v1.8.0`)

```text
df834ba5a480c09844b0af51ac79f0ba25de574bf53f4446248ab54d05ee6ead  Lekt_1.8.0_aarch64.dmg
5252f8dcd42368e63fb0521def918779666fbdd29d3aa2a3917c911d6af37c91  Lekt_1.8.0_aarch64.app.tar.gz
f927f08c9e7ce839eb377ba4d920be19b0fb5d81ef0a1fc4fb9d8d1a1d011b72  Lekt_1.8.0_x64-setup.exe
b5f8a2611b1f7ab9c94dace0a613886d32be2d8e47ca987113773b0c36fd7b4c  Lekt_1.8.0_x64_en-US.msi
```

---

## Feature & Tool Comparison

| Capability | Lekt v1.8.0 | PAC (2024/2026) | Adobe Acrobat Pro | PDFix Pro | CommonLook PDF |
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

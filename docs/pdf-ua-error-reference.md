# ISO 14289-1 (PDF/UA-1) & Matterhorn Quick Remediation Reference

This reference summarizes the 7 most frequent validation failures reported by **veraPDF 1.30.4** and **PAC (PDF Accessibility Checker)**, and how **Lekt** repairs them offline with 0px visual diff.

| Failure | ISO 14289-1 Clause | Remediation Type | Lekt Workflow |
| --- | --- | --- | --- |
| PDF/UA identifier missing (`pdfuaid:part`) | Clause 5 | Tier-1 Auto-Fix | Namespace-aware XMP update preserving `dc:creator`, `dc:rights`, and multilingual titles |
| `DisplayDocTitle` false/missing or `dc:title` missing | Clause 7.1 | Tier-1 Auto-Fix | Sets `/ViewerPreferences << /DisplayDocTitle true >>` + syncs XMP `dc:title` |
| Natural language (`/Lang`) missing | Clause 7.2 | Tier-1 Auto-Fix | Sets valid BCP-47 catalog `/Lang` tag (e.g., `en-US`) |
| Annotation `/Tabs /S` or `/Contents` missing | Clause 7.18 | Tier-1 Auto-Fix | Sets structure tab order `/Tabs /S` on tagged pages |
| Table `<TH>` missing `/Scope` | Clause 7.5 | Visual Grid Inspector | Toggle `TH`/`TD` and assign `Column` / `Row` / `Both` scope in Lekt's Tables tab |
| `<Figure>` missing `/Alt` text | Clause 7.3 | Batch Alt-Text Drawer | Write Alt-Text beside cropped PDFium previews or mark decorative graphics as `/Artifact` |
| Untagged / image-only scanned PDF (`Marked=false`) | Clause 7.1 | Offline OS OCR | Apple Vision / Windows WinRT OCR with 2-column reading-order detection and 0px visual diff |

Full illustrated guides:
- [How to Fix the 7 Most Common PAC & veraPDF PDF/UA Errors](https://lekt.jianlanzhiwei.com/verapdf-pac-error-fixes)
- [PAC Alternative for Mac (Native Apple Silicon)](https://lekt.jianlanzhiwei.com/pac-alternative-for-mac)
- [ADA Title II & FERPA Offline PDF Remediation Comparison](https://lekt.jianlanzhiwei.com/ada-title-ii-offline-pdf-remediation)

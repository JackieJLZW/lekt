# Changelog

All notable releases of **Lekt** (`com.jianlanzhiwei.lekt`) are documented here.

## [1.4.0] — 2026-11-25
### Added & Improved
- **Native Vector Auto-Tag (Zero Raster OCR) + Smart Hybrid Routing:** Untagged digital PDFs exported from Word, PowerPoint, LaTeX, or InDesign are now tagged directly in-stream (`VectorAutoTagger`) by wrapping existing vector text-showing operators, lists (`<L>` → `<LI>` → `<LBody>`), headings (`<H1>`–`<H3>`), figures, `<Link>` annotations, and `<Form>` widgets with automatic multi-page running header/footer `/Artifact` pagination detection—producing zero OCR typos and verified 0px visual diff at 150 DPI. Hybrid untagged PDFs automatically vector-tag digital pages and run offline OS OCR solely on scanned pages in one unified `/StructTreeRoot`.
- **Clause `7.1-3` (Matterhorn `01-005`) Untagged Content Canvas Highlighter & 1-Click `/Artifact`:** Extracts normalized bounding boxes for stray unmarked text, vector paths, and images on tagged PDFs, renders red dashed highlights directly on the PDFium canvas, and wraps unmarked content into `/Artifact BMC...EMC` per-page or document-wide (including mixed `BT...ET` text objects and nested Form XObjects) with 0px visual diff.
- **Damaged XRef / `%%EOF` Trailer Parser Recovery (`veraPDF` `#1657` / `#1658`):** PDFs with Acrobat hybrid XRef loops or trailing bytes after `%%EOF` that trip strict Greenfield parsing now open cleanly in Parser Recovery Mode (`01-PARSER`) and rebuild a clean standard cross-reference table via 1-Click Auto-Fix.
- **PDF/UA-2 (`ISO 14289-2:2024`) PDF 2.0 & Namespace Binding:** Automatically upgrades `%PDF-2.0` / Catalog `/Version /2.0` and binds standard structure elements to `http://iso.org/pdf2/ssn` when remediating against `PDF/UA-2`.
- **WCAG 2.2 AA Self-Accessibility (VPAT Dogfooding) & Native OS Lifecycle:** Added keyboard focus + `Enter`/`Space` activation across Screen Reader, Reading Order (`Alt+↑/↓` keyboard reorder), Alt-Text, and Forms cards; full ARIA `tablist`/`tabpanel` roving focus without arrow-key page-turn hijacking; ≥ 4.5:1 muted text contrast; `prefers-reduced-motion` & Windows High Contrast (`forced-colors`) support; macOS Dock `Reopen` after `Cmd+W`; and Windows single-instance CLI `.pdf` forwarding.

## [1.3.0] — 2026-11-24
### Added & Improved
- **Interactive Form Remediation (`<Form>` OBJR & `/TU` Tooltips):** New Forms panel + Tier-1 auto-fix nests widget annotations inside `<Form>` structure elements in original order and edits missing `/TU` accessible tooltips cleanly (preserving static print-only form fields).
- **Table `RowSpan`/`ColSpan` Editor & Unwrap Layout Tables:** Edit merged cell spans directly in the visual Tables inspector and unwrap decorative layout tables to `<Div>` without losing draft edits.
- **Full WCAG 2.2 Machine Validation:** Bundled `org.verapdf:wcag-validation:1.30.4` (`WCAG-2-2MACHINE.xml`) directly inside the offline JRE engine alongside PDF/UA-1 and PDF/UA-2.
- **Selective Hybrid-PDF Offline OCR:** Detects scanned pages inside mixed vector/scanned PDFs and runs Apple Vision / Windows WinRT offline OCR strictly on scanned pages so existing vector tables and forms stay intact.
- **Full-Text Search (`Cmd/Ctrl+F`) & Adaptive Zoom:** Added fast local search across multi-page PDFs with highlight overlays, forward/reverse navigation, and Fit Width / Fit Page zoom modes.
- **Clear Automated vs. Human-Review Batch Reports:** Batch UI, CSV, and HTML reports now clearly distinguish `MACHINE_PASS` / `NEEDS_FIX` / `ERROR` from required human review items and always record renamed output paths.
### Hardened
- **Enforced 0-Pixel Visual Diff Gate:** Single-file and batch exports enforce 0 changed pixels before committing outputs.
- **macOS & Windows File Association ("Open With"):** Fixed cold-start and hot-start PDF opening queues across macOS Launch Services and Windows Explorer.
- **Unsaved Draft Protection:** Preserves cross-panel drafts across revalidation and prompts before discarding pending edits or installing app updates.

## [1.2.2] — 2026-11-23
### Added & Improved
- **Pure Native Apple Silicon (`arm64`) Runtime:** Replaced the bundled macOS JRE with self-contained Eclipse Temurin 17 `aarch64`, eliminating Rosetta 2 translation and macOS 28 deprecation warnings while cutting packaged self-test cold-start + validation + OCR time down to ~2.2 seconds.
- **Mandatory Mach-O Architecture & Linkage Gates:** Release packaging now verifies 100% pure `arm64` Mach-O slices across every nested binary/dylib inside `Lekt.app` and zero external Homebrew/local dynamic library links.
- **Reading Order UI Polish:** Fixed horizontal text truncation (`min-width: 0`) for long table previews inside the Visual Reading Order panel.

## [1.2.1] — 2026-11-23
### Fixed & Hardened
- **Atomic Document Switching:** Failed PDF opens (e.g., encrypted/password-protected files) no longer overwrite the active document snapshot or export pointer.
- **Non-Overwriting Batch Exports:** Batch remediation protects every input file and automatically avoids colliding with previously audited `_PDFUA_Fixed.pdf` outputs.
- **Unique `snapshotId` Unsaved-Change Tracking:** Undoing and re-editing now reliably marks unsaved changes so modified documents cannot be closed without confirmation.
- **Namespace-Aware XMP Preservation:** Fixing `pdfuaid:part` and `dc:title` preserves existing author (`dc:creator`), copyright (`dc:rights`), and multilingual `rdf:Alt` titles.
- **Smooth ContinuousCanvas Zoom Queue:** Eliminated rapid zoom stutter on multi-page documents.
- **macOS 13+ Alignment:** Aligned `minimumSystemVersion` cleanly to macOS 13.0+.

## [1.2.0] — 2026-11-22
### Added
- **Multi-Page Continuous Viewer & Thumbnail Rail:** Smooth virtualized multi-page scrolling with quick page jump and **Show Issues Only** page filtering.
- **Document Outline / TOC Navigation:** Clickable PDF bookmark outline with instant page synchronization.
- **Per-Page Failure Badges:** Visual issue counts mapped to every failing page in the thumbnail sidebar.

## [1.1.0] — 2026-11-22
### Added
- **100% Offline OS OCR & 2-Column Layout Detection:** Native Apple Vision (macOS) and Windows WinRT OCR (Windows) with automatic full-width header, left/right column, and footer reading-order reconstruction.
- **Folder Batch Auditor & Remediator:** Audit up to 500 PDFs per folder with effort triage scoring, live progress/cancel, Batch Auto-Fix, Batch Offline OCR, and CSV/HTML compliance reports.
- **Inline Semantic Role Re-Tagging & Mark-as-Artifact:** Retag blocks (`P` ↔ `H1`–`H6`, `Caption`, `BlockQuote`, `Note`) and silence decorative headers/footers as `/Artifact` with 0px visual diff.

## [0.1.0] — 2026-11-21
### Initial Release
- Native macOS & Windows PDF/UA-1, PDF/UA-2 & WCAG 2.2 validator powered by **veraPDF 1.30.4** and **PDFium**.
- Linear Screen Reader Preview, interactive Reading Zone overlays, 1-Click Tier-1 Auto-Fix, Visual Reading Order, Table `TH`/`Scope` Inspector, Batch Figure Alt-Text editor, and Ed25519 air-gapped offline licensing.

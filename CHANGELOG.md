# Changelog

All notable releases of **Lekt** (`com.jianlanzhiwei.lekt`) are documented here.

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

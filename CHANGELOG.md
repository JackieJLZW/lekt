# Changelog

All notable releases of **Lekt** (`com.jianlanzhiwei.lekt`) are documented here.

## [1.8.0] — 2026-11-28
### Added & Improved
- **Batch Auditor Row Selection, Search & By-Clause Filter Bar:** Select individual files via row checkboxes for targeted **Batch Auto-Fix** or **Batch Vector Auto-Tag / Offline OCR**, filter instant matches by filename, title, or clause, and click aggregated **By Clause** chips (`[06-002]`, `[15-003]`, `[13-004]`, etc.) to isolate affected documents across large department folders.
- **Keep-Original-Name Separate-Folder Batch Exports:** Added a `"Keep Original Name (Separate Folder)"` batch naming mode alongside `_PDFUA_Fixed.pdf` / `_OCR_PDFUA.pdf` suffixes—enforcing strict separate-folder validation (never touching source folders or nested source subfolders, with `O_CREAT | O_EXCL` collision protection) so institutional web archives keep stable filenames across multi-pass remediation.
- **Structured `JSON` Compliance Report Export (`lekt-compliance-audit-v1`):** Export machine-readable `JSON` compliance reports alongside `CSV` and printable `HTML` in both single-document and 500-PDF folder batch workflows for CI/CD pipelines and institutional ADA Title II / EU EAA records.
- **Transparent `>500`-PDF Discovery Alert & Stale-Profile Re-Scan Banner:** Folders containing more than 500 PDFs now report total discovered files (`totalDiscovered` + `truncated` alert) instead of truncating silently, and switching the top validation profile (`PDF/UA-1` ↔ `PDF/UA-2` ↔ `WCAG 2.2`) displays an immediate 1-click **Re-scan** notice on open batch reports.
- **Page-Level Batch OCR Progress, Mid-PDF Cancel & Multi-Pass Action History:** Long multi-page scanned PDFs in Batch OCR now emit per-page progress (`file.pdf (p.k/N)`) and stop immediately at the current page boundary when cancelled, while multi-pass runs (**Batch OCR / Vector Auto-Tag** → **Batch Auto-Fix**) preserve full cumulative `actionsApplied` history.
### Fixed & Hardened
- **PDF/UA-2 Table Span & Forbidden `ToUnicode` Matterhorn Mapping:** Mapped ISO 14289-2 `8.2.5.26-4` (`RowSpan`/`ColSpan` grid mismatch) accurately to Matterhorn `15-002` instead of `15-003` (`TH /Scope`), and mapped `7.21.7-2` / `8.4.5.5.1-2` (`U+0000` / `U+FEFF` / `U+FFFE` forbidden `ToUnicode` codepoints) to `10-001` (`source_required`) with plain-English source re-export guidance.
- **Complex Table `/Headers` Cell ID Editor & Post-Fix Batch Triage Refresh:** Added visual `/Headers` ID linking (`headerCellIds` + `/IDTree` synchronization) in the 2D logical **Tables** grid inspector for irregular multi-level header tables, and refreshed post-remediation human-review counts (`missingAltCount`, `unresolvedTableCount`, `missingFormTipCount`) immediately after Batch Auto-Fix / OCR.

## [1.7.1] — 2026-11-27
### Added & Improved
- **Guided Human Confirmation for Free Watermarked Proof PDF (`preflightWatermarkedProof`):** When a PDF contains complex tables or figures requiring human semantic confirmation (`TH /Scope` or `Figure /Alt`), Lekt pre-crops figure previews with offline OS OCR suggestions and walks users through confirming them in one guided modal so exported Proof PDFs reach `0` machine errors in **PAC 2024**, **Adobe Acrobat Full Check**, and **veraPDF**.

## [1.7.0] — 2026-11-26
### Added & Improved
- **Free Watermarked Proof PDF Export (`exportProofPdf`):** Free Checker users can now run Lekt's full offline automated remediation (**Native Vector Auto-Tag**, **Offline OS OCR**, and **1-Click Safe Auto-Fix**) on any PDF and export a real remediated Proof PDF (`Cmd/Ctrl+Shift+P`). Every verification curve is rendered as pure cubic-Bezier glyph outlines (`BlendMode.MULTIPLY`, zero text operators, zero font dependencies) strictly wrapped inside ISO 14289 `/Artifact BMC...EMC`—allowing independent `0`-error verification in **PAC 2024**, **Adobe Acrobat Pro Accessibility Full Check**, **veraPDF**, and **NVDA/JAWS** with zero screen-reader noise and zero WCAG 2.2 contrast regressions before purchasing.
- **5-Layer Anti-Tamper Proof Architecture:** Flattens each Proof PDF page into a single Flate `COSStream`, interleaves `/Artifact` shards across tagged elements, emits 150+ disjoint per-glyph subpaths per page, stamps synchronized XMP `dc:title`, and entangles exact IEEE-754 dyadic `CTM` coordinate shifts so automated `/Artifact`-stripping scripts scramble page layout while unmodified files render at `0.0pt` drift.
- **macOS App Sandbox Security-Scoped Bookmarks & Cold-Start File Open:** Persists `NSURLBookmarkCreationWithSecurityScope` (`com.apple.security.files.bookmarks.app-scope`) tokens across app restarts for Recent Files and hardens cold-start Finder `"Open With"` lifecycle handling.

## [1.6.0] — 2026-11-26
### Added & Improved
- **Deep Nested Reading Order & Slot-Preserving Reorder:** Removed the legacy `depth <= 3` cap in `PdfInspector` and `ReadingOrderPanel`, surfacing deeply nested block structures (`Part › Sect › Div › P`) with container breadcrumb badges while keeping unmentioned inline siblings (`<Span>`, `<Link>`, `<Annot>`) pinned at their exact original `/K` slot indices.
- **Multi-Select Batch Role Switching & Group Move:** Select multiple sibling blocks to batch-retag (`P` ↔ `H1`–`H6`, `Caption`, `BlockQuote`, `Note`/`FENote`) or move block groups together—including safe slot-bounded reordering when filtered to a single page (`Page N`) and automatic PDF/UA-2 (`http://iso.org/pdf2/ssn`) `<Note>` → `<FENote>` + nested `<P>` flattening.
- **Lossless `<L>` List & Cross-Page `<P>` Merge + `<Div>` Unwrap:** Merge fragmented single-item `<L>` lists into one semantic `<L>` or combine split multi-line/cross-page `<P>` paragraphs (preserving inherited `/Pg` page bindings), and unwrap redundant `<Div>`/`<NonStruct>` wrappers cleanly (wrapping bare MCID runs into `<P>` under ISO 32005 `<Sect>`/`<Document>` containers).
- **Named Unlimited Undo/Redo & Canvas-to-Panel Auto-Scroll:** Every snapshot records a human-readable action label in the Undo/Redo toolbar tooltips, and clicking any canvas Reading Zone scrolls both `Screen Reader Preview` and `Reading Order` directly to the matching card.
### Hardened
- **Strict 0px Diff & Process-Global PDFium Serialization:** Extended the 150 DPI 0-pixel visual diff gate to single/batch `/Artifact` conversion and layout-table unwrap, serialized PDFium library lifecycle across concurrent threads, and verified packaged engine daemon version parity (`ping.version === 1.6.0`) across macOS, Windows, and Mac App Store builds.

## [1.5.0] — 2026-11-26
### Added & Improved
- **Free Ephemeral 1-Click Fix Preview (`previewAutofix`):** Free Checker users can now test Lekt's full remediation engine (Native Vector Auto-Tag + Tier-1 Safe Auto-Fix + 150 DPI PDFium 0px visual diff verification) on any digital PDF inside an isolated ephemeral buffer—verifying exact post-fix veraPDF rule/check counts without touching the active document.
- **Canonical Domain Migration (`lektpdf.com`) & Dual Updater Failover:** Official website, Self-Service Seat Portal, and installer downloads now live at `https://lektpdf.com` (`support@lektpdf.com`) with seamless backwards-compatible updater/activation pass-through on `lekt.jianlanzhiwei.com`.
- **Mac App Store (`--features mas`) Native StoreKit 2 Edition:** Added an isolated App Sandbox + StoreKit 2 build profile (`npm run release:mas`) with zero external checkout/license/updater dependencies.

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

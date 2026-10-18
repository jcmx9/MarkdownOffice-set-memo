# Changelog

All notable changes to this project will be documented in this file.
Format based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [26.10.4] - 2026-10-18

### Changed
- **Breaking:** the front-matter key `client:` is renamed to `toptitle:` (Typst input `toptitle`, needs Markdown Office ≥ 26.10.0); rename it in existing notes. The text small above the title, in the footer and in the PDF keywords now comes from `toptitle:`

## [26.10.3] - 2026-10-18

### Changed
- Table rows slightly tighter (cell padding 7pt → 5pt)

## [26.10.2] - 2026-10-18

### Changed
- External links (`http://`, `https://`, `mailto:`) are marked in the PDF: link text in the normal text colour with a fine underline and a small raised ↗ inside the link; internal links stay unchanged, the running header and the table of contents show such links as plain text

## [26.10.1] - 2026-10-18

### Changed
- `memo.header.md` is a compact template: one line per key with a short comment; the full description lives in the Markdown Office README

## [26.10.0] - 2026-10-17

### Added
- Initial release: the rf-doc layout of real-fast-document 26.10.21 as the Markdown Office set `memo`

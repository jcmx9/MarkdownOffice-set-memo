# Markdown Office – Set `memo`

**Version:** 26.10.8 · [Deutsch](README.md)

> The default template set of Markdown Office: the former rf-doc layout of real-fast-document.

## Description

A set consists of a Typst template, a description of the editor preview (stylesheet and title block) and a frontmatter template. `memo` is the default set: title block, table of contents, header and footer, alert boxes, task lists, tables, formulas and diagrams. External links (`http://`, `https://`, `mailto:`) appear in the text colour, finely underlined and followed by a small ↗, so they remain recognisable as links on paper; internal links (`#anchor`) stay plain. Markdown Office bundles this set and uses it when a note does not specify `template:`.

## Files

| File | Purpose |
|------|---------|
| `memo.typ` | Typst template; reads `sys.inputs.mdo` (pipeline root) and `sys.inputs.version` |
| `memo.css` | Editor preview: memo's values (font, sizes, measure, spacing) as `--mdo-*` variables; no effect on the PDF |
| `memo.preview.yaml` | Editor preview: title block (toptitle, title, subtitle, "date · author" only with `author`) |
| `memo.header.md` | Frontmatter template with all keys and default values (`template: memo`) |

## Frontmatter keys

All keys with default values and a short description each are in [`memo.header.md`](memo.header.md); the [Markdown Office README](https://github.com/jcmx9/MarkdownOffice/blob/main/README.en.md#frontmatter) describes them in full.

The file [`memo.schema.yaml`](memo.schema.yaml) describes the set's keys (types, allowed values, limits). Markdown Office uses it to check a note via „YAML prüfen …“ (Edit menu) and `markdown-office validate`; extra keys remain allowed.

`lang:` may carry a region (`de-AT`, `en-GB`): labels and date follow the language (`de…` German, otherwise English), and the set passes the region to Typst separately.

## Editor preview

With the Markdown Office version that sets paragraphs like Typst, the preview breaks lines like the PDF: hyphenation with Typst's German and English patterns (language from `lang:`), the best breaks for the whole paragraph in justified text, and word spaces shrunk or stretched per line. `memo.css` states the values from `memo.typ` for it (section 8.5 of Markdown Office's TEMPLATES.md):

| Value | Source |
|-------|--------|
| `--mdo-align: justify` | `#set par(justify: true)` |
| `--mdo-hyphenate` (default `auto`: justified text hyphenates) | `#set text(hyphenate: true)` |
| `--mdo-runt-cost: 200%` | `#set par(costs: (runt: 200%))` |
| `--mdo-hyphenation-cost` (default `100%`) | not set, Typst's default |
| `--mdo-word-spacing: -0.045em` | approximation for the paragraph with the cursor and the fallback; Typst shrinks word spaces in justified text |
| `--mdo-numeric: oldstyle-nums`, `--mdo-table-numeric: lining-nums tabular-nums` | `#set text(number-type: "old-style")`; tables: `number-type: "lining"`, `number-width: "tabular"` |
| `--mdo-body-weight: 380`, `--mdo-bold-weight: 560`, `--mdo-measure: 145mm` | `#set text(weight: 380)` and `strong` +180; page 210 mm − 35 mm − 30 mm |

What still differs from the PDF: a Markdown line wrapped in the source is its own paragraph (write a paragraph on one line), there is no hanging punctuation, the paragraph with the cursor keeps the browser's wrapping, and code and tables stay raw. Page breaks, header and footer exist only in the PDF.

## Versioning

[CalVer](https://calver.org/) in the format `YY.M.MICRO`.

## Changelog

See [CHANGELOG.md](CHANGELOG.md).

## License

MIT – see [LICENSE](LICENSE).

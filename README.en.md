# Markdown Office – Set `memo`

**Version:** 26.10.2 · [Deutsch](README.md)

> The default template set of Markdown Office: the former rf-doc layout of real-fast-document.

## Description

A set consists of a Typst template, an editor stylesheet and a frontmatter template. `memo` is the default set: title block, table of contents, header and footer, alert boxes, task lists, tables, formulas and diagrams. External links (`http://`, `https://`, `mailto:`) appear in the text colour, finely underlined and followed by a small ↗, so they remain recognisable as links on paper; internal links (`#anchor`) stay plain. Markdown Office bundles this set and uses it when a note does not specify `template:`.

## Files

| File | Purpose |
|------|---------|
| `memo.typ` | Typst template; reads `sys.inputs.mdo` (pipeline root) and `sys.inputs.version` |
| `memo.css` | Editor stylesheet (comments only; overrides via `--mdo-*` and `.mdo-*`) |
| `memo.header.md` | Frontmatter template with all keys and default values (`template: memo`) |

## Frontmatter keys

All keys with default values and a short description each are in [`memo.header.md`](memo.header.md); the [Markdown Office README](https://github.com/jcmx9/MarkdownOffice/blob/main/README.en.md#frontmatter) describes them in full.

## Versioning

[CalVer](https://calver.org/) in the format `YY.M.MICRO`.

## Changelog

See [CHANGELOG.md](CHANGELOG.md).

## License

MIT – see [LICENSE](LICENSE).

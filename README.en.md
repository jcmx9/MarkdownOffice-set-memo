# Markdown Office – Set `memo`

**Version:** 26.10.0 · [Deutsch](README.md)

> The default template set of Markdown Office: the former rf-doc layout of real-fast-document.

## Description

A set consists of a Typst template, an editor stylesheet and a frontmatter template. `memo` is the default set: title block, table of contents, header and footer, alert boxes, task lists, tables, formulas and diagrams. Markdown Office bundles this set and uses it when a note does not specify `template:`.

## Files

| File | Purpose |
|------|---------|
| `memo.typ` | Typst template; reads `sys.inputs.mdo` (pipeline root) and `sys.inputs.version` |
| `memo.css` | Editor stylesheet (comments only; overrides via `--mdo-*` and `.mdo-*`) |
| `memo.header.md` | Frontmatter template with all keys and default values (`template: memo`) |

## Frontmatter keys

All keys with default values and descriptions are in [`memo.header.md`](memo.header.md).

## Versioning

[CalVer](https://calver.org/) in the format `YY.M.MICRO`.

## Changelog

See [CHANGELOG.md](CHANGELOG.md).

## License

MIT – see [LICENSE](LICENSE).

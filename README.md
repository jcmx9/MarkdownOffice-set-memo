# Markdown Office – Set `memo`

**Version:** 26.10.0 · [English](README.en.md)

> Das Standard-Vorlagen-Set von Markdown Office: das frühere rf-doc-Layout von real-fast-document.

## Beschreibung

Ein Set besteht aus einer Typst-Vorlage, einem Editor-Stylesheet und einer Frontmatter-Vorlage. `memo` ist das Standard-Set: Titelblock, Inhaltsverzeichnis, Kopf- und Fußzeile, Hinweisboxen, Aufgabenlisten, Tabellen, Formeln und Diagramme. Markdown Office bringt dieses Set mit und verwendet es, wenn eine Notiz kein `template:` angibt.

## Dateien

| Datei | Zweck |
|-------|-------|
| `memo.typ` | Typst-Vorlage; liest `sys.inputs.mdo` (Wurzel der Pipeline) und `sys.inputs.version` |
| `memo.css` | Editor-Stylesheet (nur Kommentare; Overrides über `--mdo-*` und `.mdo-*`) |
| `memo.header.md` | Frontmatter-Vorlage mit allen Schlüsseln und Standardwerten (`template: memo`) |

## Frontmatter-Schlüssel

Alle Schlüssel mit Standardwerten und Beschreibung stehen in [`memo.header.md`](memo.header.md).

## Versionierung

[CalVer](https://calver.org/) im Format `YY.M.MICRO`.

## Changelog

Siehe [CHANGELOG.md](CHANGELOG.md).

## Lizenz

MIT – siehe [LICENSE](LICENSE).

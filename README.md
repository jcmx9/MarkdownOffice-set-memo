# Markdown Office – Set `memo`

**Version:** 26.10.4 · [English](README.en.md)

> Das Standard-Vorlagen-Set von Markdown Office: das frühere rf-doc-Layout von real-fast-document.

## Beschreibung

Ein Set besteht aus einer Typst-Vorlage, einem Editor-Stylesheet und einer Frontmatter-Vorlage. `memo` ist das Standard-Set: Titelblock, Inhaltsverzeichnis, Kopf- und Fußzeile, Hinweisboxen, Aufgabenlisten, Tabellen, Formeln und Diagramme. Externe Links (`http://`, `https://`, `mailto:`) erscheinen in der Textfarbe fein unterstrichen und mit einem kleinen ↗ dahinter, damit sie auch im Ausdruck als Verweis erkennbar sind; interne Links (`#anker`) bleiben schlicht. Markdown Office bringt dieses Set mit und verwendet es, wenn eine Notiz kein `template:` angibt.

## Dateien

| Datei | Zweck |
|-------|-------|
| `memo.typ` | Typst-Vorlage; liest `sys.inputs.mdo` (Wurzel der Pipeline) und `sys.inputs.version` |
| `memo.css` | Editor-Stylesheet (nur Kommentare; Overrides über `--mdo-*` und `.mdo-*`) |
| `memo.header.md` | Frontmatter-Vorlage mit allen Schlüsseln und Standardwerten (`template: memo`) |

## Frontmatter-Schlüssel

Alle Schlüssel mit Standardwerten und je einer Kurzbeschreibung stehen in [`memo.header.md`](memo.header.md); ausführlich beschreibt sie das [README von Markdown Office](https://github.com/jcmx9/MarkdownOffice#frontmatter).

Die Datei [`memo.schema.yaml`](memo.schema.yaml) beschreibt die Schlüssel des Sets (Typen, erlaubte Werte, Grenzen). Markdown Office prüft damit eine Notiz über „YAML prüfen …“ (Bearbeiten-Menü) und `markdown-office validate`; zusätzliche Schlüssel bleiben erlaubt.

`lang:` darf eine Region tragen (`de-AT`, `en-GB`): Beschriftungen und Datum richten sich nach der Sprache (`de…` deutsch, sonst englisch), die Region gibt das Set getrennt an Typst weiter.

## Versionierung

[CalVer](https://calver.org/) im Format `YY.M.MICRO`.

## Changelog

Siehe [CHANGELOG.md](CHANGELOG.md).

## Lizenz

MIT – siehe [LICENSE](LICENSE).

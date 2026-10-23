# Markdown Office – Set `memo`

**Version:** 26.10.8 · [English](README.en.md)

> Das Standard-Vorlagen-Set von Markdown Office: das frühere rf-doc-Layout von real-fast-document.

## Beschreibung

Ein Set besteht aus einer Typst-Vorlage, einer Beschreibung der Editor-Vorschau (Stylesheet und Titelblock) und einer Frontmatter-Vorlage. `memo` ist das Standard-Set: Titelblock, Inhaltsverzeichnis, Kopf- und Fußzeile, Hinweisboxen, Aufgabenlisten, Tabellen, Formeln und Diagramme. Externe Links (`http://`, `https://`, `mailto:`) erscheinen in der Textfarbe fein unterstrichen und mit einem kleinen ↗ dahinter, damit sie auch im Ausdruck als Verweis erkennbar sind; interne Links (`#anker`) bleiben schlicht. Markdown Office bringt dieses Set mit und verwendet es, wenn eine Notiz kein `template:` angibt.

## Dateien

| Datei | Zweck |
|-------|-------|
| `memo.typ` | Typst-Vorlage; liest `sys.inputs.mdo` (Wurzel der Pipeline) und `sys.inputs.version` |
| `memo.css` | Editor-Vorschau: die Werte von memo (Schrift, Größen, Satzbreite, Abstände) als `--mdo-*`-Variablen; keine Wirkung auf das PDF |
| `memo.preview.yaml` | Editor-Vorschau: Titelblock (Obertitel, Titel, Untertitel, „Datum · Autor“ nur mit `author`) |
| `memo.header.md` | Frontmatter-Vorlage mit allen Schlüsseln und Standardwerten (`template: memo`) |

## Frontmatter-Schlüssel

Alle Schlüssel mit Standardwerten und je einer Kurzbeschreibung stehen in [`memo.header.md`](memo.header.md); ausführlich beschreibt sie das [README von Markdown Office](https://github.com/jcmx9/MarkdownOffice#frontmatter).

Die Datei [`memo.schema.yaml`](memo.schema.yaml) beschreibt die Schlüssel des Sets (Typen, erlaubte Werte, Grenzen). Markdown Office prüft damit eine Notiz über „YAML prüfen …“ (Bearbeiten-Menü) und `markdown-office validate`; zusätzliche Schlüssel bleiben erlaubt.

`lang:` darf eine Region tragen (`de-AT`, `en-GB`): Beschriftungen und Datum richten sich nach der Sprache (`de…` deutsch, sonst englisch), die Region gibt das Set getrennt an Typst weiter.

## Editor-Vorschau

Ab der Markdown-Office-Version mit Absatzsatz wie Typst bricht die Vorschau Zeilen wie das PDF: Silbentrennung mit Typsts deutschen und englischen Mustern (Sprache aus `lang:`), beste Umbrüche für den ganzen Absatz im Blocksatz und gestauchte oder gedehnte Wortzwischenräume je Zeile. `memo.css` nennt dafür die Werte aus `memo.typ` (Abschnitt 8.5 der TEMPLATES.md von Markdown Office):

| Wert | Quelle |
|------|--------|
| `--mdo-align: justify` | `#set par(justify: true)` |
| `--mdo-hyphenate` (Standard `auto`: Blocksatz trennt) | `#set text(hyphenate: true)` |
| `--mdo-runt-cost: 200%` | `#set par(costs: (runt: 200%))` |
| `--mdo-hyphenation-cost` (Standard `100%`) | nicht gesetzt, Typst-Standard |
| `--mdo-word-spacing: -0.045em` | Näherung für den Absatz mit dem Cursor und den Ausweichfall; Typst staucht Wortzwischenräume im Blocksatz |
| `--mdo-numeric: oldstyle-nums`, `--mdo-table-numeric: lining-nums tabular-nums` | `#set text(number-type: "old-style")`; Tabellen: `number-type: "lining"`, `number-width: "tabular"` |
| `--mdo-body-weight: 380`, `--mdo-bold-weight: 560`, `--mdo-measure: 145mm` | `#set text(weight: 380)` und `strong` +180; Seite 210 mm − 35 mm − 30 mm |
| `mermaid:` in `memo.preview.yaml` | Theme, Layout, `max-height: 12cm` und `font-weight: 500` der Mermaid-Regel (`memo.typ`, Zeilen 622–649); die Vorschau zeichnet Diagramme mit demselben mmdr-Plugin wie das PDF |

Mermaid-Blöcke auf oberster Ebene zeichnet die Vorschau als Diagramm, innerhalb von Listen und Zitaten, im Block mit dem Cursor und in der Code-Ansicht bleibt der Quelltext (braucht Markdown Office mit Diagrammen in der Vorschau). Was vom PDF abweicht: Eine im Quelltext umbrochene Markdown-Zeile ist ein eigener Absatz (ein Absatz gehört in eine Zeile), hängende Satzzeichen gibt es nicht, der Absatz mit dem Cursor behält den Umbruch des Browsers, und Code und Tabellen bleiben roh. Seitenumbrüche, Kopf- und Fußzeile gibt es nur im PDF.

## Versionierung

[CalVer](https://calver.org/) im Format `YY.M.MICRO`.

## Changelog

Siehe [CHANGELOG.md](CHANGELOG.md).

## Lizenz

MIT – siehe [LICENSE](LICENSE).

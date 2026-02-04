# PRD: Tractatus Relaunch

## Überblick

Relaunch der Website [tractatus.baneland.de](https://tractatus.baneland.de/) – eine digitale Ausgabe von Ludwig Wittgensteins *Tractatus logico-philosophicus*. Migration von Hugo zu Astro mit modernem Design und verbesserter Navigation.

## Ausgangslage

- **Aktuell:** Hugo-basierte statische Seite mit eigenem Theme
- **Content:** 526 Items auf Deutsch + 527 auf Englisch (Markdown-Dateien)
- **Struktur:** 7 Hauptsätze, hierarchische Nummerierung (z.B. 5 → 5.4 → 5.47 → 5.473 → 5.4732 → 5.47321), max. 6 Ebenen tief
- **Probleme:** Optik nicht ansprechend, kaum Navigation zwischen Items, keine sichtbare Hierarchie

## Verteilung der Items

| Hauptsatz | Items | Inhalt |
|-----------|-------|--------|
| 1 | 7 | Die Welt |
| 2 | 79 | Sachverhalte und Tatsachen |
| 3 | 74 | Das logische Bild |
| 4 | 109 | Der Satz |
| 5 | 151 | Wahrheitsfunktionen |
| 6 | 105 | Die allgemeine Form |
| 7 | 1 | Wovon man nicht sprechen kann... |

## Ziele

1. **Moderne, typografisch ansprechende Darstellung** – der Text verdient ein würdiges Erscheinungsbild
2. **Hierarchische Navigation** – die Baumstruktur des Tractatus sichtbar und navigierbar machen
3. **Zweisprachig** (Deutsch/Englisch) mit einfachem Sprachwechsel
4. **Responsiv** – funktioniert auf Desktop, Tablet und Mobilgeräten
5. **Statisch & schnell** – kein JavaScript nötig für die Kernfunktionalität

## Technologie

- **Framework:** Astro (Static Site Generation)
- **Styling:** Tailwind CSS
- **Content:** Astro Content Collections (Migration der bestehenden Markdown-Dateien)
- **Hosting:** Bestehendes Setup (tractatus.baneland.de)

## Features (V1)

### F1: Startseite / Übersicht
Die 7 Hauptsätze als Einstiegspunkte, jeweils mit Nummer und Text. Minimalistisches, typografisch klares Design. Kurze Einleitung zum Werk.

### F2: Einzelseite pro Item
Jedes Item (z.B. 2.0121) bekommt eine eigene Seite mit:
- Nummer + Text des Items
- **Vor/Zurück-Navigation** (lineare Reihenfolge)
- **Parent-Link** ("Zurück zu 2.012")
- **Kinder-Liste** (alle direkten Unter-Items, z.B. bei 2.012 → 2.0121, 2.0122, 2.0123, 2.0124)

### F3: Hierarchische Sidebar/Baumnavigation
- Aufklappbarer Baum der Tractatus-Struktur
- Aktuelles Item hervorgehoben
- Kontext sichtbar (Geschwister, Eltern, Kinder)
- Auf Mobilgeräten ein- und ausklappbar

### F4: Sprachwechsel Deutsch/Englisch
- Toggle/Link auf jeder Seite zum selben Item in der anderen Sprache
- URL-Struktur: `/de/2.0121/` bzw. `/en/2.0121/`

### F5: Content-Migration
- Bestehende Markdown-Dateien aus `content/de/` und `content/en/` übernehmen
- Frontmatter von TOML (Hugo `+++`) zu YAML (Astro `---`) konvertieren
- Dateinamen-Konvention: Bindestriche durch Punkte ersetzen für URLs
- HTML im Markdown beibehalten (z.B. `<em class="germph">`, `<span class="mathmode">`)

### F6: SEO & Meta
- Sinnvolle Titel: "2.0121 – Tractatus logico-philosophicus"
- Meta-Description aus dem Item-Text (gekürzt)
- Open Graph Tags
- Sitemap

## Features (V2 – optional)

### F7: Volltextsuche
Client-seitige Suche über alle Items (z.B. mit Pagefind oder Fuse.js).

### F8: Parallele Ansicht DE/EN
Beide Sprachen nebeneinander für dasselbe Item.

### F9: Permalink & Teilen
Direkte Links zu einzelnen Items, Share-Buttons.

### F10: Dunkelmodus
Optionaler Dark Mode für angenehmes Lesen.

## Design-Prinzipien

- **Typografie zuerst:** Großzügige Zeilenabstände, Serifenschrift für den Text, klare Hierarchie durch Schriftgrößen
- **Ruhiges Layout:** Viel Weißraum, keine Ablenkung – der Text steht im Mittelpunkt
- **Dezente Farben:** Schwarz/Weiß/Grau als Basis, ein Akzentton für Navigation und Links
- **Philosophischer Charakter:** Das Design soll die Klarheit und Strenge des Werks widerspiegeln

## Offene Fragen

1. **Domain:** Bleibt es bei tractatus.baneland.de oder eine neue Domain?

Bleibt bei dieser Domain


2. **Impressum/Datenschutz:** Eigenständig oder Verweis auf jakoubek.net?

Was empfiehlst du? Der Einfachheit halber würde ich sagen: Verweis auf Jakoubek.net, öffnen in neuem Tab. Ist ja keine kommerzielle Website. Im Footer auf jeden Fall ein Verweis auf jakoubek.net


3. **Analytics:** Plausible (wie aktuell in Hugo-Theme) beibehalten?

Herausnehmen. Setzen wir analog zu prospektdevice.de erst einmal nur rein mit mit Webserver-Log um.


4. **Schrift:** Welche Serifenschrift? (Vorschläge: Literata, Source Serif, Crimson Pro)

Literata oder Crimson Pro

Wichtig: die "einfache" Einbindung von Schriftarten über Google Fonts ist datenschutzrechtlich bedenklich!


Frage:

Im Originaltext gibt es einige HTML-Einschübe mit Formeln oder generierten Grafiken. Lassen sich diese so verwenden? Auf der bisherigen Seite sind die glaube ich nicht ordentlich angezeigt worden.



# Wort-Institut · Website

Statische Website für Dr. Werner Irro, gebaut mit [Eleventy](https://www.11ty.dev/), gehostet auf GitHub Pages, Inhalte gepflegt über [Pages CMS](https://pagescms.org/).

## Wie alles zusammenhängt

```
Pages CMS (Bearbeiten im Browser)
        │  speichert = Git-Commit
        ▼
GitHub Repository (alle Inhalte als Markdown in content/)
        │  Push löst GitHub Action aus
        ▼
Eleventy baut die Website (.github/workflows/deploy.yml)
        │
        ▼
GitHub Pages (live, mit eigener Domain und HTTPS)
```

Es gibt keine Datenbank und keinen Server. Alle Inhalte liegen als Textdateien im Ordner `content/`, Bilder im Ordner `media/`.

## Inhalte pflegen (für die Redaktion)

1. [app.pagescms.org](https://app.pagescms.org/) öffnen und anmelden.
2. Links die gewünschte Seite auswählen (Startseite, Lektorat, Autor, Vita, Kontakt …).
3. Text ändern, ggf. Bilder per Drag & Drop hochladen, **Speichern** klicken.
4. Nach ein bis zwei Minuten ist die Änderung auf der Website sichtbar.

Notfall-Alternative ohne Pages CMS: Datei im Ordner `content/` direkt auf github.com öffnen, Stift-Symbol anklicken, ändern, "Commit changes".

## Lokal entwickeln (optional, nur für Technik-Änderungen)

Voraussetzung: Node.js (Version 20 oder neuer).

```
npm install
npm start        # Vorschau unter http://localhost:8080
npm run build    # erzeugt die fertige Website im Ordner _site/
```

## Projektstruktur

```
content/           Alle Seiteninhalte (Markdown mit Front Matter)
media/             Hochgeladene Bilder (Buchcover, Porträt)
_includes/         HTML-Vorlagen (base.njk + Seitenlayouts)
assets/style.css   Das gesamte Design
.pages.yml         Konfiguration der Bearbeitungsoberfläche (Pages CMS)
.github/workflows/ Automatische Veröffentlichung
eleventy.config.js Eleventy-Konfiguration
```

## Wartung

- Einzige Abhängigkeit ist `@11ty/eleventy`. Ein Update ist selten nötig; wenn doch: `npm update` und testen.
- Die rechtlichen Hinweise auf der Seite **Impressum & Datenschutz** aktuell halten, z.B. bei geänderten Kontaktdaten oder neu eingebundenen Diensten.

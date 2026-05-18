# gettheflo-brand

GettheFlo-Brand als geteilte Quelle für alle visuellen + sprachlichen Outputs der Marke.

**Single Source of Truth** für:

- Visuelle Identität — Logo, Farben, Typografie, Komponenten-Stil (`tokens/`, `assets/`)
- Voice & Tone — wie GettheFlo schreibt (Du-Form, Vokabular, Beispiele) (`docs/voice.md`)
- Anwendungs-Mockups — Website-Hero, Mail-Template, Cockpit-Sektion (`assets/mockups/`)
- Komponenten-Stil — Buttons, Cards, Pillen, Inputs, Tabs (`docs/components.md`)

## Konsumenten

- **Cockpit** `admin.gettheflo.de` (Repo `attendorn/admin-gettheflo`): als Submodule `vendor/gettheflo-brand/`. Tailwind-Theme wird via Codegen aus `tokens/*.json` erzeugt.
- **Marketing-Website** `gettheflo.de` (eigenes Repo, kommt): gleiches Submodule-Pattern.
- **Mail-Templates** (in Cockpit): Tokens für Hex-Farben + Schrift-Stack im Render-Code.
- **Zukünftige Apps** (Teilnehmer-Magic-Link `mein.gettheflo.de`, etc.): Submodule + Codegen.

## Read-Only-Vertrag für Konsumenten

Edits passieren in `~/gettheflo-brand/` (Mac, Florians Filesystem). Push hierhin = SSOT aktualisiert. Konsumenten ziehen den neuen Stand via `git submodule update --remote` oder Codegen-Refresh.

## Architektur

```
gettheflo-brand/
├── README.md
├── tokens/
│   ├── colors.json       — Brand-Farbpalette (Bone, Charcoal, Cognac, ...)
│   └── typography.json   — Schrift-Familie + Skala (Geist Sans + Mono)
├── docs/
│   ├── voice.md          — Tonalität, Vokabular, Anrede-Regeln
│   ├── components.md     — Buttons, Cards, Pillen, Inputs, Tabs
│   └── application.md    — Wie wird das Brand auf neue Flächen übertragen
└── assets/
    ├── logo/
    │   ├── orbit-original.svg    — historisches Aurora-Favicon (Referenz)
    │   ├── orbit-cognac.svg      — finales Orbit-Symbol im neuen Brand
    │   └── combo-mark.svg        — Orbit + Geist-Sans-Wort-Mark
    └── mockups/
        ├── website-hero.html     — Marketing-Hero im neuen Brand
        ├── mail-template.html    — Bestätigungs-Mail-Skizze
        └── cockpit-sektion.html  — Person-Detail-Sektion (Cockpit-Referenz)
```

## Brand-Charakter (Kurzform)

**Stimmung:** Soft-Mac warm-persönlich. Helle neutrale Flächen, weiche Schatten, runde Ecken. Cockpit + Website + Mails fühlen sich wie persönliches Werkzeug an, nicht wie Admin-Behörde.

**Palette:** Bone-Off-White als Hauptfläche, Warm-Charcoal-Ink als Text + harte Akzente, **Cognac** (`#A8632A`-Familie) als Akzent statt buntiger Aurora-Farben.

**Typografie:** Geist throughout — Geist Sans für alles UI/Body/Display, Geist Mono für Zahlen + Daten + Mikrokopie. Keine Display-Serifs, keine Schnörkel.

**Logo:** Orbit-Symbol (aus gettheflo.de Favicon, Form unverändert) im neuen Cognac-Akzent + Geist-Sans-Wort-Mark zu Combo-Mark zusammengesetzt.

## Lizenz

Public-Repo aus pragmatischen Gründen (CI-Builds wie Vercel können ohne PAT-Auth klonen). Inhalte sind nicht sensitiv — Brand-Definition für GettheFlo / Florian Siepe. Kein Anspruch auf Wiederverwendung; Marken-Identität bleibt bei Florian.

---

Hintergrund: Brand-Sprint 18.05.2026, Plan-Checkpoint `~/Laura/work/plan-gettheflo-brand-sprint.md`, Brainstorm `~/Laura/work/brainstorm-gettheflo-brand-sprint-2026-05-18.md`.

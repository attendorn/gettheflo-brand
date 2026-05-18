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

**Philosophie:** Reduktion + Energie. Helle, freundliche Bühne + 5% Iridescent Aurora als Energie-Akzent. „Wie Captain Marvel — die Kraft ist immer da, sie leuchtet nur wenn's zählt." Aurora bleibt das Identity-Element von GettheFlo, wandert aber vom Dark-Mode (Stand bis 30.04.2026) auf eine helle Light-Mode-Bühne.

**Palette:** Bone-Off-White (`#FAF8F4`) als Hauptfläche, Cream/Stone-Familie für Sekundär-Flächen + Borders, Ink-Charcoal (`#0A0908`) für Display-Text. **Aurora-Gradient** (Gold → Ember → Pink → Violet → Cyan) als Energie-Akzent, max 5% der Fläche (Logo, Hover-States, Stat-Highlights, Schlüsselwörter in Headlines).

**Typografie:**
- **DM Sans** (Brand-Schrift): Headlines, Logo-Wort-Mark, Marketing-Hero, Display-Texte
- **Geist** (Cockpit-UI-Schrift): Body, Tabellen, Inputs, Buttons, Tabs — ruhige Lesbarkeit in Daten-dichten Flächen
- **JetBrains Mono**: Daten, IDs, RE-Nr, Labels, Mikrokopie

**Logo:** Orbit-Symbol mit Aurora-Gradient (übernommen aus gettheflo.de Favicon, Form unverändert). Combo-Mark mit DM-Sans-Wort-Mark „gettheflo" rechts daneben.

**Brand-Anwendungs-Regel:** Brand muss nicht jede Oberfläche dominieren. Cockpit + Mails sind eigene Tools mit eigener Identität (Geist als UI-Schrift, neutrale Bone-Bühne), Brand wird über Logo + sparsame Aurora-Akzente getragen. Marketing-Website ist der Ort wo Brand voll zur Geltung kommt.

## Lizenz

Public-Repo aus pragmatischen Gründen (CI-Builds wie Vercel können ohne PAT-Auth klonen). Inhalte sind nicht sensitiv — Brand-Definition für GettheFlo / Florian Siepe. Kein Anspruch auf Wiederverwendung; Marken-Identität bleibt bei Florian.

---

Hintergrund: Brand-Sprint 18.05.2026, Plan-Checkpoint `~/Laura/work/plan-gettheflo-brand-sprint.md`, Brainstorm `~/Laura/work/brainstorm-gettheflo-brand-sprint-2026-05-18.md`.

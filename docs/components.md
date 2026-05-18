# GettheFlo Komponenten-Stil

Visuelle Bausteine die in Cockpit, Website und Mail-Templates wiederkehren. Token-konsistent mit `tokens/colors.json` + `tokens/typography.json`.

**Anwendungs-Regel** (siehe README): Brand-Identität wird primär über **Logo + Aurora-Akzente** getragen. Komponenten-Stil ist funktional zuerst, Brand-Touches in Pillen, Hover-States, akzentuierten Headlines.

---

## Buttons

### Primary (Aurora-Akzent)

Für die EINE Haupt-Aktion auf einer Fläche: „Jetzt senden", „Workshop buchen", „Termin vorschlagen".

```css
.btn-primary {
  display: inline-flex;
  align-items: center;
  gap: 7px;
  padding: 10px 18px;
  border-radius: var(--brand-radius-pill);
  font-family: var(--brand-font-ui);
  font-size: 14px;
  font-weight: 600;
  letter-spacing: -0.01em;
  background: var(--brand-ink);
  color: var(--brand-bone);
  border: 1.5px solid var(--brand-ink);
  box-shadow: 2px 3px 0 0 var(--brand-aurora-pink);
  transform: translate(-1px, -1px);
  transition: all 160ms cubic-bezier(0.2, 0.7, 0.2, 1);
}
.btn-primary:hover {
  transform: translate(-2px, -2px);
  box-shadow: 3px 4px 0 0 var(--brand-aurora-pink);
}
.btn-primary:active {
  transform: translate(0, 0);
  box-shadow: 0 0 0 0 var(--brand-aurora-pink);
}
```

**Pattern:** Charcoal-Button mit Aurora-Pink-Versatzschatten — der Schatten ist die Brand-Energie. Beim Hover springt der Button leicht zur Seite, Schatten wird länger. Beim Click „rastet" er ein.

### Ghost

Sekundäre Aktion. „Abbrechen", „Vorschau", „Mehr".

```css
.btn-ghost {
  padding: 9px 16px;
  border-radius: var(--brand-radius-pill);
  font-family: var(--brand-font-ui);
  font-size: 13px;
  font-weight: 500;
  background: transparent;
  color: var(--brand-ink-soft);
  border: 1px solid var(--brand-stone-300);
  transition: all 140ms ease;
}
.btn-ghost:hover {
  background: var(--brand-cream);
  border-color: var(--brand-warm-gray);
  color: var(--brand-ink);
}
```

### Icon-Button

Quadratisch, für Aktion-Bars im Cockpit.

```css
.btn-icon {
  width: 34px;
  height: 34px;
  border-radius: var(--brand-radius-md);
  display: grid;
  place-items: center;
  color: var(--brand-warm-gray);
  background: transparent;
  border: none;
  transition: all 160ms cubic-bezier(0.2, 0.7, 0.2, 1);
}
.btn-icon:hover {
  background: var(--brand-cream);
  color: var(--brand-ink);
  transform: translateY(-1px);
}
```

---

## Cards

Standard-Container für Inhalt-Gruppen. Workshop-Karten, Teilnahme-Karten, Stat-Karten.

```css
.card {
  background: white; /* oder var(--brand-bone) */
  border: 1px solid var(--brand-stone-100);
  border-radius: var(--brand-radius-lg);
  padding: 22px 24px;
  box-shadow: var(--brand-shadow-1);
  transition: all 200ms cubic-bezier(0.2, 0.7, 0.2, 1);
}
.card:hover {
  box-shadow: var(--brand-shadow-2);
  border-color: var(--brand-stone-300);
}
.card-accent {
  /* Wenn Karte hervorgehoben sein soll */
  position: relative;
  overflow: hidden;
}
.card-accent::before {
  content: '';
  position: absolute;
  left: 0;
  top: 24px;
  bottom: 24px;
  width: 3px;
  background: var(--brand-aurora-gradient);
  border-radius: 0 3px 3px 0;
  opacity: 0.7;
}
```

**Variation Hero-Card:** Größeres Padding, weiche Innen-Schatten, Aurora-Gradient als dezente Hintergrund-Illumination („Aurora-Glow", `filter: blur(80px)`, opacity 0.1).

---

## Pillen (Pills / Badges)

Statusanzeigen, Filter-Marker, Bereich-Tags.

```css
.pill {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 3px 11px 4px;
  border-radius: var(--brand-radius-pill);
  font-family: var(--brand-font-ui);
  font-size: 11.5px;
  font-weight: 600;
  letter-spacing: 0;
}
.pill-status-success {
  background: var(--brand-status-success-soft);
  color: var(--brand-status-success);
}
.pill-status-warning {
  background: rgba(184, 106, 42, 0.15);
  color: var(--brand-status-warning);
}
.pill-status-error {
  background: rgba(162, 59, 38, 0.15);
  color: var(--brand-status-error);
}
.pill-neutral {
  background: var(--brand-cream);
  color: var(--brand-ink-soft);
}
.pill-brand {
  /* Für „GettheFlo"-Pille auf Person-Seite (Bereich-Marker) */
  background: var(--brand-ink);
  color: var(--brand-aurora-pink); /* Aurora-Pink als Text, Charcoal-Hintergrund */
}
```

---

## Tabs

Im Cockpit für Tab-Navigation in der Person-Seite, Workshop-Seite, Wizard.

```css
.tab-bar {
  display: inline-flex;
  gap: 4px;
  padding: 4px;
  background: var(--brand-cream);
  border: 1px solid var(--brand-stone-100);
  border-radius: var(--brand-radius-pill);
  width: fit-content;
}
.tab {
  padding: 8px 16px 9px;
  border-radius: var(--brand-radius-pill);
  font-family: var(--brand-font-ui);
  font-size: 13px;
  font-weight: 600;
  color: var(--brand-warm-gray);
  transition: all 160ms ease;
  display: inline-flex;
  align-items: center;
  gap: 7px;
}
.tab:hover { color: var(--brand-ink-soft); }
.tab.active {
  background: var(--brand-ink);
  color: var(--brand-bone);
}
.tab-count {
  font-family: var(--brand-font-mono);
  font-size: 10.5px;
  background: rgba(10, 9, 8, 0.08);
  padding: 1px 7px;
  border-radius: var(--brand-radius-pill);
  color: var(--brand-warm-gray);
}
.tab.active .tab-count {
  background: var(--brand-aurora-pink);
  color: var(--brand-ink);
}
```

---

## Inputs

```css
.input {
  font-family: var(--brand-font-ui);
  font-size: 14px;
  padding: 9px 13px;
  border-radius: var(--brand-radius-md);
  border: 1px solid var(--brand-stone-300);
  background: white;
  color: var(--brand-ink);
  transition: border-color 140ms ease;
}
.input:focus {
  outline: none;
  border-color: var(--brand-ink);
  box-shadow: 0 0 0 3px var(--brand-cream);
}
.input::placeholder {
  color: var(--brand-warm-gray);
}
.label {
  font-family: var(--brand-font-mono);
  font-size: 10.5px;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--brand-warm-gray);
  margin-bottom: 6px;
}
```

---

## Hero-Headline mit Aurora-Akzent

Für Marketing-Hero, Workshop-Anschreiben, gelegentlich auch Cockpit-Sektion-Header wenn Brand spürbar sein soll.

```css
.hero {
  font-family: var(--brand-font-display);
  font-weight: 700;
  font-size: clamp(48px, 8vw, 96px);
  letter-spacing: -0.04em;
  line-height: 0.95;
  color: var(--brand-ink);
}
.hero .energy {
  background: var(--brand-aurora-gradient);
  background-size: 300% 300%;
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  animation: aurora-shimmer 20s ease infinite;
}
@keyframes aurora-shimmer {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}
```

**Anwendungs-Regel:** Maximal **ein bis zwei Schlüsselwörter** pro Headline kriegen Aurora-Highlight. Nicht den ganzen Satz, nicht jeden Absatz. „Wie Captain Marvel — die Kraft ist immer da, sie leuchtet nur wenn's zählt."

---

## Stat-Row (Cockpit-spezifisch)

Kennzahlen-Karten im Person-Hero, Workshop-Übersicht.

```css
.stat-row {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}
.stat {
  background: var(--brand-cream);
  border: 1px solid var(--brand-stone-100);
  border-radius: var(--brand-radius-lg);
  padding: 14px 18px 12px;
}
.stat-label {
  font-family: var(--brand-font-mono);
  font-size: 10.5px;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--brand-warm-gray);
  margin-bottom: 6px;
}
.stat-value {
  font-family: var(--brand-font-display);
  font-size: 26px;
  font-weight: 700;
  letter-spacing: -0.03em;
  line-height: 1;
  color: var(--brand-ink);
}
.stat-highlight {
  /* Wenn eine Stat-Karte besonders hervorzuheben ist */
  background: linear-gradient(135deg, rgba(255, 210, 63, 0.10), rgba(255, 60, 172, 0.05));
  border-color: rgba(255, 60, 172, 0.20);
}
```

---

## Sticky Header (Cockpit-Wizard)

Pattern für ConfirmationWizard und ähnliche Action-Sequenzen mit Vor-/Zurück + Senden.

```css
.sticky-action-bar {
  position: sticky;
  top: 0;
  z-index: 10;
  background: var(--brand-ink);
  color: var(--brand-bone);
  border-radius: var(--brand-radius-xl);
  display: flex;
  align-items: center;
  gap: 16px;
  padding: 12px 22px;
  box-shadow: var(--brand-shadow-3);
}
.sticky-action-bar .wiz-tabs {
  display: flex;
  gap: 2px;
  background: rgba(250, 248, 244, 0.06);
  padding: 4px;
  border-radius: var(--brand-radius-pill);
  margin: 0 auto;
}
.wiz-tab.done { color: var(--brand-status-success); }
.wiz-tab.active {
  background: var(--brand-aurora-pink);
  color: var(--brand-ink);
}
```

---

## Spacing-Skala

Token-basiert, aber als Anhalt:

| Use Case | Wert |
|---|---|
| Inline-Gap (Icon ↔ Text) | 6-8 px |
| Stack-Gap (Felder in einem Formular) | 12-16 px |
| Section-Gap (zwischen Cards) | 16-24 px |
| Section-Padding (Card-innen) | 22-28 px |
| Page-Padding (Cockpit-Main) | 28-42 px |
| Page-Padding (Website-Sektion) | 80-120 px |

---

## Animations-Prinzipien

- **Easing:** Standard `cubic-bezier(0.2, 0.7, 0.2, 1)` für Buttons, Cards, Hover-States — schneller Start, langsames Ausklingen.
- **Dauer:** 140-200ms für UI-Reaktionen. 600ms+ nur für Page-Loads / Reveal.
- **Aurora-Shimmer:** Endlos-Loop 20s, ease, nur für Headlines/Logos. Nicht für ganze Flächen-Backgrounds (visuelles Rauschen).

---

## Was NICHT gehört

- ❌ Slap-Schatten (`box-shadow: 0 20px 40px rgba(0,0,0,0.5)`) — passt nicht zu Light-Mode
- ❌ Bunte Multi-Color-Border-Animations — Aurora bleibt reserviert
- ❌ Border-Gradients als Default — nur für 1-2 Sonderkomponenten
- ❌ Glassmorphism (`backdrop-filter: blur` als zentrales Pattern) — Light-Mode + Glass = visuell instabil

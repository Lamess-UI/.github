# LAMESS UI — DESIGN SYSTEM

> The single source of truth for all design decisions across the Lamess UI ecosystem.
> Every project under this organization follows these guidelines.

---

## `// PHILOSOPHY`

```
  DARK MODE ONLY      —  No light theme. Ever.
  TUI FIRST           —  Every solution starts as a terminal application.
  TRANSPARENCY        —  Surfaces reveal the desktop beneath them.
  TERMINAL AESTHETIC  —  Retro cyberpunk. Monospace. Sharp. Precise.
  THEMEABLE           —  Orange is the default. The user always chooses.
```

---

## `// TYPOGRAPHY`

**Primary Font:** `Cascadia Mono`

```
  Family   : Cascadia Mono
  Style    : Monospace only — no proportional fonts anywhere
  Rendering: Subpixel antialiasing preferred
  Fallback : JetBrains Mono → Hack → monospace
```

All text — labels, headers, body, inputs — uses monospace.
No serif. No sans-serif. Ever.

---

## `// SHAPE & GEOMETRY`

```
  Border Radius  : 0px — sharp corners everywhere, no rounding
  Borders        : 1px solid — precise, thin, intentional
  Spacing Unit   : 4px base grid
  Layout         : Structured, grid-aligned, terminal-inspired
```

Panels, cards, inputs, buttons — all sharp rectangles.
The interface should feel like a terminal, not a mobile app.

---

## `// BACKGROUNDS & SURFACES`

### TUI Applications
```
  Background     : NONE — inherits from terminal theme
  Transparency   : Controlled by the user's terminal emulator
  Rule           : Never hardcode a background in TUI apps
```

### GUI Applications & System UI
```
  Background     : Transparent + blur — the desktop wallpaper shows through
  Blur Intensity : Medium (15–20px backdrop-filter blur)
  Overlay        : Dark tint at 40–60% opacity over the blur
  Rule           : Surfaces should feel glassy, not opaque
```

The wallpaper is always part of the UI. Design with that in mind.

---

## `// COLOR SYSTEM`

### Theme Architecture

Colors are defined as CSS-style variables. Every app ships with at least the 3 Lamess UI default themes. Users can apply any theme or define custom ones.

```
  --color-accent         : primary accent color
  --color-accent-muted   : accent at ~40% opacity / desaturated
  --color-accent-glow    : accent at ~15% opacity (for glows/halos)
  --color-bg             : base background
  --color-surface        : panel / card background
  --color-border         : border color
  --color-text           : primary text
  --color-text-muted     : secondary / inactive text
```

### Built-in Themes

#### `lamess` — Default
```
  --color-accent         : #FF6B00
  --color-accent-muted   : #FF6B0066
  --color-accent-glow    : #FF6B0026
  --color-bg             : #0A0A0A
  --color-surface        : #111111
  --color-border         : #FF6B0099
  --color-text           : #E0E0E0
  --color-text-muted     : #555555
```

#### `cyan` — Cool Variant
```
  --color-accent         : #00D4FF
  --color-accent-muted   : #00D4FF66
  --color-accent-glow    : #00D4FF26
  --color-bg             : #0A0A0A
  --color-surface        : #0D1117
  --color-border         : #00D4FF99
  --color-text           : #E0E0E0
  --color-text-muted     : #444455
```

#### `monochrome` — Minimal
```
  --color-accent         : #E0E0E0
  --color-accent-muted   : #E0E0E066
  --color-accent-glow    : #E0E0E026
  --color-bg             : #0A0A0A
  --color-surface        : #111111
  --color-border         : #333333
  --color-text           : #E0E0E0
  --color-text-muted     : #444444
```

### Custom Themes
Any app can expose additional themes by defining the same variable set.
A global theme system using a variables file may replace per-app themes in a future version.

---

## `// COMPONENTS`

### Borders
```
  Active / focused  : 1px solid var(--color-accent)
  Default / idle    : 1px solid var(--color-border)
  Disabled          : 1px solid var(--color-text-muted)
```

### Glows & Shadows
```
  Hover / active    : box-shadow: 0 0 8px var(--color-accent-glow)
  No heavy shadows  — subtle glow only
```

### Text Labels
```
  Section headers   : ALL CAPS, monospace, accent color
  Body text         : Sentence case, --color-text
  Inactive / meta   : --color-text-muted
```

### Progress & Indicators
```
  Style     : Block / segmented — not smooth bars
  Example   : [████████░░░░] 66%
  Color     : var(--color-accent) filled, var(--color-surface) empty
```

### ASCII / Box Drawing
```
  Use box-drawing characters for panels and tables in TUI:
  ┌ ─ ┐ ├ ┤ │ └ ┘ ┬ ┴ ┼
  Preferred over heavy borders or padding-based layouts
```

---

## `// ANIMATIONS`

```
  Principle   : Functional motion only — no decorative animations
  Duration    : 100–200ms max
  Easing      : linear or ease-out — no bouncy/spring effects
  Transitions : Opacity and position only — no scale or rotate
```

---

## `// LOGOS & ASSETS`

All official assets are stored in [Lamess-UI/.github/Logo](https://github.com/Lamess-UI/.github/tree/main/Logo).

```
  Lamess Symbol Logo.png                    — Full color, with background
  Lamess Symbol Logo Transparent.png        — Full color, no background ✔ preferred
  Lamess Symbol Logo Monochrom White.png    — White, with background
  Lamess Symbol Logo Monochrom White Transparent.png  — White, no background
  Lamess Symbol Logo Monochrom Black.png    — Black, with background
  Lamess Symbol Logo Monochrom Black Transparent.png  — Black, no background
```

Per-project logos live inside their own repo under `public/images/`.

---

## `// RULES (NON-NEGOTIABLE)`

```
  [01]  No light mode
  [02]  No rounded corners
  [03]  No hardcoded backgrounds in TUI apps
  [04]  No proportional fonts
  [05]  No heavy drop shadows
  [06]  No smooth progress bars
  [07]  No decorative animations
  [08]  Always ship the 3 default themes (lamess / cyan / monochrome)
  [09]  Always use the variable system for colors — never hardcode hex in components
  [10]  Always monospace
```

---

<div align="center">

```
[ LAMESS UI DESIGN SYSTEM ] ── [ VERSION 1.0 ]
```

</div>

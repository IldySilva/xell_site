# Design System

A minimal, dark, developer-first visual language. Built for tools that respect the user's focus. No decoration, no brand noise — just clarity at every layer.

---

## Philosophy

- **Dark by default.** Not as a theme option — as a conviction. The interface never fights for attention.
- **Borders over shadows.** Structure is expressed through thin borders, not elevation or blur.
- **Monospace for anything machine-made.** Code, commands, brand names, identifiers — mono. Human prose — sans.
- **Density with breathing room.** Small type, tight spacing — but sections have room to breathe. Never cramped, never sprawling.
- **Hover, don't transform.** Interactions are color shifts, not animations or movement.
- **Nothing is decorative.** Every element earns its place. No gradients, no illustrations, no icons that don't carry meaning.

---

## Color

All values are intentional. The palette has exactly seven roles.

| Token      | Hex       | Role                                           |
|------------|-----------|------------------------------------------------|
| `bg`       | `#0F1115` | Page background. The darkest layer.            |
| `surface`  | `#151922` | Cards, inputs, code blocks. One step up.       |
| `elevated` | `#1A2030` | Hover state of surface elements.               |
| `border`   | `#232734` | All borders. Also used as grid-line fill.      |
| `text`     | `#E6EAF2` | Primary readable text. Slightly off-white.     |
| `muted`    | `#9AA4B2` | Secondary text, labels, icon fills.            |
| `accent`   | `#5E81F4` | Primary action, links, highlights, dot markers.|

**Rules:**
- Never use pure black or pure white.
- `muted` at reduced opacity (e.g. `/60`, `/50`) is used for the least important text — timestamps, footnotes, brand wordmarks in footers.
- `accent` at `/25` opacity is the selection highlight color.
- `accent` at `/40` or `/30` is used for border hover states — it signals interactivity without shouting.

---

## Typography

Two typefaces. Used in strict roles.

**Sans-serif** — Inter (400, 500, 600)
Used for all body copy, labels, buttons, navigation, and headings.

**Monospace** — JetBrains Mono (400, 500) / fallback: Fira Code
Used for: brand name in nav/footer, code snippets, shell commands, terminal prompts, any identifier that should read as a machine string.

### Scale

| Usage                | Size   | Weight | Notes                            |
|----------------------|--------|--------|----------------------------------|
| Hero heading         | 40–50px| 600    | `line-height: 1.1`, tight tracking|
| Section heading      | 22px   | 600    | Tight tracking                   |
| Body / descriptions  | 14–16px| 400    | `line-height: relaxed`           |
| UI labels / buttons  | 13px   | 500    | —                                |
| Small labels / meta  | 12–12.5px | 400 | Often `muted` color              |
| Micro / badges       | 11px   | 400–500| Monospace preferred              |

**Anti-aliasing:** always on (`-webkit-font-smoothing: antialiased`).

---

## Layout

- **Max content width:** ~896px (`max-w-4xl`), centered with horizontal padding.
- **Horizontal padding:** 24px on all containers.
- **Sections:** separated by a single `border` line, with `64px` vertical padding each.
- **Nav height:** ~52px, fixed to top, blurred background (`backdrop-blur`), thin bottom border.
- **Footer:** thin top border, 24px vertical padding. Brand wordmark (mono) on the left, links on the right.

The layout never goes full-width. Content lives in a comfortable column. Nothing stretches to the viewport edges.

---

## Components

### Navigation

Fixed to top. Backdrop-blurred with semi-transparent background. One thin bottom border. Logo (monospace wordmark) on the left. Icon link + primary CTA button on the right. No mega-menus, no dropdowns.

### Buttons

**Primary:** Accent background, white text, rounded (`6px` radius). Hover: accent at 90% opacity.

**Secondary:** Surface background, border, `text` colored text. Hover: border shifts toward accent tint, text stays.

Both sizes: `13px`, `500` weight, `8px × 10px` padding vertically/horizontally. Can include a leading icon at `16×16`.

No shadows on buttons. Ever.

### Code / Command block

```
[ $ ]  [ command text ... ]          [ Copy ]
```

- Surface background, rounded, border.
- `$` prompt in accent color, monospace.
- Command text in `text` color, monospace, truncated.
- Copy button is a separate secondary button, shrinks to fit.
- On copy: label swaps to "Copied!" and resets after 2 seconds.

### Feature grid

A grid of cards separated not by gaps but by a single-pixel border mesh. Achieved by setting the grid's background to `border` color with `1px` gaps between cells — each cell is `surface` colored and fills its slot. Hover state lifts the cell to `elevated`.

Each card: small icon (16–18px, `muted` colored, stroke style), title in `text`, description in `muted`. No borders on individual cards. No shadows.

### Badges / Pills

Small inline labels. Rounded-full, `surface` background, `border` border, `muted` text at `11px` mono. Can include a small filled dot in `accent` as a status indicator.

### Links (inline)

Accent colored. Hover: underline appears. Transition on color. Arrow suffix (`→`) used for standalone CTAs at the bottom of sections.

### Scrollbar

5px wide. Track matches `bg`. Thumb matches `border`, `3px` border-radius. Minimal and unobtrusive.

### Text selection

Accent color at 25% opacity. Consistent with the palette.

---

## Icons

- **Style:** Stroke-based (not filled), `1.5px` stroke width, round caps and joins.
- **Size:** 14–18px in most contexts.
- **Color:** `muted` as default fill/stroke. `text` on hover or active states. `white` when on accent background.
- Inline SVG. No icon library dependency implied — just consistent geometry.

Brand logos (GitHub, Apple, Linux, etc.) use filled paths to match their official forms — the only exception to the stroke rule.

---

## Motion

Transitions are `colors`-only. Duration: 150ms. No transforms, no scale, no fade-in animations on load.

Interactivity is expressed purely through color change:
- `muted` → `text` on hover for links and icon buttons.
- `border` → `accent/30` on hover for bordered secondary buttons.
- `surface` → `elevated` on hover for cards.

Nothing bounces, slides, or fades in.

---

## Spacing Rhythm

Use a base-4 scale. Common values: 4, 8, 12, 16, 20, 24, 32, 40, 64px.

Section vertical padding: 64px.
Card internal padding: 20px.
Nav height: ~52px.
Between grouped inline elements: 12–16px.
Between stacked text lines in a card: 4px (title → desc).

---

## Voice in the Interface

Labels, descriptions, and CTAs are written like a developer wrote them — precise, lowercase where possible, no fluff.

- "Browse, upload, download, rename, delete." — not "Effortlessly manage your remote files"
- "Full xterm. ANSI, resize, zero lag." — not "A powerful integrated terminal experience"
- "No telemetry. No analytics. No hidden calls." — direct denial, not a promise

Short sentences. Often fragments. Never marketing language.

---

## What This System Is Not

- Not a light/dark toggle system. It's dark-only.
- Not a component library with variants for every state. Minimal surface area.
- Not gradient-forward, glassmorphism, or shadow-heavy.
- Not animated or playful.

It's a focused instrument for developer tools, CLIs, and open-source products that want to communicate: *we respect your intelligence and your screen.*

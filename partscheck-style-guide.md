# PartsCheck — Design & Style Guide

> This document is the single source of truth for the PartsCheck UI. It covers colours, typography, spacing, components, navigation, screen patterns and design principles. All new development should reference this guide. When a decision is made that changes or extends the design system, this document should be updated.

---

## 1. Brand

**Product name:** PartsCheck  
**Tagline:** Smart. Simple. Streamlined.
**Audience:** Panel repairers, estimators, workshop managers

---

## 2. Colour System

### Primary Brand Green

| Token | Hex | Usage |
|---|---|---|
| `brand-green` | `#16a34a` | Nav active states, selected tab underlines, Save buttons, quote number text, tooltip headers, profit text, selected count. Same hex as Tailwind `green-600` — no Tailwind config override needed. |
| `brand-green-dark` | `#15803d` | Hover state on green buttons, border on green buttons. Same hex as Tailwind `green-700`. |

> The brand green is identical to Tailwind `green-600` and the dark variant to `green-700`, so the entire green system runs on stock Tailwind values — no custom theme extensions required. Use the brand green for identity and interaction (text, nav active state, primary button fill); for backgrounds and pill fills, use the lighter shades (`green-50`–`green-200`) rather than the brand shade.

### Action & Status Greens (Tailwind scale)

These are stock Tailwind values, used for pills, badges, selected states and backgrounds. The brand green sits inside this scale at `green-600`, so the whole palette is internally consistent — no custom values to maintain.

| Token | Hex | Usage |
|---|---|---|
| `green-50` | `#f0fdf4` | Selected cell background, pill backgrounds |
| `green-100` | `#dcfce7` | DEFAULT badge background |
| `green-200` | `#bbf7d0` | Borders on green pills |
| `green-500` | `#22c55e` | Grid View selected cell outline — deliberately one step softer than brand-green so selection reads distinctly from primary actions |
| `green-600` | `#16a34a` | **Primary brand green** (same as `brand-green`) |
| `green-700` | `#15803d` | Hover state for primary buttons / nav, dark text on light green |
| `green-800` | `#166534` | Text on DEFAULT badge |

### Grey Scale (Tailwind)

| Token | Hex | Usage |
|---|---|---|
| `slate-50` | `#f8fafc` | Table column headers, card section headers |
| `gray-50` | `#f9fafb` | Row hover, button fills, alternate row bg |
| `gray-100` | `#f3f4f6` | Inactive badges, light dividers, tooltip row dividers |
| `gray-200` | `#e5e7eb` | Borders, card borders, table dividers |
| `gray-300` | `#d1d5db` | Stronger borders |
| `gray-400` | `#9ca3af` | Placeholder text, secondary labels, bullet points |
| `gray-500` | `#6b7280` | Body text, descriptions, tooltip labels |
| `gray-600` | `#4b5563` | Parallel type text, secondary icons. **Not for card headers** — those are `gray-500` |
| `gray-700` | `#374151` | Primary body text |
| `gray-900` | `#111827` | Headings, strong emphasis. Not for form field values — those are `gray-700` |

### Part Types

**Part types are always listed in this order**, everywhere they appear — the
Check Price grid, the margin rule dropdown, the Settings list and the rule form:

1. OEM
2. Parallel
3. Aftermarket
4. Reconditioned
5. Recycled

> The order mirrors the Check Price grid, which is where estimators spend their
> day. If Settings lists them differently, someone reading a rule has to
> re-map five rows against what they know from the grid.

All five are always present. Parallel and Recycled are distinct types and must
never be merged into a single "Used / Parallel" row.

### Part Type Colours

In the standard order. The third column is the readable text shade — the true
colours fail AA as text on white, so they are used for dots, bars and fills only.

| Type | Hex | Tailwind | As text |
|---|---|---|---|
| OEM | `#2563eb` | blue-600 | `#1d4ed8` |
| Parallel | `#6b7280` | gray-500 | `#4b5563` |
| Aftermarket (AftM) | `#a855f7` | purple-500 | `#7e22ce` |
| Reconditioned (Reco) | `#f59e0b` | amber-500 | `#b45309` |
| Recycled | `#84cc16` | lime-500 | `#4d7c0f` |

### Line Status Colours

Row-level status indicators applied as background fills. Each status has two shades so the same colour language can be used across both views without visual overload:

- **Part row shade** (the Tailwind `-200` scale) — used on Grid View rows and on the part-description header in the List View. This is the strong, attention-carrying shade.
- **Supplier row shade** (the Tailwind `-50` scale) — used on the supplier price rows in the List View only. This is a much softer version of the same hue, so the whole part group reads as one status while the part header remains emphasised.

All values are stock Tailwind — no custom hexes.

| Status | Meaning | Part row (`-200`) | Supplier row — List View only (`-50`) |
|---|---|---|---|
| Removed | No longer in the quote package | `red-200` `#fecaca` — `--line-accent-removed-bg` | `red-50` `#fef2f2` — `--line-accent-removed-bg-subtle` |
| Additional | Added after quote was authorised (pending buy) | `sky-200` `#bae6fd` — `--line-accent-additional-bg` | `sky-50` `#f0f9ff` — `--line-accent-additional-bg-subtle` |
| Supplier | Extra line added by the supplier | `amber-200` `#fde68a` — `--line-accent-supplier-bg` | `amber-50` `#fffbeb` — `--line-accent-supplier-bg-subtle` |
| Modified | Line modified from its original state | `orange-200` `#fed7aa` — `--line-accent-modified-bg` | `orange-50` `#fff7ed` — `--line-accent-modified-bg-subtle` |
| Optional | Optional extra part added by the supplier | `green-200` `#bbf7d0` — `--line-accent-optional-bg` | `green-50` `#f0fdf4` — `--line-accent-optional-bg-subtle` |

These are line/row backgrounds only. Do not apply to buttons, pills or badges — those have their own colour system. Text colour on top of these backgrounds stays at the standard grid text colours (`#111827` / `#374151`) for legibility; do not tint the text to match the background. When a line is in multiple states, priority order is: **Removed → Modified → Supplier → Additional → Optional** (removed always wins because it signals the strongest information, that the line no longer counts toward the quote).

**View-specific application:**

- **Grid View** — apply the part row (`-200`) shade to the whole line (all cells across the row).
- **List View** — apply the part row (`-200`) shade to the part-description header row; apply the supplier row (`-50`) shade to every supplier price row grouped underneath. Both must use the same status colour so the group reads as one unit.

### Semantic Colours

| Colour | Hex | Usage |
|---|---|---|
| Red (destructive) | `#ef4444` | Delete buttons, error states |
| Red background | `#fef2f2` | Destructive button background |
| Red border | `#fecaca` | Destructive button border |
| Amber | `#d97706` | Warning, supplier discount flag, pinned star |
| Amber background | `#fffbeb` | Warning banners |
| Amber border | `#fde68a` | Warning banner border |

### Dark Surfaces

| Token | Hex | Usage |
|---|---|---|
| `nav-dark` | `#3a3a3a` | Top sub-nav bar, settings tab bar |
| `sidebar-dark` | `#1f2937` | Rule Summary left accent border, dark buttons |
| `page-bg` | `#1a1a2e` | Deprecated — was tooltip background, now replaced with white |
| `form-bg` | `#f4f5f7` | Background for focused task pages (Create Rule) |

---

## 3. Typography

**Font family:** `-apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif`  
System font stack — no external font loaded. Clean, fast, neutral.

### Type Scale

| Size | Usage |
|---|---|
| `9px` | Badge labels (SYSTEM, DEFAULT, NEW), tiny metadata |
| `10px` | Column headers (uppercase), tooltip labels, ETD label |
| `11px` | Section card headers (uppercase), pill text, sub-labels, descriptions |
| `12px` | Body text, table data, form labels, nav sub-items |
| `13px` | Primary body text, rule values, modal content |
| `14px` | Card headings (System Templates, Margin Rules, Create Rule heading) |
| `16px` | Page headings (Info, Documents) |
| `22px` | Selected count in grid header |

### Weights

| Weight | Usage |
|---|---|
| `400` / normal | Body text, descriptions |
| `500` | Sub-nav labels, secondary nav links |
| `600` | Form labels, table values, button text (secondary) |
| `700` | Section headings, column headers, badge text, most UI labels |
| `800` | Page headings, section titles (System Templates, Margin Rules) |
| `800` | Price amounts in grid cells (selected) |
| `500` | Price amounts in grid cells (unselected) |

### Text Colour Conventions

- **Headings:** `#111827`
- **Primary body:** `#374151`
- **Secondary / descriptions:** `#6b7280`
- **Placeholders / metadata:** `#9ca3af`
- **Green text (profit, active states, brand):** `#16a34a`
- **Uppercase tracking labels:** `letter-spacing: 0.5px–0.6px`

---

## 4. Spacing

Spacing follows a consistent 4px base unit.

| Token | Value | Usage |
|---|---|---|
| `xs` | `4px` | Gap between badges and labels |
| `sm` | `8px` | Row padding, gap between inline elements |
| `md` | `12px` | Card section header padding (vertical), button padding |
| `lg` | `16px` | Standard card content padding (horizontal) |
| `xl` | `20px` | Card content padding, modal padding |
| `2xl` | `24px` | Page section padding |
| `3xl` | `28px–32px` | Gap between major page sections |

### Card Padding Pattern

Section card headers: `padding: 11px 20px`  
Section card content: `padding: 20px` or `padding: 24px`

---

## 5. Borders & Radius

| Context | Border | Radius |
|---|---|---|
| Cards (Info, Settings tables) | `1px solid #e5e7eb` | `6px` |
| Create Rule section cards | `1px solid #e5e7eb` | `8px` |
| Buttons (primary) | none | `4px` |
| Buttons (secondary) | `1px solid #d1d5db` | `4px` |
| Inputs | `1px solid #d1d5db` | `4px–5px` |
| Badges / pills | none | `10px–20px` (fully rounded) |

### Radius scale

Cards are square. Everything steps up from there — nothing should look softer
than the surface it sits on.

| Radius | Applies to |
|---|---|
| `0` | Cards, panels, section containers |
| `2px` | Cell indicator chips |
| `3px` | Buttons, inputs, selects, badges, small pills |
| `4px` | Popovers, modals — one step softer than the controls inside them |
| `50%` / `999px` | Radio dots, icon circles, toggle tracks, legend pills |

> Controls were previously 4px and containers 6px. Both were reduced once cards
> were squared — at the old values the buttons visibly stood out against the
> surfaces holding them. Fully-round elements are round by intent, not by scale,
> and are unaffected.
| Small badges (SYSTEM, DEFAULT) | none | `3px` |
| Modals | none | `8px` |
| Tooltips | `1px solid #e5e7eb` | `6px` |
| Rule Summary card | Top/Right/Bottom: `1px solid #e5e7eb`, Left: `4px solid #1f2937` | `8px` |

---

## 6. Shadows

| Context | Shadow |
|---|---|
| Tooltips | `0 8px 24px rgba(0,0,0,.10)` |
| Modals | `0 20px 60px rgba(0,0,0,.25)` |
| Dropdowns (rule picker, print menu) | `0 12px 36px rgba(0,0,0,.15)` |
| Green action buttons | `0 2px 8px rgba(22,163,74,.3)` |

---

## 7. Components

### Buttons

#### Primary (Green)
```css
background: #16a34a;
color: white;
border: none;
border-radius: 3px;
padding: 7px 16px;
font-size: 12px;
font-weight: 700;
cursor: pointer;
```
Hover: `background: #15803d`

**Height is 30px** for every button. There is no second size.

### The three button tiers

Every button is one of these three. A new button picks a tier; it does not
invent values.

| Tier | Fill | Border | Text | Used for |
|---|---|---|---|---|
| **Primary** | `#16a34a` | none | white | The main action on a screen or row — Submit, Save, Apply, Open |
| **Secondary** | `#fff` | `#16a34a` | `#16a34a` | A choice that is currently applied — Quick Select, selected time slot, active margin rule |
| **Tertiary** | `#fff` | `#d1d5db` | `#374151` | Neutral actions — Print, Export, Clear Selections, Cancel |

All three are 30px tall with a 3px radius and 12px text.

**Case follows context, not tier.**

| Where | Case | Examples |
|---|---|---|
| On the screen | UPPERCASE | OPEN, MODIFY, SUBMIT QUOTE, OPTIONS |
| Inside a modal or dropdown | Sentence case | Apply, Cancel, Done, Save contact |

> A button sitting in a full screen competes with a grid, a toolbar and a
> supplier list, so it is set in uppercase to hold its own. A modal has already
> taken the user's attention — its buttons do not need to shout, and sentence
> case reads more calmly at the end of a task.

Uppercase is also used for card headers, column headers and section labels. That
is not a conflict: those are 10–11px at weight 700 in grey, while an uppercase
button is 12px white on green or bordered. The colour and weight separate them.

**Primary carries no stroke.** A solid green fill needs no outline, and adding
one only muddies the difference between primary and the green-outlined secondary.

**Hover stays in the control's own colour family.** A green-outlined control
washes to `#f0fdf4` and deepens its border to `#15803d`; a grey-outlined control
washes to `#f3f4f6` and deepens to `#9ca3af`. A primary darkens its fill to `#15803d`.

> Hovering a green control to grey reads as it switching off. Keeping the hover
> in the same family means the control looks like itself under the cursor.

**Tertiary is the default.** Reach for it unless the button commits something
(primary) or reflects a state that is currently on (secondary). Most buttons on
a screen should be tertiary; a screen with several primaries has no primary.

**Inline text links are not buttons.** `+ Add parts`, `Show Details`,
`Edit types` and similar sit inside content rather than beside it: no fill, no
border, `#16a34a` text. They follow the link pattern, not a button tier.

**An applied state is an outline, not a fill.** Quick Select toggles, the active
margin rule tag and the selected time slot all share one treatment: white fill,
`#16a34a` border, `#16a34a` text, green tick.

> These are secondary controls. They record a choice the user can change; they
> do not commit anything. A solid green fill is reserved for the single primary
> action on a screen — Submit, Save, Apply. Filling a toggle solid gives it the
> weight of the primary action and leaves two things competing for the eye.

#### Secondary (Bordered)
```css
background: white;
color: #374151;
border: 1px solid #d1d5db;
border-radius: 3px;
padding: 7px 12–14px;
font-size: 12px;
font-weight: 600;
cursor: pointer;
```
Hover: `background: #f9fafb`

#### Destructive (Red)
```css
background: #fef2f2;
color: #ef4444;
border: 1px solid #fecaca;
border-radius: 3px;
padding: 4–7px 7–14px;
font-size: 11–12px;
font-weight: 600–700;
```

#### Disabled state
Replace green with `#e5e7eb`, text with `#9ca3af`. Use `cursor: not-allowed`. Do not use `opacity` — prefer explicit colour change.

---

### Pills & Badges

Pills are status indicators. **Do not change their colours** — they are intentional and the user has approved them.

| Type | Background | Border | Text |
|---|---|---|---|
| Default/Active (green) | `#f0fdf4` | `#bbf7d0` | `#15803d` |
| Warning/Missing (red) | `#fef2f2` | `#fecaca` | `#b91c1c` |
| Neutral/Pending (amber) | `#fef3c7` | `#fde68a` | `#92400e` |
| Inactive/Empty | `#f1f5f9` | `#e2e8f0` | `#9ca3af` |
| NEW badge | `#16a34a` bg | none | `white` |
| SYSTEM badge | `#e5e7eb` bg | none | `#6b7280` |
| DEFAULT badge | `#dcfce7` bg | none | `#166534` |
| INACTIVE badge | `#f3f4f6` bg | none | `#9ca3af` |

All pills: `border-radius: 10px–20px`, `padding: 2px 8–10px`, `font-size: 9–11px`, `font-weight: 700`

---

### Tooltips

All tooltips use a light card style. **Do not use dark backgrounds.**

```css
background: #fff;
border: 1px solid #e5e7eb;
border-radius: 4px;
padding: 10px 12px;
box-shadow: 0 8px 24px rgba(0,0,0,.10);
width: 230px;
position: fixed;
z-index: 9999;
pointer-events: none;
```

**Header row** (supplier name):
```css
font-size: 10px;
font-weight: 700;
color: #16a34a;
text-transform: uppercase;
letter-spacing: 0.5px;
border-bottom: 1px solid #f3f4f6;
margin-bottom: 6px;
padding-bottom: 5px;
```

**Data rows:**
- Label: `font-size: 10px; color: #6b7280`
- Value: `font-size: 10px; color: #111; font-weight: 600`
- Green value: `color: #16a34a`
- Amber value: `color: #d97706`
- Row divider: `border-bottom: 1px solid #f3f4f6`

**Tooltip positioning:** Use JavaScript to calculate `position: fixed` top/left on `mouseover`. Flip above the element when within 300px of the bottom of the viewport.

#### Field Help (form labels)

A small info ring beside a form label, revealing an explainer on hover. Used on
every field in the add/edit rule form.

**Icon**
```css
width: 13px; height: 13px;
border: 1px solid #c3c7cd;
border-radius: 50%;
font-size: 8px;          /* fa-info */
color: #9ca3af;
cursor: help;
```
Hover: border `#6b7280`, glyph `#374151`.

**Tooltip** — same light card as above, at `width: 230px`, `font-size: 11px`,
`font-weight: 500`, `color: #374151`, `line-height: 1.45`. Opens **above** the
icon, centred, with a bordered arrow.

Two things that will break it:
- It must reset `text-transform` and `letter-spacing`. Table headers are uppercase
  and letter-spaced, and the tooltip inherits both otherwise.
- Any ancestor with `overflow: hidden` will clip it regardless of `z-index`. Cards
  containing help icons must not set it.

---

### Modals

```css
overlay: rgba(0,0,0,.45), position: fixed, inset: 0, z-index: 800
modal: background: white, border-radius: 4px, width: 480px, max-width: 95vw
shadow: 0 20px 60px rgba(0,0,0,.25)
```

**Modal header:** `padding: 16px 20px`, `border-bottom: 1px solid #e5e7eb`  
**Modal body:** `padding: 20px`, `max-height: 68vh`, `overflow-y: auto`  
**Modal footer:** `padding: 12px 20px`, `border-top: 1px solid #e5e7eb`, `background: #fafafa`

---

### Dropdowns

Dropdowns (rule picker, print menu, supplier info) use:
```css
background: #fff;
border: 1px solid #d1d5db;
border-radius: 4px;
box-shadow: 0 12px 36px rgba(0,0,0,.15);
z-index: 400–500;
```

Menu items: `padding: 10px 14px`, hover `background: #f9fafb`  
Close on outside click using a `document.addEventListener('click')` handler.

---

### Toasts

```css
position: fixed;
bottom: 24px;
left: 50%;
transform: translateX(-50%);
background: #1a1a2e;
color: white;
padding: 12px 24px;
border-radius: 4px;
font-size: 13px;
font-weight: 600;
box-shadow: 0 8px 24px rgba(0,0,0,.3);
```

Show for 3–3.5 seconds then fade out. Include a green dot indicator (`background: #16a34a`, `border-radius: 50%`, `20px × 20px`) on the left.

---

### Form Inputs

```css
width: 100%;
border: 1px solid #e5e7eb;
border-radius: 5px;
padding: 8px 10px;
font-size: 13px;
outline: none;
background: #fff;
```

Active/focused border: `1px solid #16a34a`  
Disabled: `background: #f9fafb; color: #9ca3af`

**Select dropdowns** — always use `appearance: none` and a custom chevron SVG background:
```css
background-image: url("data:image/svg+xml,...chevron svg...");
background-repeat: no-repeat;
background-position: right 10px center;
padding-right: 28px;
```

**Number inputs** — always hide spinners:
```css
-moz-appearance: textfield;
/* Chrome */
input[type=number]::-webkit-outer-spin-button,
input[type=number]::-webkit-inner-spin-button { display: none; }
```

---

### Toggle Switch

```css
width: 40px;
height: 22px;
border-radius: 11px;
background: checked ? #16a34a : #d1d5db;
```

Thumb: `16px × 16px`, `border-radius: 50%`, `background: white`, `transition: left 0.2s`  
Left position: checked `21px`, unchecked `3px`

---

### Section Cards (Info/Settings pattern)

All detail cards follow the same structure:

```html
<div style="border: 1px solid #e5e7eb; border-radius: 4px; overflow: hidden; background: #fff">
  <!-- Header -->
  <div style="background: #f8fafc; padding: 11px 20px; border-bottom: 1px solid #e5e7eb">
    <span style="font-size: 11px; font-weight: 700; color: #6b7280; text-transform: uppercase; letter-spacing: 0.6px">
      Section Title
    </span>
  </div>
  <!-- Content -->
  <div style="padding: 20px">
    ...
  </div>
</div>
```

Cards are separated by `gap: 16px` inside a flex column container.

---

### Data Table (Grid View)

The grid view is a `<table>` with `border-collapse: collapse`.

**Colour bar:** First `<thead>` row — 5px tall `<td>` cells, one per supplier column, filled with the supplier colour. Black for the part description column.

**Column headers:** `background: #fff`, `padding: 8px`, `font-size: 10px`, `font-weight: 700`, `color: #6b7280`, `text-transform: uppercase`, `position: sticky`, `top: ~271px`, `z-index: 295`

**Part cell:** `width: 180px`, contains qty input (24px wide, no spinners) and part name/number/list price stacked.

**Price cells:** `width: 96px`, `text-align: center`, `padding: 8px 6px 22px`, `position: relative`, `cursor: pointer`

Price cell content (top to bottom):
1. Type label (`font-size: 10px, font-weight: 700, uppercase, supplier type colour`) + optional comment icon
2. Price amount (`font-size: 16px, font-weight: 800 selected / 500 unselected, color: #222`)
3. Profit (`font-size: 10px, font-weight: 700, color: #16a34a`)
4. ETD (`font-size: 9px, color: #999`)
5. MODIFY button (hidden, revealed on selection — `position: absolute, bottom: 0, left: 0, right: 0`)

**Line status backgrounds:** Apply the corresponding CSS variable from §2 Line Status Colours as the row background — `--line-accent-removed-bg`, `--line-accent-additional-bg`, `--line-accent-supplier-bg`, `--line-accent-modified-bg`, `--line-accent-optional-bg`. Row backgrounds are painted on the `<tr>` (or the row's price cells) beneath the Selected state outline, so a line can be, say, "Modified" *and* "Selected" at the same time — the outline reads on top of the modified-orange background.

**Selected state:** `outline: 2px solid #22c55e` (Tailwind `green-500` — deliberately softer than brand-green so the outline reads as "selected" rather than competing with the primary action colour), `outline-offset: -2px; background: #f0fff4`

> Note: the selected state's `background: #f0fff4` and the line status backgrounds coexist. If a line has a status colour, that colour wins for the base row fill; the selected outline still appears on top to indicate selection. Do not blend the two backgrounds — use the status colour and rely on the outline for selection.

**Part No. Match indicator:** Green corner triangle (`#16a34a`) with white tick — `position: absolute, top: 0, right: 0`

**Totals row:** `background: #f0f0f0`, `border-top: 2px solid #ccc`, `font-weight: 700`, `font-size: 12px`

**Supplier header tooltip:** Appears on hover over column header — same light tooltip style, shows Status, Phone, Type, Delivery, Price Expiry, Supplier Quote #, Settlement Disc.

---

### Data Table (List View)

List view groups parts as sections with a header row per part.

**Part header:** `background: #e8e8e8`, `border-top: 2px solid #bbb`, `border-bottom: 1px solid #ccc`, `padding: 9px 14px`  
Shows: Part name (bold 13px), Dealer Part Nr, Qty input, Dealer List Price.

**Column headers:** `background: #f5f5f5`, `font-size: 11px`, `font-weight: 700`, `color: #666`  
Columns: Supplier | Comments | Qty | Type | Cost | Sell | Margin | Profit | Action

**Supplier rows:** `border-bottom: 1px solid #ebebeb`  
Selected row: `background: #f0fff4`  
Selected values: bold, `color: #111827`

**Line status backgrounds:** In the List View, line status colours are applied at two levels — the part-description header row uses the strong `-200` shade (`--line-accent-<status>-bg`), and every supplier price row grouped beneath uses the softer `-50` shade (`--line-accent-<status>-bg-subtle`). Both must reflect the same status so the whole group reads as one unit. See §2 Line Status Colours for the full state map. When a supplier row is also selected, the selected background (`#f0fff4`) is overridden by the status colour — status wins for the row fill, and bolding + `color: #111827` on the values still indicates selection.

**SELECT button:** `border: 1px solid #ccc`, `background: #fff`, `border-radius: 3px`  
**SELECTED button:** `background: #16a34a` (brand-green / Tailwind `green-600`), `color: white`  
**Modify button:** `border: 1px solid #ccc`, `background: #fff`, appears alongside SELECTED

---

## 8. Navigation

### Top Nav

```css
background: #fff;
border-bottom: 2px solid #ddd;
min-height: 62px;
position: sticky;
top: 0;
z-index: 300;
```

Nav items: `padding: 8px 18px`, `font-size: 10px`, `font-weight: 700`, `letter-spacing: 0.6px`, `text-transform: uppercase`

**Icon circles:** `28px × 28px`, `border-radius: 50%`  
- Inactive: `background: #e0e0e0`, icon fill `#bbb`  
- Active: `background: #16a34a`, icon fill `white`

Active item text: `color: #16a34a`  
Inactive item text: `color: #999`  
Active bottom border: `3px solid transparent` → active tab has no bottom border (the icon circle indicates active state)

---

### Sub-Nav (Check Price)

```css
background: #3a3a3a;
position: sticky;
top: 62px;
z-index: 299;
```

Items: `padding: 10px 36px`, `font-size: 11.5px`, `font-weight: 700`, `letter-spacing: 0.6px`, `text-transform: uppercase`

**Badge circles:** `21px × 21px`, `border-radius: 50%`  
- Inactive: `background: #555; color: #ccc`  
- Active: `background: #16a34a; color: white`

Active item: `color: white`, `border-bottom: 3px solid #16a34a`  
Inactive item: `color: #ccc`, `border-bottom: 3px solid transparent`

---

### Settings Tab Bar

Same style as Sub-Nav — `background: #3a3a3a`. Tabs span the full width.

Tabs: General Settings | Account Settings | Margin Settings | Data Settings  
Each tab has: circle badge with icon + label text + optional NEW pill

**NEW pill on tab:** `background: #16a34a; color: white; font-size: 9px; font-weight: 800; border-radius: 3px; padding: 1px 5px`

---

### Settings Sidebar Nav (future)

Not currently implemented. Pattern would follow: `background: #fff`, `border-right: 1px solid #e5e7eb`, active item `border-left: 3px solid #16a34a; background: #f0fdf4; color: #16a34a`

---

## 9. Summary Bar (Check Price)

The three stat blocks — Your Cost, Your Sell, Your Profit — sit in a white `border-bottom: 2px solid #e5e7eb` bar.

```
position: sticky;
top: 104px; /* nav + sub-nav height */
z-index: 298;
```

**Stat label:** `font-size: 10px; color: #6b7280; font-weight: 500; text-transform: uppercase; letter-spacing: 0.5px`  
**Stat value:** `font-size: 22px; font-weight: 700; color: #111827`  
**Your Profit value:** `color: #16a34a`

**Inline badge pills (below values):**
- Cost: `▼ $X vs list` — green if below dealer list, red if above
- Sell: `▼ $X vs list` — green if below, dark if above
- Profit: `X.X% margin` — always green background

Hovering each stat reveals a `.sitip` tooltip with detailed breakdown.

---

## 10. Toolbar

```
background: #f8fafc;
border-bottom: 1px solid #e5e7eb;
padding: 8px 16px;
position: sticky;
top: 220px;
z-index: 296;
```

Toolbar elements left to right:
1. **Active Rule** — label outside + button showing current rule name + chevron
2. **Quick Select** — label outside + two toggle buttons (Maximum Profit, Minimum Cost). *Replaced the dropdown. OEM Dealer removed — clicking the OEM supplier column header already does this.*
3. **Clear Selections** — beside Quick Select. Disabled until a line is selected
4. **Filter legend** — Dealer Part Match, ETD Alert, Comments, Images, Donor Part
5. **View** — label outside + grid/list icon toggle
6. **List Settings** — gear icon, only visible in list view

**Print** has moved out of the toolbar and now sits with **Cancel Request** and **Save** in the quote actions group.

*Greyed out until conditions are met.

### Margin rule dropdown

One table, used identically on Check Price and Get Price. Both screens call the
same renderer, so they cannot drift apart.

| Rule | OEM | Parallel | Aftm | Reco | Recycled |
|---|---|---|---|---|---|
| ◉ Allianz Standard `Matched` | 100% | 80% | 70% | 85% | 85% |
| ○ NRMA Standard | 100% | 80% | 75% | 75% | 70% |

| Element | Spec |
|---|---|
| Header row | `10px / 700` uppercase `#6b7280`, `1px solid #e5e7eb` beneath |
| Rule name | `12px / 700` `#111827`, with a radio indicator |
| Rate cells | `12px / 600` `#374151`, centred |
| Row divider | `1px solid #f3f4f6` |
| Selected row | `#f0fdf4` background, rates in `#166534` |
| Matched pill | `#dcfce7` fill, `#86efac` border, `#15803d` text, `9px / 800` |
| Matched row | `#fbfefc` tint, hovering to `#f0fdf4` |

**Rates align down the column.** That is the reason for the table: the rule name
column is fixed at 38% and every rate sits under its type heading, so two rules
can be compared at a glance. The previous card grid made that impossible.

**Matched rules are flagged in place, not separated.** They carry a green
Matched pill and sort to the top, but stay in the single list.

> Splitting matched rules into their own group broke the column alignment that
> justified the table, and a group of one with a heading above it is more
> furniture than the flag needs.

**Rate cells show the percentage only.** The pricing method is stripped, whether
it reads "of List" or "Markup on Cost", with the full value kept as a tooltip.

> The method is a rule-level setting, not a per-rate one, so repeating it in
> five columns adds nothing. It also overflows: "100% Markup on Cost" runs past
> the cell and collides with the column beside it.

### Quick Select Toggles

Two-state buttons. The applied state must be obvious at a glance.

| State | Background | Border | Text |
|---|---|---|---|
| Resting | `#fff` | `#d1d5db` | `#374151` |
| Hover | `#f3f4f6` | `#9ca3af` | `#374151` |
| **Applied** | `#fff` | `#16a34a` | `#16a34a` + green tick |

`height: 30px`, `padding: 0 12px`, `border-radius: 3px`, `font-size: 12px`, `font-weight: 600`

Clicking an applied button clears it. Selecting the other switches. Changing the
margin rule **re-runs** an active Quick Select under the new rule, so the button
never claims a selection that is no longer true. Manual selections are never
disturbed by a rule change.

---

## 10a. Control strips

A horizontal strip of controls above the content — the Check Price toolbar, the
Get Price quote bar.

| | |
|---|---|
| Fill | `#ffffff` |
| Corners | square |
| Border | `#d1d5db` normally |
| Border | **`#4ade80` if the strip carries the margin rule** |
| Dividers | 1px `#e5e7eb` between component groups |

**A strip that carries the margin rule takes the green border**, the same as the
Active Margin Rule Card below. One green-bordered surface per screen: whichever
surface holds the rule.

---

## 10b. Active Margin Rule Card

A standalone bordered card so the applied rule stands apart from the page.

```css
background: #fff;
border: 1px solid #4ade80;   /* green-400 — the only green-bordered surface */
padding: 10px 12px;
margin: 0 24px 10px;
border-radius: 0;
```

### Status control

One control that both confirms the rule and opens the picker.

```
[ ✓ MARGIN RULE APPLIED │ Allianz Standard ▾ ]
```

| Element | Spec |
|---|---|
| Button | `#fff`, 1px `#16a34a`, 3px radius, 32px tall |
| Hover | `#f3f4f6` bg, `#15803d` border |
| Tick | `#16a34a`, 15px |
| Label | 10px/700, `#15803d`, uppercase, 0.7px tracking |
| Divider | 1px × 14px, `#22c55e` |
| Rule name | 13px/800, `#16a34a` |
| Chevron | 12px, `#16a34a` |

### Part type indicators

Rates sit beside the picker as **coloured dots with grey text** — a legend, not
controls. No container, no hover, `cursor: default`.

| Element | Spec |
|---|---|
| Dot | 7px circle, `::before` |
| Type label | 11px/600, `#6b7280` |
| Value | 11px/700, `#374151` |
| Gap | 16px between entries |

Dot colours use the **Part Type Colours** already defined in section 2, matching
the grid's column type strips.

> **Do not use pills here.** The pill shape reads as clickable and was rejected
> for that reason.

**No-match prompt removed.** The previous *"No margin rule set up for this insurer"*
prompt is gone. A fallback rule always applies, so the user is never blocked.

---

## 11. Screens

### Check Price
Primary quoting screen. Shows parts grid with supplier pricing. Sticky nav, sub-nav, summary bar, toolbar and column headers. Two views: Grid (default) and List.

**Sub-nav tabs:** Check Price | Info | Images | Documents

### Info
Quote and vehicle metadata. Three white cards: Quote Basic Info, Vehicle Info, No Parts. Same card style as Settings detail cards.

### Documents  
Placeholder for supplier documents. Single card with empty state icon.

### Settings
Tabbed settings page. Four tabs: General Settings | Account Settings | Margin Settings | Data Settings.

**Margin Settings** contains:
- System Templates (read-only, Standard Baseline only)
- Margin Rules (editable, pre-seeded with common insurers)

**Create Rule** is a sub-page of Margin Settings. Grey `#f4f5f7` background with white section cards. Sidebar shows Rule Summary with dark left accent border.

---

## 12. Pricing Logic

### Sell price calculation (per line item)

```
IF rule_method = "% of list"
  sell_price = dealer_list_price × (rule_value / 100)

IF rule_method = "markup on cost"
  sell_price = supplier_cost × (1 + rule_value / 100)
```

### Totals

```
your_cost   = SUM(supplier_cost) for selected parts
your_sell   = SUM(sell_price) for selected parts
your_profit = your_sell − your_cost
```

### Badges

```
cost_vs_list  = your_cost − SUM(dealer_list_price)
sell_vs_list  = your_sell − SUM(dealer_list_price)
profit_margin = (your_profit / your_sell) × 100
```

### Margin Rules — part types

Each rule defines pricing for: OEM | Aftermarket | Reconditioned | Parallel | Recycled

---

## 13. Design Principles

**1. White is the canvas, grey signals focus.**  
White backgrounds are the default. Grey (`#f4f5f7`) is reserved for focused task pages like Create Rule — it signals you've stepped into a sub-task and anchors the white cards visually.

**2. Pills are fixed.**  
Status pill colours have been deliberately chosen and user-approved. Do not replace them with the brand green or other colours.

**3. Sticky context.**  
Everything above the pricing grid is sticky. Users should always be able to see their quote details, financial totals, toolbar controls and column headers while scrolling through parts.

**4. Tooltips are always light.**  
All tooltips use white backgrounds with light borders and shadows. Never use dark backgrounds.

**5. The sell price is never stored — it is always calculated.**  
Sell prices are derived from the active rule at display time. If the active rule changes, all sell prices and totals recalculate automatically.

**6. The brand green is for identity and interaction, not decoration.**  
Use `#16a34a` for active states, confirmation actions, profit values and brand moments. Use the Tailwind green scale for backgrounds and pill colours.

**7. Consistent card pattern.**  
Detail cards always follow the same structure: `#f8fafc` header with uppercase label, `1px solid #e5e7eb` border, `6px` radius, white content area. The Rule Summary card is the exception — it uses a `4px solid #1f2937` left accent to signal it is a reference panel, not an input section.

**8. Typography hierarchy is simple.**  
Headings are `#111827`, body is `#374151`, secondary is `#6b7280`, metadata is `#9ca3af`. Green text is brand green `#16a34a` only.

**9. Labels sit outside controls.**  
Dropdowns and selects always have their label as plain text to the left (e.g. "Active Rule:", "Quick Select:", "View:") — never inside the control as a default option. Exception: the Quick Select `— None —` placeholder which indicates an unset state.

**10. Breadcrumb for context switches.**  
When a user navigates from a quote to Settings, a back link banner appears in amber at the top of Settings: *"You navigated here from Quote 89734. ← Return to quote."* This disappears when returning to the quote.

---

## 14. Icons

**Font Awesome 6 Free** (`cdnjs.cloudflare.com`) is loaded for:
- `fa-solid fa-comment-dots` — comment indicator on price cells

All other icons are inline SVGs. Sizing conventions:
- Nav circle icons: `14px × 14px`
- Toolbar / action icons: `13–14px`
- Badge / cell icons: `9–11px`
- Page icons (empty states): `28–32px`

**Supplier avatars:** Person/user SVG path inside a coloured `border: 2px solid [supplier colour]` circle, `22–24px` diameter.

---

## 15. Accessibility Notes (to be expanded)

- All interactive elements should have `cursor: pointer`
- Disabled states use `cursor: not-allowed` and colour change (not opacity alone)
- Tooltips are `pointer-events: none` and positioned with `position: fixed`
- Modals trap focus when open (to be implemented)
- Colour is never the only indicator of state — text labels accompany all status changes

---

*Last updated: June 2026 — primary green moved to Tailwind `green-600` (`#16a34a`) with hover at `green-700` (`#15803d`); the standalone `list-green` token was retired; List View SELECTED button now uses brand green; Grid View selected cell outline moved to Tailwind `green-500` (`#22c55e`) for a softer "selected" read that doesn't compete with primary actions. Added Line Status Colours (§2) for row states across both views — Removed (`red`), Additional (`sky`), Supplier (`amber`), Modified (`orange`), Optional (`green`). Each status has two shades: `-200` (part row / Grid View / List View part header) with CSS variable `--line-accent-<status>-bg`, and `-50` (List View supplier price rows) with CSS variable `--line-accent-<status>-bg-subtle`. The entire green palette (except part-type colours) is now stock Tailwind with no custom theme overrides. Maintained alongside the PartsCheck prototype. Update this document whenever a design decision changes.*

---

## 16. Modals

All modals follow a single standard. The **Supplier Associations modal** is the reference implementation. **Do not use coloured (green or brand) modal headers** — all headers are `#f8fafc` (Tailwind slate-50) with `#111827` dark text regardless of context.

### Overlay
```css
position: fixed; inset: 0;
background: rgba(0,0,0,0.45);
z-index: 800;
display: flex; align-items: center; justify-content: center;
```

### Container
```css
background: #fff;
border-radius: 3px; /* NOT 8px */
box-shadow: 0 20px 60px rgba(0,0,0,0.25);
overflow: hidden;
```

### Header `.mhd`
```css
background: #f8fafc; /* Tailwind slate-50 */
padding: 14px 20px;
border-bottom: 1px solid #e5e7eb;
display: flex; align-items: center; justify-content: space-between;
```

| Element | Style |
|---|---|
| Title `.mht` | `font-size: 13px; font-weight: 700; color: #111827` |
| Subtitle `.mhs` | `font-size: 11px; color: #6b7280; margin-top: 2px` |
| Close `.mhx` | `color: #9ca3af; font-size: 18px; background: none; border: none` |

### Footer `.emf`
```css
padding: 12px 20px;
border-top: 1px solid #e5e7eb;
display: flex; justify-content: flex-end; gap: 8px;
background: #f9fafb;
```

### Buttons
| Type | Style |
|---|---|
| Cancel | `border: 1px solid #d1d5db; background: #fff; color: #374151` |
| Primary | `background: #16a34a; color: #fff; border: none` |
| Destructive | `background: #ef4444; color: #fff; border: none` |

Destructive modals may show a small red circle icon (`background: #fef2f2; stroke: #ef4444`) alongside the standard `#f8fafc` (slate-50) header — the header background does not change to red.

---

## 16b. Anchored Popover (Modify)

**Replaces the full-screen modal** for per-cell pricing edits. Anchored to the
cell being edited rather than centred on the screen.

### Container
```css
width: 320px;
max-width: calc(100vw - 16px);
background: #fff;
border: 1px solid #d1d5db;
border-radius: 4px;
box-shadow: 0 8px 24px rgba(0,0,0,.14);
z-index: 800;
```

### Positioning

1. Below the cell, centred, 1px overlap — **if it fits at full height**
2. Otherwise **above** the cell, at full height
3. Only if it fits neither: cap the body and scroll, on whichever side has more room

> Never scroll internally when flipping above would avoid it. A scroll inside a
> short panel was the main complaint about the previous behaviour.

Closes on outside click or Escape. Re-anchors on scroll and resize. Hover tooltips
are suppressed while open, so the two never stack.

Opens pre-selected on the pricing method **currently applied to that cell** — an
existing override if one exists, otherwise the active margin rule.

### Form fields

No section headings. Labels sit **inline** to the left in a fixed 92px column, so
both fields align.

```
Display Format   [ Type or select...        ⌄ ]
Part Number      [ 86510-G3700                ]
```

Combo fields carry a 12px `#6b7280` caret inside the field on the right, with
`padding-right: 26px` so text cannot run under it, and `pointer-events: none` so
clicking it still opens the list.

### Pricing method list

Five options as a tight radio list. **Chrome only on the selected row.**

| | Resting | Selected |
|---|---|---|
| Background | transparent | `#f0fdf4` |
| Border | transparent | `#86efac` |
| Label | 11px/500 `#374151` | same, weight 600 |
| Figures | `#c3c7cd` | `#374151` |

Row padding `3px 7px`, 1px gap. All value fields **62px**, right-aligned. No
trailing `%` — the labels already say it, and it pushed those rows out of
alignment with the `$` rows.

### Stepper

▲▼ to the left of the field on percentage methods.

```css
width: 15px; height: 9px;
background: #f9fafb;
border: 1px solid #d1d5db;
```
Steps by 10, clamped to the field's min/max, disables with its row. Fields also
carry `step="10"` so keyboard arrows match.

### Scope

An override applies to **one cell only** — that part, that supplier — keyed on
`partId|supplierId`. It outranks the margin rule, so a later rule change does not
disturb it. **Reset** clears the override and returns the cell to the rule.

---

## 17. Sub-Nav Count Pill — Unread Treatment

Used on Images and Documents tabs to indicate unseen content. The pill sits inline after the tab label.

**Unread state** (default until user clicks the tab):
```css
background: #fff;
border: 1px solid #e5e7eb;
color: #ef4444;        /* red-500 */
font-size: 9px;
font-weight: 700;
border-radius: 10px;
padding: 1px 6px;
min-width: 18px;
position: relative;
```

A red dot sits above the pill:
```css
position: absolute;
top: -4px;
right: -4px;
width: 7px;
height: 7px;
border-radius: 50%;
background: #ef4444;           /* red-500 */
border: 1.5px solid #404040;   /* matches nav background — cut-out effect */
```

**Read state** (after user clicks the tab):
```css
color: #6b7280;        /* gray-500 */
border-color: #e5e7eb;
/* red dot: display: none */
```

Transition triggered by the tab's `onclick` handler. No animation — instant state change.

---

## 18. Documents Tab — Table Layout

The Documents card uses a table matching the Applied Associations table in Data Settings.

**Table header row:**
```css
background: #f8fafc;
border-bottom: 1px solid #e5e7eb;
font-size: 10px;
font-weight: 700;
color: #6b7280;
text-transform: uppercase;
letter-spacing: 0.5px;
padding: 8px 14px;
```

**Table body rows:**
```css
padding: 10px 14px;
border-bottom: 1px solid #e5e7eb;
hover: background #f8fafc;
```

**Columns:** Supplier (display name, not raw ID) | File Name (type badge + name + size/date) | Download (styled button)

**File type badge:**
```css
width: 30px;
height: 36px;
background: #ef4444;   /* red-500 for PDF */
border-radius: 3px;
color: #fff;
font-size: 8px;
font-weight: 800;
```

**Download button:** `border: 1px solid #e5e7eb; border-radius: 3px; padding: 5px 12px; font-size: 11px; font-weight: 600; color: #374151` — not a plain text link.

---

## 19. Tooltip Headers

All tooltip headers use `.tth`:

```css
font-size: 10px;
font-weight: 700;
text-transform: uppercase;
letter-spacing: 0.5px;
text-align: center;
border-bottom: 1px solid #f3f4f6;
margin-bottom: 6px;
padding-bottom: 5px;
```

**Colour** — always the supplier's type colour, not a fixed colour:
- Price cell tooltip: uses `TYPE_COLOR` (part type colour)
- Supplier header tooltip: uses `SUP_COLORS[sid]`

**Alignment** — centre aligned on all tooltips.

---

## 20. Supplier Response Tooltips

Hover over a supplier response dot (coloured circle in the grid header) to see a tooltip showing:
- Header: Part type + RECEIVED in supplier type colour, centre-aligned
- Rows: Supplier name, Phone, Parts Priced, Quote Ref

---

## 21. Price Cell Corner Indicators

### Part No. Match (Flame)
Green triangle (`#16a34a`) in the top-right corner of a price cell. Contains an inline SVG flame icon (no FA4 equivalent). Tooltip: "Part No. Match".

### Chip stroke rule

**Every chip carries a 1px stroke one step darker than its own fill.** This keeps
the set visually even — no chip should read as heavier than its neighbours.

| Chip | Fill | Stroke |
|---|---|---|
| Dealer Part Match | `#16a34a` | `#15803d` |
| ETD Alert | `#d97706` | `#b45309` |
| Comment | `#d1d5db` | `#9ca3af` |
| Image | `#0891b2` | `#0e7490` |
| Donor Part | `#1d4ed8` | `#1e40af` |

> The comment chip briefly used a `#4b5563` stroke, inherited from the `fa-exclamation`
> chip it replaced. That dark outline was needed to hold a thin glyph's shape; a
> solid speech bubble does not need it, and it made the chip the heaviest in the
> set. Do not reintroduce it.

Legend swatches use the same fills and strokes as the cell chips, at 12px with
`box-sizing: border-box` so the stroke does not change the footprint.

### Comment (Speech Bubble)

`fa-comment` in a grey chip. Shown when the line carries a **comment only** —
photos have their own chip.

| | |
|---|---|
| Size | 16×16, 2px radius |
| Background | `#d1d5db` |
| Border | `1px solid #9ca3af` |
| Icon | `fa-comment`, 8px, `#4b5563` |

*Changed from `fa-exclamation`, which read as a warning rather than a message.*

The comment chip is the only one with an unsaturated fill and a dark icon rather
than a white one. That is deliberate — comment is the quietest signal in the
priority order below.

### Image (Camera)

`fa-camera` in a cyan chip. Shown when a supplier has attached a photo to the
quote line.

| | |
|---|---|
| Size | 16×16, 2px radius |
| Background | `#0891b2` |
| Border | `1px solid #0e7490` |
| Icon | `fa-camera`, 8px, white |

*Cyan rather than another blue: Donor Part is `#1d4ed8` and the two pills sit
adjacent in the legend, where two blues would be hard to separate at pill size.*

### ETD Alert (Clock)

`fa-clock-o` in an amber chip. Shown when the supplier's ETD is at or beyond the
**Long ETD** threshold set in Settings.

| | |
|---|---|
| Size | 16×16, 2px radius |
| Background | `#d97706` |
| Border | `1px solid #b45309` |
| Icon | `fa-clock-o`, 9px, white |

### Stacking order and priority

Chips stack vertically in the top-right corner in this order:

| | | Why |
|---|---|---|
| 1 | Dealer Part Match **or** Donor Part | Sourcing — changes which option you would pick |
| 2 | ETD Alert | Operational — changes whether you *can* pick it |
| 3 | Image | Evidence — helps verify the part |
| 4 | Comment | Context — usually qualifies the above |

Match and Donor are mutually exclusive in practice and occupy the same slot, so
the practical maximum is four.

**Show the chips; do not rely on filter highlighting alone.** Measured across a
full quote, no cell carried more than 2 chips and 52% carried none — the vertical
stack fits four in a 76px cell. Hiding them would remove passive discovery: a user
comparing prices would have no signal that an option carries a six-week ETD unless
they thought to apply a filter they had no reason to suspect applied.

If a cell ever exceeds four, cap at three plus a subtle `+1` rather than shrinking
the chips.

### Donor Part Match (Blue Star)
Blue triangle (`#1d4ed8`) in the top-right corner. Contains a ★ character. Tooltip: "Donor Part Match".

---

## 21b. Empty States

Match the section they sit in — white card, not a bare outline.

```css
background: #fff;
border: 1px solid #d1d5db;
border-radius: 0;
padding: 32px 20px;
text-align: center;
```

| Element | Spec |
|---|---|
| Icon | `fa-file-o`, 22px, `#9ca3af` (never an emoji) |
| Heading | 14px/700, `#374151` |
| Body | 12px, `#9ca3af` |
| Action | primary green `#16a34a`, 12px/700, `8px 20px`, 3px radius |

---

## 22. Margin Rules — Insurer Mapping (Debtor Mapping)

Each margin rule has an **Applies To** field — a list of debtor names that should be matched against the quote's work provider/insurer name.

- Matching is case-insensitive exact string match
- A debtor name can only belong to one rule — enforced at UI level via amber conflict prompt
- Standard Baseline has no debtors and always appears as the fallback
- The rule dropdown shows every rule in one table. Rules whose debtors match the quote carry a **Matched** pill and sort to the top; they are not split into a separate group

---

## 23. Role-Based Access — Margin Settings

| Role | Can View | Can Edit | Can Create | Can Delete |
|---|---|---|---|---|
| Owner | ✓ | ✓ | ✓ | ✓ |
| Manager | ✓ | ✓ | ✓ | ✗ |
| Estimator | ✓ | ✗ | ✗ | ✗ |

Estimators see margin rules in read-only mode. Edit controls (pencil, Add Rule button, inline edit, delete) are hidden.

---

## 24. Donor Parts Scheme

When `SITE_DONOR_ENABLED = true` a Donor Parts row appears in the Margin Settings rule form below the Recycled row. It maps the donor parts scheme to an insurer (Allianz / Suncorp / IAG / Not mapped).

Donor part matches are shown in the price grid with a blue corner triangle indicator (see Section 21).

---

## 25. Settings — Additions

### Price Grid Display

Dropdown controlling what shows beneath the price on every Check Price cell:
**Profit** ($), **Margin** (%), or **Hide**. Applies to the whole grid at once.

### Settlement Discounts

| Setting | Default |
|---|---|
| Apply Settlement Discounts | **No** |
| Show Settlement Discounts to Dealers | **No**, and dependent on the above |

When off, Invoice Cost and Settlement Discount are hidden everywhere — cell, price
hover, list panel and supplier hover.

### ETD Alerts — not configurable

There is **no ETD setting**. Alerts are always on, with a fixed threshold of
**1 Week**: any supplier quoting an ETD at or beyond that is flagged.

The threshold compares against the supplier-side ETD list, in order:

`Same Day · 1-2 Days · 2-3 Days · 4-5 Days · 1 Week · 2-3 Weeks · 4-6 Weeks · 6 Weeks+ · NLA`

Because it is an ordinal list rather than free text, "longer than X" is a position
comparison. NLA ranks last, so an unavailable part is always flagged.

*A configurable version was built and removed. Making the alert optional meant a
user could hide the chips entirely, losing the passive signal that a part is weeks
away — the one indicator most likely to cause a problem discovered too late.*

### Dependent settings pattern

Where a setting is meaningless without its parent:

```css
opacity: 0.45;
cursor: not-allowed;
```
Label greys to `#9ca3af`, neither option reads as selected, and the help text
swaps to *"Available once {parent} is on."*

### Part type acceptance

Each part type row in a rule carries an **Accepted** Yes/No control, separate from
its pricing method.

> Acceptance and pricing are independent questions. *Does this insurer accept this
> part type?* drives the flag. *What do we charge if it gets used anyway?* always
> needs an answer. "Not Acceptable" was previously an option in the pricing method
> dropdown, which meant choosing it left nothing to price with.

- Setting **No** auto-fills **Markup on Cost at 20%**, which stays editable
- Setting it back to **Yes** leaves the pricing alone — the user may have tuned it
- Stored as `notAccepted: ['Recycled','Reconditioned']` on the rule

**On Check Price**, refused part types appear as red pills in the existing
exceptions strip, and selecting one raises a confirm dialog — acknowledged **once
per part line**, not once per quote. The part still prices normally.

*Temporary home. Phase 2 introduces a Part Restrictions section; acceptance is the
same kind of statement and should fold into it. See `phase-2-notes.md`.*

#### Not-accepted pills in the exceptions strip

Refused part types appear as pills in the existing amber exceptions strip, before
any rule exceptions.

```
⚠  Not accepted: [● Aftermarket] [● Recycled]  │  Exceptions: ...
```

**The pill takes the colour of the part type it names** — not a generic red or
warning colour. A user reading "Aftermarket" should see the same purple they see
on the grid column strip and the rule-card legend dot.

| | |
|---|---|
| Fill | `#ffffff` — lifts off the amber `#fffbeb` strip |
| Border | the part type's **true** colour |
| Dot | 6px circle, the part type's **true** colour |
| Text | a **darker shade** of the same hue (see below) |
| Label | "Not accepted:" in `#92400e`, matching the strip |

**Text uses a darker shade, deliberately.** The true type colours fail contrast on
white — Recycled 1.98:1, Reconditioned 2.15:1, Aftermarket 3.96:1. Splitting the
colour keeps the pill recognisable as that part type while staying readable.

| Part type | Dot / border | Text | Text on white |
|---|---|---|---|
| OEM | `#2563eb` | `#1d4ed8` | 6.70:1 |
| Aftermarket | `#a855f7` | `#7e22ce` | 6.98:1 |
| Reconditioned | `#f59e0b` | `#b45309` | 5.02:1 |
| Parallel | `#6b7280` | `#4b5563` | 7.56:1 |
| Recycled | `#84cc16` | `#4d7c0f` | 4.99:1 |

> Do not use the true colour for the text to "match" the dot. Three of the five
> fail AA, and lime on white is effectively unreadable.

#### Confirm dialog

Selecting a refused part raises the **standard modal** — `.mo` / `.md` / `.mhd` /
`.emf`, 420px wide, `#f8fafc` header with a close ✕, and **Accept / Cancel** in
the footer. It is not a bespoke alert box.

**Cancel takes the primary treatment**, not Accept. The dialog warns that the
insurer may not approve the part, so the safe path carries the emphasis.

> **Title:** {Part type} parts not accepted
> **Body:** This part type has been flagged as not acceptable by the insurer. It
> will be priced at **{rate}** and may not be approved.

The rate is computed live from the active rule, so it reflects what that part type
is actually set to.

Copy notes:
- The **part type leads**, not the insurer. The user knows which insurer they are
  quoting; what they need is which part type is the problem.
- *"may not be approved"* rather than *"the insurer may reject it"* — softer, and
  accurate. Rejection is not certain.
- Acknowledged **once per part line** (`partId|supplierId`), not once per quote.
  Each line is a separate commercial decision.

### Yes/No controls — use one pattern

Settings uses **one** Yes/No component: a pair of radio-style buttons with a green
ring and `#f0fdf4` fill when selected.

Do not introduce sliding toggles. A slider communicates on/off but leaves the
values implicit; the radio pair states both, and handles disabled and
indeterminate states — which dependent settings rely on.

### Rule form validation

Mapping an insurer already held by another rule **blocks the save**:

> ⚠ "NRMA Insurance" is already mapped to "NRMA Standard" - remove it from that
> rule first, or map a different insurer here.

Amber `#d97706`, 11px, driven by live state so it clears the moment the insurer is
removed. Save stays disabled while any conflict exists, and the footer names the
insurer.

### Section count pills

`2 provided`, `5 rules` — white fill, `#d1d5db` border. These sit directly on the
grey page rather than inside a card, so the lighter `#e5e7eb` border used
elsewhere is too faint.

---

## Get Price — Quote Bar

One white card with a green outline holding every decision that applies to the
whole quote. Sections are separated by dividers, not by their own borders.

```
Quote Type: ⓘ ◉ Competitive ○ Direct │ ✓ MARGIN RULE APPLIED │ Allianz ⌄ │ Prices Needed By: [9:30][10:00][11:00][More…] │ Today, 11:00am  18 parts to 7 suppliers  [SUBMIT QUOTE]
```

| Element | Spec |
|---|---|
| Bar | `#fff`, `1px solid #4ade80`, `3px` radius, `align-items: center`, wraps |
| Divider | `::before` pseudo-element, `1px × 30px`, `#e5e7eb`, vertically centred |
| Group label | `12px / 600` `#374151`, sentence case with a colon |
| Quote type | Radio pair, `accent-color: #16a34a` |
| Margin rule | 32px, `1px solid #16a34a`, `3px` radius |
| Time slot | 32px, `13px / 700`, `#d1d5db` border |
| Slot selected | White fill, `#16a34a` border and text, green tick |
| More… | 32px, `1px dashed #d1d5db`, `#374151` |
| Resolved time | `19px / 800` `#16a34a` |
| Summary | `12px / 600` `#6b7280`, figures `14px / 800` `#111827` |
| Submit | 30px, `#16a34a`, no stroke |

**The divider is a fixed 30px pseudo-element, not a border.** A `border-left`
takes the height of whatever section it sits beside, so the dividers ended up
different lengths. A pseudo-element is the same height regardless.

**Breakpoints.** At `1240px` the groups take a grid with a shared baseline and
the summary section drops to its own row; at `760px` everything stacks. The bar
carries its own vertical padding so a wrapped row never sits flush against the
edge.

### Urgency

Anything inside three hours is urgent, and the slots enforce it rather than
warning about it:

| Timeframe | Slots offered |
|---|---|
| Normal | +3h, +3.5h, +4h, +4.5h |
| Urgent | +30m, +1h, +1.5h, +2h |

Urgent turns the time area amber — selected slot `#d97706`, resolved time
`#b45309` — and shows a `⚠ URGENT` pill. Changing the Timeframe regenerates the
four slots immediately.

### Direct Purchase

Selecting Direct Purchase swaps **Prices Needed By** for **Supply Date**: the
time slots and More… hide, a date field appears, and the summary names the
supplier instead of counting them — *"18 parts to West End Hyundai"*. With no
supplier chosen it reads *"no supplier selected"* in grey.

---

## Get Price — Cards

Three fixed-height cards: Parts to Quote, Suppliers, Photos and Comments.

| Element | Spec |
|---|---|
| Card height | `560px`, set by `--card-h` |
| Card body | `overflow-y: auto` — each card scrolls on its own |
| Table headings | `position: sticky; top: 0` inside the scrolling body |
| Column widths | Three equal thirds |

**Cards hold one height and scroll their own body**, so the three stay level and
the page does not grow with the longest list.

### Parts to Quote

Part type columns are hidden by default behind an **Edit types** toggle in the
card header. When shown, the table takes a `430px` minimum width and the card
scrolls sideways — the four 38px type columns would otherwise crush the
description and the checkboxes would sit over the text.

The `<col>` elements collapse to zero width when hidden as well as the cells;
with `table-layout: fixed` the colgroup reserves width even for hidden cells, so
hiding only the cells leaves the columns' width behind.

**Comments sit under their part, always visible.** A part with a comment shows
its text; a part without shows *"Add comment"* in `#c3c7cd`. Clicking into a
description opens that row's comment field. There is no chip and no hover
reveal — a comment is its own indicator, so an icon repeating that was noise.

The divider closes the part-and-comment pair rather than sitting between them,
otherwise the comment reads as belonging to the next part.

### Suppliers

Part type is shown as a coloured dot beside the type name: `7px` circle in the
true part-type colour, with the name in `#374151` `12px / 600`. The dot carries
the colour so the text does not have to, which keeps it readable.

---

## Get Price — Show Details

A green text link in the quote header, not a button — it sits in a line of plain
text and a bordered control would interrupt it.

| Element | Spec |
|---|---|
| Toggle | `12px / 700` `#16a34a`, no fill or border, chevron rotates when open |
| Panel | `#fff`, `1px solid #e5e7eb`, two columns, `align-items: stretch` |
| Section heading | `#f8fafc` strip, `1px solid #e5e7eb` beneath, `11px / 700` `#6b7280` uppercase — identical to a card header |
| Field label | `11px / 600` `#6b7280` |
| Field value | `12px / 700` `#374151`, borderless, transparent |
| Field hover | `border-bottom: #d1d5db` |
| Field focus | `border-bottom: #16a34a` |
| Required marker | `*` in `#ef4444` |

**Two areas**: Quote on the left (Quote Number, Claim Number), Vehicle on the
right in the standard order — Registration, VIN, Make, Model, Model Number,
Body, Colour, Transmission, Series, Month, Year. Make, Body, Month and Year are
dropdowns.

**Fields are borderless.** They read as text until touched, matching the part
description on the grid. A panel of stroked boxes reads as a form to be filled
in rather than details to be checked.

**Required:** Quote Number, VIN, Make, Model, Month, Year. Flagged on blur, not
while typing. Submitting with one empty opens the panel and focuses the first
missing field — otherwise the message points at something collapsed.

Editing Make, Model, Year, Registration or Quote Number updates the header line
above.

---

## Sticky Navigation

| Element | Spec |
|---|---|
| `.nav-top` | `position: sticky; top: 0; z-index: 400` |
| `.nav-sub` | `position: sticky; top: var(--nav-h); z-index: 399` |

**The sub nav's offset is measured, never hard-coded.** `syncNavOffsets()` reads
the top nav's height on load and on resize and writes it to `--nav-h`.

> Hard-coded offsets — `62px`, `137px`, `97px` — are what detached the headers
> when the layout changed. A measured value survives a nav that grows.

**Nothing above a sticky element may set `overflow`.** An ancestor with
`overflow: hidden`, `auto` or `scroll` silently disables sticky positioning, with
no error and no visible cause.


---

## 26. Principles Added by This Work

1. **A green border marks the one rule-bearing surface on a screen.** It is not a
   general card treatment.
2. **Rate indicators are a legend, not controls** — coloured dot, bare text, no
   container, no hover. Pills read as clickable.
3. **Prefer flipping a popover over scrolling it.** Anchored panels open above
   rather than making the user scroll inside a short panel.
4. **Dim the figures, not the copy.** In a list of options, unselected rows keep
   readable labels; only their values recede.
5. **An empty field shows its placeholder, which `color:` does not reach.** Style
   `::placeholder` separately or it will not dim with the rest of its row.
6. **Every chip carries a stroke one step darker than its own fill.** No chip
   should read as heavier than its neighbours.
7. **A pill naming a part type carries that part type's colour.** Never a generic
   warning colour — the user should recognise the type before reading the word.
   Where contrast fails, darken the text and keep the true colour on the dot and
   border rather than abandoning the hue.
8. **Passive signals beat filters for discovery.** A filter answers a question the
   user already has; a chip tells them there is a question worth asking.
9. **A control that asserts state must stay true.** If the underlying data
   changes, either re-run the action or drop the state — never leave a button
   claiming something that no longer holds.

# PartsCheck — Design & Style Guide

> This document is the single source of truth for the PartsCheck UI. It covers colours, typography, spacing, components, navigation, screen patterns and design principles. All new development should reference this guide. When a decision is made that changes or extends the design system, this document should be updated.

---

## 1. Brand

**Product name:** PartsCheck  
**Tagline:** Parts pricing, simplified.  
**Audience:** Panel repairers, estimators, workshop managers, insurers.

---

## 2. Colour System

### Primary Brand Green

| Token | Hex | Usage |
|---|---|---|
| `brand-green` | `#16a34a` | Nav active states, selected tab underlines, Save buttons, quote number text, tooltip headers, profit text, selected count |
| `brand-green-dark` | `#15803d` | Hover state on green buttons, border on green buttons |

> The brand green is used for identity and interaction. Do not use it for backgrounds — use the Tailwind green scale for that.

### Action & Status Greens (Tailwind scale)

These are used for pills, badges, selected states and backgrounds. **Do not replace these with the brand green.**

| Token | Hex | Usage |
|---|---|---|
| `green-50` | `#f0fdf4` | Selected cell background, pill backgrounds |
| `green-100` | `#dcfce7` | DEFAULT badge background |
| `green-200` | `#bbf7d0` | Borders on green pills |
| `green-500` | `#16a34a` | Primary action (same as brand) |
| `green-600` | `#15803d` | Button hover |
| `green-700` | `#15803d` | Dark text on light green |
| `green-800` | `#166534` | Text on DEFAULT badge |

### List View Green

| Token | Hex | Tailwind | Usage |
|---|---|---|---|
| `list-green` | `#16a34a` | green-600 | Selected row highlight, SELECT/SELECTED buttons in list view |

### Grey Scale (Tailwind)

| Token | Hex | Usage |
|---|---|---|
| `slate-50` | `#f8fafc` | Table column headers, card section headers |
| `gray-50` | `#f9fafb` | Row hover, button fills, alternate row bg |
| `gray-100` | `#f3f4f6` | Inactive badges, light dividers, page background |
| `gray-200` | `#e5e7eb` | Borders, card borders, table dividers |
| `gray-300` | `#d1d5db` | Stronger borders, input borders |
| `gray-400` | `#9ca3af` | Placeholder text, secondary labels |
| `neutral-200` | `#e5e5e5` | Nav icon circle inactive background |
| `neutral-400` | `#a3a3a3` | Inactive nav text, icon fill on inactive circles |
| `gray-500` | `#6b7280` | Body text, descriptions, tooltip labels |
| `gray-700` | `#374151` | Primary body text |
| `gray-800` | `#1f2937` | Sidebar accent border, dark buttons |
| `gray-900` | `#111827` | Headings, strong emphasis, body colour |

### Part Type Colours

All part type colours are Tailwind standard. Used for cell type labels, tooltip type rows, and active rule pills.

| Type | Hex | Tailwind | Notes |
|---|---|---|---|
| OEM | `#2563eb` | blue-600 | Closest to current system `#3067cb` |
| Aftermarket (AftM) | `#a855f7` | purple-500 | Closest to current system `#a852ba` |
| Used / Recycled | `#84cc16` | lime-500 | Closest to current system `#6bc23c` |
| Reconditioned (Reco) | `#f59e0b` | amber-500 | Closest to current system `#e99f24` |
| Parallel | `#6b7280` | gray-500 | Neutral — no insurer mandate |

### Active Rule Pills

Parallel and Recycled are deliberately swapped from the type colours — Recycled gets lime (matches Used type), Parallel stays neutral grey.

| Pill | Text | Background | Border | Tailwind |
|---|---|---|---|---|
| OEM | `#2563eb` | `#eff6ff` | `#bfdbfe` | blue-600 / blue-50 / blue-200 |
| Aftm | `#a855f7` | `#faf5ff` | `#e9d5ff` | purple-500 / purple-50 / purple-200 |
| Reco | `#f59e0b` | `#fffbeb` | `#fde68a` | amber-500 / amber-50 / amber-200 |
| Recycled | `#65a30d` | `#f7fee7` | `#d9f99d` | lime-600 / lime-50 / lime-200 |
| Parallel | `#6b7280` | `#f9fafb` | `#e5e7eb` | gray-500 / gray-50 / gray-200 |

### Semantic Colours

| Colour | Hex | Tailwind | Usage |
|---|---|---|---|
| Red (destructive) | `#ef4444` | red-500 | Delete buttons, error states |
| Red background | `#fef2f2` | red-50 | Destructive button background |
| Red border | `#fecaca` | red-200 | Destructive button border |
| Amber | `#d97706` | amber-600 | Warning, supplier discount flag |
| Amber background | `#fffbeb` | amber-50 | Warning banners |
| Amber border | `#fde68a` | amber-200 | Warning banner borders |
| Blue | `#1d4ed8` | blue-700 | Donor parts indicator, info states |
| Blue background | `#eff6ff` | blue-50 | Donor parts background |
| Blue border | `#bfdbfe` | blue-200 | Donor parts borders |

### Dark Surfaces

| Token | Hex | Tailwind | Usage |
|---|---|---|---|
| `nav-dark` | `#404040` | neutral-700 | Top nav bar, settings tab bar |
| `nav-circle-hover` | `#4a4a4a` | — | Nav icon circle hover (between neutral-600/700) |
| `sidebar-dark` | `#1f2937` | gray-800 | Rule Summary left accent border, dark buttons |
| `toast` | `#1a1a2e` | — | Toast notification background (intentionally dark, do not change) |
| `form-bg` | `#f4f5f7` | — | Background for focused task pages e.g. Create Rule |

---

## 3. Typography

**Font family:** `-apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif`  
System font stack — no external font loaded. Clean, fast, neutral.

### Type Scale

| Size | Usage |
|---|---|
| `9px` | Badge labels (SYSTEM, DEFAULT, NEW), tiny metadata |
| `10px` | Column headers (uppercase), tooltip labels, ETD label, badge/pill text — intentionally small UI chrome only. **Not used for body-level text or descriptions.** |
| `11px` | Section card headers (uppercase), pill text, sub-labels |
| `12px` | Body text, descriptions, table data, form labels, nav sub-items — **minimum size for readable body-level content** |
| `13px` | Primary body text, rule values, modal content |
| `14px` | Card headings (System Templates, Margin Rules, Create Rule heading) |
| `16px` | Page headings (Info, Documents) |
| `22px` | Selected count in grid header |

> **Note:** 10px is not a standard Tailwind size (`text-xs` = 12px). Use 10px only for intentionally small UI chrome (column headers, tooltip meta, badges, pills). All body-level labels and descriptions must be 12px minimum.

### Weights

| Weight | Usage |
|---|---|
| `400` / normal | Body text, descriptions |
| `500` | Sub-nav labels, secondary nav links |
| `600` | Form labels, table values, button text (secondary) |
| `700` | Section headings, column headers, badge text, most UI labels |
| `800` | Page headings, section titles (System Templates, Margin Rules) |
| `900` | Price amounts in grid cells |

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
| Cards (Info, Settings tables) | `1px solid #e5e7eb` | `4px` |
| Create Rule section cards | `1px solid #e5e7eb` | `4px` |
| Buttons (primary) | none | `4px` |
| Buttons (secondary) | `1px solid #d1d5db` | `4px` |
| Inputs | `1px solid #d1d5db` | `4px` |
| Dropdowns / panels | `1px solid #d1d5db` | `4px` |
| Tooltips | `1px solid #e5e7eb` | `6px` |
| Modals | none | `8px` |
| Badges / pills | none | `10px–20px` (fully rounded) |
| Small badges (SYSTEM, DEFAULT, NEW) | none | `3px` |
| Rule Summary card | Top/Right/Bottom: `1px solid #e5e7eb`, Left: `4px solid #1f2937` | `4px` |
| Nav badge circles | none | `50%` |

> **Standard button radius is `4px` across all button types.** `6px` was considered too consumer/app-like for a B2B data product. Tooltips (`6px`) and modals (`8px`) are exceptions — they are floating surfaces, not interactive controls.

---

## 6. Shadows

| Context | Shadow |
|---|---|
| Tooltips | `0 8px 24px rgba(0,0,0,.10)` |
| Modals | `0 20px 60px rgba(0,0,0,.25)` |
| Dropdowns (rule picker, print menu) | `0 12px 36px rgba(0,0,0,.15)` |
| Green action buttons | `0 2px 8px rgba(15,168,62,.3)` |

---

## 7. Components

### Buttons

#### Primary (Green)
```css
background: #16a34a;
color: white;
border: none;
border-radius: 6px;
padding: 7px 16px;
font-size: 12px;
font-weight: 700;
cursor: pointer;
```
Hover: `background: #15803d`

#### Secondary (Bordered)
```css
background: white;
color: #374151;
border: 1px solid #d1d5db;
border-radius: 4px;
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
border-radius: 4px;
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
border-radius: 6px;
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
- Value: `font-size: 10px; color: #111827; font-weight: 600`
- Green value: `color: #16a34a`
- Amber value: `color: #d97706`
- Row divider: `border-bottom: 1px solid #f3f4f6`

**Tooltip positioning:** Use JavaScript to calculate `position: fixed` top/left on `mouseover`. Flip above the element when within 300px of the bottom of the viewport.

---

### Modals

```css
overlay: rgba(0,0,0,.45), position: fixed, inset: 0, z-index: 800
modal: background: white, border-radius: 8px, width: 480px, max-width: 95vw
shadow: 0 20px 60px rgba(0,0,0,.25)
```

**Modal header:** `padding: 16px 20px`, `border-bottom: 1px solid #e5e7eb`  
**Modal body:** `padding: 20px`, `max-height: 68vh`, `overflow-y: auto`  
**Modal footer:** `padding: 12px 20px`, `border-top: 1px solid #e5e7eb`, `background: #f9fafb`

---

### Dropdowns

Dropdowns (rule picker, print menu, supplier info) use:
```css
background: #fff;
border: 1px solid #d1d5db;
border-radius: 6px;
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
border-radius: 8px;
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
<div style="border: 1px solid #e5e7eb; border-radius: 6px; overflow: hidden; background: #fff">
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
2. Price amount (`font-size: 16px, font-weight: 900, color: #222`)
3. Profit (`font-size: 10px, font-weight: 700, color: #16a34a`)
4. ETD (`font-size: 9px, color: #a3a3a3`)
5. MODIFY button (hidden, revealed on selection — `position: absolute, bottom: 0, left: 0, right: 0`)

**Selected state:** `outline: 2px solid #5cb85c; outline-offset: -2px; background: #f0fff4`

**Part No. Match indicator:** Green corner triangle (`#16a34a`) with white tick — `position: absolute, top: 0, right: 0`

**Totals row:** `background: #f3f4f6`, `border-top: 2px solid #d1d5db`, `font-weight: 700`, `font-size: 12px`

**Supplier header tooltip:** Appears on hover over column header — same light tooltip style, shows Status, Phone, Type, Delivery, Price Expiry, Supplier Quote #, Settlement Disc.

---

### Data Table (List View)

List view groups parts as sections with a header row per part.

**Part header:** `background: #e8e8e8`, `border-top: 2px solid #d4d4d4`, `border-bottom: 1px solid #d1d5db`, `padding: 9px 14px`  
Shows: Part name (bold 13px), Dealer Part Nr, Qty input, Dealer List Price.

**Column headers:** `background: #f5f5f5`, `font-size: 11px`, `font-weight: 700`, `color: #666`  
Columns: Supplier | Comments | Qty | Type | Cost | Sell | Margin | Profit | Action

**Supplier rows:** `border-bottom: 1px solid #ebebeb`  
Selected row: `background: #f0fff4`  
Selected values: bold, `color: #111827`

**SELECT button:** `border: 1px solid #d1d5db`, `background: #fff`, `border-radius: 3px`  
**SELECTED button:** `background: #5cb85c`, `color: white`  
**Modify button:** `border: 1px solid #d1d5db`, `background: #fff`, appears alongside SELECTED

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

**Icon circles:** `28px × 28px`, `border-radius: 50%`, icon size `13px` using Font Awesome 4

| State | Background | Icon colour |
|---|---|---|
| Inactive | `#e5e5e5` | `#d4d4d4` |
| Hover | `#4a4a4a` | `#fff` |
| Active | `#16a34a` | `#fff` |

```css
.nav-icon-circle { background: #e5e5e5; }
.nav-icon-circle i { font-size: 13px; color: #d4d4d4; }
.nav-link:hover .nav-icon-circle.gray { background: #4a4a4a; }
.nav-link:hover .nav-icon-circle.gray i { color: #fff; }
.nav-link.active .nav-icon-circle { background: #16a34a; }
.nav-link.active .nav-icon-circle i { color: #fff; }
```

Active item text: `color: #16a34a`
Inactive item text: `color: #a3a3a3` (Tailwind neutral-400)
Active bottom border: `3px solid transparent` → active tab has no bottom border (the icon circle indicates active state)

**TeamViewer button:** Blue rounded square (`22×22px`, `rx: 4`, `fill: #0E6EB8`) with white bidirectional arrow SVG. Positioned in the top-right of the nav bar.

---

### Sub-Nav (Check Price)

```css
background: #404040;
position: sticky;
top: 62px;
z-index: 299;
```

Items: `padding: 10px 36px`, `font-size: 11.5px`, `font-weight: 700`, `letter-spacing: 0.6px`, `text-transform: uppercase`

**Badge circles:** `21px × 21px`, `border-radius: 50%`  
- Inactive: `background: #4b5563; color: #d1d5db`  
- Active: `background: #16a34a; color: white`

Active item: `color: white`, `border-bottom: 3px solid #16a34a`  
Inactive item: `color: #d1d5db`, `border-bottom: 3px solid transparent`

---

### Settings Tab Bar

Same style as Sub-Nav — `background: #404040`. Tabs span the full width.

| Tab | FA4 Icon |
|---|---|
| General Settings | `fa fa-cog` |
| Account Settings | `fa fa-user` |
| Margin Settings | `fa fa-percent` |
| Data Settings | `fa fa-database` |

Each tab has: circle badge with FA4 icon + label text + optional NEW pill

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
- Cost: `▼ $X below dealer list` / `▲ $X above dealer list` — green if below, red if above
- Sell: `▼ $X below dealer list` / `▲ $X above dealer list` — green if below, red if above
- Profit: `X.X% margin` — always green background

> **Tooltip format — standardised:** Both Your Cost and Your Sell tooltips use identical language for comparisons against dealer list: `$X below list (Y%)` or `$X above list (Y%)`. Do **not** use `$+/- vs dealer list`.

**Your Cost tooltip rows**

| Label | Value |
|---|---|
| What this is | Total buy price across selected parts |
| List Total | SUM(p.list) for selected parts |
| vs List | `$X below list (Y%)` or `$X above list (Y%)` |

```
vs List $  = Dealer List Total − Your Cost Total
vs List %  = |Dealer List Total − Your Cost Total| / Dealer List Total × 100
```

**Your Sell tooltip rows**

| Label | Value |
|---|---|
| What this is | Your sell price based on the active margin rule |
| List Total | SUM(p.list) for selected parts — same reference as Your Cost |
| Job Saving | `$X below list (Y%)` or `$X above list (Y%)` |

```
Job Saving $  = Dealer List Total − Your Sell Total
Job Saving %  = |Dealer List Total − Your Sell Total| / Dealer List Total × 100
```

> **Label distinction:** Your Cost uses **"vs List"** (measures buying efficiency — how much cheaper you're buying vs dealer list). Your Sell uses **"Job Saving"** (measures the saving passed to the insurer vs dealer list). Same formula, different meaning.

**Shared reference point**
```
Dealer List Total = SUM(p.list) for all selected parts
                  = manufacturer RRP — never the supplier cost or sell price
```

**Display rules**
- `below list` — your figure is less than dealer list → green
- `above list` — your figure exceeds dealer list → red
- `%` reflects the magnitude as a proportion of dealer list in both cases
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
2. **Quick Select** — label outside + select dropdown (— None —, Maximum Profit, Minimum Cost, OEM Dealer)
3. **Print** — button with dropdown (Print Available Prices, List Price Report, Unavailable Part List, Cost Price Report*, Purchase Order Summary*)
4. **View** — label outside + grid/list icon toggle
5. **List Settings** — gear icon, only visible in list view

*Greyed out until conditions are met.

**Active Rule dropdown:** `width: 680px`, 2-column card grid, brand green radio indicators, light card style matching Info page.

---

## 11. Modals

All modals follow a single standard. The **Supplier Associations modal** is the reference implementation. **Do not use coloured (green or brand) modal headers** — all headers are `#f8fafc` with `#111827` dark text regardless of context.

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
border-radius: 4px; /* NOT 8px */
box-shadow: 0 20px 60px rgba(0,0,0,0.25);
overflow: hidden;
```

### Header `.mhd`
```css
background: #f8fafc;
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

Destructive modals may show a small red circle icon (`background: #fef2f2; stroke: #ef4444`) alongside the standard `#f8fafc` header — the header background does not change to red.

---

## 12. Screens

### Check Price
Primary quoting screen. Shows parts grid with supplier pricing. Sticky nav, sub-nav, summary bar, toolbar and column headers. Two views: Grid (default) and List.

**Sub-nav tabs:** Check Price | Info | Documents

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

## 13. Pricing Logic

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

## 14. Design Principles

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

## 15. Icons

**Font Awesome 4.7** (`cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css`) is the icon library for PartsCheck. All icons use the `fa fa-icon-name` class pattern.

### Navigation Icons

| Nav Item | FA4 Class |
|---|---|
| Dashboard | `fa fa-tachometer` |
| Get Price | `fa fa-car` |
| Check Price | `fa fa-usd` |
| Orders | `fa fa-file-text-o` |
| Credits | `fa fa-credit-card-alt` |
| Reports | `fa fa-bar-chart` |
| Settings | `fa fa-cog` |

### UI Icons (to be confirmed)

| Usage | FA4 Class |
|---|---|
| Comment indicator on price cells | `fa fa-comment` |
| Chevron / dropdown arrows | `fa fa-chevron-down` |
| Back navigation | `fa fa-chevron-left` |
| Tick / confirm | `fa fa-check` |
| Warning | `fa fa-exclamation-triangle` |
| Info / notice | `fa fa-info-circle` |
| Close / remove | `fa fa-times` |
| Add | `fa fa-plus` |
| Lock / view only | `fa fa-lock` |
| Edit | `fa fa-pencil` |
| Delete / trash | `fa fa-trash` |
| Pin / star | `fa fa-star` |
| Quick edit | `fa fa-cog` |
| User / supplier avatar | `fa fa-user` |
| Grid view | `fa fa-th` |
| List view | `fa fa-list` |
| Database (Data Settings tab) | `fa fa-database` |
| Margin Settings tab | `fa fa-percent` |
| File (Documents empty state) | `fa fa-file-text-o` |

### Exception — Flame icon (Part No. Match)

The flame on the Part No. Match corner indicator has no FA4 equivalent. This remains as an inline SVG. It is a small corner decoration, not a standalone icon, and does not load from the CDN.

### Sizing conventions
- Nav circle icons: `14px × 14px`
- Toolbar / action icons: `13–14px`
- Badge / cell icons: `9–11px`
- Page icons (empty states): `28–32px`

**Supplier avatars:** `fa fa-user` inside a coloured `border: 2px solid [supplier colour]` circle, `22–24px` diameter.

---

## 16. Accessibility Notes (to be expanded)

- All interactive elements should have `cursor: pointer`
- Disabled states use `cursor: not-allowed` and colour change (not opacity alone)
- Tooltips use `pointer-events: auto` with a 120ms dismiss grace period (see Section 7)
- Modals trap focus when open (to be implemented)
- Colour is never the only indicator of state — text labels accompany all status changes

---

## 17. Tooltip Hover Grace Period

All cell tooltips in the price grid use a **hover intent / dismiss grace period** pattern — the tooltip stays visible when the user moves their mouse onto it, allowing them to read or copy content.

```css
.tt { pointer-events: auto; } /* NOT pointer-events: none */
```

```javascript
// 120ms delay before hiding — cancel if mouse re-enters
var _ttTimer = null;

function hideTooltip(cell, relatedTarget) {
  if (ttEl.contains(relatedTarget)) return; // moving into tooltip
  _ttTimer = setTimeout(() => { ttEl.style.display = 'none'; }, 120);
}

ttEl.onmouseenter = () => clearTimeout(_ttTimer);
ttEl.onmouseleave = () => {
  _ttTimer = setTimeout(() => { ttEl.style.display = 'none'; }, 120);
};
```

**Technical term:** hover grace period / interactive tooltip. Referenced in Floating UI and Radix UI documentation.

---

## 18. Chip / Tag Input

Used in the **Applies To** field in Add/Edit Rule. Allows multiple values to be entered as removable chips.

**Behaviour:**
- User types a value and presses **Enter** or **,** to add it as a chip
- Each chip has an **×** to remove
- A tooltip dropdown appears on focus (when input is empty) showing helper text
- Duplicate detection is case-insensitive
- Conflict warning shown if a value already exists in another rule (amber, non-blocking)

**Chip style:**
```css
background: #eff6ff;
border: 1px solid #bfdbfe;
border-radius: 4px;
padding: 3px 8px;
font-size: 12px;
font-weight: 600;
color: #1d4ed8;
```

**Remove button:** `color: #93c5fd`, hover `color: #1d4ed8`

**Empty state tooltip (on focus):**
```css
background: #fff;
border: 1px solid #d1d5db;
border-radius: 4px;
box-shadow: 0 4px 12px rgba(0,0,0,0.1);
font-size: 12px;
color: #9ca3af;
font-style: italic;
```

**Validation:** The Save button remains disabled until at least one chip is added.

---

## 19. Supplier Response Tooltips

Hovering over a supplier response dot in the quote header reveals a tooltip showing key supplier details.

**Order:** Always matches column order in the price grid — OEM first, then by column sequence.

**Header:** Part type + status in supplier's brand colour e.g. `OEM — RECEIVED`, `AFTERMARKET — RECEIVED`

**Rows:** Supplier name, Phone, Parts Priced (e.g. "7 of 8"), Quote Reference

**Note:** ETD is not shown at supplier level — it varies per part and is shown on individual price cells.

```css
.resp-tip {
  background: #fff;
  border: 1px solid #e5e7eb;
  border-radius: 4px;
  padding: 10px 12px;
  box-shadow: 0 8px 24px rgba(0,0,0,.10);
  width: 220px;
}
.resp-tip-hd {
  font-size: 10px;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  border-bottom: 1px solid #f3f4f6;
  margin-bottom: 7px;
  padding-bottom: 6px;
}
.resp-tip-row {
  display: flex;
  justify-content: space-between;
  font-size: 10px;
  border-bottom: 1px solid #f3f4f6;
  padding: 3px 0;
}
```

---

## 20. Price Cell Corner Indicators

Two corner indicators can appear in the top-right of a price cell. Both use a CSS triangle pattern.

### Part No. Match (Flame)

Green triangle with a white flame SVG. Shown when supplier's part number matches the vehicle's OEM part number.

```css
.cf  { border-width: 0 20px 20px 0; }
.cfg { border-color: transparent #16a34a transparent transparent; }
```

Tooltip: `"Part No. Match"` — light theme, same style as other tooltips.

### Donor Part Match (Blue Star)

Blue triangle with a white ★. Shown when the part is recycled/reconditioned and the insurer has an active Donor Parts Scheme mapping.

```css
.mf { border-color: transparent #1d4ed8 transparent transparent; border-width: 0 22px 22px 0; }
```

Tooltip: `"Donor Part Match"` — light theme.

Both indicators can appear on the same cell simultaneously. The donor flag (22px) is slightly larger than the flame (20px).

---

## 21. Margin Rules — Insurer Mapping (Debtor Mapping)

Each margin rule maps to one or more **debtor names** — the exact names as they appear in the quote package (e.g. "AAI Limited", "NRMA Insurance").

**Purpose:** Avoids creating duplicate rules for insurers that operate multiple consumer brands under identical margin structures (e.g. IAG runs NRMA, RACV, CGU, SGIO, SGIC under the same margins).

**Rules table:** The Applies To column shows the first 3 debtor chips inline with "+N more" for overflow. Rules with no debtors show *"Not set"* in grey italic.

**In Add/Edit Rule:** The Applies To field is a chip input (see Section 17). Save is disabled until at least one debtor is added.

**Conflict detection:** If a debtor name is already mapped to another rule an amber warning appears — non-blocking, user can still save.

**Unmapped Debtors alert:** An amber banner above the Margin Rules table lists debtor names from recent quotes that don't match any rule. These quotes fall back to the Standard Baseline.

---

## 22. Role-Based Access — Margin Settings

The MJ badge in the top nav is a clickable role switcher (demo only — in production roles come from the user record).

| Role | Margin Settings Access |
|---|---|
| Administrator | Full — Add Rule, Edit, Delete, Copy & customise |
| Manager | View only — all action buttons replaced with "View only" badge |
| Estimator | View only — same as Manager |

**View only mode:**
- Add Rule button hidden
- Action buttons replaced with a grey **View only** pill (clickable — opens rule in read-only RuleForm)
- Copy & customise on System Templates replaced with View only pill
- All inputs in RuleForm disabled (`background: #f9fafb`, `cursor: not-allowed`)
- Save button hidden, replaced with Close
- Edit warning banner hidden
- Add Exception button hidden

Role change dispatched via `window.dispatchEvent(new CustomEvent('rolechange', {detail:{role:id}}))` — React Dashboard listens and re-renders.

---

## 23. Donor Parts Scheme

A Donor Parts Scheme is an arrangement where an insurer pre-approves recycled parts sourced from written-off vehicles for use on eligible claims. The ★ indicator appears on the Check Price screen when the insurer, supplier and part type all match.

**Controlled at two levels in the DB:**
1. The insurer must have `donor_parts_enabled = 1`
2. The repair site must have `donor_parts_enabled = 1` against their client ID

**In Add/Edit Rule:** A **★ Donor Parts** row appears below the Recycled pricing row — only if the site feature flag is active. Shows a dropdown mapping the rule to Allianz, Suncorp, or IAG (current participating insurers).

```
IF client.features.donor_parts === true
  SHOW Donor Parts dropdown below Recycled row
ELSE
  HIDE entirely — no empty state
```

**Dropdown style:** `#f8fafc` background, `4px` radius, description text left, dropdown right-aligned at `180px` width.

**Currently participating insurers:** Allianz, Suncorp, IAG.

---

*Last updated: June 2026. Maintained alongside the PartsCheck prototype. Update this document whenever a design decision changes.*

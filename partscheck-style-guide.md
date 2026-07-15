# PartsCheck — Design & Style Guide

> This document is the single source of truth for the PartsCheck UI. It covers colours, typography, spacing, components, navigation, screen patterns and design principles. All new development should reference this guide. When a decision is made that changes or extends the design system, this document should be updated.

---

## 1. Brand

**Product name:** PartsCheck  
**Tagline:** Smart. Simple. Streamlined
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
| `gray-700` | `#374151` | Primary body text |
| `gray-900` | `#111` | Headings, strong emphasis |

### Part Type Colours

| Type | Hex |
|---|---|
| OEM | `#2563eb` | blue-600 |
| Aftermarket (AftM) | `#a855f7` | purple-500 |
| Used / Recycled | `#84cc16` | lime-500 |
| Reconditioned (Reco) | `#f59e0b` | amber-500 |
| Parallel | `#6b7280` | gray-500 |

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

These are line/row backgrounds only. Do not apply to buttons, pills or badges — those have their own colour system. Text colour on top of these backgrounds stays at the standard grid text colours (`#111` / `#374151`) for legibility; do not tint the text to match the background. When a line is in multiple states, priority order is: **Removed → Modified → Supplier → Additional → Optional** (removed always wins because it signals the strongest information, that the line no longer counts toward the quote).

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

- **Headings:** `#111`
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
border-radius: 4px;
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
- Value: `font-size: 10px; color: #111; font-weight: 600`
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
**Modal footer:** `padding: 12px 20px`, `border-top: 1px solid #e5e7eb`, `background: #fafafa`

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
Selected values: bold, `color: #111`

**Line status backgrounds:** In the List View, line status colours are applied at two levels — the part-description header row uses the strong `-200` shade (`--line-accent-<status>-bg`), and every supplier price row grouped beneath uses the softer `-50` shade (`--line-accent-<status>-bg-subtle`). Both must reflect the same status so the whole group reads as one unit. See §2 Line Status Colours for the full state map. When a supplier row is also selected, the selected background (`#f0fff4`) is overridden by the status colour — status wins for the row fill, and bolding + `color: #111` on the values still indicates selection.

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
**Stat value:** `font-size: 22px; font-weight: 700; color: #111`  
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
2. **Quick Select** — label outside + select dropdown (— None —, Maximum Profit, Minimum Cost, OEM Dealer)
3. **Print** — button with dropdown (Print Available Prices, List Price Report, Unavailable Part List, Cost Price Report*, Purchase Order Summary*)
4. **View** — label outside + grid/list icon toggle
5. **List Settings** — gear icon, only visible in list view

*Greyed out until conditions are met.

**Active Rule dropdown:** `width: 680px`, 2-column card grid, brand green radio indicators, light card style matching Info page.

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
Headings are `#111`, body is `#374151`, secondary is `#6b7280`, metadata is `#9ca3af`. Green text is brand green `#16a34a` only.

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
border-radius: 4px; /* NOT 8px */
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

**Download button:** `border: 1px solid #e5e7eb; border-radius: 4px; padding: 5px 12px; font-size: 11px; font-weight: 600; color: #374151` — not a plain text link.

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

### Donor Part Match (Blue Star)
Blue triangle (`#1d4ed8`) in the top-right corner. Contains a ★ character. Tooltip: "Donor Part Match".

---

## 22. Margin Rules — Insurer Mapping (Debtor Mapping)

Each margin rule has an **Applies To** field — a list of debtor names that should be matched against the quote's work provider/insurer name.

- Matching is case-insensitive exact string match
- A debtor name can only belong to one rule — enforced at UI level via amber conflict prompt
- Standard Baseline has no debtors and always appears as the fallback
- The active rule dropdown on Check Price filters to show **Matched** (rules where quote debtor is mapped) and **Other** (everything else)

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

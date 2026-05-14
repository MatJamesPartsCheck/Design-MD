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
| `brand-green` | `#0FA83E` | Nav active states, selected tab underlines, Save buttons, quote number text, tooltip headers, profit text, selected count |
| `brand-green-dark` | `#0d9235` | Hover state on green buttons, border on green buttons |

> The brand green is used for identity and interaction. Do not use it for backgrounds — use the Tailwind green scale for that.

### Action & Status Greens (Tailwind scale)

These are used for pills, badges, selected states and backgrounds. **Do not replace these with the brand green.**

| Token | Hex | Usage |
|---|---|---|
| `green-50` | `#f0fdf4` | Selected cell background, pill backgrounds |
| `green-100` | `#dcfce7` | DEFAULT badge background |
| `green-200` | `#bbf7d0` | Borders on green pills |
| `green-500` | `#0FA83E` | Primary action (same as brand) |
| `green-600` | `#0d9235` | Button hover |
| `green-700` | `#15803d` | Dark text on light green |
| `green-800` | `#166534` | Text on DEFAULT badge |

### List View Green

| Token | Hex | Usage |
|---|---|---|
| `list-green` | `#5cb85c` | Selected row highlight, SELECT/SELECTED buttons in list view |

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

### Supplier Colours

Each supplier has a fixed colour used for their circle avatar, column colour bar and type labels.

| Supplier | Hex |
|---|---|
| OEM Direct | `#337ab7` (blue) |
| Parts Network | `#9b59b6` (purple) |
| ATS Parts | `#e91e8c` (pink) |
| Eco Parts | `#5cb85c` (green) |
| Reco Centre | `#f0ad4e` (amber) |

### Part Type Colours

| Type | Hex |
|---|---|
| OEM | `#337ab7` |
| Aftermarket (AftM) | `#9b59b6` |
| Used | `#5cb85c` |
| Reconditioned (Reco) | `#f0ad4e` |
| Parallel | `#5cb85c` |

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
| `900` | Price amounts in grid cells |

### Text Colour Conventions

- **Headings:** `#111`
- **Primary body:** `#374151`
- **Secondary / descriptions:** `#6b7280`
- **Placeholders / metadata:** `#9ca3af`
- **Green text (profit, active states, brand):** `#0FA83E`
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
| Buttons (primary) | none | `4px–6px` |
| Buttons (secondary) | `1px solid #d1d5db` | `4px–6px` |
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
| Green action buttons | `0 2px 8px rgba(15,168,62,.3)` |

---

## 7. Components

### Buttons

#### Primary (Green)
```css
background: #0FA83E;
color: white;
border: none;
border-radius: 6px;
padding: 7px 16px;
font-size: 12px;
font-weight: 700;
cursor: pointer;
```
Hover: `background: #0d9235`

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
| NEW badge | `#0FA83E` bg | none | `white` |
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
color: #0FA83E;
text-transform: uppercase;
letter-spacing: 0.5px;
border-bottom: 1px solid #f3f4f6;
margin-bottom: 6px;
padding-bottom: 5px;
```

**Data rows:**
- Label: `font-size: 10px; color: #6b7280`
- Value: `font-size: 10px; color: #111; font-weight: 600`
- Green value: `color: #0FA83E`
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

Show for 3–3.5 seconds then fade out. Include a green dot indicator (`background: #0FA83E`, `border-radius: 50%`, `20px × 20px`) on the left.

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

Active/focused border: `1px solid #0FA83E`  
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
background: checked ? #0FA83E : #d1d5db;
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
3. Profit (`font-size: 10px, font-weight: 700, color: #0FA83E`)
4. ETD (`font-size: 9px, color: #999`)
5. MODIFY button (hidden, revealed on selection — `position: absolute, bottom: 0, left: 0, right: 0`)

**Selected state:** `outline: 2px solid #5cb85c; outline-offset: -2px; background: #f0fff4`

**Part No. Match indicator:** Green corner triangle (`#0FA83E`) with white tick — `position: absolute, top: 0, right: 0`

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

**SELECT button:** `border: 1px solid #ccc`, `background: #fff`, `border-radius: 3px`  
**SELECTED button:** `background: #5cb85c`, `color: white`  
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
- Active: `background: #0FA83E`, icon fill `white`

Active item text: `color: #0FA83E`  
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
- Active: `background: #0FA83E; color: white`

Active item: `color: white`, `border-bottom: 3px solid #0FA83E`  
Inactive item: `color: #ccc`, `border-bottom: 3px solid transparent`

---

### Settings Tab Bar

Same style as Sub-Nav — `background: #3a3a3a`. Tabs span the full width.

Tabs: General Settings | Account Settings | Margin Settings | Data Settings  
Each tab has: circle badge with icon + label text + optional NEW pill

**NEW pill on tab:** `background: #0FA83E; color: white; font-size: 9px; font-weight: 800; border-radius: 3px; padding: 1px 5px`

---

### Settings Sidebar Nav (future)

Not currently implemented. Pattern would follow: `background: #fff`, `border-right: 1px solid #e5e7eb`, active item `border-left: 3px solid #0FA83E; background: #f0fdf4; color: #0FA83E`

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
**Your Profit value:** `color: #0FA83E`

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
Use `#0FA83E` for active states, confirmation actions, profit values and brand moments. Use the Tailwind green scale for backgrounds and pill colours.

**7. Consistent card pattern.**  
Detail cards always follow the same structure: `#f8fafc` header with uppercase label, `1px solid #e5e7eb` border, `6px` radius, white content area. The Rule Summary card is the exception — it uses a `4px solid #1f2937` left accent to signal it is a reference panel, not an input section.

**8. Typography hierarchy is simple.**  
Headings are `#111`, body is `#374151`, secondary is `#6b7280`, metadata is `#9ca3af`. Green text is brand green `#0FA83E` only.

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

*Last updated: May 2026. Maintained alongside the PartsCheck prototype. Update this document whenever a design decision changes.*

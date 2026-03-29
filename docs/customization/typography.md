---
title: Customizing Typography
---

# Customizing Typography

The eShopping theme uses **3 configurable font families** and a structured type scale. All typographic settings are available in the Theme Editor and can be overridden per-store without code changes.

---

## Font Families

### Headings --- Playfair Display (serif)

A classic serif typeface applied via the `.eshopping-heading` class. Used for page titles, section headings, and hero text.

**How to change:** Theme Styles > General > Typography > Headings Font

<div class="placeholder-screenshot">Example of Playfair Display heading font applied to a page title and section headings</div>

---

### Body --- Source Sans 3 (sans-serif)

The default body font for all general text, navigation, buttons, and form elements.

**How to change:** Theme Styles > General > Typography > Body Font

---

### Monospace --- IBM Plex Mono

A technical monospace font for data-oriented content.

| Detail | Value |
|--------|-------|
| **Setting ID** | `eshopping-mono-font` |
| **CSS class** | `.eshopping-mono` |
| **Used for** | SKUs, prices, product codes, quantities, technical values |

**How to change:** Theme Styles > eShopping > Typography > Mono Font (font selector in Theme Editor)

<div class="placeholder-screenshot">Product card showing IBM Plex Mono applied to the price and SKU fields</div>

---

## Type Scale

The theme uses a consistent type scale based on a **14px root font size** (`config.json` > `fontSize-root`). All sizes are defined as SCSS variables and expressed in `rem` units for proportional scaling.

| Token | Size | ~px | Usage |
|-------|------|-----|-------|
| `$eshopping-fs-3xs` | 0.5rem | 7px | Tiny labels |
| `$eshopping-fs-2xs` | 0.64rem | 9px | Fine print, legal text |
| `$eshopping-fs-xs` | 0.71rem | 10px | Badges, tags, captions |
| `$eshopping-fs-sm` | 0.79rem | 11px | Secondary text, meta info |
| `$eshopping-fs-base` | 0.86rem | 12px | Base body text |
| `$eshopping-fs-md` | 0.93rem | 13px | Navigation items, buttons |
| `$eshopping-fs-lg` | 1.07rem | 15px | Subheadings, card titles |
| `$eshopping-fs-xl` | 1.29rem | 18px | Section titles |
| `$eshopping-fs-2xl` | 1.5rem | 21px | Page headings |
| `$eshopping-fs-3xl` | 2.21rem | 31px | Hero text, large display |

!!! tip "Relative sizing"
    Because the scale uses `rem`, changing `fontSize-root` in `config.json` proportionally adjusts every text element on the site. Increase it for a more spacious feel; decrease it for a denser layout.

---

## Spacing Tokens

The theme provides consistent spacing via CSS custom properties. Use these tokens for all padding, margin, and gap values to maintain visual rhythm across the storefront.

| Token | Value | Usage |
|-------|-------|-------|
| `--eshopping-sp-1` | 4px | Tight gaps (icon-to-text, inline elements) |
| `--eshopping-sp-2` | 8px | Small padding (badges, tag spacing) |
| `--eshopping-sp-3` | 12px | Standard padding (form fields, list items) |
| `--eshopping-sp-4` | 16px | Card padding, button padding |
| `--eshopping-sp-6` | 24px | Section gaps, grid gutters |
| `--eshopping-sp-8` | 32px | Large gaps between content blocks |
| `--eshopping-sp-10` | 40px | Section spacing |
| `--eshopping-sp-12` | 48px | Page-level spacing (top/bottom margins) |

---

## Border Radius Tokens

Consistent rounding for interactive and container elements.

| Token | Value | Usage |
|-------|-------|-------|
| `--eshopping-r-xs` | 4px | Subtle rounding (inputs, badges) |
| `--eshopping-r-sm` | 8px | Cards, dropdowns |
| `--eshopping-r-md` | 12px | Modals, larger cards |
| `--eshopping-r-lg` | 18px | Buttons, pills, prominent containers |

---

## Shadow Tokens

Elevation levels for layered UI elements.

| Token | Usage |
|-------|-------|
| `--eshopping-shadow-xs` | Subtle lift (cards at rest) |
| `--eshopping-shadow-sm` | Hover state elevation |
| `--eshopping-shadow-md` | Dropdowns, popovers |
| `--eshopping-shadow-lg` | Modals, drawers, overlays |

---

## Quick Reference: Applying Typography in Code

### In Handlebars Templates

```handlebars
{{!-- Heading with serif font --}}
<h2 class="eshopping-heading">{{lang 'eshopping.section_title'}}</h2>

{{!-- Monospace for prices/SKUs --}}
<span class="eshopping-mono">{{product.sku}}</span>
```

### In SCSS

```scss
// Use type scale tokens --- never hardcode px
.my-component__title {
  font-size: $eshopping-fs-xl;       // 1.29rem / ~18px
  line-height: 1.3;
}

.my-component__meta {
  font-size: $eshopping-fs-sm;       // 0.79rem / ~11px
  color: var(--eshopping-bark-500);
}

// Use spacing tokens --- never hardcode px
.my-component {
  padding: var(--eshopping-sp-4);    // 16px
  margin-bottom: var(--eshopping-sp-6); // 24px
  border-radius: var(--eshopping-r-sm); // 8px
}
```

!!! warning "Coding standards"
    Never use hardcoded `px` values for font sizes, spacing, or border radius. Always use the design token variables (`$eshopping-fs-*` for fonts, `--eshopping-sp-*` for spacing, `--eshopping-r-*` for radii). Hardcoded values will not pass code review.

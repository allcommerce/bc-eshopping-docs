---
title: Customizing Colors
---

# Customizing Colors

All colors in the eShopping theme use **design tokens** configured through Theme Editor. Navigate to **Theme Styles** > **eShopping** > **Colors** to customize every color on your storefront without touching code.

<div class="placeholder-screenshot">Theme Editor Colors panel showing the eShopping color settings with swatches for bark, terra, forest, and base colors</div>

---

## Color Palettes

### Bark Scale (Neutrals)

A 10-level neutral scale from light to dark, used for backgrounds, text, borders, and muted elements.

| Setting ID | Role | Default |
|-----------|------|---------|
| `eshopping-color-bark-50` | Lightest neutral (subtle backgrounds) | `#f5f3ef` |
| `eshopping-color-bark-100` | Light neutral | |
| `eshopping-color-bark-200` | Border, divider lines | |
| `eshopping-color-bark-300` | Muted text, placeholders | |
| `eshopping-color-bark-400` | Secondary text | |
| `eshopping-color-bark-500` | Mid-tone neutral | |
| `eshopping-color-bark-600` | Body text | |
| `eshopping-color-bark-700` | Strong text | |
| `eshopping-color-bark-800` | Heading text | |
| `eshopping-color-bark-900` | Near-black | |
| `eshopping-color-bark-950` | Darkest neutral | `#0f0d0a` |

!!! tip
    Adjusting the bark scale changes the overall warmth or coolness of your store. The [Industry Presets](presets.md) each use a different neutral family --- warm bark (Industrial), slate (AutoParts), stone (Packaging), or zinc (Electronics).

---

### Terra (Primary Accent)

Four shades of the primary brand color, used for buttons, links, highlights, and interactive elements.

| Setting ID | Role | Default |
|-----------|------|---------|
| `eshopping-color-terra` | Main accent (buttons, links, highlights) | `#bf5b33` |
| `eshopping-color-terra-light` | Hover states, secondary highlights | |
| `eshopping-color-terra-dark` | Active states, emphasis | |
| `eshopping-color-terra-pale` | Subtle backgrounds, badges | |

<div class="placeholder-screenshot">Close-up of buttons and links showing the four terra shades in use: main, light (hover), dark (active), and pale (badge background)</div>

---

### Forest (Secondary Accent)

Six shades for success states, stock indicators, and secondary accents.

| Setting ID | Role |
|-----------|------|
| `eshopping-color-forest-50` | Lightest green (success backgrounds) |
| `eshopping-color-forest-100` | Light green |
| `eshopping-color-forest-200` | Borders, subtle accents |
| `eshopping-color-forest-500` | Mid-tone green |
| `eshopping-color-forest-700` | In-stock badges, success text |
| `eshopping-color-forest-900` | Dark green (emphasis) |

**Common uses:** "In Stock" badges, success messages, eco-themed promotional elements, add-to-cart confirmations.

---

### Base Colors

| Setting ID | Role | Default |
|-----------|------|---------|
| `eshopping-color-cream` | Off-white page background | `#faf8f4` |
| `eshopping-color-white` | Pure white (cards, modals) | `#ffffff` |

---

## Component Colors

Beyond the global palette, the theme exposes color settings for specific UI components. These let you fine-tune individual sections without affecting the rest of the store.

### Top Bar

| Setting ID | Controls |
|-----------|----------|
| `eshopping-topbar-bg` | Background color |
| `eshopping-topbar-color` | Text color |
| `eshopping-topbar-color-hover` | Hover text color |

<div class="placeholder-screenshot">Top bar component with labels pointing to the background, text, and hover text color areas</div>

---

### Main Navigation

| Setting ID | Controls |
|-----------|----------|
| `eshopping-nav-bg` | Background color |
| `eshopping-nav-color` | Text color |
| `eshopping-nav-color-hover` | Hover text color |
| `eshopping-nav-search-bg` | Search bar background |
| `eshopping-nav-search-color` | Search input text color |
| `eshopping-nav-search-btn` | Search button color |

<div class="placeholder-screenshot">Main navigation bar with labels pointing to the background, nav links, search bar, and search button color areas</div>

---

### Footer

| Setting ID | Controls |
|-----------|----------|
| `eshopping-footer-bg` | Background color |
| `eshopping-footer-color` | Body text color |
| `eshopping-footer-heading` | Section heading color |
| `eshopping-footer-link` | Link color |
| `eshopping-footer-link-hover` | Link hover color |
| `eshopping-footer-border` | Separator border color |

<div class="placeholder-screenshot">Footer component with labels pointing to the background, heading, body text, link, and border color areas</div>

---

## How Colors Flow Through the Theme

```
config.json          Theme Editor           SCSS                    CSS
─────────────   ───────────────────   ──────────────────   ──────────────────
Default value → Merchant overrides → stencilColor()     → --eshopping-*
                                      (design tokens)     (CSS custom props)
```

1. **config.json** defines the default hex value for each color setting.
2. **Theme Editor** lets merchants override any color with a color picker.
3. **SCSS** reads the value via `stencilColor('eshopping-color-terra')` and outputs it as a CSS custom property (`--eshopping-terra`).
4. **Components** reference the CSS custom property, so every element updates automatically when a color changes.

!!! warning "Never hardcode colors"
    All colors in templates and SCSS must use design tokens (`stencilColor()` in SCSS, `var(--eshopping-*)` in CSS). Hardcoded hex, RGB, or HSL values will not respond to Theme Editor changes and will fail code review.

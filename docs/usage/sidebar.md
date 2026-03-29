# Configuring the Sidebar

The eShopping sidebar provides category navigation, faceted filters, and an optional promotional card. It appears on **category**, **brand**, and **search** pages automatically.

<div class="placeholder-screenshot">Category page showing the 280px sidebar on the left with category tree, filters, and promo card, and the product grid on the right.</div>

---

## Overview

| Property | Value |
|----------|-------|
| **Width** | 280px (fixed) |
| **Position** | Sticky (scrolls with the page, stays visible) |
| **Pages** | Category, Brand, Search |
| **Mobile** | Converts to a bottom sheet overlay |

The sidebar is always visible on desktop for the pages listed above. It cannot be toggled off entirely -- it is a core navigation element of the eShopping layout.

---

## Category Tree

The category tree displays your store's product category hierarchy, allowing visitors to browse and drill down into subcategories.

| Setting | Location | Default | Purpose |
|---------|----------|---------|---------|
| `eshopping-sidebar-depth` | Theme Styles > Sidebar | `3` | Number of subcategory levels to display |
| `eshopping-sidebar-auto-expand` | Theme Styles > Sidebar | `true` | Auto-expand the current category path |

### Depth

The `eshopping-sidebar-depth` setting controls how many levels of the category tree are rendered:

- **1** -- Top-level categories only
- **2** -- Top-level + one level of subcategories
- **3** -- Three levels deep (default)

Categories deeper than the configured depth are not displayed in the sidebar tree. Visitors can still access them by navigating into a parent category.

### Auto-expand

When `eshopping-sidebar-auto-expand` is enabled, the sidebar automatically expands the tree to reveal the current page's category. For example, if a visitor is on the "Cordless Drills" category page (nested under "Power Tools > Drills"), the tree expands to show the full path:

```
Power Tools
  └─ Drills
       └─ Cordless Drills  ← current page (highlighted)
```

When disabled, all categories start in a collapsed state and visitors must manually click to expand each level.

<div class="placeholder-screenshot">Sidebar category tree with three levels expanded, showing the current category highlighted with a bold style.</div>

### How to configure

1. Open the **Theme Editor** (**Storefront > My Themes > Customize**).
2. Navigate to **Theme Styles > Sidebar**.
3. Set **Category tree depth** to the desired number of levels (1--3).
4. Toggle **Auto-expand current category** on or off.
5. Click **Save & Apply**.

---

## Faceted Filters

When faceted search is enabled in your BigCommerce admin, filter groups (price, brand, rating, custom fields, etc.) appear in the sidebar below the category tree.

<div class="placeholder-screenshot">Sidebar filter groups showing Price range slider, Brand checkboxes, and Rating stars filter.</div>

### Enabling faceted search

1. In your BigCommerce admin, go to **Products > Product Filtering**.
2. Enable the filters you want to display (price, brand, rating, product options, custom fields).
3. Configure the display style (checkboxes, sliders, swatches) for each filter.

The eShopping theme automatically renders these filters in the sidebar with styles matching the theme's design tokens. No additional theme settings are needed.

!!! tip
    On category pages with many filters, the sidebar becomes scrollable independently of the main content, ensuring filters are always accessible.

---

## Promotional Card

The sidebar includes an optional promotional card that can display a marketing message with a call-to-action button.

| Setting | Location | Default |
|---------|----------|---------|
| `eshopping-promo-text` | Theme Styles > Sidebar | Pipe-separated string |

### Content format

The `eshopping-promo-text` setting is a pipe-separated string with four segments:

```
Title|Description|CTA Text|URL
```

| Segment | Purpose | Example |
|---------|---------|---------|
| Title | Bold heading text | `Free Shipping $500+` |
| Description | Supporting message | `Free ground shipping on qualifying orders.` |
| CTA Text | Button label | `Shop Now` |
| URL | Button link destination | `/shipping/` |

**Default value:**

```
Free Shipping $500+|Free ground shipping on qualifying orders.|Shop Now|/shipping/
```

<div class="placeholder-screenshot">Sidebar promotional card showing "Free Shipping $500+" heading, description text, and a "Shop Now" button.</div>

### How to configure

1. Open the **Theme Editor**.
2. Navigate to **Theme Styles > Sidebar**.
3. Edit the **Promo text** field using the four-segment pipe-separated format.
4. Click **Save & Apply**.

To hide the promo card, clear the `eshopping-promo-text` field entirely (leave it blank).

!!! tip
    Use the promo card for shipping thresholds, seasonal sales, or clearance announcements. The URL can point to any page -- a category, a CMS page, or an external link.

---

## Mobile Behavior

On screens below 801px, the sidebar is not visible by default. Instead, it transforms into a **bottom sheet overlay** that slides up from the bottom of the screen.

<div class="placeholder-screenshot">Mobile bottom sheet overlay showing the category tree and filter options sliding up from the bottom of the screen.</div>

### How it works

1. A **filter button** appears in the mobile toolbar above the product grid.
2. Tapping the button opens the bottom sheet with the full sidebar content -- category tree, filters, and promo card.
3. Visitors can scroll within the sheet, apply filters, and tap outside or press the close button to dismiss it.
4. Applied filters appear as **active chips** above the product grid, allowing visitors to remove individual filters without reopening the sheet.

No additional settings are needed for mobile behavior. The bottom sheet is enabled automatically when the viewport width is below the desktop breakpoint.

---

## Quick Reference

| Setting | Default | Description |
|---------|---------|-------------|
| `eshopping-sidebar-depth` | `3` | Category tree nesting depth (1--3 levels) |
| `eshopping-sidebar-auto-expand` | `true` | Auto-expand tree to current category |
| `eshopping-promo-text` | `Free Shipping $500+\|...\|Shop Now\|/shipping/` | Promotional card content (4 pipe-separated segments) |

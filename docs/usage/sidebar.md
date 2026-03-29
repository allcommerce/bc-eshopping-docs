# Configuring the Sidebar

The eShopping sidebar helps visitors browse and filter your products. It appears automatically on **category**, **brand**, and **search results** pages and includes a category tree, product filters, and an optional promotional card.

<div class="placeholder-screenshot">Category page showing the sidebar on the left with a category tree, product filters, and a promotional card, and the product grid on the right.</div>

---

## Overview

The sidebar is a key navigation element of the eShopping theme:

- **Desktop:** The sidebar is always visible on the left side of category, brand, and search pages. It stays in view as visitors scroll.
- **Mobile:** The sidebar converts to a slide-up panel that visitors can open and close with a tap (see [Mobile Behavior](#mobile-behavior) below).

---

## Category Tree

The category tree displays your store's product categories in a collapsible hierarchy, making it easy for visitors to browse and drill down into subcategories.

<div class="placeholder-screenshot">Sidebar category tree with three levels expanded, showing the current category highlighted with bold text.</div>

When a visitor is browsing a category page, the tree automatically expands to show where they are. For example, if they are viewing "Cordless Drills" nested under "Power Tools > Drills", the tree opens to reveal the full path:

```
Power Tools
  +-- Drills
       +-- Cordless Drills  (current page, highlighted)
```

### How to configure

The category tree works automatically based on the categories you have created in **Products > Product Categories** in your BigCommerce admin. To organize or reorder your categories, manage them from that admin section.

---

## Product Filters (Faceted Search)

When faceted search is enabled in your BigCommerce admin, filter groups appear in the sidebar below the category tree. Visitors can narrow down products by price, brand, rating, product options, and custom fields.

<div class="placeholder-screenshot">Sidebar filter groups showing a price range slider, brand checkboxes, and a star rating filter.</div>

### How to enable product filters

1. In your BigCommerce admin, go to **Products > Product Filtering**.
2. Turn on the filters you want to display (price, brand, rating, product options, custom fields).
3. Configure how each filter appears (checkboxes, sliders, swatches, etc.).

The eShopping theme automatically styles these filters to match your store's design. No additional theme settings are needed.

!!! tip
    On pages with many filters, the sidebar scrolls independently from the main product grid, so filters are always within easy reach.

---

## Promotional Card

The sidebar includes a built-in promotional card that you can use to highlight a special offer, shipping threshold, seasonal sale, or any other message. It appears below the filters and includes a heading, description, and a call-to-action button.

<div class="placeholder-screenshot">Sidebar promotional card showing a "Free Shipping $500+" heading, a short description, and a "Shop Now" button.</div>

### How to set it up

1. Open the **Theme Editor** (**Storefront > My Themes > Customize**).
2. Go to **Theme Styles** > **eShopping** > **Sidebar** > **Sidebar Promo Card**.
3. In the **Sidebar Promo Text** field, enter your content using the format below.
4. Click **Save & Apply**.

### Content format

Enter four pieces of information separated by pipe characters (`|`):

```
Title|Description|Button Text|Button Link
```

| Piece | What it is | Example |
|-------|-----------|---------|
| Title | The bold heading | `Free Shipping $500+` |
| Description | Supporting text below the heading | `Free ground shipping on qualifying orders.` |
| Button Text | The label on the call-to-action button | `Shop Now` |
| Button Link | Where the button takes visitors | `/shipping/` |

**Example:**

```
Free Shipping $500+|Free ground shipping on qualifying orders.|Shop Now|/shipping/
```

To hide the promotional card, clear the **Sidebar Promo Text** field entirely (leave it blank).

!!! tip
    The button link can point to anything -- a category page, a custom web page, or even an external URL. Great uses include free shipping thresholds, clearance sales, or new arrivals.

---

## Mobile Behavior

On phones and small tablets, the sidebar is hidden by default to give products more screen space. Instead, it becomes a **slide-up panel** (bottom sheet) that visitors can open and close.

<div class="placeholder-screenshot">Mobile bottom sheet panel sliding up from the bottom of the screen, showing the category tree, product filters, and promotional card.</div>

### How it works

1. A **Filter** button appears in the toolbar above the product grid on mobile.
2. Tapping the button slides up a panel containing the full sidebar -- category tree, filters, and promotional card.
3. Visitors can scroll through the panel, select filters, and tap outside the panel or press the close button to dismiss it.
4. Any active filters appear as small **chips** above the product grid, so visitors can see and remove individual filters without reopening the panel.

No additional settings are needed -- the mobile layout adapts automatically based on screen size.

---

## Quick Setup Checklist

| Feature | Theme Editor Path | What to do |
|---------|-------------------|------------|
| Category Tree | _(automatic)_ | Manage your categories in **Products > Product Categories** in the BigCommerce admin |
| Product Filters | _(automatic)_ | Enable filters in **Products > Product Filtering** in the BigCommerce admin |
| Promotional Card | **eShopping** > **Sidebar** > **Sidebar Promo Card** | Enter your content in the **Sidebar Promo Text** field |
| Mobile Panel | _(automatic)_ | No setup needed -- adapts to small screens automatically |

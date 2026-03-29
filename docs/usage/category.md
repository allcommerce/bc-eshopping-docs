# Customizing Category & Brand Pages

The eShopping theme provides a consistent layout for category, brand, and search result pages with a left sidebar, product grid, and configurable display options. All settings are managed from the Theme Editor.

---

## Page Layout

Category and brand pages use a two-column layout:

- **Left sidebar** -- Contains the category navigation tree and faceted search filters (price, brand, rating, custom fields, etc.).
- **Right content area** -- Displays the product grid with toolbar controls for sorting, pagination, and view mode.

On mobile, the sidebar collapses into a bottom sheet that slides up when the customer taps the filter button.

<div class="placeholder-screenshot">Category page showing left sidebar with category tree and filters, right side showing product grid with toolbar</div>

<div class="placeholder-screenshot">Category page on mobile showing product grid with filter button that opens a bottom sheet</div>

---

## Product Grid

### Products per page

You can control how many products appear on each page of the listing.

**Where to find it:**
**Theme Styles** > **Products** > **Number of products displayed**

| Setting label | What it controls |
|---------------|------------------|
| **Category page** | Products per page on category pages |
| **Brand page** | Products per page on brand pages |

### How to configure

1. Open your **Theme Editor** (Storefront > My Themes > Customize).
2. Go to **Theme Styles** > **Products** > **Number of products displayed**.
3. Set the number for **Category page** and/or **Brand page**.
4. Click **Save & Apply**.

### Grid / list view toggle

The product listing toolbar includes a grid/list view toggle that customers can use to switch between:

- **Grid view** -- Products displayed in a multi-column card layout (default).
- **List view** -- Products displayed in a single-column row layout with more detail visible.

The customer's preference is saved in their browser and persists across page visits.

<div class="placeholder-screenshot">Category page toolbar showing grid/list view toggle buttons, sort dropdown, and products per page selector</div>

---

## Brands Page Layout

The dedicated brands page (`/brands/`) supports two layout modes, and customers can switch between them at any time using a toggle in the toolbar.

<div class="placeholder-screenshot">Brands page toolbar showing A-Z and Grid toggle buttons next to the search input</div>

### Where to find it

The default layout is set in the General settings area of the Theme Editor.

### A-Z layout

When the default is set to **A-Z**, the brands page displays an alphabetical listing with:

- A **search input** at the top to filter brands by name.
- A **letter navigation bar** (A--Z) for quick jumping to a specific letter.
- Brands grouped alphabetically with letter headings.
- An **All** button to reset the letter filter.

This layout is ideal for stores with a large number of brands.

<div class="placeholder-screenshot">Brands page in A-Z layout showing letter navigation bar at top, search input, and brands listed alphabetically with letter group headings</div>

### Grid layout

When the default is set to **Grid**, the brands page displays a visual grid of brand cards:

- Each card shows the brand logo (or a fallback letter avatar if no image is set).
- The brand name appears below the image.
- Cards link directly to the brand's product listing page.
- The search input is still available for filtering.

This layout works well for stores with visually distinctive brand logos.

<div class="placeholder-screenshot">Brands page in grid layout showing brand logo cards in a multi-column grid with search input above</div>

### Layout toggle

Regardless of which default you choose, customers can always switch between A-Z and Grid views using the toggle buttons in the toolbar.

---

## Hiding Breadcrumbs & Page Headings

You can hide breadcrumbs and page headings globally or specifically for category pages.

### Where to find it

**Theme Styles** > **Global** > **Page**

| Setting label | What it does |
|---------------|--------------|
| **Hide breadcrumbs** | Hides breadcrumbs on all pages across the store. |
| **Hide page heading** | Hides the page heading (H1) on all pages across the store. |
| **Hide category page heading** | Hides the page heading on category pages only, leaving other pages unaffected. |

### How to configure

1. Open your **Theme Editor**.
2. Go to **Theme Styles** > **Global** > **Page**.
3. Check or uncheck the options for **Hide breadcrumbs**, **Hide page heading**, or **Hide category page heading** as desired.
4. Click **Save & Apply**.

<div class="placeholder-screenshot">Comparison showing a category page with breadcrumbs and heading visible vs. the same page with both hidden</div>

!!! tip
    Hiding the category page heading is useful when you have a prominent category banner image that already identifies the category. Use **Hide category page heading** to remove just the category title without affecting other pages.

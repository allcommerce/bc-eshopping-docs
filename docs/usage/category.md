# Customizing Category & Brand Pages

The eShopping theme provides a consistent layout for category, brand, and search result pages with a left sidebar, product grid, and configurable display options.

## Page Layout

Category and brand pages use a two-column layout:

- **Left sidebar** (280px): Contains the category navigation tree and faceted search filters (price, brand, rating, custom fields, etc.)
- **Right content area**: Displays the product grid with toolbar controls for sorting, pagination, and view mode

On mobile, the sidebar collapses into a bottom sheet that slides up when the customer taps a filter button.

<div class="placeholder-screenshot">Category page showing left sidebar with category tree and filters, right side showing product grid with toolbar</div>

<div class="placeholder-screenshot">Category page on mobile showing product grid with filter button that opens a bottom sheet</div>

## Product Grid

### Products Per Page

Configure how many products appear per page in **Page Builder** > **Theme Styles** > **Products** > **Category/Brand Pages**.

| Setting | Type | Default | Description |
|---------|------|---------|-------------|
| `categorypage_products_per_page` | Number | `12` | Products per page on category pages |
| `brandpage_products_per_page` | Number | `12` | Products per page on brand pages |

### Grid / List View Toggle

The product listing toolbar includes a grid/list view toggle. Customers can switch between:

- **Grid view:** Products displayed in a multi-column card layout (default)
- **List view:** Products displayed in a single-column row layout with more detail visible

The customer's preference is saved in their browser and persists across page visits.

<div class="placeholder-screenshot">Category page toolbar showing grid/list view toggle buttons, sort dropdown, and products per page selector</div>

## Brands Page Layout

The dedicated brands page (`/brands/`) supports two layout modes with a toggle for customers to switch between them.

### Settings

Navigate to **Page Builder** > **Theme Styles** > **eShopping** > **eShopping Layout**.

| Setting | Type | Default | Options |
|---------|------|---------|---------|
| `eshopping-brands-default-layout` | Select | `az` | `az`, `grid` |

### A-Z Layout

When set to `az`, the brands page displays an alphabetical listing with:

- A **search input** at the top to filter brands by name
- A **letter navigation bar** (A-Z) for quick jumping to a specific letter
- Brands grouped alphabetically with letter headings
- An "All" button to reset the letter filter

This layout is ideal for stores with a large number of brands.

<div class="placeholder-screenshot">Brands page in A-Z layout showing letter navigation bar at top, search input, and brands listed alphabetically with letter group headings</div>

### Grid Layout

When set to `grid`, the brands page displays a visual grid of brand cards:

- Each card shows the brand logo (or a fallback letter avatar if no image is set)
- Brand name displayed below the image
- Cards link directly to the brand's product listing page
- The search input is still available for filtering

This layout works well for stores with visually distinctive brand logos.

<div class="placeholder-screenshot">Brands page in grid layout showing brand logo cards in a multi-column grid with search input above</div>

### Layout Toggle

Regardless of the default setting, customers can switch between A-Z and Grid views using the toggle buttons in the toolbar. The toggle appears next to the search input.

<div class="placeholder-screenshot">Brands page toolbar showing A-Z and Grid toggle buttons next to the search input</div>

## Hiding Breadcrumbs & Page Headings

You can hide breadcrumbs and page headings globally or specifically for category pages.

### Settings

Navigate to **Page Builder** > **Theme Styles** > **Global** > **Page**.

| Setting | Type | Default | Description |
|---------|------|---------|-------------|
| `hide_breadcrumbs` | Checkbox | `false` | Hide breadcrumbs on all pages |
| `hide_page_heading` | Checkbox | `false` | Hide the page heading (H1) on all pages |
| `hide_category_page_heading` | Checkbox | `false` | Hide the page heading on category pages only |

!!! tip
    Hiding the category page heading can be useful when you have a prominent category banner image that already identifies the category. Use `hide_category_page_heading` to remove just the category H1 without affecting other pages.

<div class="placeholder-screenshot">Comparison showing a category page with breadcrumbs and heading visible vs. the same page with both hidden</div>

# Bulk Order Mode

Bulk Order mode transforms the standard product grid on category and brand pages into a spreadsheet-like table optimized for fast, multi-product ordering. It is designed for B2B stores and wholesale buyers who need to add many products to the cart quickly.

<div class="placeholder-screenshot">Category page toolbar showing Grid, List, and Bulk Order toggle buttons with Bulk Order active</div>

---

## Enabling Bulk Order Mode

### Where to find it

**Theme Styles** > **eShopping** > **Bulk Order** > **Show bulk order mode**

### How to configure

1. Open your **Theme Editor** (Storefront > My Themes > Customize).
2. Go to **Theme Styles** > **eShopping** > **Bulk Order**.
3. Check the **Show bulk order mode** box to enable it, or uncheck to disable.
4. Click **Save & Apply**.

When enabled, a **Bulk Order** toggle button appears in the product listing toolbar alongside the grid and list view toggles on every category and brand page. Customers click it to switch into the table view.

---

## How It Works

### Table layout (desktop)

The bulk order table displays products in rows with these columns:

| Column | What it shows |
|--------|---------------|
| **Image** | Small product thumbnail (clicks through to the product page) |
| **Product** | Product name, brand, and SKU |
| **Qty in Cart** | How many of this product are already in the customer's cart |
| **Qty** | Quantity input with +/- buttons |
| **Price** | Unit price |
| **Subtotal** | Calculated total (quantity x price) |
| **Action** | **Add to Cart** or **Choose Options** button |

The table header row stays pinned at the top as customers scroll through the product list, making it easy to reference which column they are working in.

<div class="placeholder-screenshot">Bulk order table on desktop showing multiple product rows with quantity inputs, prices, subtotals, and Add to Cart buttons</div>

<div class="placeholder-screenshot">Bulk order table scrolled down showing the sticky header row pinned at the top</div>

### Mobile layout

On mobile devices, the table reformats into a card-based layout. Each product row becomes a compact card showing the product image, name, price, stock status, and quantity controls.

<div class="placeholder-screenshot">Bulk order view on mobile showing product cards with quantity inputs and action buttons</div>

### Products with options

Products that have configurable options (size, color, etc.) display a **Choose Options** button instead of a direct **Add to Cart** button. Clicking it opens a quick-view popup where the customer can select their options.

After options are selected, the chosen options appear as tags on the product row, and the button changes to **Add to Cart**.

<div class="placeholder-screenshot">Bulk order row showing a product with Choose Options button, and another row with selected options displayed as tags</div>

---

## Adding Products to Cart

### One at a time

Each row has its own **Add to Cart** button. The customer enters a quantity and clicks the button to add that single product.

### All at once

The table provides two ways to add all selected products in one action:

1. **Footer bar** -- A running-total row at the bottom of the table shows the total number of items and combined price. Click the **Add All to Cart** button to add everything with a quantity greater than zero.

2. **Sticky bottom bar** -- As the customer scrolls through the table, a bar stays fixed at the bottom of the screen showing the item count, total amount, and an **Add All to Cart** button with a cart icon and item badge.

<div class="placeholder-screenshot">Bulk order table footer showing total items count, total price, and Add All to Cart button</div>

<div class="placeholder-screenshot">Sticky bottom bar on bulk order page showing item count, total, and Add All button with badge</div>

### Progress indicator

When adding multiple products via the **Add All** button, a progress popup appears showing the current progress of adding items to the cart. Once complete, the popup offers two options:

- **View Cart** -- Navigate to the cart page.
- **Continue Shopping** -- Close the popup and keep ordering.

<div class="placeholder-screenshot">Progress popup showing a progress bar during bulk add-to-cart operation with View Cart and Continue Shopping buttons</div>

---

## Dedicated Bulk Order Page Templates

The theme includes special page templates that open directly in bulk order mode when the page loads. These are available for both category and brand pages.

### How to assign the bulk order template to a category

1. In your BigCommerce admin, go to **Products** > **Product Categories**.
2. Edit the category you want to use bulk order mode.
3. In the **Template Layout File** dropdown, select the **Bulk Order** template for categories.
4. Save the category.

For brand pages, the same option is available in the brand settings.

Pages using these templates load directly into the bulk order table. Customers can still toggle back to grid view if they prefer.

!!! tip
    Dedicated bulk order templates are ideal for categories like "Order Supplies" or "Restock Inventory" where your B2B customers expect a spreadsheet-style ordering experience.

---

## View Mode Memory

The customer's view preference (grid, list, or bulk order) is saved in their browser. When they return to a category or brand page, the theme automatically restores their last-used view mode.

You can also link directly to the bulk order view by adding `?mode=bo` to any category or brand page URL. This is useful for sharing links that open straight into the bulk order table -- for example, in email campaigns or B2B portals.

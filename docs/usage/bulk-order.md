# Bulk Order Mode

Bulk Order mode transforms the standard product grid on category and brand pages into a spreadsheet-like table optimized for fast, multi-product ordering. It is designed for B2B stores and wholesale buyers who need to add many products to the cart quickly.

## Settings

Navigate to **Page Builder** > **Theme Styles** > **eShopping** > **Product Page**.

| Setting | Type | Default | Description |
|---------|------|---------|-------------|
| `eshopping-show-bulk-order-mode` | Checkbox | `true` | Show the Bulk Order toggle button on category and brand pages |

## How It Works

When enabled, a **Bulk Order** toggle button appears in the product listing toolbar alongside the grid/list view toggle. Clicking it switches the product display from the standard grid to a compact table view.

<div class="placeholder-screenshot">Category page toolbar showing Grid, List, and Bulk Order toggle buttons with Bulk Order active</div>

### Table Layout

The bulk order table displays products in rows with the following columns:

| Column | Description |
|--------|-------------|
| **Image** | Small product thumbnail linking to the PDP |
| **Product** | Product name, brand, and SKU |
| **Qty in Cart** | Shows how many of this product are already in the cart |
| **Qty** | Quantity input with increment/decrement buttons |
| **Price** | Unit price |
| **Subtotal** | Calculated subtotal (quantity x price) |
| **Action** | Add to Cart or Choose Options button |

<div class="placeholder-screenshot">Bulk order table on desktop showing multiple product rows with quantity inputs, prices, subtotals, and Add to Cart buttons</div>

### Mobile View

On mobile devices, the table reformats into a card-based layout. Each product row becomes a compact card showing the product image, name, price, stock status, and quantity controls.

<div class="placeholder-screenshot">Bulk order view on mobile showing product cards with quantity inputs and action buttons</div>

### Products with Options

Products that have configurable options (size, color, etc.) display a **Choose Options** button instead of a direct Add to Cart button. Clicking it opens a quick-view modal where the customer can select their options before the product is added to the table.

After options are selected, the chosen options are displayed as pills on the product row, and the button changes to allow adding to cart.

<div class="placeholder-screenshot">Bulk order row showing a product with Choose Options button, and another row with selected options displayed as pills</div>

## Adding Products to Cart

### Individual Add to Cart

Each row has its own **Add to Cart** button. Enter a quantity and click the button to add that single product to the cart.

### Bulk Add All

The table includes two ways to add all selected products at once:

1. **Footer bar:** A running total row at the bottom of the table shows the total number of items and combined price. Click the **Add All to Cart** button to add everything with a quantity greater than zero.

2. **Sticky bottom bar:** As you scroll through the table, a sticky bar stays fixed at the bottom of the screen showing the item count, total amount, and an **Add All to Cart** button with a cart icon and item badge.

<div class="placeholder-screenshot">Bulk order table footer showing total items count, total price, and Add All to Cart button</div>

<div class="placeholder-screenshot">Sticky bottom bar on bulk order page showing item count, total, and Add All button with badge</div>

### Progress Modal

When adding multiple products via the **Add All** button, a progress modal appears showing the current progress of adding items to the cart. Once complete, the modal offers two options:

- **View Cart** -- navigate to the cart page
- **Continue Shopping** -- close the modal and keep ordering

<div class="placeholder-screenshot">Progress modal showing a progress bar during bulk add to cart operation with View Cart and Continue Shopping buttons</div>

## Sticky Header Row

On desktop, the table header row (column labels) remains sticky as you scroll through the product list, making it easy to reference which column you are working in.

<div class="placeholder-screenshot">Bulk order table scrolled down showing the sticky header row pinned at the top</div>

## Custom Page Templates

The theme includes dedicated bulk order page templates that default to bulk order mode when the page loads:

- **Category:** `custom/category/bulk-order.html`
- **Brand:** `custom/brand/bulk-order.html`

To assign a custom template to a category:

1. In your BigCommerce admin, go to **Products** > **Product Categories**
2. Edit the category you want to use bulk order mode
3. In the **Template Layout File** field, select `custom/category/bulk-order.html`
4. Save the category

Pages using these templates load directly into bulk order mode. The customer can still toggle back to grid view if they prefer.

!!! tip
    Custom bulk order templates are ideal for categories like "Order Supplies" or "Restock Inventory" where your B2B customers expect a spreadsheet-style ordering experience.

## Mode Persistence

The customer's view preference (grid or bulk order) is saved in their browser's local storage. When they return to a category or brand page, the theme restores their last-used view mode automatically.

The mode can also be set via URL parameter: adding `?mode=bo` to any category or brand page URL forces bulk order mode. This is useful for sharing direct links to the bulk order view.

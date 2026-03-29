# Cross-Sell Recommendations

The eShopping theme includes a built-in cross-sell feature that displays "You May Also Like" product recommendations in the cart. These recommendations are automatically generated based on the products already in the customer's cart, encouraging additional purchases without requiring any third-party apps.

## You May Also Like (Cart Cross-sell)

The cross-sell section appears in both the **cart drawer** and the **cart page**, showing a horizontal scrollable row of related product cards.

<div class="placeholder-screenshot">Cart drawer with the "You May Also Like" cross-sell section at the bottom showing a horizontal row of product cards with images, names, prices, and Add to Cart buttons</div>

<div class="placeholder-screenshot">Cart page with the "You May Also Like" cross-sell section below the line items showing a wider row of product cards</div>

### Configuration

| Setting | Value | Description |
|---------|-------|-------------|
| `eshopping-crosssell-count` | `"DESKTOP,MOBILE"` | Number of products to display |
| `eshopping-crosssell-img-width` | Integer (pixels) | Product card image width |

**Default values:**

| Setting | Default |
|---------|---------|
| `eshopping-crosssell-count` | `"6,4"` |
| `eshopping-crosssell-img-width` | `240` |

The count setting uses a comma-separated pair: the first number is the maximum products shown on **desktop**, the second is the maximum on **mobile**.

### How It Works

The cross-sell engine uses the following logic to select recommendations:

1. **Fetch related products** -- For each product in the cart, the theme retrieves its related products (configured in BigCommerce under each product's settings)
2. **Rank by frequency** -- Products that appear as related to **multiple** cart items are ranked higher, since they are more broadly relevant to the customer's interests
3. **Exclude cart items** -- Any product already in the cart is automatically excluded from the recommendations to avoid redundant suggestions
4. **Limit results** -- The list is trimmed to the configured count for the current device (desktop or mobile)

### Product Cards

Each cross-sell product card displays:

- **Product image** at the configured width
- **Product name** (linked to the product page)
- **Price** (sale price shown if applicable)
- **Add to Cart button** for quick one-click adding

<div class="placeholder-screenshot">Close-up of a single cross-sell product card showing the product image, name, price, and Add to Cart button</div>

When a customer clicks **Add to Cart** on a cross-sell product:

1. The product is added to the cart via AJAX (no page reload)
2. The cart drawer updates to show the new item
3. The cross-sell section refreshes to exclude the newly added product and potentially show new recommendations

### Responsive Behavior

| Viewport | Products Shown | Layout |
|----------|---------------|--------|
| Desktop (1024px+) | Up to 6 (configurable) | Horizontal scrollable row with left/right navigation arrows |
| Mobile (below 1024px) | Up to 4 (configurable) | Horizontal scrollable row with swipe navigation |

The product cards maintain consistent sizing across viewports, with the image width controlled by the `eshopping-crosssell-img-width` setting.

### Setting Up Related Products

For cross-sell recommendations to appear, your products must have **related products** configured in BigCommerce:

1. Go to **Products** in your BigCommerce admin
2. Edit a product
3. Scroll to the **Related Products** section
4. Add products that complement the current product
5. Save the product

!!! tip
    For the best cross-sell experience, ensure every product in your catalog has at least 3-5 related products configured. Products without related products will not contribute recommendations to the cross-sell section.

!!! note
    The cross-sell section is hidden when the cart is empty. It only appears when there is at least one product in the cart that has related products configured.

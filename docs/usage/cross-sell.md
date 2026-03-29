# Cross-Sell Recommendations

The eShopping theme includes a built-in cross-sell feature that displays "You May Also Like" product recommendations in the cart. These recommendations are automatically generated based on the products already in the customer's cart, encouraging additional purchases without requiring any third-party apps.

---

## Where Cross-Sell Appears

The cross-sell section appears in both the **cart drawer** (mini cart) and the **cart page**, showing a horizontal scrollable row of related product cards.

<div class="placeholder-screenshot">Cart drawer with the "You May Also Like" cross-sell section at the bottom showing a horizontal row of product cards with images, names, prices, and Add to Cart buttons</div>

<div class="placeholder-screenshot">Cart page with the "You May Also Like" cross-sell section below the line items showing a wider row of product cards</div>

---

## Configuration

Go to **Theme Styles** > **eShopping** > **Cart Cross-sell** and find the **Cross-sell products** setting.

This setting controls how many products are displayed in the cart drawer and on the cart page. Enter two numbers separated by a comma:

```
cart_page_count,cart_drawer_count
```

**Example:**

```
6,4
```

This means: show up to **6** cross-sell products on the cart page, and up to **4** in the cart drawer.

To disable cross-sell recommendations entirely, set this value to `0`.

---

## How It Works

The cross-sell engine selects recommendations using the following logic:

1. **Fetches related products** -- For each product in the cart, the theme retrieves its related products (configured in BigCommerce under each product's settings)
2. **Ranks by relevance** -- Products that appear as related to **multiple** cart items are ranked higher, since they are more broadly relevant to the customer's interests
3. **Excludes cart items** -- Any product already in the cart is automatically excluded from the recommendations
4. **Limits results** -- The list is trimmed to the configured count

### Product Cards

Each cross-sell product card displays:

- **Product image**
- **Product name** (linked to the product page)
- **Price** (sale price shown if applicable)
- **Add to Cart button** for quick one-click adding

<div class="placeholder-screenshot">Close-up of a single cross-sell product card showing the product image, name, price, and Add to Cart button</div>

When a customer clicks **Add to Cart** on a cross-sell product:

1. The product is added to the cart instantly (no page reload)
2. The cart drawer updates to show the new item
3. The cross-sell section refreshes to exclude the newly added product and may show new recommendations

### Responsive Behavior

| Viewport | Layout |
|----------|--------|
| **Desktop** (1024px and above) | Horizontal scrollable row with left/right navigation arrows |
| **Mobile** (below 1024px) | Horizontal scrollable row with swipe navigation |

---

## Setting Up Related Products

For cross-sell recommendations to appear, your products must have **related products** configured in BigCommerce:

1. Go to **Products** in your BigCommerce admin
2. Edit a product
3. Scroll to the **Related Products** section
4. Add products that complement the current product
5. Save the product
6. Repeat for other products in your catalog

!!! tip
    For the best cross-sell experience, ensure every product in your catalog has at least 3--5 related products configured. Think about what a customer would naturally want to buy together -- for example, a phone case and screen protector for a phone, or matching accessories for an outfit.

!!! note
    The cross-sell section is hidden when the cart is empty. It only appears when there is at least one product in the cart that has related products configured.

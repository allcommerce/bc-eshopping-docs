# Customizing the Cart

The eShopping theme provides two cart experiences: a **Cart Drawer** (mini cart) that slides in from the right for quick access, and a full **Cart Page** at `/cart` for detailed order review. Both include support for a goal progress bar, cross-sell recommendations, coupon codes, shipping estimation, and gift certificates.

## Cart Drawer (Mini Cart)

The cart drawer is a slide-out panel that appears from the right side of the screen. It opens automatically when a product is added to the cart, or when the user clicks the cart icon in the header.

<div class="placeholder-screenshot">Cart drawer open on the right side of the screen showing line items, quantity controls, subtotal, and checkout button</div>

The cart drawer displays:

- **Line items** with product image, name, selected options, and unit price
- **Quantity controls** with +/- buttons to adjust quantity inline
- **Remove button** on each item to delete it from the cart
- **Subtotal** showing the current cart total
- **Checkout button** to proceed directly to checkout
- **View Cart link** to navigate to the full cart page

At the bottom of the cart drawer, a **cross-sell section** displays product recommendations based on items in the cart. See [Cross-Sell Recommendations](cross-sell.md) for configuration details.

<div class="placeholder-screenshot">Cart drawer scrolled to bottom showing the cross-sell "You May Also Like" product row</div>

## Cart Goal Progress Bar

The cart goal progress bar encourages customers to add more items by showing visual milestones for rewards like free shipping, discounts, or free gifts. It appears at the top of both the cart drawer and the cart page.

<div class="placeholder-screenshot">Cart goal progress bar showing three milestones -- Free Shipping at $50, 10% Off at $100, Free Gift at $150 -- with progress filled to the current cart subtotal</div>

### Configuration

The progress bar is configured with a single setting:

| Setting | Value |
|---------|-------|
| `eshopping-cart-goal-items` | Pipe-and-comma separated tier list |

**Format:** `AMOUNT|TYPE|LABEL,AMOUNT|TYPE|LABEL,...`

Each tier consists of three parts separated by pipes (`|`):

- **AMOUNT** -- the cart subtotal threshold (in your store's currency)
- **TYPE** -- the reward type icon: `shipping`, `discount`, or `gift`
- **LABEL** -- the text displayed on the milestone marker

**Default value:**

```
50|shipping|Free Shipping,100|discount|10% Off,150|gift|Free Gift
```

This creates three milestones:

1. **$50** -- Free Shipping (shipping truck icon)
2. **$100** -- 10% Off (discount tag icon)
3. **$150** -- Free Gift (gift box icon)

### How It Works

- The progress bar fills proportionally as the cart subtotal increases toward each milestone
- When a milestone is reached, it is highlighted with a checkmark
- A message above the bar tells the customer how much more they need to spend to reach the next milestone (e.g., "Spend $12.50 more for Free Shipping!")
- The bar updates dynamically when items are added or removed -- no page reload required

### Preset Variations

Each theme preset ships with different goal amounts tailored to its industry:

| Preset | Tiers |
|--------|-------|
| Industrial (default) | $50 / $100 / $150 |
| AutoParts | $50 / $100 / $200 |
| Packaging | $75 / $150 / $300 |
| Electronics | $30 / $75 / $150 |

!!! tip
    Set the amounts to match your store's actual promotions. If you offer free shipping at $75, set the first tier to `75|shipping|Free Shipping`. The progress bar is purely visual -- you must also configure matching promotions in **Marketing** > **Promotions** for the rewards to actually apply at checkout.

## Cart Page

The full cart page is accessible at `/cart` and provides a complete order management experience before checkout.

<div class="placeholder-screenshot">Full cart page showing line items table, coupon code input, shipping estimator, gift certificate field, and order summary sidebar</div>

### Line Items

Each item in the cart displays:

- Product thumbnail image
- Product name (linked to the product page)
- Selected options (size, color, etc.)
- Unit price
- Quantity input with +/- buttons
- Line total (unit price x quantity)
- Remove button

<div class="placeholder-screenshot">Close-up of a cart page line item row showing image, name, options, quantity controls, price, and remove button</div>

### Coupon Code

The coupon code section allows customers to apply discount codes to their order.

1. Click the **Coupon Code** toggle to expand the input field
2. Enter the code and click **Apply**
3. If valid, the discount appears in the order summary
4. If invalid, an error message is displayed below the input

<div class="placeholder-screenshot">Cart page with coupon code section expanded, showing an entered code and the Apply button</div>

### Shipping Estimator

The shipping estimator lets customers see estimated shipping costs before proceeding to checkout.

1. Click the **Estimate Shipping & Tax** toggle to expand the form
2. Select **Country**, **State/Province**, and enter a **Zip/Postal Code**
3. Click **Estimate Shipping** to see available shipping options
4. Select a shipping method to update the order summary totals

<div class="placeholder-screenshot">Cart page with shipping estimator expanded showing country, state, and zip fields with estimated shipping options listed below</div>

### Gift Certificate Redemption

Customers can apply gift certificate codes to reduce their order total.

1. Click the **Gift Certificate** toggle to expand the input field
2. Enter the gift certificate code and click **Apply**
3. If valid, the gift certificate amount is deducted from the order total
4. If invalid or already fully redeemed, an error message is displayed

<div class="placeholder-screenshot">Cart page with gift certificate section expanded, showing an entered code and the Apply button</div>

### Order Summary

The order summary sidebar shows a breakdown of the order:

- **Subtotal** -- sum of all line item totals
- **Discount** -- any applied coupon or automatic discounts
- **Shipping** -- estimated shipping cost (if calculated)
- **Tax** -- estimated tax amount
- **Gift Certificate** -- applied gift certificate credit
- **Grand Total** -- final order total
- **Checkout button** -- proceeds to the checkout flow

<div class="placeholder-screenshot">Order summary sidebar showing subtotal, discount, shipping, tax, and grand total with a Checkout button</div>

## Configuring Cart Page Promotions

The cart goal progress bar is a visual motivator, but the actual discounts and free shipping must be configured as real promotions in your BigCommerce admin.

### Creating a Free Shipping Promotion

1. Go to **Marketing** > **Promotions** in your BigCommerce admin
2. Click **Create Promotion**
3. Set the promotion type to **Free Shipping**
4. Configure the minimum order amount to match your cart goal tier (e.g., $50)
5. Optionally add a **Banner Message** that displays on the cart page

### Using Dynamic Placeholders in Banner Messages

BigCommerce promotion banners support dynamic placeholders. Use `%%condition.remaining%%` to show the customer how much more they need to spend:

```
Spend %%condition.remaining%% more to get FREE SHIPPING!
```

This message automatically updates based on the customer's current cart subtotal and disappears once the threshold is met.

!!! note
    The same approach works for any promotion type supported by BigCommerce. Refer to the [BigCommerce Promotions documentation](https://support.bigcommerce.com/s/article/Automatic-Promotions) for full details on creating and configuring promotions.

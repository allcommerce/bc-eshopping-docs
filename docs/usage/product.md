# Customizing Product Pages

The eShopping theme provides a feature-rich product detail page (PDP) with a custom image gallery, shipping info strip, FAQ/warranty tabs, mobile sticky add-to-cart, frequently bought together bundles, volume discount display, and urgency signals.

## Product Detail Page Layout

The PDP uses a two-column layout on desktop:

- **Left column:** Image gallery with vertical thumbnails. The gallery uses a custom slider with EasyZoom for hover-to-zoom functionality. This is **not** a Slick carousel -- it is a purpose-built image viewer with thumbnail navigation on the left side of the main image.
- **Right column:** Product information including title, price, options, quantity selector, and Add to Cart button.

On mobile, the layout switches to a full-width image slider with dot navigation below the image. Thumbnails are hidden on small screens.

<div class="placeholder-screenshot">Product detail page showing image gallery with left-side thumbnails on desktop, product info on the right</div>

<div class="placeholder-screenshot">Product detail page on mobile showing full-width image slider with dot pagination</div>

## Shipping & Returns Info Strip

A row of info badges appears below the price area on the PDP, providing at-a-glance shipping, warranty, and return policy information.

### Settings

Navigate to **Page Builder** > **Theme Styles** > **eShopping** > **Product Page**.

| Setting | Type | Default |
|---------|------|---------|
| `eshopping-pdp-shipping-text` | Text input | `Free Shipping|on orders over $500|1-Year Warranty|included with purchase|30-Day Returns|hassle-free policy` |

### How It Works

The value is a **pipe-separated** string of alternating label/description pairs:

```
Label1|Description1|Label2|Description2|Label3|Description3
```

Each pair renders as one info badge with an icon, a bold label, and a smaller description line. The theme displays up to three badges with dedicated icons:

1. Truck icon -- for shipping info
2. Shield icon -- for warranty info
3. Clock icon -- for returns info

### Customization Examples

**For an auto parts store:**

```
Free Shipping|on parts orders over $250|Fitment Guarantee|verified compatibility|30-Day Returns|no-hassle policy
```

**For a packaging store:**

```
Free Shipping|on orders over $300|Bulk Pricing|volume discounts available|Same-Day Ship|orders by 2pm
```

<div class="placeholder-screenshot">Shipping info strip on PDP showing three badges: Free Shipping, 1-Year Warranty, and 30-Day Returns</div>

## FAQ / Warranty Tab

The PDP includes a configurable FAQ tab and warranty card grid displayed within the product description tabs area.

### Settings

Navigate to **Page Builder** > **Theme Styles** > **eShopping** > **Product Page**.

| Setting | Type | Default |
|---------|------|---------|
| `eshopping-pdp-show-faq-tab` | Checkbox | `true` |
| `eshopping-pdp-warranty-text` | Text input | *(see below)* |

### FAQ Tab

When `eshopping-pdp-show-faq-tab` is enabled, an **FAQ** tab appears alongside the Description, Videos, and Warranty tabs. The FAQ tab contains a question submission form where customers can enter their name, email, and question about the product.

<div class="placeholder-screenshot">PDP tabs showing Description, Videos, Specs, Warranty, and FAQ tabs with the FAQ form visible</div>

### Warranty Card Grid

The warranty card grid is displayed inside the **Warranty** tab (which uses the product's built-in warranty field from BigCommerce). Below the warranty text, the theme renders a grid of four info cards.

The `eshopping-pdp-warranty-text` setting uses the same pipe-separated format as the shipping strip:

```
Heading1|Content1|Heading2|Content2|Heading3|Content3|Heading4|Content4
```

**Default value:**

```
What's Covered|Manufacturing defects, material failures, broken welds, and faulty components under normal field use conditions.|What's Not Covered|Damage from misuse, improper maintenance, normal wear and tear, or unauthorized modifications.|How to Claim|Contact us with your order number and description of the issue.|Extended Warranty|Extend your coverage for additional protection. Contact us for details.
```

Each pair renders as a card with a colored icon, heading, and description text. The four cards use alternating green (positive) and terra (caution) icon colors:

1. Shield check icon (green) -- What's Covered
2. Close icon (terra) -- What's Not Covered
3. Badge check icon (green) -- How to Claim
4. Plus icon (terra) -- Extended Warranty

<div class="placeholder-screenshot">Warranty tab showing warranty text from BigCommerce followed by four warranty info cards in a grid</div>

## Mobile Sticky Add-to-Cart

A fixed bottom bar on mobile devices that keeps the product price and Add to Cart button always accessible as the customer scrolls through the page.

### Settings

Navigate to **Page Builder** > **Theme Styles** > **eShopping** > **Product Page**.

| Setting | Type | Default |
|---------|------|---------|
| `eshopping-pdp-show-mobile-atc` | Checkbox | `true` |

When enabled, a compact bar appears at the bottom of the screen on mobile devices containing:

- The product price (with or without tax, matching the store's configuration)
- An **Add to Cart** button

The bar is hidden on desktop. It becomes visible as the user scrolls past the main Add to Cart button in the product info section.

<div class="placeholder-screenshot">Mobile PDP showing the sticky add-to-cart bar fixed at the bottom of the screen with price and Add to Cart button</div>

## Frequently Bought Together (FBT)

The Frequently Bought Together section encourages customers to purchase complementary products as a bundle, with optional discount pricing.

### Settings

Navigate to **Page Builder** > **Theme Styles** > **eShopping** > **Product Page**.

| Setting | Type | Default | Description |
|---------|------|---------|-------------|
| `eshopping-fbt-count` | Select | `2` | Number of related products to show (0 disables FBT) |
| `eshopping-fbt-discount-percent` | Number | `0` | Bundle discount percentage (0 = no discount) |

### How It Works

The FBT section uses the product's **Related Products** data from BigCommerce. To configure which products appear:

1. In your BigCommerce admin, go to **Products** > edit a product
2. Scroll to the **Related Products** section
3. Add the products you want to recommend as a bundle

The FBT section displays:

- **The current product** (always included, checkbox checked and disabled)
- **Related products** up to the configured `eshopping-fbt-count` limit
- Each related product has a checkbox to include/exclude it from the bundle
- Products with options show a **Select Options** button that opens a quick-view modal
- A **summary bar** at the bottom shows the bundle price, original price, savings, and an **Add Items** button

### Bundle Discount

When `eshopping-fbt-discount-percent` is set to a value greater than 0:

- The bundle total reflects the discounted price
- A strikethrough original price is shown
- A savings badge displays the amount saved (e.g., "You save $12.50")

!!! tip
    Set the discount to `0` if you want to show the FBT section without any price reduction. Customers can still conveniently add multiple products to the cart in one click.

<div class="placeholder-screenshot">Frequently Bought Together section showing the main product plus two related products with checkboxes, bundle pricing, and Add Items button</div>

## Volume Discount Display

When a product has **bulk pricing** configured in BigCommerce, the theme automatically displays an inline pricing table on the PDP. No theme setting is required -- the display is driven entirely by the product's bulk pricing data.

### What It Shows

- **Pricing table:** A collapsible table showing quantity ranges, per-unit prices, and savings percentages for each bulk pricing tier
- **Active tier highlighting:** The current quantity's pricing tier is highlighted in the table
- **Savings summary:** Above the table, a summary shows the current per-unit price with a strikethrough original price when a bulk discount applies
- **Progress nudge:** When the customer's quantity is close to the next discount tier, a nudge message encourages them to add more items

The volume discount display updates dynamically when:

- The customer changes the quantity input
- A product variant is selected (bulk pricing may differ per variant)

### How to Configure Bulk Pricing

Bulk pricing is configured in your BigCommerce admin:

1. Go to **Products** > edit a product
2. Navigate to the **Pricing** section
3. Under **Bulk Pricing**, add your pricing tiers

The theme supports all BigCommerce bulk pricing types: percentage discount, fixed amount off, and fixed price.

<div class="placeholder-screenshot">Volume discount table on PDP showing quantity tiers with per-unit pricing, active tier highlighted, and savings summary above</div>

## Urgency Signals

Urgency signals display social-proof indicators on the PDP to create a sense of demand and encourage purchase decisions. These are simulated values based on configurable ranges.

### Settings

Navigate to **Page Builder** > **Theme Styles** > **eShopping** > **Product Page**.

#### Viewing Count

| Setting | Type | Default | Description |
|---------|------|---------|-------------|
| `eshopping-urgency-view-count` | Checkbox | `true` | Enable "X people are viewing this" signal |
| `eshopping-urgency-view-range` | Text input | `3,25` | Min and max viewer count, comma-separated |

When enabled, displays a message like **"12 people are viewing this right now"** with a fire icon. The number is randomly generated within the configured range and remains consistent per product within a browser session.

#### Last Order

| Setting | Type | Default | Description |
|---------|------|---------|-------------|
| `eshopping-urgency-last-order` | Checkbox | `true` | Enable "Last ordered X hours ago" signal |
| `eshopping-urgency-order-range` | Text input | `1,48` | Min and max hours, comma-separated |

When enabled, displays a message like **"Last ordered 5 hours ago"** with a cart icon. The time is randomly generated within the configured range. This signal is automatically hidden for out-of-stock products.

#### Auto-Refresh

| Setting | Type | Default | Description |
|---------|------|---------|-------------|
| `eshopping-urgency-refresh` | Checkbox | `true` | Periodically update urgency numbers |

When enabled, the displayed numbers drift slightly every 30 seconds to simulate real-time activity. The values animate smoothly when they change.

### How the Numbers Work

The urgency values use a seeded random number generator based on the product ID and a per-session key. This means:

- The same visitor sees consistent numbers for the same product during their session
- Different visitors see different numbers
- Numbers refresh naturally between sessions

Both signals appear simultaneously below the Add to Cart area on the PDP.

<div class="placeholder-screenshot">Urgency signals on PDP showing "14 people are viewing this right now" with fire icon and "Last ordered 3 hours ago" with cart icon</div>

!!! note
    These are simulated social-proof signals, not real-time data. They are intended to create a sense of urgency. The values are randomly generated within your configured ranges.

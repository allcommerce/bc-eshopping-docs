# Customizing Product Pages

The eShopping theme gives your product detail pages (PDP) a polished, conversion-focused layout with an image gallery, shipping info strip, FAQ and warranty tabs, mobile sticky add-to-cart, Frequently Bought Together bundles, volume discount display, and urgency signals. Everything is controlled from the Theme Editor -- no coding required.

---

## Product Page Layout

On desktop the PDP uses a two-column design:

- **Left column** -- Image gallery with vertical thumbnails on the left side of the main image. Hover over the main image to zoom in.
- **Right column** -- Product title, price, options, quantity selector, and **Add to Cart** button.

On mobile, the layout switches to a full-width image slider with dot navigation below the image. Thumbnails are hidden on small screens.

<div class="placeholder-screenshot">Product detail page showing image gallery with left-side thumbnails on desktop, product info on the right</div>

<div class="placeholder-screenshot">Product detail page on mobile showing full-width image slider with dot pagination</div>

---

## Shipping & Returns Info Strip

A row of info badges appears below the price area, giving customers at-a-glance shipping, warranty, and return policy information.

<div class="placeholder-screenshot">Shipping info strip on PDP showing three badges: Free Shipping, 1-Year Warranty, and 30-Day Returns</div>

### Where to find it

**Theme Styles** > **eShopping** > **Product Page (PDP)** > **PDP Shipping Text**

### How to edit

The **PDP Shipping Text** field uses a simple pipe-separated format. Enter alternating label and description pairs separated by `|`:

```
Label 1|Description 1|Label 2|Description 2|Label 3|Description 3
```

Each pair becomes one info badge with an icon, a bold label, and a smaller description line. The theme assigns a dedicated icon to each position:

| Position | Icon | Purpose |
|----------|------|---------|
| 1st pair | Truck | Shipping info |
| 2nd pair | Shield | Warranty info |
| 3rd pair | Clock | Returns info |

### Examples

**Auto parts store:**

```
Free Shipping|on parts orders over $250|Fitment Guarantee|verified compatibility|30-Day Returns|no-hassle policy
```

**Packaging store:**

```
Free Shipping|on orders over $300|Bulk Pricing|volume discounts available|Same-Day Ship|orders by 2pm
```

### How to configure

1. Open your **Theme Editor** (Storefront > My Themes > Customize).
2. Go to **Theme Styles** > **eShopping** > **Product Page (PDP)**.
3. Edit the **PDP Shipping Text** field using the pipe-separated format above.
4. Click **Save & Apply**.

---

## FAQ Tab

An **FAQ** tab can be added alongside the Description, Videos, and Warranty tabs on the product page. It displays a question-submission form so customers can ask about the product directly.

<div class="placeholder-screenshot">PDP tabs showing Description, Videos, Specs, Warranty, and FAQ tabs with the FAQ form visible</div>

### Where to find it

**Theme Styles** > **eShopping** > **Product Page (PDP)** > **Show FAQ Tab**

### How to configure

1. Open your **Theme Editor**.
2. Go to **Theme Styles** > **eShopping** > **Product Page (PDP)**.
3. Check the **Show FAQ Tab** box to enable it, or uncheck to hide it.
4. Click **Save & Apply**.

When enabled, customers see a tab labeled **FAQ** where they can enter their name, email, and question.

---

## Warranty Info Cards

The **Warranty** tab (which displays the warranty text you set in the BigCommerce product editor) also includes a grid of four info cards below the warranty description. These cards summarize coverage, exclusions, claim instructions, and extended warranty options.

<div class="placeholder-screenshot">Warranty tab showing warranty text from BigCommerce followed by four warranty info cards in a grid</div>

### Where to find it

**Theme Styles** > **eShopping** > **Product Page (PDP)** > **PDP Warranty Text**

### How to edit

The **PDP Warranty Text** field uses the same pipe-separated format as the shipping strip. Enter alternating heading and content pairs:

```
Heading 1|Content 1|Heading 2|Content 2|Heading 3|Content 3|Heading 4|Content 4
```

Each pair becomes a card with a colored icon, a bold heading, and descriptive text. The four cards use alternating green and accent-colored icons:

| Card | Icon | Default heading |
|------|------|-----------------|
| 1 | Shield check (green) | What's Covered |
| 2 | Close (accent) | What's Not Covered |
| 3 | Badge check (green) | How to Claim |
| 4 | Plus (accent) | Extended Warranty |

**Default value:**

```
What's Covered|Manufacturing defects, material failures, broken welds, and faulty components under normal field use conditions.|What's Not Covered|Damage from misuse, improper maintenance, normal wear and tear, or unauthorized modifications.|How to Claim|Contact us with your order number and description of the issue.|Extended Warranty|Extend your coverage for additional protection. Contact us for details.
```

### How to configure

1. Open your **Theme Editor**.
2. Go to **Theme Styles** > **eShopping** > **Product Page (PDP)**.
3. Edit the **PDP Warranty Text** field using the pipe-separated format above.
4. Click **Save & Apply**.

---

## Mobile Sticky Add-to-Cart

A compact bar fixed to the bottom of the screen on mobile devices keeps the product price and **Add to Cart** button always visible as customers scroll through the page.

<div class="placeholder-screenshot">Mobile PDP showing the sticky add-to-cart bar fixed at the bottom of the screen with price and Add to Cart button</div>

### Where to find it

**Theme Styles** > **eShopping** > **Product Page (PDP)** > **Show Mobile Sticky Add to Cart**

### How it works

- The bar appears only on mobile devices.
- It becomes visible once the customer scrolls past the main **Add to Cart** button in the product info area.
- It displays the current product price (with or without tax, matching your store configuration) and a compact **Add to Cart** button.

### How to configure

1. Open your **Theme Editor**.
2. Go to **Theme Styles** > **eShopping** > **Product Page (PDP)**.
3. Check the **Show Mobile Sticky Add to Cart** box to enable it, or uncheck to disable.
4. Click **Save & Apply**.

---

## Frequently Bought Together (FBT)

The Frequently Bought Together section encourages customers to purchase complementary products as a bundle, with an optional discount.

<div class="placeholder-screenshot">Frequently Bought Together section showing the main product plus two related products with checkboxes, bundle pricing, and Add Items button</div>

### Where to find it

**Theme Styles** > **eShopping** > **Frequently Bought Together**

Two settings control this feature:

| Setting label | What it does |
|---------------|--------------|
| **FBT Products Count** | How many related products to show. Choose **Off** to disable the section, or **1**, **2**, or **3** to display that many products alongside the main item. |
| **Visual Bundle Discount %** | A percentage discount applied to the bundle total. Enter **0** for no discount. |

### Setting up related products

The FBT section pulls from the product's **Related Products** in BigCommerce:

1. In your BigCommerce admin, go to **Products** and edit a product.
2. Scroll to the **Related Products** section.
3. Add the products you want to recommend as a bundle.
4. Save the product.

### How it works for customers

- **The current product** is always included (its checkbox is checked and cannot be unchecked).
- **Related products** appear beside it, each with a checkbox to include or exclude it from the bundle.
- Products with options (size, color, etc.) show a **Select Options** button that opens a quick-view popup.
- A **summary bar** at the bottom shows the bundle price, original price, savings, and an **Add Items** button.

### Bundle discount

When the **Visual Bundle Discount %** is set to a value greater than 0:

- The bundle total reflects the discounted price.
- A strikethrough original price is shown.
- A savings badge displays the amount saved (e.g., "You save $12.50").

!!! tip
    Set the discount to **0** if you want to show the FBT section without any price reduction. Customers can still conveniently add multiple products to the cart in one click.

### How to configure

1. Open your **Theme Editor**.
2. Go to **Theme Styles** > **eShopping** > **Frequently Bought Together**.
3. Set **FBT Products Count** to the number of related products you want to display (or **Off** to hide the section).
4. Enter a value for **Visual Bundle Discount %** (use **0** for no discount).
5. Click **Save & Apply**.

---

## Volume Discount Display

When a product has **bulk pricing** configured in BigCommerce, the theme automatically displays an inline pricing table on the product page. No theme setting is needed -- the display appears whenever bulk pricing data exists for the product.

<div class="placeholder-screenshot">Volume discount table on PDP showing quantity tiers with per-unit pricing, active tier highlighted, and savings summary above</div>

### What customers see

- **Pricing table** -- A collapsible table showing quantity ranges, per-unit prices, and savings percentages for each tier.
- **Active tier highlighting** -- The tier matching the customer's current quantity is highlighted.
- **Savings summary** -- Above the table, a summary shows the per-unit price with a strikethrough original price when a bulk discount applies.
- **Progress nudge** -- When the customer's quantity is close to the next discount tier, a message encourages them to add more items.

The table updates dynamically when:

- The customer changes the quantity.
- A different variant is selected (bulk pricing may differ per variant).

### Setting up bulk pricing

Bulk pricing is configured in your BigCommerce admin -- not in the Theme Editor:

1. Go to **Products** and edit a product.
2. Navigate to the **Pricing** section.
3. Under **Bulk Pricing**, add your pricing tiers.

The theme supports all BigCommerce bulk pricing types: percentage discount, fixed amount off, and fixed price.

---

## Urgency Signals (Social Proof)

Urgency signals display social-proof indicators on the product page to create a sense of demand and encourage faster purchase decisions.

<div class="placeholder-screenshot">Urgency signals on PDP showing "14 people are viewing this right now" with fire icon and "Last ordered 3 hours ago" with cart icon</div>

### Where to find it

**Theme Styles** > **eShopping** > **Urgency Signals (Social Proof)**

Four settings control urgency signals:

| Setting label | What it does |
|---------------|--------------|
| **Show live view count** | Displays a message like "12 people are viewing this right now" with a fire icon. |
| **Show last order time** | Displays a message like "Last ordered 5 hours ago" with a cart icon. Automatically hidden for out-of-stock products. |
| **Fake view count range** | The minimum and maximum viewer count, entered as two numbers separated by a comma (e.g., `3,25`). |
| **Last order time range** | The minimum and maximum hours ago, entered as two numbers separated by a comma (e.g., `1,48`). |

Both signals appear below the **Add to Cart** area on the product page.

### How the numbers work

- Numbers are randomly generated within the range you set.
- The same visitor sees consistent numbers for the same product during their browsing session.
- Different visitors see different numbers.
- Numbers refresh naturally between sessions.
- The displayed values drift slightly every 30 seconds to simulate real-time activity.

### How to configure

1. Open your **Theme Editor**.
2. Go to **Theme Styles** > **eShopping** > **Urgency Signals (Social Proof)**.
3. Check **Show live view count** and/or **Show last order time** to enable the signals you want.
4. Set the **Fake view count range** (e.g., `3,25` means the viewer count will be between 3 and 25).
5. Set the **Last order time range** (e.g., `1,48` means the "last ordered" time will be between 1 and 48 hours ago).
6. Click **Save & Apply**.

!!! note
    These are simulated social-proof signals, not real-time data. They are designed to create a sense of urgency. The numbers are randomly generated within the ranges you set.

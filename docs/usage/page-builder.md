# Using Page Builder with eShopping

The eShopping theme is fully compatible with BigCommerce's **Page Builder**, a drag-and-drop editor that lets you add custom content to your store pages without any coding.

Page Builder works alongside the theme's built-in sections. While the theme's features are configured through **Theme Styles** > **eShopping**, Page Builder lets you add additional content blocks like banners, text, images, videos, and custom HTML to specific areas on each page.

---

## How to Open Page Builder

1. In your BigCommerce admin, go to **Storefront** > **My Themes**.
2. Click **Customize** on the eShopping theme.
3. The Page Builder editor opens with a preview of your storefront.
4. On the left panel, you can switch between **Theme Styles** (for eShopping settings) and the **widget library** (for drag-and-drop content).

<div class="placeholder-screenshot">Page Builder interface showing the left panel with widget library and the storefront preview on the right</div>

---

## Widget Regions

The eShopping theme includes **widget regions** — designated areas on each page where you can drop widgets. These regions are marked with blue dotted outlines when you open Page Builder.

### Home Page Regions

The home page has the most widget regions, allowing you to add content between each built-in section:

| Region | Location |
|--------|----------|
| **Below Menu** | Between the navigation bar and the hero carousel |
| **Below Carousel** | Between the hero carousel and the first content section |
| **Home Content** | Main content area (useful for full-width banners or promotions) |
| **Below Featured Products** | After the featured products section |
| **Below Top Products** | After the best-selling products section |
| **Below New Products** | After the new arrivals section |
| **Below Products by Category** | After the tabbed products-by-category section |
| **Below Brands** | After the brand logos section |
| **Below Blog Posts** | After the blog posts section (if enabled) |
| **Below Newsletter** | After the newsletter signup section |

<div class="placeholder-screenshot">Home page in Page Builder showing blue dotted widget regions between sections like Below Carousel, Home Content, Below Featured Products</div>

!!! tip
    The **Below Carousel** and **Home Content** regions are great places to add a promotional banner, seasonal sale announcement, or featured collection highlight.

### Product Page Regions

| Region | Location |
|--------|----------|
| **Above Content** | Above the product details (image + info area) |
| **Below Price** | Below the product price |
| **Below Actions** | Below the Add to Cart button area |
| **Above Description** | Above the product description tabs |
| **Below Description** | Below the product description tabs |
| **Above Related Products** | Above the related products carousel |
| **Below Related Products** | Below the related products carousel |
| **Below Content** | At the bottom of the product page |
| **Below Warranty** | Below the FAQ/warranty tab content |

<div class="placeholder-screenshot">Product page in Page Builder showing widget regions like Below Price, Below Actions, Above Description</div>

!!! tip
    Use the **Below Price** region to add trust badges, payment icons, or a short promotional message. Use **Below Warranty** to add an FAQ accordion widget (using PapaThemes Widgets).

### Category Page Regions

| Region | Location |
|--------|----------|
| **Below Header** | Below the category title and breadcrumbs |
| **Below Content** | Below the product grid |

### Brand Page Regions

| Region | Location |
|--------|----------|
| **Below Header** | Below the brand name and logo |
| **Below Content** | Below the product grid |

### Cart Page

| Region | Location |
|--------|----------|
| **Below Totals** | Below the cart totals and checkout button |

### Sidebar

| Region | Location |
|--------|----------|
| **Below Sidebar** | Below all sidebar content (category tree, filters, promo card) |

### Search Page

| Region | Location |
|--------|----------|
| **Below Content** | Below the search results |

---

## Recommended Widgets

### PapaThemes Widgets (Free App)

For the best experience with eShopping, install the free **[PapaThemes Widgets](https://www.bigcommerce.com/apps/papathemes-widgets/)** app. It adds several useful widgets to Page Builder:

- **Flex Banners** — Responsive banner images with text overlays, buttons, and multiple layout options. Great for hero banners, promotional tiles, and category features.
- **Accordion** — Expandable FAQ-style content blocks. Perfect for adding Q&A sections to category or product pages.
- **HTML Widget** — Insert custom HTML code for special content like embedded videos, custom layouts, or third-party scripts.

### Using Flex Banners

Flex Banners are the most versatile widget for customizing your store's visual appearance.

**To add a promotional banner on the home page:**

1. Open **Page Builder** and navigate to the home page.
2. Drag a **Flex Banners | PapaThemes Beautify** widget into the **Below Carousel** or **Home Content** region.
3. In the widget settings:
    - Upload your banner image.
    - Set **Image width** and **Image height** to match your image dimensions.
    - Optionally add heading text, description text, and an action button.
    - Configure responsive sizes for tablet and mobile.
4. Click **Save**.

<div class="placeholder-screenshot">Page Builder showing a Flex Banners widget being configured with image upload, heading text, and button settings</div>

### Using the Accordion Widget

The Accordion widget is ideal for adding FAQ sections to category pages.

**To add FAQs to a category page:**

1. Open **Page Builder** and navigate to the category page.
2. Drag an **Accordion | PapaThemes** widget into the **Below Content** region.
3. Add your questions and answers using the widget editor.
4. Click **Save**.

<div class="placeholder-screenshot">Category page with an Accordion widget in the Below Content region showing expandable FAQ items</div>

### Using the HTML Widget

The HTML Widget lets you insert custom content like:

- A promotional announcement bar
- Embedded YouTube videos
- Custom trust badges or partner logos
- Payment method icons

**To add a promotional message to the cart page:**

1. Open **Page Builder** and navigate to the cart page.
2. Drag an **HTML Widget** into the **Below Totals** region.
3. Paste your HTML content. For example, a simple list of checkout benefits:

```html
<ul>
  <li>Free shipping on orders over $500</li>
  <li>30-day hassle-free returns</li>
  <li>Secure checkout with SSL encryption</li>
</ul>
```

4. Click **Save HTML**.

<div class="placeholder-screenshot">Cart page with an HTML widget in the Below Totals region showing a benefits list</div>

---

## Global vs. Page-Specific Regions

Some widget regions have two versions:

- **Page-specific** (e.g., "Above Content") — Widgets placed here only appear on the page you are editing.
- **Global** (e.g., "Above Content - Global") — Widgets placed here appear on **all pages** of that type across your store.

For example, placing a trust badge widget in the "Below Price - Global" region on a product page will show that badge on every product page in your store.

!!! note
    Global regions are useful for content that should appear everywhere, like trust badges, shipping information, or payment icons. Use page-specific regions for content unique to a particular product, category, or page.

---

## Tips for Page Builder

- **Preview on mobile:** Use the device toggle in Page Builder to check how your widgets look on desktop, tablet, and mobile.
- **Don't overload regions:** Adding too many widgets can slow down page load time. Keep it focused.
- **Match the theme's style:** Use colors and fonts that complement the eShopping theme. Check your current palette in **Theme Styles** > **eShopping** > **Colors**.
- **Use PapaThemes Widgets:** They are designed and tested specifically to work well with eShopping and other PapaThemes themes.

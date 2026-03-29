# Setting Up the Home Page

The eShopping home page is built from modular sections that you can turn on or off and customize entirely from the **Theme Editor**. No coding is required -- just toggle sections, enter your content, and save.

To open the Theme Editor, go to **Storefront > My Themes > Customize** in your BigCommerce admin panel.

<div class="placeholder-screenshot">Full home page overview showing all sections stacked vertically: hero carousel, trust strip, products-by-category tabs, brand logos, newsletter, and footer.</div>

---

## Hero Carousel

The hero carousel is a full-width banner area at the top of your home page that rotates through promotional slides with a smooth crossfade animation.

<div class="placeholder-screenshot">Hero carousel displaying a large promotional banner with heading text and a call-to-action button.</div>

### How to set it up

1. In your BigCommerce admin, go to **Storefront > Home Page Carousel**.
2. Upload your carousel images and fill in the heading, description, and link URL for each slide.
3. Open the **Theme Editor** (**Storefront > My Themes > Customize**).
4. Go to **Theme Styles** > **eShopping** > **Homepage Sections**.
5. Check **Show Hero Carousel** to turn it on.
6. Click **Save & Apply**.

!!! tip
    For best results, use images that are at least 1600 pixels wide. Images are automatically cropped to fit the full width of the screen without causing any layout jump.

---

## Trust Strip

The trust strip is a row of badges displayed directly below the hero carousel. Use it to highlight key selling points like free shipping, satisfaction guarantees, customer ratings, or support hours.

<div class="placeholder-screenshot">Trust strip showing four badges in a horizontal row below the hero carousel, each with a bold title and supporting text.</div>

### How to set it up

1. Open the **Theme Editor**.
2. Go to **Theme Styles** > **eShopping** > **Homepage Sections**.
3. Check **Show Trust Strip** to turn it on.
4. Go to **Theme Styles** > **eShopping** > **Trust Strip**.
5. In the **Trust Strip Items** field, enter your badges using the format below.
6. Click **Save & Apply**.

### Content format

Enter your badges as a single line of text with each piece separated by a pipe character (`|`). Badges are defined in pairs: a **Title** followed by a **Subtitle**.

**Format:**

```
Title 1|Subtitle 1|Title 2|Subtitle 2|Title 3|Subtitle 3
```

**Example (4 badges):**

```
Made in USA|Fast & reliable shipping on all orders|Free Shipping|Shop with confidence, guaranteed|4.8 Star Rating|Easy returns within 30 days|Expert Support|Available Mon-Sat, 9am-6pm
```

This produces:

| Badge | Title | Subtitle |
|-------|-------|----------|
| 1 | Made in USA | Fast & reliable shipping on all orders |
| 2 | Free Shipping | Shop with confidence, guaranteed |
| 3 | 4.8 Star Rating | Easy returns within 30 days |
| 4 | Expert Support | Available Mon-Sat, 9am-6pm |

!!! warning
    Make sure you have an even number of items separated by pipes. If you have an odd number, the last badge will appear without a subtitle.

---

## Products by Category Tabs

This section displays your products in a tabbed layout on the home page. Visitors can switch between tabs like "Best Selling", "Featured", "New Arrivals", and "Top Rated" without reloading the page.

<div class="placeholder-screenshot">Products-by-category section with a tab bar showing "Featured", "Best Selling", and "New Arrivals" tabs, with a product grid below.</div>

### How to set it up

1. Open the **Theme Editor**.
2. Go to **Theme Styles** > **eShopping** > **Homepage Sections**.
3. Check the product sections you want to display: **Show Featured Products**, **Show Best Sellers**, **Show New Arrivals**, and/or **Show Categories**.
4. Go to **Theme Styles** > **eShopping** > **Products by Category** for additional options.
5. Click **Save & Apply**.

### Choosing which tabs to show

Each tab can be turned on or off independently under **Theme Styles** > **eShopping** > **Products by Category**:

- **Show Bestselling tab** -- Products that sell the most
- **Show Featured tab** -- Products you have marked as featured
- **Show New tab** -- Your newest products
- **Show Reviews tab** -- Top-rated products by customer reviews

### Setting the default active tab

Under **Theme Styles** > **eShopping** > **Products by Category**, use the **Default active tab** dropdown to choose which tab is selected when the page first loads. Options are:

- Bestselling
- Featured
- Newest
- Top Rated

### Grid layout

The **Grid layout** field under **Theme Styles** > **eShopping** > **Products by Category** controls how many items appear. Enter three numbers separated by commas:

```
categories, products, subcategories
```

For example, `3,4,6` means 3 categories, 4 products per category, and 6 subcategories.

### Showing products from specific categories

By default, products are pulled from your homepage product settings in the BigCommerce admin.

To show products from specific categories, enter the category IDs in the **Category IDs** field under **Theme Styles** > **eShopping** > **Products by Category**, separated by commas:

```
23,45,67
```

!!! tip "Finding a category ID"
    In your BigCommerce admin, go to **Products > Product Categories** and click on a category. The category ID appears in the browser's address bar at the end of the URL.

### Lazy loading for faster pages

Check **Lazy load sections on scroll** under **Theme Styles** > **eShopping** > **Products by Category** to load product data only when visitors scroll down to that section. This makes your page load faster initially.

---

## Brand Logos

Displays a horizontally scrollable row of brand logos sourced from your product catalog.

<div class="placeholder-screenshot">Brand logos row showing several brand images in a horizontal scrollable strip.</div>

### How to set it up

1. Make sure your products have brands assigned in **Products > Brands** in the BigCommerce admin, and that each brand has a logo image uploaded.
2. Open the **Theme Editor**.
3. Go to **Theme Styles** > **eShopping** > **Homepage Sections**.
4. In the **Homepage Brands Limit** field, enter the maximum number of brand logos to display (for example, `8`).
5. Click **Save & Apply**.

---

## Newsletter Section

A call-to-action block that encourages visitors to subscribe to your email newsletter.

<div class="placeholder-screenshot">Newsletter section showing a heading, subtitle text, and an email subscription form with a submit button.</div>

### How to set it up

1. Open the **Theme Editor**.
2. Go to **Theme Styles** > **eShopping** > **Homepage Sections**.
3. Check **Show Newsletter** to turn it on.
4. In the **Newsletter Signup Text** field, enter your heading and subtitle separated by a pipe character (`|`).
5. Click **Save & Apply**.

### Content format

```
Heading|Subtitle
```

**Example:**

```
Stay Updated with Our Newsletter|Product launches, tips, and exclusive offers delivered to your inbox.
```

You can use basic HTML in the heading for emphasis. For example, wrapping words in `<em>` tags will display them in an elegant italic style:

```
Stay Updated with <em>Our Newsletter</em>|Product launches, tips, and exclusive offers.
```

!!! note
    The newsletter form connects to the email marketing provider you have configured in your BigCommerce admin under **Marketing > Email Marketing**.

---

## Section Display Order

Sections appear on the home page in this fixed order from top to bottom:

1. Hero Carousel
2. Trust Strip
3. Products by Category Tabs
4. Brand Logos
5. Newsletter
6. Footer

Any section that is turned off is simply skipped -- the remaining sections stack together seamlessly.

!!! info
    The order of sections cannot be rearranged from the Theme Editor. If you need a custom layout, contact your theme developer.

---

## Quick Setup Checklist

Here is a summary of where to find each homepage setting:

| Section | Theme Editor Path | Key Settings |
|---------|-------------------|--------------|
| Hero Carousel | **eShopping** > **Homepage Sections** | **Show Hero Carousel** |
| Trust Strip | **eShopping** > **Homepage Sections** + **Trust Strip** | **Show Trust Strip**, **Trust Strip Items** |
| Products by Category | **eShopping** > **Homepage Sections** + **Products by Category** | Tab visibility, **Grid layout**, **Category IDs**, **Default active tab** |
| Brand Logos | **eShopping** > **Homepage Sections** | **Homepage Brands Limit** |
| Newsletter | **eShopping** > **Homepage Sections** | **Show Newsletter**, **Newsletter Signup Text** |

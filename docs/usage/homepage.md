# Setting Up the Home Page

The eShopping home page is built from modular sections that you can toggle on or off and configure entirely from the **Theme Editor**. Each section is controlled by one or more `eshopping-*` settings in **Storefront > My Themes > Customize**.

<div class="placeholder-screenshot">Full home page overview showing all sections stacked vertically: hero carousel, trust strip, products-by-category tabs, brand logos, newsletter, social icons, SEO text block, and footer.</div>

---

## Hero Carousel

The hero carousel occupies the full width above the fold and rotates through promotional slides with a crossfade animation.

| Setting | Location | Value |
|---------|----------|-------|
| `eshopping-show-hero` | Theme Styles > Home Page | `true` / `false` |

### How to configure

1. In your BigCommerce admin, go to **Storefront > Home Page Carousel**.
2. Upload carousel images and set the link URL, heading, and description for each slide.
3. Open **Storefront > My Themes > Customize** (Theme Editor).
4. Navigate to **Theme Styles > Home Page**.
5. Enable **Show carousel** (`eshopping-show-hero`).

<div class="placeholder-screenshot">Theme Editor with "Show carousel" toggle highlighted under Home Page section.</div>

!!! tip
    For best results, use images that are at least 1600px wide. The carousel uses `object-fit: cover`, so images will be cropped to fit the viewport width without causing layout shift.

---

## Trust Strip

The trust strip displays a row of trust badges directly below the hero carousel -- for example, "Made in USA", "Free Shipping", or "Expert Support".

| Setting | Location | Value |
|---------|----------|-------|
| `eshopping-show-trust-strip` | Theme Styles > Home Page | `true` / `false` |
| `eshopping-trust-text` | Theme Styles > Home Page | Pipe-separated string |

### How it works

The `eshopping-trust-text` setting is a single string where each badge is defined by a **Label** and **Subtitle** pair, separated by the pipe character `|`. You can have as many badges as you like -- each pair of segments becomes one badge.

**Format:**

```
Label 1|Subtitle 1|Label 2|Subtitle 2|Label 3|Subtitle 3|Label 4|Subtitle 4
```

**Default value (4 badges):**

```
Made in USA|Fast & reliable shipping on all orders|Free Shipping|Shop with confidence, guaranteed|4.8 Star Rating|Easy returns within 30 days|Expert Support|Available Mon-Sat, 9am-6pm
```

This produces:

| Badge | Label | Subtitle |
|-------|-------|----------|
| 1 | Made in USA | Fast & reliable shipping on all orders |
| 2 | Free Shipping | Shop with confidence, guaranteed |
| 3 | 4.8 Star Rating | Easy returns within 30 days |
| 4 | Expert Support | Available Mon-Sat, 9am-6pm |

<div class="placeholder-screenshot">Trust strip showing four badges in a horizontal row below the hero carousel.</div>

### How to configure

1. Open the **Theme Editor**.
2. Navigate to **Theme Styles > Home Page**.
3. Toggle **Show trust strip** on.
4. Edit the **Trust strip text** field. Enter your badges as pipe-separated `Label|Subtitle` pairs.
5. Click **Save & Apply**.

!!! warning
    Make sure you have an even number of pipe-separated segments. An odd number will cause the last badge to display without a subtitle.

---

## Products by Category / Tab Section (PBCST)

This section displays products in a tabbed layout. Visitors can switch between tabs like "Featured", "Best Selling", and "New Arrivals" without a page reload. Products are fetched dynamically.

| Setting | Location | Default |
|---------|----------|---------|
| `eshopping-pbcst-show-featured` | Theme Styles > Home Page | `true` |
| `eshopping-pbcst-show-bestselling` | Theme Styles > Home Page | `true` |
| `eshopping-pbcst-show-new` | Theme Styles > Home Page | `true` |
| `eshopping-pbcst-show-reviews` | Theme Styles > Home Page | `false` |
| `eshopping-pbcst-grid` | Theme Styles > Home Page | `3,4,6` |
| `eshopping-pbcst-active` | Theme Styles > Home Page | `featured` |
| `eshopping-pbcst-catIDs` | Theme Styles > Home Page | _(empty)_ |
| `eshopping-pbcst-lazy` | Theme Styles > Home Page | `false` |

<div class="placeholder-screenshot">Products-by-category section with tab bar showing "Featured", "Best Selling", and "New Arrivals" tabs, with a product grid below.</div>

### Tab visibility

Each tab can be independently shown or hidden:

- **Featured** -- `eshopping-pbcst-show-featured`
- **Best Selling** -- `eshopping-pbcst-show-bestselling`
- **New Arrivals** -- `eshopping-pbcst-show-new`
- **Top Reviewed** -- `eshopping-pbcst-show-reviews`

### Grid columns

The `eshopping-pbcst-grid` setting controls how many columns of products appear at each breakpoint. The value is three comma-separated numbers:

```
desktop,tablet,mobile
```

For example, `3,4,6` means:

- **Desktop:** 3 products per row
- **Tablet:** 4 products per row (narrower cards)
- **Mobile:** 6 products in a scrollable row

### Active tab

Set `eshopping-pbcst-active` to control which tab is selected by default when the page loads:

- `featured` -- Featured products (default)
- `bestselling` -- Best Selling products
- `new` -- New Arrival products

### Category filtering

By default (when `eshopping-pbcst-catIDs` is empty), products are pulled from the homepage product settings in your BigCommerce admin.

To display products from specific categories, enter a comma-separated list of **category IDs**:

```
23,45,67
```

!!! tip "Finding a category ID"
    In your BigCommerce admin, go to **Products > Product Categories** and click on a category. The category ID appears in the URL: `manage/products/categories/edit/**23**`.

### Lazy loading

When `eshopping-pbcst-lazy` is enabled, product data for non-active tabs is loaded on demand when the visitor clicks the tab, rather than on initial page load. This improves initial page speed.

---

## Brand Logos

Displays a horizontally scrollable row of brand logos sourced from your BigCommerce catalog.

| Setting | Location | Default |
|---------|----------|---------|
| `eshopping-homepage-brands-limit` | Theme Styles > Home Page | `8` |

<div class="placeholder-screenshot">Brand logos row showing 8 brand images in a horizontal scrollable strip.</div>

### How to configure

1. Ensure your products have brands assigned in **Products > Brands** in the BigCommerce admin.
2. Upload brand images/logos for each brand.
3. In the **Theme Editor**, set **Homepage brands limit** to control how many logos appear (default: 8).

---

## Newsletter Section

A call-to-action block encouraging visitors to subscribe to your newsletter.

| Setting | Location | Default |
|---------|----------|---------|
| `eshopping-show-newsletter` | Theme Styles > Home Page | `true` |
| `eshopping-newsletter-text` | Theme Styles > Home Page | Pipe-separated string |

### Content format

The `eshopping-newsletter-text` setting uses the same pipe-separated format:

```
Heading|Subtitle
```

HTML is supported in the heading for emphasis. For example:

```
Stay Updated with <em>Our Newsletter</em>|Product launches, field tips, and exclusive offers in your inbox.
```

This renders the heading with "Our Newsletter" in italic (styled as the accent/serif font).

<div class="placeholder-screenshot">Newsletter section showing a heading, subtitle text, and an email subscription form.</div>

### How to configure

1. Open the **Theme Editor**.
2. Navigate to **Theme Styles > Home Page**.
3. Toggle **Show newsletter** on.
4. Edit the **Newsletter text** field with your `Heading|Subtitle` content.
5. Click **Save & Apply**.

!!! note
    The newsletter form connects to the email marketing provider configured in your BigCommerce admin under **Marketing > Email Marketing**.

---

## Social Icons

Displays a row of social media icons linking to your brand's social profiles.

| Setting | Location | Default |
|---------|----------|---------|
| `eshopping-show-social-icons` | Theme Styles > Home Page | `true` |

### How to configure

1. In your BigCommerce admin, go to **Storefront > Social Media Links**.
2. Enter the URLs for each social platform (Facebook, Instagram, Twitter/X, YouTube, Pinterest, etc.).
3. In the **Theme Editor**, ensure **Show social icons** is enabled.

Only platforms with a URL entered will display an icon.

<div class="placeholder-screenshot">Social icons row showing icons for Facebook, Instagram, Twitter/X, and YouTube.</div>

---

## SEO Text Block

A text content block intended for search engine optimization. Displays a heading and one or more paragraphs of descriptive content about your store.

| Setting | Location | Default |
|---------|----------|---------|
| `eshopping-show-seo` | Theme Styles > Home Page | `false` |
| `eshopping-seo-text` | Theme Styles > Home Page | Pipe-separated string |

### Content format

```
Heading|Paragraph 1|Paragraph 2
```

Each pipe-separated segment after the heading becomes a separate paragraph. HTML is supported.

**Example:**

```
Sampling & Testing Tools|Ever since 1942, we have been a leader in manufacturing soil sampling equipment for agricultural, geotechnical, environmental, and groundwater applications.|Our soil sampling equipment includes soil probes, soil augers, soil core samplers, and more. Browse our official online store today.
```

<div class="placeholder-screenshot">SEO text block showing a heading and two paragraphs of descriptive content near the bottom of the home page.</div>

### How to configure

1. Open the **Theme Editor**.
2. Navigate to **Theme Styles > Home Page**.
3. Toggle **Show SEO text** on.
4. Edit the **SEO text** field using the pipe-separated format.
5. Click **Save & Apply**.

!!! tip
    Keep the SEO text relevant and natural. Search engines favor content that genuinely helps visitors understand what your store offers.

---

## Additional Sections

The following sections are available but **disabled by default**. Enable them in **Theme Styles > Home Page** as needed.

| Section | Setting | Description |
|---------|---------|-------------|
| **CTA Bar** | `eshopping-show-cta` | A prominent call-to-action banner with a button |
| **Why Choose Us** | `eshopping-show-why` | Feature highlight cards explaining your value proposition |
| **Reviews** | `eshopping-show-reviews` | Customer review/testimonial carousel |
| **Resources** | `eshopping-show-resources` | Links to blog posts, guides, or downloadable resources |

<div class="placeholder-screenshot">Theme Editor toggles for CTA Bar, Why Choose Us, Reviews, and Resources sections -- all shown in the off position.</div>

To enable any of these sections:

1. Open the **Theme Editor**.
2. Navigate to **Theme Styles > Home Page**.
3. Toggle the desired section on.
4. Configure any associated content fields that appear.
5. Click **Save & Apply**.

---

## Section Order

Sections appear on the home page in this fixed order from top to bottom:

1. Hero Carousel
2. Trust Strip
3. Products by Category Tabs
4. CTA Bar _(off by default)_
5. Why Choose Us _(off by default)_
6. Brand Logos
7. Reviews _(off by default)_
8. Resources _(off by default)_
9. Newsletter
10. Social Icons
11. SEO Text Block

!!! info
    Section order cannot be changed from the Theme Editor. If you need a custom section order, contact your developer or see the [Customization Guide](../customization/presets.md).

# Customizing the Header & Navigation

The eShopping header consists of two sticky bars -- the **Top Bar** (54px) and the **Main Navigation** (52px) -- that remain visible as visitors scroll. Both bars are fully configurable from the Theme Editor.

<div class="placeholder-screenshot">Full header showing the dark top bar with utility links and the white main navigation bar with logo, search, and cart icons.</div>

---

## Top Bar

The top bar sits at the very top of every page. It displays utility information such as your store address, phone number, welcome message, and links to informational pages.

### Color settings

| Setting | Location | Default | Purpose |
|---------|----------|---------|---------|
| `eshopping-topbar-bg` | Theme Styles > Header | `#1a1713` | Background color |
| `eshopping-topbar-color` | Theme Styles > Header | `#978a74` | Text and link color |
| `eshopping-topbar-color-hover` | Theme Styles > Header | `#faf8f4` | Link hover color |

<div class="placeholder-screenshot">Theme Editor color pickers for top bar background, text color, and hover color.</div>

### Content toggles

| Setting | Location | Default | Purpose |
|---------|----------|---------|---------|
| `eshopping-topbar-show-address` | Theme Styles > Header | `true` | Show store address |
| `eshopping-topbar-show-phone` | Theme Styles > Header | `true` | Show phone number |
| `eshopping-welcome-text` | Theme Styles > Header | _(empty)_ | Custom welcome message |

- **Address and phone** are pulled from your BigCommerce store profile (**Settings > Store Profile**).
- **Welcome text** accepts a custom message. Leave it blank to hide the welcome message entirely.

### Page links

| Setting | Location | Default | Purpose |
|---------|----------|---------|---------|
| `eshopping-topbar-pages-range` | Theme Styles > Header | `6,8` | Which web pages to show |

The `eshopping-topbar-pages-range` setting controls which **web pages** (created in **Storefront > Web Pages**) appear as links in the top bar. The value is two comma-separated numbers:

```
start_index,limit
```

For example, `6,8` means: starting from the 7th web page (index 6, zero-based), show up to 8 pages.

This lets you split your web pages between the top bar and main navigation. Informational pages like "About Us", "Contact", "FAQs", and "Shipping Policy" are good candidates for the top bar.

!!! tip
    The page order matches the sort order you set in **Storefront > Web Pages**. Drag pages into the desired order there, then use the range setting to select which ones appear in the top bar.

<div class="placeholder-screenshot">Top bar showing store address on the left, welcome message in the center, and page links (About, Contact, FAQ) on the right.</div>

### How to configure

1. Open the **Theme Editor** (**Storefront > My Themes > Customize**).
2. Navigate to **Theme Styles > Header**.
3. Set the **Top bar background** color and **text/hover colors** to match your brand.
4. Toggle **Show address** and **Show phone** as needed.
5. Enter a **Welcome text** message, or leave blank to hide.
6. Adjust **Top bar pages range** to control which web pages appear.
7. Click **Save & Apply**.

---

## Main Navigation

The main navigation bar sits directly below the top bar. It contains your store logo, category navigation links, the search bar, and action icons (account, cart).

### Color settings

| Setting | Location | Default | Purpose |
|---------|----------|---------|---------|
| `eshopping-nav-bg` | Theme Styles > Header | `#ffffff` | Navigation background color |
| `eshopping-nav-color` | Theme Styles > Header | `#6b5e4f` | Navigation link color |
| `eshopping-nav-color-hover` | Theme Styles > Header | `#1a1713` | Navigation link hover color |

### Category navigation

| Setting | Location | Default | Purpose |
|---------|----------|---------|---------|
| `eshopping-nav-pages-range` | Theme Styles > Header | `0,6` | Which categories to show |

Similar to the top bar pages range, `eshopping-nav-pages-range` controls which **product categories** appear in the main navigation:

```
start_index,limit
```

The default `0,6` means: starting from the first category (index 0), show up to 6 categories.

Categories are displayed in the order set in **Products > Product Categories** in your BigCommerce admin. Mega-menu dropdowns with subcategories appear on hover.

<div class="placeholder-screenshot">Main navigation bar showing the logo on the left, six category links in the center, and search/account/cart icons on the right.</div>

### Sticky behavior

Both the top bar and main navigation are sticky:

- **Top bar** sticks at `top: 0` (always visible at the very top)
- **Main navigation** sticks at `top: 54px` (directly below the top bar)

Together they occupy 106px of vertical space when scrolling. On mobile, the layout collapses to a hamburger menu.

### How to configure

1. Open the **Theme Editor**.
2. Navigate to **Theme Styles > Header**.
3. Set the **Navigation background**, **link color**, and **hover color**.
4. Adjust **Navigation pages range** to control how many top-level categories appear.
5. Click **Save & Apply**.

---

## Search Bar

The search bar is embedded in the main navigation and includes several advanced features.

### Color settings

| Setting | Location | Default | Purpose |
|---------|----------|---------|---------|
| `eshopping-nav-search-bg` | Theme Styles > Header | `#f5f0ea` | Search input background |
| `eshopping-nav-search-color` | Theme Styles > Header | `#3d352c` | Search input text color |
| `eshopping-nav-search-btn` | Theme Styles > Header | `#c75a2a` | Search button color |

### Animated typing placeholder

| Setting | Location | Default |
|---------|----------|---------|
| `eshopping-search-typing-phrases` | Theme Styles > Header | Pipe-separated phrases |

The search bar displays animated placeholder text that cycles through phrases, guiding visitors on what to search for.

**Format:**

```
Phrase 1|Phrase 2|Phrase 3|Phrase 4
```

**Default value:**

```
Search for power tools...|Find welding equipment...|Browse safety gear...|Discover compressors & accessories...
```

Each phrase types out character by character, pauses, then erases before the next phrase begins.

<div class="placeholder-screenshot">Search bar showing animated typing placeholder text "Search for power tools..." with a blinking cursor effect.</div>

### Category dropdown

| Setting | Location | Default | Purpose |
|---------|----------|---------|---------|
| `eshopping-search-category-depth` | Theme Styles > Header | `4` | Category filter depth (1--4, or off) |

When enabled, a category dropdown appears inside the search bar, letting visitors narrow their search to a specific category. The depth setting controls how many levels of subcategories appear in the dropdown:

- **1** -- Top-level categories only
- **2** -- Top-level + one level of subcategories
- **3** -- Three levels deep
- **4** -- Four levels deep (default)

Set to **off** to hide the category dropdown entirely.

### Voice search

| Setting | Location | Default |
|---------|----------|---------|
| `eshopping-search-voice` | Theme Styles > Header | `true` |

When enabled, a microphone icon appears in the search bar. Clicking it activates the browser's speech recognition API, allowing visitors to search by voice.

<div class="placeholder-screenshot">Search bar with category dropdown on the left, animated placeholder text in the center, and voice search microphone icon on the right.</div>

!!! note
    Voice search requires browser support for the Web Speech API. It works in Chrome, Edge, and Safari. In unsupported browsers, the microphone icon is automatically hidden.

### How to configure

1. Open the **Theme Editor**.
2. Navigate to **Theme Styles > Header**.
3. Set the **Search background**, **text color**, and **button color**.
4. Edit **Search typing phrases** with your pipe-separated placeholder text.
5. Set **Search category depth** (1--4 or off).
6. Toggle **Voice search** on or off.
7. Click **Save & Apply**.

---

## Sign-In Popup

| Setting | Location | Default |
|---------|----------|---------|
| `eshopping-signin-popup` | Theme Styles > Header | `true` |

When enabled, guest visitors are shown a sign-in modal on their first visit, encouraging them to log in or create an account. The popup appears once per session and does not reappear after being dismissed.

<div class="placeholder-screenshot">Sign-in popup modal overlaying the home page with email/password fields and "Create Account" link.</div>

### How to configure

1. Open the **Theme Editor**.
2. Navigate to **Theme Styles > Header**.
3. Toggle **Sign-in popup** on or off.
4. Click **Save & Apply**.

!!! tip
    If your store does not require customer accounts, disable this to reduce friction for casual shoppers.

---

## Currency Selector

The currency selector appears automatically in the top bar when your store has **multiple currencies** configured.

### How to configure

1. In your BigCommerce admin, go to **Settings > Currency**.
2. Add and enable the currencies you want to support.
3. Set exchange rates or enable automatic conversion.

No theme setting is required -- the selector shows up whenever more than one currency is active.

<div class="placeholder-screenshot">Top bar with a currency dropdown showing "USD", "EUR", and "GBP" options.</div>

---

## Mobile Header

On screens below 801px, the header collapses into a mobile-optimized layout:

- The **top bar** shrinks to show only essential icons
- The **main navigation** becomes a **hamburger menu** icon
- Tapping the hamburger opens a full-screen slide-out menu with category tree, account links, and search
- The **search bar** moves to the top of the mobile menu

<div class="placeholder-screenshot">Mobile header showing hamburger menu icon on the left, logo in the center, and cart icon on the right.</div>

No additional settings are needed -- the mobile layout is fully responsive and adapts automatically based on viewport width.

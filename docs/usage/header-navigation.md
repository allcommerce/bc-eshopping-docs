# Customizing the Header & Navigation

The eShopping header has two bars that stay visible as visitors scroll your store:

- **Top Bar** -- A slim utility bar at the very top with store info, welcome messages, and page links.
- **Main Navigation** -- The primary bar with your logo, category links, search, account icon, and cart.

Both are fully customizable from the **Theme Editor** (**Storefront > My Themes > Customize**).

<div class="placeholder-screenshot">Full header showing the dark top bar with store info and utility links, and the white main navigation bar with logo, category links, search bar, and cart icon.</div>

---

## Top Bar

The top bar sits at the very top of every page. It can display your store address, phone number, a welcome message, social media icons, and links to informational pages.

<div class="placeholder-screenshot">Top bar showing store address on the left, welcome message in the center, and page links (About, Contact, FAQ) on the right.</div>

### Colors

You can set the top bar colors to match your brand. Go to **Theme Styles** > **eShopping** > **Header** > **Topbar**:

| Setting | What it controls |
|---------|-----------------|
| **Topbar Background** | Background color of the entire bar |
| **Topbar Text** | Color of text and links |
| **Topbar Text Hover** | Color when hovering over a link |

### Content options

Under **Theme Styles** > **eShopping** > **Header** > **Topbar**, you can control what appears in the top bar:

| Setting | What it does |
|---------|-------------|
| **Show Social Icons** | Displays icons linking to your social media profiles |
| **Show Address in Topbar** | Shows your store's physical address |
| **Show Phone in Topbar** | Shows your store's phone number |
| **Welcome Text** | A custom greeting message (leave blank to hide) |

!!! note
    Your store address and phone number are pulled from **Settings > Store Profile** in your BigCommerce admin. Update them there if they need to change.

### Page links in the top bar

The **Topbar pages range** field controls which of your web pages appear as links in the top bar.

Enter two numbers separated by a comma: the starting position and how many pages to show. Pages are numbered starting from 0.

```
start,count
```

**Example:** `6,8` means start at the 7th page (position 6) and show up to 8 pages.

This lets you split your web pages between the top bar and the main navigation. Good candidates for the top bar include "About Us", "Contact", "FAQ", and "Shipping Policy".

!!! tip
    The page order matches the sort order you set in **Storefront > Web Pages** in your BigCommerce admin. Drag pages into the order you want there, then use the range setting to pick which ones appear in the top bar.

### How to configure the top bar

1. Open the **Theme Editor** (**Storefront > My Themes > Customize**).
2. Go to **Theme Styles** > **eShopping** > **Header** > **Topbar**.
3. Set the **Topbar Background**, **Topbar Text**, and **Topbar Text Hover** colors to match your brand.
4. Check or uncheck **Show Social Icons**, **Show Address in Topbar**, and **Show Phone in Topbar** as needed.
5. Enter a **Welcome Text** message, or leave it blank to hide the greeting.
6. Adjust the **Topbar pages range** to control which web pages appear.
7. Click **Save & Apply**.

---

## Main Navigation

The main navigation bar sits directly below the top bar. It contains your store logo, product category links, the search bar, and icons for your account and cart.

<div class="placeholder-screenshot">Main navigation bar showing the logo on the left, category links in the center, and search/account/cart icons on the right.</div>

### Colors

Go to **Theme Styles** > **eShopping** > **Header** > **Navigation**:

| Setting | What it controls |
|---------|-----------------|
| **Navigation Background** | Background color of the navigation bar |
| **Navigation Text** | Color of category links |
| **Navigation Text Hover** | Color when hovering over a link |

### Category links

The **Nav pages range** field under **Theme Styles** > **eShopping** > **Header** > **Navigation** controls which product categories appear in the navigation bar.

Enter two numbers separated by a comma: the starting position and how many categories to show.

```
start,count
```

**Example:** `0,6` means start at the first category (position 0) and show up to 6 categories.

Categories appear in the order you have set in **Products > Product Categories** in the BigCommerce admin. When you hover over a category that has subcategories, a dropdown menu appears automatically.

### How to configure the navigation

1. Open the **Theme Editor**.
2. Go to **Theme Styles** > **eShopping** > **Header** > **Navigation**.
3. Set the **Navigation Background**, **Navigation Text**, and **Navigation Text Hover** colors.
4. Adjust the **Nav pages range** to control how many top-level categories appear.
5. Click **Save & Apply**.

---

## Search Bar

The search bar is built into the main navigation and includes several features to help visitors find products quickly.

<div class="placeholder-screenshot">Search bar with a category dropdown on the left, animated typing placeholder in the center, and a voice search microphone icon on the right.</div>

### Search bar colors

Go to **Theme Styles** > **eShopping** > **Header** > **Navigation**:

| Setting | What it controls |
|---------|-----------------|
| **Search Background** | Background color of the search input |
| **Search Text** | Text color inside the search input |
| **Search Button** | Color of the search button |

### Category dropdown

Under **Theme Styles** > **eShopping** > **Search**, the **Category dropdown depth in search** setting adds a category filter inside the search bar. Visitors can narrow their search to a specific category before searching.

Choose how many levels of categories to show:

| Option | What it shows |
|--------|--------------|
| **Disabled** | No category dropdown |
| **Top-level only** | Only your main categories |
| **Two levels** | Main categories + one level of subcategories |
| **Three levels** | Three levels deep |
| **Four levels** | Four levels deep |

### Animated typing placeholder

Under **Theme Styles** > **eShopping** > **Search**, the **Typing phrases** field lets you set animated placeholder text that cycles through suggestions in the search bar, giving visitors ideas of what to search for.

Enter your phrases separated by pipe characters (`|`):

```
Search for power tools...|Find welding equipment...|Browse safety gear...|Discover compressors...
```

Each phrase types out character by character, pauses briefly, then erases before the next one begins.

### Voice search

Under **Theme Styles** > **eShopping** > **Search**, check **Enable voice search** to show a microphone icon in the search bar. Visitors can click it to search using their voice.

!!! note
    Voice search works in Chrome, Edge, and Safari. In browsers that do not support it, the microphone icon is automatically hidden.

### How to configure the search bar

1. Open the **Theme Editor**.
2. Go to **Theme Styles** > **eShopping** > **Header** > **Navigation** for search colors.
3. Go to **Theme Styles** > **eShopping** > **Search** for search features.
4. Set the **Search Background**, **Search Text**, and **Search Button** colors.
5. Edit the **Typing phrases** field with your pipe-separated placeholder text.
6. Choose a **Category dropdown depth in search** level.
7. Check or uncheck **Enable voice search**.
8. Click **Save & Apply**.

---

## Sign-In Popup

The eShopping theme can display a sign-in popup for first-time visitors, encouraging them to log in or create an account.

<div class="placeholder-screenshot">Sign-in popup modal overlaying the home page with email and password fields, a sign-in button, and a "Create Account" link.</div>

The popup appears once per session and does not reappear after being dismissed.

### How to configure

1. Open the **Theme Editor**.
2. Go to **Theme Styles** > **eShopping** > **Header** > **Navigation**.
3. Look for the sign-in popup toggle and check or uncheck it.
4. Click **Save & Apply**.

!!! tip
    If your store does not require customer accounts, turn this off to reduce friction for casual shoppers.

---

## Currency Selector

If your store supports multiple currencies, a currency selector automatically appears in the top bar. Visitors can click it to switch between currencies.

<div class="placeholder-screenshot">Top bar with a currency dropdown showing "USD", "EUR", and "GBP" options.</div>

### How to set it up

1. In your BigCommerce admin, go to **Settings > Currency**.
2. Add and enable the currencies you want to support.
3. Set exchange rates or enable automatic conversion.

No theme setting is needed -- the currency selector appears automatically whenever more than one currency is active.

---

## Mobile Header

On smaller screens (phones and small tablets), the header automatically adapts to a mobile-friendly layout:

- The **top bar** shows only essential icons.
- The **category links** are replaced by a **hamburger menu** icon.
- Tapping the hamburger icon opens a full-screen slide-out menu with your category tree, account links, and search bar.
- The **search bar** moves to the top of the mobile menu for easy access.

<div class="placeholder-screenshot">Mobile header showing a hamburger menu icon on the left, the store logo in the center, and a cart icon on the right.</div>

No additional settings are needed -- the mobile layout adapts automatically based on screen size.

---

## Quick Setup Checklist

Here is a summary of where to find each header setting:

| Area | Theme Editor Path | Key Settings |
|------|-------------------|--------------|
| Top Bar Colors | **eShopping** > **Header** > **Topbar** | **Topbar Background**, **Topbar Text**, **Topbar Text Hover** |
| Top Bar Content | **eShopping** > **Header** > **Topbar** | **Show Social Icons**, **Show Address**, **Show Phone**, **Welcome Text**, **Topbar pages range** |
| Navigation Colors | **eShopping** > **Header** > **Navigation** | **Navigation Background**, **Navigation Text**, **Navigation Text Hover** |
| Navigation Links | **eShopping** > **Header** > **Navigation** | **Nav pages range** |
| Search Colors | **eShopping** > **Header** > **Navigation** | **Search Background**, **Search Text**, **Search Button** |
| Search Features | **eShopping** > **Search** | **Category dropdown depth**, **Typing phrases**, **Enable voice search** |

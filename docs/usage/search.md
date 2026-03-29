# Search Features

The eShopping theme includes an enhanced search experience with live results, animated placeholder text, category filtering, voice input, and keyword suggestions. All search features are configured in **Theme Styles** > **eShopping** > **Search**.

---

## Quick Search

The quick search is located in the main navigation bar and provides instant results as the customer types. It searches across products, categories, and content pages simultaneously.

<div class="placeholder-screenshot">Quick search dropdown open below the navigation bar showing product results, category matches, and content page results</div>

### How It Works

1. The customer clicks the search icon or focuses the search input in the navigation bar
2. As they type, results appear in a dropdown below the search bar
3. Results are grouped by type: **Products**, **Categories**, and **Content**
4. Product results include a thumbnail image, name, and price
5. Clicking a result navigates directly to that product, category, or page
6. Pressing Enter submits the search and navigates to the full search results page

<div class="placeholder-screenshot">Quick search dropdown with a typed query showing grouped results -- products with thumbnails, category links, and content page links</div>

---

## Animated Typing Placeholder

The search bar features an animated typing effect that cycles through placeholder phrases, giving customers ideas of what to search for. Each theme preset includes industry-specific phrases.

<div class="placeholder-screenshot">Search bar in the navigation showing an animated typing placeholder mid-phrase, e.g. "Search for power too" with a blinking cursor</div>

### Configuration

Go to **Theme Styles** > **eShopping** > **Search** and find the **Typing phrases** setting.

Enter your phrases separated by a pipe character (`|`):

```
Phrase 1|Phrase 2|Phrase 3
```

**Example:**

```
Search for power tools...|Find welding equipment...|Browse safety gear...|Discover compressors & accessories...
```

### Theme Preset Defaults

Each preset ships with industry-relevant placeholder phrases:

| Preset | Phrases |
|--------|---------|
| Industrial | Search for power tools... / Find welding equipment... / Browse safety gear... / Discover compressors & accessories... |
| AutoParts | Search for brake pads... / Find oil filters & fluids... / Browse suspension parts... / Discover lighting & accessories... |
| Packaging | Search for shipping boxes... / Find bubble wrap & packing... / Browse tape & labels... / Discover mailer bags & envelopes... |
| Electronics | Search for laptops & monitors... / Find headphones & speakers... / Browse keyboards & mice... / Discover cables & adapters... |

### Behavior

- Phrases are typed out character by character with a typewriter animation effect
- After a phrase is fully typed, there is a brief pause before it is erased
- The next phrase in the list then begins typing
- The cycle repeats continuously
- When the customer clicks into the search input, the animation stops and the placeholder clears to allow typing

!!! tip
    Customize the phrases to match your store's product catalog. Use action words like "Search for," "Find," "Browse," or "Discover" to encourage engagement. Keep each phrase under 50 characters for best display on mobile devices.

---

## Category Dropdown Filter

A category dropdown can be added next to the search input, allowing customers to narrow their search to a specific category before submitting.

<div class="placeholder-screenshot">Search bar with a category dropdown selector on the left side showing "All Categories" expanded with a list of top-level and subcategories</div>

### Configuration

Go to **Theme Styles** > **eShopping** > **Search** and find the **Category dropdown depth in search** setting.

Choose from the following options:

| Option | What it does |
|--------|--------------|
| **Disabled** | Category dropdown is hidden; search bar spans full width |
| **Top-level only** | Only top-level categories are shown |
| **Two levels** | Top-level categories and their direct subcategories |
| **Three levels** | Three levels of category nesting |
| **Four levels** | Four levels of category nesting (deepest) |

### How It Works

1. The dropdown defaults to **All Categories**
2. The customer selects a specific category from the dropdown
3. When a search is submitted, results are filtered to only products within the selected category (and its subcategories)
4. The selected category is preserved in the search results page URL

!!! note
    Subcategories are indented in the dropdown to visually indicate the hierarchy. If your store has a deeply nested category tree, consider using **Two levels** or **Three levels** to keep the dropdown manageable.

---

## Voice Search

Voice search adds a microphone icon to the search bar, allowing customers to speak their search query instead of typing.

<div class="placeholder-screenshot">Search bar with a microphone icon on the right side, shown in both inactive and active (listening) states</div>

### Configuration

Go to **Theme Styles** > **eShopping** > **Search** and check or uncheck **Enable voice search**.

### How It Works

1. The customer clicks the microphone icon in the search bar
2. The browser requests microphone permission (first time only)
3. A listening indicator appears while the customer speaks
4. The spoken words are converted to text and populated in the search input
5. The search is automatically submitted after the speech is recognized

### Browser Support

Voice search is supported in the following browsers:

- Google Chrome (desktop and Android)
- Microsoft Edge
- Safari (macOS and iOS)

If the customer's browser does not support voice search, the microphone icon is automatically hidden and the search bar functions normally without it.

!!! warning
    Voice search requires a secure connection (HTTPS). It will not work on HTTP-only sites or during local development without SSL.

---

## Keyword Suggestions

As customers type in the search bar, keyword suggestions appear to help them find products faster. These suggestions are based on popular search terms and product names.

<div class="placeholder-screenshot">Search bar with a dropdown showing keyword suggestions below the input, such as "power drill," "power tool set," "power washer"</div>

### Configuration

Go to **Theme Styles** > **eShopping** > **Search** and check or uncheck **Enable keyword suggestions**.

### How It Works

1. The customer begins typing in the search bar
2. After a brief pause, suggested keywords appear in a dropdown
3. Suggestions are ranked by relevance to the typed characters
4. Clicking a suggestion populates the search input and submits the search
5. The customer can also use arrow keys to navigate suggestions and press Enter to select

Keyword suggestions work alongside the quick search results -- suggestions appear at the top of the dropdown, with product/category/content results below.

!!! tip
    Keyword suggestions pull from your store's product catalog and search history. Ensure your products have descriptive names and relevant keywords in their search fields to improve suggestion quality.

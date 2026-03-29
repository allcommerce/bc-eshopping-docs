# Popups & Marketing Features

The eShopping theme includes built-in marketing tools to help convert visitors into customers. These features include newsletter popups, promotional popups, exit-intent popups, recent sales notifications, and urgency signals. All are configured entirely through the Theme Editor -- no third-party apps required.

## Newsletter Popup

The newsletter popup encourages visitors to subscribe to your email list by offering an incentive (e.g., a discount code). It appears as a centered modal overlay after a configurable delay.

<div class="placeholder-screenshot">Newsletter popup modal centered on the page with a headline, subtitle, email input field, and subscribe button</div>

### Configuration

| Setting | Value | Description |
|---------|-------|-------------|
| `eshopping-popup-nl-text` | `"Headline\|Subtitle"` | Pipe-separated headline and subtitle text |
| `eshopping-popup-nl-opts` | `"DELAY\|EXPIRE"` | Seconds before showing, days before re-showing |

**Default content:**

```
Get 10% Off Your First Order|Sign up for our newsletter and receive an exclusive discount code.
```

**Default options:**

```
20|14
```

This means: show the popup **20 seconds** after the page loads, and if the visitor dismisses it, do not show it again for **14 days**.

### Behavior

- The popup appears once per visitor session based on the delay timer
- After dismissal, a cookie is set to suppress the popup for the configured number of days
- If the visitor subscribes, the popup is permanently suppressed for that browser
- The email is submitted to BigCommerce's built-in newsletter subscriber list

### Disabling the Newsletter Popup

To disable the newsletter popup, set the delay to `0`:

```
0|14
```

!!! tip
    Keep the headline short and benefit-focused (e.g., "Get 10% Off"). The subtitle should explain what the visitor needs to do (e.g., "Sign up for our newsletter"). Make sure the discount code referenced in the text is actually configured as a valid coupon in **Marketing** > **Promotions**.

## Promotional Popup

The promotional popup displays a timed offer with a coupon code and a call-to-action button. It appears as a modal overlay and is useful for announcing sales, seasonal promotions, or limited-time deals.

<div class="placeholder-screenshot">Promotional popup modal showing a sale title, description, a coupon code in a highlighted box, and a "Shop Now" CTA button</div>

### Configuration

| Setting | Value | Description |
|---------|-------|-------------|
| `eshopping-popup-promo-text` | `"Title\|Description\|Coupon\|CTA\|URL"` | Five pipe-separated fields |
| `eshopping-popup-promo-opts` | `"DELAY\|EXPIRE\|\|"` | Seconds delay, days to re-show, two unused fields |

**Default content:**

```
Spring Sale|Get 15% off your entire order with the code below.|SPRING15|Shop Now|/
```

**Default options:**

```
5|3||
```

This means: show the popup **5 seconds** after page load, and re-show after **3 days** if dismissed.

### Content Fields

The five pipe-separated fields in `eshopping-popup-promo-text` are:

| Position | Field | Example |
|----------|-------|---------|
| 1 | Title | `Spring Sale` |
| 2 | Description | `Get 15% off your entire order with the code below.` |
| 3 | Coupon Code | `SPRING15` |
| 4 | CTA Button Text | `Shop Now` |
| 5 | CTA Button URL | `/` (homepage) or any store URL |

### Behavior

- The coupon code is displayed in a highlighted, copy-friendly box
- Clicking the CTA button navigates to the configured URL
- After dismissal, the popup is suppressed for the configured number of days
- To disable, set the delay to `0` or clear the text field

## Exit-Intent Popup

The exit-intent popup triggers when a visitor shows signs of leaving the site. On desktop, it detects when the mouse cursor moves toward the browser's close button or address bar. On mobile, it triggers after a period of inactivity.

<div class="placeholder-screenshot">Exit-intent popup modal with an attention-grabbing headline, discount offer description, coupon code, and "Claim Discount" button</div>

### Configuration

| Setting | Value | Description |
|---------|-------|-------------|
| `eshopping-popup-exit-text` | `"Title\|Description\|Coupon\|CTA\|URL"` | Five pipe-separated fields |
| `eshopping-popup-exit-opts` | `"TYPE\|DELAY\|EXPIRE"` | Popup type, inactivity seconds (mobile), days to re-show |

**Default content:**

```
Wait! Don't Go Empty-Handed|Here's a special 10% discount just for you.|STAY10|Claim Discount|/
```

**Default options:**

```
discount|45|1
```

This means: the popup type is `discount`, on mobile it triggers after **45 seconds** of inactivity, and it re-shows after **1 day** if dismissed.

### Options Fields

| Position | Field | Description |
|----------|-------|-------------|
| 1 | TYPE | The popup style -- `discount` shows a coupon-focused layout |
| 2 | DELAY | Inactivity timeout in seconds for mobile trigger |
| 3 | EXPIRE | Number of days before re-showing after dismissal |

### Trigger Behavior

| Platform | Trigger |
|----------|---------|
| Desktop | Mouse cursor leaves the viewport (moves above the page area toward the browser chrome) |
| Mobile | No interaction (scroll, tap, or input) for the configured number of seconds |

- The popup only fires once per page visit
- After dismissal, it is suppressed for the configured number of days via a cookie
- To disable, clear the text field entirely

!!! note
    Exit-intent popups are most effective with an exclusive offer not shown elsewhere on the site. Use a unique coupon code (e.g., `STAY10`) that is only available through this popup.

## Recent Sales Notifications

Recent sales notifications display small toast messages that cycle through simulated recent purchases, creating social proof and urgency. For example: "Someone in California purchased [Product Name] 2 hours ago."

<div class="placeholder-screenshot">Small toast notification in the bottom-left corner of the page showing a product thumbnail, customer location, product name, and "2 hours ago" timestamp</div>

### Configuration

| Setting | Value | Description |
|---------|-------|-------------|
| `eshopping-recent-sales-pages` | Page type | Which pages show notifications |
| `eshopping-recent-sales-position` | Position | Corner position of the toast |
| `eshopping-recent-sales-items` | Item list | Products, locations, and times |
| `eshopping-recent-sales-timing` | Timing | Animation and cycle timing |

### Pages Setting

| Value | Behavior |
|-------|----------|
| `"all"` | Show on every page |
| `"home"` | Homepage only |
| `"category"` | Category pages only |
| `"product"` | Product pages only |
| `"none"` | Disabled |

**Default value:** `"all"`

### Position Setting

| Value | Behavior |
|-------|----------|
| `"bottom-left"` | Toast appears in the bottom-left corner |
| `"bottom-right"` | Toast appears in the bottom-right corner |

**Default value:** `"bottom-left"`

### Items Setting

**Format:** `PRODUCT_ID|LOCATION|TIME_AGO,PRODUCT_ID|LOCATION|TIME_AGO,...`

Each item is comma-separated and contains three pipe-separated fields:

| Field | Description | Example |
|-------|-------------|---------|
| PRODUCT_ID | BigCommerce product ID | `77` |
| LOCATION | City or state name | `California` |
| TIME_AGO | Time description | `2 hours ago` |

**Default value:**

```
77|California|2 hours ago,78|Texas|35 min ago,79|Florida|4 hours ago,80|New York|1 hour ago,81|Oregon|6 hours ago
```

!!! tip
    Use real product IDs from your store so that the notification displays the correct product name and thumbnail image. Find the product ID in your BigCommerce admin by navigating to **Products** > click a product > the ID is in the URL.

### Timing Setting

**Format:** `INITIAL_DELAY,DISPLAY_DURATION,PAUSE,CYCLE_DELAY`

All values are in seconds:

| Position | Field | Description |
|----------|-------|-------------|
| 1 | Initial Delay | Seconds after page load before the first notification appears |
| 2 | Display Duration | How long each notification is visible |
| 3 | Pause | Seconds of silence between notifications |
| 4 | Cycle Delay | Seconds before restarting the cycle after all items have been shown |

**Default value:**

```
5,5,15,5
```

This means: wait **5 seconds** after page load, show each notification for **5 seconds**, pause **15 seconds** between notifications, and wait **5 seconds** before restarting the cycle.

## Urgency Signals

Urgency signals add real-time social proof and scarcity cues to product pages. They display messages like "12 people are viewing this right now" and "Last ordered 3 hours ago" to encourage faster purchasing decisions.

<div class="placeholder-screenshot">Product page showing urgency signals below the Add to Cart button -- "14 people are viewing this right now" and "Last ordered 2 hours ago"</div>

### Viewing Count

Displays a simulated count of people currently viewing the product.

| Setting | Value | Description |
|---------|-------|-------------|
| `eshopping-urgency-view-count` | `true` / `false` | Enable or disable the viewing count |
| `eshopping-urgency-view-range` | `"MIN,MAX"` | Range for the random viewer count |

**Default values:**

- Enabled: `true`
- Range: `"3,25"` (displays a random number between 3 and 25)

The displayed count is randomized within the configured range and updates periodically to simulate real-time activity.

### Last Order

Displays a simulated "last ordered" timestamp to show recent purchasing activity.

| Setting | Value | Description |
|---------|-------|-------------|
| `eshopping-urgency-last-order` | `true` / `false` | Enable or disable the last order timestamp |
| `eshopping-urgency-order-range` | `"MIN_HOURS,MAX_HOURS"` | Range for the random time-ago value |

**Default values:**

- Enabled: `true`
- Range: `"1,48"` (displays "Last ordered X hours ago" with X between 1 and 48)

### Auto-Refresh

| Setting | Value | Description |
|---------|-------|-------------|
| `eshopping-urgency-refresh` | `true` / `false` | Periodically update the displayed numbers |

**Default value:** `true`

When enabled, the viewing count and last order time are periodically recalculated with new random values within their configured ranges, simulating real-time updates without requiring a page reload.

!!! warning
    Urgency signals use simulated data -- they do not reflect actual store traffic or order history. Use these features responsibly and ensure your displayed ranges are realistic for your store's size. Overly aggressive numbers (e.g., "500 people viewing this") can erode customer trust.

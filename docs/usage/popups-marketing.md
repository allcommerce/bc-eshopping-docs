# Popups & Marketing Features

The eShopping theme includes built-in marketing tools to help convert visitors into customers. These features include newsletter popups, promotional popups, exit-intent popups, recent sales notifications, and urgency signals. All are configured entirely through the Theme Editor -- no third-party apps required.

---

## Newsletter Popup

The newsletter popup encourages visitors to subscribe to your email list by displaying a centered modal overlay after a configurable delay.

<div class="placeholder-screenshot">Newsletter popup modal centered on the page with a headline, subtitle, email input field, and subscribe button</div>

### Configuration

Go to **Theme Styles** > **eShopping** > **Newsletter Popup** to find the following settings:

#### Newsletter Content

Enter your headline and description separated by a pipe character (`|`):

```
Headline|Description
```

**Example:**

```
Get 10% Off Your First Order|Sign up for our newsletter and receive an exclusive discount code.
```

To disable the newsletter popup entirely, leave this field empty.

#### Show after/Repeat

Control when the popup appears and how often it re-appears after being dismissed:

```
seconds|days
```

**Example:**

```
20|14
```

This means: show the popup **20 seconds** after the page loads, and if the visitor dismisses it, do not show it again for **14 days**.

### Behavior

- The popup appears once per visitor session based on the delay timer
- After dismissal, a cookie is set to suppress the popup for the configured number of days
- If the visitor subscribes, the popup is permanently suppressed for that browser
- The email is submitted to BigCommerce's built-in newsletter subscriber list

!!! tip
    Keep the headline short and benefit-focused (e.g., "Get 10% Off"). The description should explain what the visitor needs to do (e.g., "Sign up for our newsletter"). Make sure any discount code you reference is actually configured as a valid coupon in **Marketing** > **Promotions** in your BigCommerce admin.

---

## Promotional Popup

The promotional popup displays a timed offer with a coupon code and a call-to-action button. It appears as a modal overlay and is ideal for announcing sales, seasonal promotions, or limited-time deals.

<div class="placeholder-screenshot">Promotional popup modal showing a sale title, description, a coupon code in a highlighted box, and a "Shop Now" CTA button</div>

### Configuration

Go to **Theme Styles** > **eShopping** > **Promotion Popup** to find the following settings:

#### Promo Content

Enter five fields separated by pipe characters (`|`):

```
Title|Description|Coupon Code|Button Text|Button URL
```

**Example:**

```
Spring Sale|Get 15% off your entire order with the code below.|SPRING15|Shop Now|/
```

| Field | What it does | Example |
|-------|--------------|---------|
| **Title** | The headline of the popup | `Spring Sale` |
| **Description** | Supporting text explaining the offer | `Get 15% off your entire order with the code below.` |
| **Coupon Code** | The discount code displayed in a copy-friendly box | `SPRING15` |
| **Button Text** | The label on the call-to-action button | `Shop Now` |
| **Button URL** | Where the button links to | `/` (homepage) or any store URL |

To disable the promotional popup entirely, leave this field empty.

#### Show after/Repeat

Control when the popup appears and how often it re-appears after being dismissed:

```
seconds|days||
```

**Example:**

```
5|3||
```

This means: show the popup **5 seconds** after page load, and re-show after **3 days** if dismissed.

### Behavior

- The coupon code is displayed in a highlighted, copy-friendly box
- Clicking the button navigates to the configured URL
- After dismissal, the popup is suppressed for the configured number of days

---

## Exit-Intent Popup

The exit-intent popup triggers when a visitor shows signs of leaving your site. On desktop, it detects when the mouse cursor moves toward the browser's close button or address bar. On mobile, it triggers after a period of inactivity.

<div class="placeholder-screenshot">Exit-intent popup modal with an attention-grabbing headline, discount offer description, coupon code, and "Claim Discount" button</div>

### Configuration

Go to **Theme Styles** > **eShopping** > **Exit Intent Popup** to find the following settings:

#### Exit Content

Enter five fields separated by pipe characters (`|`):

```
Title|Description|Coupon Code|Button Text|Button URL
```

**Example:**

```
Wait! Don't Go Empty-Handed|Here's a special 10% discount just for you.|STAY10|Claim Discount|/
```

The fields work the same as the [Promotional Popup](#promo-content) above.

To disable the exit-intent popup entirely, leave this field empty.

#### Type/Timing

Control the popup style, mobile trigger delay, and how often it re-appears:

```
type|mobile_timeout_seconds|repeat_days
```

**Example:**

```
discount|45|1
```

| Field | What it does | Example |
|-------|--------------|---------|
| **Type** | The popup style | `discount` shows a coupon-focused layout |
| **Mobile timeout** | Seconds of inactivity on mobile before the popup triggers | `45` |
| **Repeat days** | Number of days before re-showing after dismissal | `1` |

### Trigger Behavior

| Platform | How it triggers |
|----------|----------------|
| **Desktop** | Mouse cursor leaves the page area (moves toward the browser's close button or address bar) |
| **Mobile** | No interaction (scroll, tap, or input) for the configured number of seconds |

- The popup only fires once per page visit
- After dismissal, it is suppressed for the configured number of days

!!! note
    Exit-intent popups are most effective with an exclusive offer not shown elsewhere on the site. Use a unique coupon code (e.g., `STAY10`) that is only available through this popup.

---

## Recent Sales Notifications

Recent sales notifications display small toast messages that cycle through simulated recent purchases, creating social proof and urgency. For example: *"Someone in California purchased [Product Name] 2 hours ago."*

<div class="placeholder-screenshot">Small toast notification in the bottom-left corner of the page showing a product thumbnail, customer location, product name, and "2 hours ago" timestamp</div>

### Configuration

Go to **Theme Styles** > **eShopping** > **Recent Sales Popup** to find the following settings:

#### Show on pages

Choose which pages display the notifications:

| Option | What it does |
|--------|--------------|
| **Off** | Notifications are disabled |
| **All pages** | Show on every page |
| **Homepage only** | Show only on the homepage |
| **Product pages only** | Show only on product pages |
| **Category pages only** | Show only on category pages |

#### Popup timing

Control the animation and cycle timing with four comma-separated values:

```
initial_delay,display_duration,pause,max_cycle_delay
```

All values are in seconds.

| Value | What it does | Example |
|-------|--------------|---------|
| **Initial delay** | Seconds after page load before the first notification appears | `5` |
| **Display duration** | How long each notification is visible | `5` |
| **Pause** | Seconds of silence between notifications | `15` |
| **Max cycle delay** | Seconds before restarting the cycle after all items have been shown | `5` |

**Example:**

```
5,5,15,5
```

This means: wait **5 seconds** after page load, show each notification for **5 seconds**, pause **15 seconds** between notifications, and wait **5 seconds** before restarting the cycle.

#### Products

Define which products appear in the notifications. Enter each item in this format:

```
ProductID|Location|TimeAgo
```

Separate multiple items with commas.

| Field | What it does | Example |
|-------|--------------|---------|
| **ProductID** | The BigCommerce product ID | `77` |
| **Location** | A city or region name | `California` |
| **TimeAgo** | A time description | `2 hours ago` |

**Example:**

```
77|California|2 hours ago,78|Texas|35 min ago,79|Florida|4 hours ago
```

!!! tip
    Use real product IDs from your store so that the notification displays the correct product name and thumbnail image. To find a product's ID, go to **Products** in your BigCommerce admin, click on a product, and look at the number in the browser's address bar.

---

## Urgency Signals

Urgency signals add real-time social proof and scarcity cues to product pages. They display messages like *"12 people are viewing this right now"* and *"Last ordered 3 hours ago"* to encourage faster purchasing decisions.

<div class="placeholder-screenshot">Product page showing urgency signals below the Add to Cart button -- "14 people are viewing this right now" and "Last ordered 2 hours ago"</div>

### Configuration

Go to **Theme Styles** > **eShopping** > **Urgency Signals** to find the following settings:

#### Live View Count

Check **Show live view count** to display a simulated count of people currently viewing the product.

Use the **View range** setting to define the minimum and maximum values for the random viewer count, separated by a comma:

```
min,max
```

**Example:**

```
3,25
```

This displays a random number between 3 and 25, such as *"14 people are viewing this right now."*

#### Last Order Time

Check **Show last order time** to display a simulated "last ordered" timestamp showing recent purchasing activity.

Use the **Order range** setting to define the minimum and maximum hours for the random time value, separated by a comma:

```
min_hours,max_hours
```

**Example:**

```
1,48
```

This displays a message like *"Last ordered 5 hours ago"* with a random value between 1 and 48 hours.

### Behavior

- The displayed numbers are randomized within your configured ranges
- Values update periodically to simulate real-time activity without requiring a page reload

!!! warning
    Urgency signals use simulated data -- they do not reflect actual store traffic or order history. Use these features responsibly and ensure your displayed ranges are realistic for your store's size. Overly aggressive numbers (e.g., "500 people viewing this") can erode customer trust.

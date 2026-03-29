# FAQs

## How to disable the sign-in popup

By default, the eShopping theme displays a sign-in popup that prompts visitors to log in or create an account. To disable this popup:

1. Go to **Storefront** > **My Themes**
2. Click **Customize** on the eShopping theme
3. In the left panel, navigate to the **eShopping** section
4. Find the setting **eshopping-signin-popup** and set it to **false**
5. Click **Save**

<div class="placeholder-screenshot">Theme Editor showing eshopping-signin-popup setting toggled to false</div>

---

## How to disable urgency signals (viewing count, recent orders)

The theme can display urgency signals on product pages, such as "X people are viewing this" and "Last ordered Y minutes ago." To disable these:

1. Go to **Storefront** > **My Themes**
2. Click **Customize** on the eShopping theme
3. In the left panel, navigate to the **eShopping** section
4. Find the setting **eshopping-urgency-view-count** and set it to **false** to hide the viewing count
5. Find the setting **eshopping-urgency-last-order** and set it to **false** to hide the recent order indicator
6. Click **Save**

<div class="placeholder-screenshot">Theme Editor showing eshopping-urgency-view-count and eshopping-urgency-last-order settings toggled to false</div>

---

## How to disable recent sales notifications

The theme can show toast-style notifications about recent purchases made by other customers. To disable these notifications:

1. Go to **Storefront** > **My Themes**
2. Click **Customize** on the eShopping theme
3. In the left panel, navigate to the **eShopping** section
4. Find the setting **eshopping-recent-sales-pages** and set the value to **none**
5. Click **Save**

When set to "none," the recent sales notification will not appear on any page.

<div class="placeholder-screenshot">Theme Editor showing eshopping-recent-sales-pages setting with value "none"</div>

---

## How to change the cart goal tiers

The cart goal progress bar encourages shoppers to add more items to their cart to unlock rewards such as free shipping or a free gift. To customize the goal tiers:

1. Go to **Storefront** > **My Themes**
2. Click **Customize** on the eShopping theme
3. In the left panel, navigate to the **eShopping** section
4. Find the setting **eshopping-cart-goal-items**
5. Edit the value using the pipe-separated format: `AMOUNT|TYPE|LABEL`

**Format explanation:**

- **AMOUNT** -- the dollar amount the customer must reach
- **TYPE** -- the reward type (e.g., `shipping` for free shipping, `gift` for a free gift)
- **LABEL** -- the display text shown to the customer

**Example value:**

```
50|shipping|Free Shipping|100|gift|Free Gift
```

This creates two tiers:

- Spend $50 to unlock **Free Shipping**
- Spend $100 to unlock a **Free Gift**

6. Click **Save**

<div class="placeholder-screenshot">Theme Editor showing eshopping-cart-goal-items setting with pipe-separated tier values</div>

---

## How to disable popups

The eShopping theme supports several popup types including newsletter signup, promotional banners, and exit-intent overlays. Each popup has a delay setting that controls how long to wait before displaying. To disable a popup, set its delay to **0**:

1. Go to **Storefront** > **My Themes**
2. Click **Customize** on the eShopping theme
3. In the left panel, navigate to the **eShopping** section
4. Find the delay setting for the popup you want to disable (e.g., **eshopping-popup-newsletter-delay**, **eshopping-popup-promo-delay**, **eshopping-popup-exit-delay**)
5. Set the delay value to **0**
6. Click **Save**

A delay of 0 prevents the popup from appearing.

<div class="placeholder-screenshot">Theme Editor showing popup delay settings set to 0 to disable popups</div>

---

## How to add custom trust strip items

The trust strip displays a row of trust badges (such as "Free Shipping," "Secure Payment," or "30-Day Returns") below the header or on product pages. To customize the trust strip items:

1. Go to **Storefront** > **My Themes**
2. Click **Customize** on the eShopping theme
3. In the left panel, navigate to the **eShopping** section
4. Find the setting **eshopping-trust-text**
5. Edit the value using the pipe-separated format, where each item is separated by a `|` character

**Example value:**

```
Free Shipping on Orders $50+|Secure Checkout|30-Day Returns|24/7 Support
```

This creates four trust badges displayed in a row across the strip.

6. Click **Save**

<div class="placeholder-screenshot">Theme Editor showing eshopping-trust-text setting with pipe-separated trust badge labels</div>

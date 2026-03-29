# FAQs

Answers to the most common questions about configuring the eShopping theme. All settings are found in the Theme Editor -- no coding required.

---

## How do I disable the sign-in popup?

By default, a sign-in popup prompts visitors to log in or create an account when they click the account icon. To disable it:

1. Go to **Storefront** > **My Themes** > click **Customize** on the eShopping theme.
2. Navigate to **Theme Styles** > **eShopping** > **Header**.
3. Uncheck **Sign-in Popup**.
4. Click **Save**.

<div class="placeholder-screenshot">Theme Editor showing the Header section with the Sign-in Popup checkbox unchecked</div>

---

## How do I disable urgency signals (viewing count, recent orders)?

The theme can display urgency signals on product pages, such as "X people are viewing this" and "Last ordered Y hours ago." To disable them:

1. Go to **Storefront** > **My Themes** > click **Customize** on the eShopping theme.
2. Navigate to **Theme Styles** > **eShopping** > **Urgency Signals (Social Proof)**.
3. Uncheck **Show live view count** to hide the viewing counter.
4. Uncheck **Show last order time** to hide the recent order indicator.
5. Click **Save**.

<div class="placeholder-screenshot">Theme Editor showing the Urgency Signals section with both checkboxes unchecked</div>

---

## How do I disable recent sales notifications?

The theme can show toast-style notifications about recent purchases made by other customers. To turn them off:

1. Go to **Storefront** > **My Themes** > click **Customize** on the eShopping theme.
2. Navigate to **Theme Styles** > **eShopping** > **Recent Sales Popup**.
3. Set **Show on pages** to **Off -- don't show**.
4. Click **Save**.

<div class="placeholder-screenshot">Theme Editor showing the Recent Sales Popup section with Show on pages set to Off</div>

---

## How do I change the cart goal tiers?

The cart goal progress bar encourages shoppers to spend more by showing reward milestones like free shipping or a free gift. To customize the tiers:

1. Go to **Storefront** > **My Themes** > click **Customize** on the eShopping theme.
2. Navigate to **Theme Styles** > **eShopping** > **Cart Goal Bar**.
3. Edit the **Goal items** field.

The format is `amount|icon|label` with each tier separated by a comma. For example:

```
50|shipping|Free Shipping,100|discount|10% Off,150|gift|Free Gift
```

This creates three tiers:

- Spend $50 to unlock **Free Shipping**
- Spend $100 to unlock **10% Off**
- Spend $150 to unlock a **Free Gift**

4. Click **Save**.

<div class="placeholder-screenshot">Theme Editor showing the Cart Goal Bar section with Goal items field filled in with example tier values</div>

---

## How do I disable popups (newsletter, promotion, exit intent)?

The eShopping theme supports three popup types: **Newsletter Popup**, **Promotion Popup**, and **Exit Intent Popup**. To disable any popup, clear its content field:

1. Go to **Storefront** > **My Themes** > click **Customize** on the eShopping theme.
2. Navigate to **Theme Styles** > **eShopping**.
3. Scroll to the popup section you want to disable:
    - **Newsletter Popup** -- clear the **Newsletter Content** field
    - **Promotion Popup** -- clear the **Promo Content** field
    - **Exit Intent Popup** -- clear the **Exit Content** field
4. Click **Save**.

When the content field is empty, that popup will not appear on your store.

<div class="placeholder-screenshot">Theme Editor showing the Newsletter Popup section with the content field cleared to disable it</div>

---

## How do I customize the trust strip?

The trust strip displays a row of trust badges (such as "Free Shipping" or "Secure Payment") across your store. To customize the badges:

1. Go to **Storefront** > **My Themes** > click **Customize** on the eShopping theme.
2. Navigate to **Theme Styles** > **eShopping** > **Trust Strip**.
3. Edit the **Trust Strip Items** field.

Enter pairs of `Label|Subtitle` separated by pipes. Four pairs will display four badges. For example:

```
Free Shipping|On orders $50+|Secure Checkout|256-bit SSL|Easy Returns|30-day policy|24/7 Support|We're here to help
```

This creates four trust badges:

| Badge | Label | Subtitle |
|-------|-------|----------|
| 1 | Free Shipping | On orders $50+ |
| 2 | Secure Checkout | 256-bit SSL |
| 3 | Easy Returns | 30-day policy |
| 4 | 24/7 Support | We're here to help |

4. Click **Save**.

<div class="placeholder-screenshot">Theme Editor showing the Trust Strip section with Trust Strip Items field filled in with example badge values</div>

---

## How do I change the footer brands count?

To control how many brand logos appear in the footer:

1. Go to **Storefront** > **My Themes** > click **Customize** on the eShopping theme.
2. Navigate to **Theme Styles** > **General**.
3. Find the **Footer Brands Limit** setting and enter the number of brands you want to display.
4. Click **Save**.

<div class="placeholder-screenshot">Theme Styles > General panel with the Footer Brands Limit setting highlighted</div>

---

## How do I change products per page on category pages?

To set how many products appear on each category page:

1. Go to **Storefront** > **My Themes** > click **Customize** on the eShopping theme.
2. Navigate to **Theme Styles** > **Products**.
3. Under **Number of products displayed**, set the **Category page** count to your preferred number.
4. Click **Save**.

<div class="placeholder-screenshot">Theme Styles > Products panel showing the Category page products count setting</div>

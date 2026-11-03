# Rate Card Quote Tool

A single-page quote tool that estimates the monthly cost of a Boost Mobile account: up to 7 phone lines (the in-store limit), add-ons, tablets and watches.

## Features
- Mix and match plans per line: $25 Unlimited (BYOD), $40 Global Connection, $50 Unlimited+, $60 Unlimited Premium
- Plan features on every line: premium data, hotspot, international, and device options (BYOD / SRP / device deals)
- AutoPay on/off toggle that shows what AutoPay saves ($5/mo per line)
- Multi-line savings for $50/$60 lines
- 6 x $10 Offer (RPD Only): $10/mo for the first 6 months on up to 3 $25 Unlimited lines. Only shown when a $25 line is selected
- Boost Protect per line ($8 / $12 / $15 / $18 by device MSRP), plus a field for any other monthly add-on
- Connected devices: tablet ($20/mo) and watch ($10/mo) with an active phone line
- Add-a-line mode: amount due today (first month upfront + prorated charge) and the monthly bill going forward. Tablets and watches added the same day are charged the same way
- Line-by-line rate plan breakdown in the summary when there's more than one line
- Responsive layout, keyboard and screen-reader friendly

## Run it
No build step or dependencies. Open `index.html` in any browser.

## Publish with GitHub Pages
1. Create a new repository and upload `index.html` and `README.md` to the root.
2. Go to **Settings -> Pages**.
3. Under **Build and deployment**, set **Source** to *Deploy from a branch*, pick `main` and `/ (root)`, then **Save**.
4. After a minute or two the quote tool is live at `https://<your-username>.github.io/<repo-name>/` (for example, a repo named `rate-card-quote-tool`).

## Updating prices and labels
Everything is in the CONFIG section at the top of the `<script>` block in `index.html`:
- `MAX_LINES` - line limit (7)
- `AUTOPAY_DISCOUNT` - AutoPay savings per line
- `PLANS` - prices, features, device messaging, the 6 x $10 offer, and `rpdOnly` flags (set `rpdOnly: true` to add an "RPD Only" label)
- `DEVICE_PRICES` - tablet and watch prices
- `MULTILINE_DISCOUNTS` - total account savings by number of eligible lines
- `PROTECT_TIERS` - Boost Protect monthly fees

## How add-a-line charges are estimated
Boost is prepaid, so when a line is added the customer pays today:
- **First month upfront:** the new line(s)' monthly cost (including any change in multi-line savings, Boost Protect and the 6 x $10 offer)
- **Prorated charge:** that same monthly cost x days left until the next bill / days in the bill cycle

Taxes and activation fees are not included.

## Disclaimer
Estimate only. Excludes taxes, fees, device financing and activation fees. Check current offers with Boost Mobile; this project is not affiliated with Boost Mobile.

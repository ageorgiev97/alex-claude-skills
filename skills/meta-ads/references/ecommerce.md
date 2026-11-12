# Ecommerce: the playbook for online stores

Sales campaigns for businesses where people buy on the site and the purchase is tracked. Read this when planning, auditing or scaling a store account. Setup, targeting, creative, testing and tracking rules that apply to every advertiser live in their own files and are only summarised here.

## Contents
- Economics a store must know first
- Default structure
- What to optimise for, and when value optimisation applies
- Existing customers and new-customer acquisition
- Creative that stores need
- Offer and order-value levers
- Sale events and the end-of-December period
- Omnichannel ads (online plus physical stores)
- Product page and checkout
- Judging results
- Case studies
- Outdated advice to ignore

## Economics a store must know first

Abbreviations: AOV = average order value; ROAS = return on ad spend; LTV = customer lifetime value; CPM = cost per 1,000 impressions. Formulas and targets are in `offers-and-economics.md`.

- **Break-even cost per purchase = AOV x gross margin** (deduct direct costs such as cost of goods, not overheads). $80 at 50% margin allows up to $40; $200 at 50% allows $100. This is the maximum acceptable cost and the yardstick for every ad metric. [v001, v128]
- **Break-even ROAS follows from margin.** About 40% gross margin means 2.5x; a high-margin £27 product broke even at 1.4-1.5x. About 60% margin makes store advertising much easier; at 40% a price rise is usually the first recommendation. [v080, v114]
- **Start by breaking even on the first order,** which is cash-flow safe. Go below that only with cash reserves and proven repeat purchase. A repeat-purchase store can accept any first-order ROAS above 1.0. [v001, v024]
- **Trap: wanting a cost per purchase of 10-20% of AOV (about 10x ROAS).** It is rarely achievable consistently, cannot scale because cost per purchase rises with spend, and ignores repeat value. [v128, v398]
- **Low AOV** (about $20-30) needs high margin and a one-step funnel. A $15 product that needs a $7 cost per purchase is rarely achievable at scale. [v080, v133]
- **Amazon test.** If buyers can get the same or a similar product cheaper on Amazon, the campaign will not work, because they check. Differentiate by brand, features or price. Dropshipping a commodity with the manufacturer's creative is a race to the bottom. [v128, v133]

## Default structure

As of late 2026: one Sales campaign, one ad set, many ads, warm and cold audiences combined. Meta retargets inside "cold" ad sets anyway, so separate ad sets only split conversion data and stop Meta planning how often each person sees ads. [v037, v043]

| Setting | Choice for a store | Reason |
|---|---|---|
| Objective | Sales | Meta optimises literally; Traffic finds clickers, not buyers [v029] |
| Conversion location | "Website", chosen as a single location | A combined default can lock the performance goal to number of conversions [v045] |
| Performance goal | "Maximize value of conversions" once purchases arrive steadily; "Maximize number of conversions" in a brand-new account (next section) | Otherwise a $30 buyer and a $300 buyer count the same [v011, v008] |
| Conversion event | Purchase | Add-to-cart optimisation finds cart-adders, not buyers [v029] |
| Bid strategy | "Highest volume" to start; "ROAS goal" is available when order values vary | See `campaign-setup.md` [v029] |
| Audience | Broad. Location = everywhere you can ship. Custom audiences, age and interests as suggestions only | See `targeting.md` [v029] |
| Attribution | Default windows: 7-day click, 1-day engage-through, 1-day view | More conversion data for optimisation. See `tracking-and-attribution.md` [v032] |
| Ads | Typically 20+, mixed formats and styles; up to 5 primary texts and 5 headlines inside each ad | Delivery is personalised per person; copy variants go inside the ad [v043] |
| Destination | Product page or dedicated landing page, not the homepage | See "Product page and checkout" [v021, v058] |

Budget, placement and learning-phase rules are the general ones in `campaign-setup.md`.

When to split:

- **One campaign per product range, not per product** (hats vs shoes, not red hats vs blue hats). Ranges need different audiences and messaging, and a separate campaign can be paused when a range is out of stock. A store with one product type needs one or two campaigns. [v043, v080]
- **A catalogue campaign may span all ranges.** On a small budget it mostly retargets, showing people what they just viewed. Catalogue ads are strong for stores, especially on warm audiences, but they are an addition to the core campaign, not the starting point. Missing or invalid catalogue data costs campaign score points (12 of 100 in one demo). The source material gives no setup steps for catalogue ads, so none are given here. [v043, v049, v089]
- **A separate testing campaign** needs volume: do not split below about 50 purchases a week; at 100-200+ a week it is fine, with roughly 10-30% of spend. Below that, test inside the ad set with the ad-level tools ("Push delivery to this ad", creative testing). See `testing-and-scaling.md`. [v005, v014, v048]
- **One-step funnel for low-priced and impulse products.** A £27 order cannot pay for a lead magnet step plus retargeting, and a gift or impulse purchase needs no warming up. Cut awareness and traffic campaigns that do not drive ROAS. [v080]
- **No separate warm messaging for most stores.** Show the best ads to everyone. Warm-only creative or a warming campaign is for purchases above about $1,000. [v092]
- **New account or small budget:** one campaign, one ad set, one offer (the best seller or most profitable product), with an age range and a few obvious interests as suggestions to give Meta a starting direction. [v025, v029]

Settings that differ for stores:

- "Personalized destinations" (Meta may send a click to a different URL on the site) is acceptable when every destination is a product page. Turn it off for any planned funnel. [v012]
- Automatic translation of ad text is useful for physical products, where language is no barrier. [v029]
- Creative enhancements: a text overlay suits a clean product image (sale, main benefit, price), and AI backgrounds are acceptable on product shots if the result does not look AI-made. Re-check enhancements after every edit or duplication, because they can switch back on. [v003, v012, v097]
- Set the ad account "Industry" to "E-commerce" plus a second fitting option (Ads Manager menu > "Advertising settings" > "Industry"). It affects only new or duplicated campaigns. One store saw 32% more sales at the same spend after setting it and relaunching, though the relaunch may explain part of that. [v113]

## What to optimise for, and when value optimisation applies

The ad set performance goal matters more than the objective. Inside a Sales campaign never choose landing page views or link clicks (the campaign then behaves like Traffic) or reach or impressions (it behaves like Awareness). [v045, v087]

**Rule: a store with varying order values uses "Maximize value of conversions" as soon as the account has some purchase history.** A brand-new account, or one with only a handful of purchases a week, starts on "Maximize number of conversions" and switches once purchases arrive steadily. Meta then favours people predicted to spend more. Expect somewhat fewer purchases and higher revenue and ROAS. Meta quotes about 7% higher ROAS; the source agency's experience is higher, varying by business. [v024, v045]

| Situation | What to do | Source |
|---|---|---|
| Order values vary ($20 vs $200 baskets), purchase values reach Meta, and purchases arrive steadily | "Maximize value of conversions". It no longer needs high volume; this is the default for new builds as of late 2026 | v011, v008, v045 |
| Brand-new account with no conversion data, or only a handful of purchases a week | Start on "Maximize number of conversions" and switch to value once there is conversion history. The sources give no numeric floor, only "some conversion data" and "not a handful a week" | v008, v013 |
| One product at one price, bought once | Value and number are equivalent. The better fix is to add an upsell or a more expensive option | v045, v087 |
| The value option is locked or missing | Change conversion location from a combined default (for example "Website and calls") to the single location "Website" | v045 |
| A long-running campaign on "Maximize number of conversions" that performs well | Leave it. Test value in another campaign and switch only on a clear improvement | v024 |
| Purchases far below what Meta needs (for example 7 a week against 35 add-to-carts) | Stay on Purchase if about 20 a week is reachable. Otherwise run add-to-cart for a month as a test against Purchase and compare overall results; expect fewer carts to become purchases | v034 |

Requirements: the pixel and the Conversions API both installed and passing accurate purchase values. Store platforms such as Shopify pass values automatically. [v045, v087]

**Value rules cover what value optimisation cannot see.** Meta sees value only inside the attribution window, so repeat purchase, refunds and lifetime value are invisible to it. If one segment is worth more over time, raise its bid with a value rule and keep targeting broad. Mechanics are in `targeting.md`.

- Standard case: an online women's jewellery store. Broad targeting sent a large share of spend to men buying one-off gifts; women bought for themselves and came back. A rule bidding more for women fixed it without excluding men. [v028, v073]
- Set the percentage from customer data (a segment worth 70% more justifies about +70%). When unsure, start near the 20% default and watch the mix; in one illustration a 50/50 gender split became 65% women after +20%. [v073, v074]
- Adjust in one direction only: do not pair "increase women" with "decrease men". [v074]
- Expect a higher reported cost per purchase. A 10% rise is a good trade if the favoured segment is worth 2.4x over its lifetime. [v028]
- Do not build rules from where purchases already come from. Meta optimises for that already. [v013]

## Existing customers and new-customer acquisition

Meta spends on warm people inside broad ad sets because they convert cheapest. In one broad US ad set with just under $80,000 spent, about 40% went to engaged audience and existing customers, and they produced more than half of 942 purchases at a clearly lower cost. In another, 59 of 93 purchases came from existing customers. [v037, v043]

**Step 1: measure it.** Define the segments once (Ads Manager > "Advertising settings" > "Audience segments": set "Engaged audience" and "Existing customers" from custom audiences), then use Breakdown > "Audience segments". "Unknown" means the segments are not defined. [v006, v043]

- Existing customers: a customer list (uploaded, or synced from a platform such as Shopify) plus the website purchase audience. Purchase audiences can now look back 730 days instead of 180; update old ones. [v006, v037]
- Upload at least the last three years of customers, with a value column if available. Meta cannot otherwise know who bought two years ago. [v089, v132]
- Engaged audience: website visitors (180 days), page and profile engagers, video viewers, email list. [v037]

**Step 2: decide.**

| Finding | Action | Reason |
|---|---|---|
| Existing customers take a modest share of spend | Leave the customer lifecycle setting (ad set level, Sales campaigns, introduced in autumn 2026) on "Get conversions from all audiences", the default | Customers repurchase, refer and need reminders, and reaching them is cheap [v006, v128] |
| A large share of spend or purchases goes to existing customers (typical of established brands, long-time advertisers, one-time-purchase products) | Switch the ad set to "Acquire new customers" | Existing customers are excluded, so budget goes to incremental buyers [v006] |
| A softer correction is wanted, or the business sells through many channels | Change the ad set attribution model from standard to incremental | Meta optimises for purchases that would not have happened anyway. For larger advertisers with big customer bases, not beginners [v006, v013] |
| A deal for new customers only, or a deep discount that would upset people who paid full price | Run that ad set on "Acquire new customers". Excluding the customer list by hand in audience controls is the older route | Neither route is airtight, and hand exclusions disrupted delivery in recent tests [v006, v142, v291] |
| An offer only customers should see (for example an upgrade) | Separate ad set with the customer audience as a hard limit ("Further limit the reach of your ads", with "Use as a suggestion" unticked) | The one case for a retargeting-only ad set. See `targeting.md` [v037] |

Cautions:

- With "Acquire new customers", do not also exclude the engaged audience. Yesterday's website visitor is the best prospect. [v006]
- Matching is only about 50% accurate, so some customers still see ads. [v006]
- Reported ROAS and cost per purchase get worse after the switch, because existing customers were the cheapest conversions. That is the price of incremental growth, not a decline. The same applies to incremental attribution. [v006, v072]
- Do not exclude purchaser audiences in audience controls as a routine way to force new customers. In testing ROAS fell and daily spend dropped from about $200 to $50. [v006]
- Heavy warm delivery flatters early results. A campaign that looks excellent at launch and then fades may have used up the warm pool; check the segment breakdown before calling it a winner. [v128]

Reactivating past customers deserves more effort than most stores give it, mostly outside the ad account (email, SMS, comeback codes, samples). A list of a few thousand customers is very cheap to keep reaching with ads. Do not spend more on warm audiences than on cold unless the customer base is very large. [v128]

## Creative that stores need

Meta has automated most of a sales campaign, so creative is where stores still beat competitors. `creative.md` owns the detail; these points are specific to stores. [v046]

- **Run a mix in one ad set:** statics, video, carousels and flexible ads. As of late 2026 Meta gives statics more of the budget inside mixed ad sets, and statics are cheap to make in volume (for example 16 statics and 4 videos out of 20). Do not drop video. [v003]
- **Match format to price and familiarity.** A $15-20 impulse item sells with a single image or carousel and one to three lines of copy. A $150+ or unfamiliar product needs video, demonstration and longer copy. [v003, v398]
- **UGC (user-generated-content style video) suits impulse purchases** because it reads as a peer recommendation. Low production value is fine there; it hurts a premium product. A store that says video does not work has usually tried two weak videos; test distinct styles (UGC, creator, founder-led, demonstration, slideshow, animation) first. [v050, v080]
- **Creators are the biggest single lever.** Pay niche creators to record ads the brand runs, ideally as partnership ads, instead of paying for an organic post that fades in 24-48 hours. Start with small relevant creators and scale the name with the budget. It is hit and miss, so use several. See the case studies. [v046, v088, v114]
- **Carousels** suit stores where people buy several similar items. Put the best past product images side by side, each card linking to its own product page. They can raise AOV because shoppers arrive aware of the range. [v080]
- **Flexible format** (ad level > Format > "Flexible"; Sales and App objectives only): upload up to 10 creatives and Meta shows them singly, as a slideshow or as a carousel. Against ordinary image ads in the same ad set it nearly always attracts more budget and usually better results; it fits image-heavy stores without strong video. Use different images of one product or of a range, each able to stand alone, with copy that fits any of them. Do not load near-identical variants or cards that only make sense together. Leave its enhancements on (they are all-or-nothing). It starts slowly: weeks 1-2 are often clearly worse than weeks 4-8, so do not kill it early. [v082]
- **One product, many use cases.** Make separate ads for each use of the same product (marathon shorts, winter shorts, cross-country shorts) and keep targeting broad. That can mean 40 ads instead of 4. Back each with a matching landing page, or matching wording on the product page; the claimed uplift is about 40% ROAS. [v088, v128]
- **Show the product working.** Open with a visual demonstration of the outcome, then give context. Contrast the old way with the new way. [v058]
- **End with a specific call to action, an offer and scarcity,** stated in the creative and mirrored in the headline and button. Weak endings were the most common fault in reviewed store ads. For cold audiences say what the product is within seconds; slow-reveal hooks only work on people who know the brand. Give benefits with numbers, pre-empt objections, and add numeric social proof or third-party validation. [v046]
- **Budget for creative:** about 10% of ad spend; it needs only a 10% lift to pay for itself. [v128]
- **Refresh rate depends on the market.** Where buyers pass through quickly (baby products) the audience renews itself and winners last longer. Where the same hobbyists stay for years, rotate creative more. A single-country audience with heavy seasonal spend needs many fresh variations. [v080, v114]

## Offer and order-value levers

Raising what a customer is worth usually moves results more than shaving cost per purchase, which has a floor set by competition. Moving margin per customer from $26 to $30 does the same as forcing cost per purchase from $12 to $10, and is usually easier. Offer design in general is in `offers-and-economics.md`. [v128, v133]

| Lever | How | Numbers | Source |
|---|---|---|---|
| Bundles | Sell closely related items together. Cost per purchase does not rise in proportion to order value, and bundles are harder to price-compare | $50 shoes at a $30 cost per purchase lose money; four pairs for $200 at $60-75 do not | v328 |
| Tiers | Entry tier, a core bundle labelled "most popular", and a high-ticket best-value tier, each for a buyer segment. The discount becomes implied bulk value | Part of the changes that took ROAS from 4.07 to 4.7 while spend rose about 60% | v058 |
| Post-purchase upsells | One-click offers straight after purchase with no card re-entry, up to about three in sequence; plus order bumps and email upsells | AOV $30 to $60 moves acceptable cost per purchase from $15 to $30 | v398, v596 |
| Higher AOV in general | Price, bundles, carousels that show the range | AOV $80 to $120 raises allowable cost from $40 to $60, which may allow about 5x the spend | v128 |
| Subscription | Offer recurring billing even if few take it and each payment is smaller | Retention of 10 months instead of 5 doubles LTV and the affordable acquisition cost | v001, v128 |
| Repeat purchase | Email, SMS, retargeting, samples, comeback codes, packaging inserts | Average purchases from 2 to 6 triples lifetime profit with no change to ads | v128, v137 |
| Surprise gift | About 30 days after the first order, send a cheap related item as its own unannounced delivery | The few stores that did it saw more sharing and cheaper later conversions | v088 |
| Time-limited offer | Keep a dated promotion running most of the time and rotate the mechanic | See next section | v088, v128 |

Offer rules:

- **Urgency and scarcity are different, and both are underused.** Urgency is a deadline ("30% off ends 30 June"). Scarcity is limited quantity ("only 10 left"). Every promotion needs a stated end date; state stock limits when they are real. [v103, v128]
- **Rotate the mechanic, not just the date:** 30% off, then buy two get one free, then a free item with purchase. Change the featured range too. Repeating the same "ends this month" discount trains people to ignore it. [v088, v128]
- **Find a reason for a sale at any time of year** (a seasonal theme, an industry day) instead of waiting for Black Friday. [v088]
- **Discounting is not the only offer.** Discounts help most when competitors sell near-identical products. With few direct competitors, sell on effectiveness, tiers, bundles, guarantees and bonus products. [v058]
- **Offer fatigue is separate from ad fatigue.** If results fall while creative is being refreshed, most of the audience has seen the offer and declined. Keep a second offer ready: a different discount structure, a guarantee, a free gift or a different range. [v121]

## Sale events and the end-of-December period

- **Lean into seasonality.** Load budget into peak periods and cut hard in the off-season (possibly down to keeping regulars buying). Whole-year ROAS ends up better than with even spend. Compare a seasonal month with the same month last year. [v107, v128]
- **Scale faster for a dated event.** For Black Friday, a Christmas sale or a few-day sale, raise budgets hard while it works. A higher cost per purchase is worth the risk and re-entering learning is not a disaster. See `testing-and-scaling.md`. [v026, v097]
- **Skip formal creative tests around a one-off sale.** Add the sale ads to the ad set and let Meta sort them. The exception is a sale repeated every few months, where knowing which creatives work has future value. [v005, v048]
- **Sale ads are simple and specific.** Offer readable at a glance, a text overlay with the discount size and end date, the headline restating the offer, the same deadline in the primary text. "Flash sale" or "limited time" with no size and no end time is weak. Use several images or products so a short sale does not tire the audience, and repeat the offer in a banner or countdown on the landing page. [v244, v435]
- **Discount-led ads mostly convert warm people,** who already know the product and were held back by price. They do not scale to cold audiences, who still need a reason to buy at all. Keep product-selling ads in the mix during a sale. [v050]
- **A dated discount shortens an ad's life.** A winner with no date or event in it can run all year; a dated offer lifts short-term sales at the cost of longevity. Choose deliberately. [v050]
- **Expect dearer auctions.** Q4 2024 CPMs were about 20-21% above Q4 2023. A store at 3x ROAS with break-even at 2.5x can absorb only so many such rises, which is why order value and LTV matter. [v080, v088]
- **Plan stock before scaling into peak.** Stock-outs are common. If a limit is foreseeable, hold spend steady instead of scaling and then switching campaigns off, and turn off ads for sold-out products. One brand reached £3.69M in a quarter where an estimated £5M+ was possible. [v080, v114]

**The end-of-December period ("Q5": about 20/21 to 31 December).** Many advertisers switch off once gift shipping cut-offs pass, so CPMs fall. Buying falls too, but less, and people are off work and on their phones. Do not switch off on 20 December and return in January. [v103]

| Window | What changes | What to run |
|---|---|---|
| 21-25 Dec | Less competition and lower cost. Buying shifts from gifts to buying for oneself | "Treat yourself" messaging in place of gifting copy. With physical stores, push store visits once delivery cannot arrive in time |
| 26-31 Dec | Shoppers expect big deals, as on Black Friday | Heavy discounts and bundles, a genuine stated reason for the sale (clearing Christmas stock), a clear end date ("until New Year's Eve") in copy and creative, stock scarcity where real |
| Either | Evergreen ads underperform seasonal ones | Seasonal creative with a text overlay confirming the sale. Health, fitness and goal-related stores can start new-year angles in the second window |

Before Christmas, gifting copy works because it gives a specific use case. Pause over the holidays only if the business is closed or cannot deliver. January CPMs are often cheaper because advertiser activity drops. [v103, v133, v265]

## Omnichannel ads (online plus physical stores)

For any business that sells online and has at least one physical location. A Sales campaign optimises for a mix of website and in-store purchases. [v074, v086]

- **Where:** Sales campaign > ad set > Conversion location > "Website and in-store". Reporting column: "Purchases (website and in-store)". Described in 2025 as rolling out to all eligible advertisers; check the account. [v029, v086]
- **Eligibility:** physical stores plus online sales; Conversions API sending offline (in-store) purchases; event match quality of at least 4.8; Sales objective. [v086]
- **What shoppers see:** nearby store locations with distance, a link to store details and a map, "in store" availability on products through local inventory ads, and promotion options (a code, or an offer tag with no code). [v086]
- **Evidence:** in Meta's test with about 100 advertisers, cost per purchase counted across both channels was 16% lower than when optimising for website purchases only. Catalogue ads gave a 41% lower cost per such purchase than other ad types. [v086]
- **Practice:** keep the offline data feed and event match quality healthy, because performance drops when they slip. Update store location pages. Use catalogue ads and local inventory ads with an accurate inventory feed. Keep creative diverse. [v086]
- **When to push people in store:** when in-store order value is higher (about 2x online for some clients), or when shipping can no longer arrive before a gifting date (Christmas, Mother's Day, Valentine's Day). [v086]

## Product page and checkout

The ads can work while the store loses the sale after the click. `offers-and-economics.md` owns landing pages in general.

- **Send each ad to a page about that product.** A generic multi-product page, or a page where the product looks different from the ad, is a common failure. Each ad or product needs a matching page with one clear action. [v021]
- **Homepage traffic underperforms.** One store replaced the homepage with an explainer-first page: a short video at the top (outcome, how it works, who it is for, why it beats alternatives), no header menu, one action, and an optional quiz that recommends a product to undecided visitors. [v058]
- **Benchmarks.** Purchases per link click: 2-5% is normal, under 2% is poor, 0.5-0.7% is a clear problem. Going from 0.5% to 2.5% is 5x the purchases at the same spend. Landing page views 20-25% below link clicks is fine; a gap of 50% or more means a slow page or accidental clicks. [v118, v389]
- **Good click-through rate, poor conversion:** check ad-to-page match, unexpected costs such as a shipping fee that appears late, and missing reviews or proof. First check that the ad actually sells the product; curiosity-bait ads send low-intent clicks. [v118]
- **Many add-to-carts, few purchases** (about 10 to 1 is too many): look at the checkout, delivery fees and times, load speed and bugs. Plenty of add-to-carts means the ads are doing their job. [v262, v409]
- **Reviews are part of the page and the product.** Many buyers, younger ones especially, check reviews and competitors before buying, and AI assistants draw on the same reviews. The bar is better than competitors, not good. Make review collection a standing process. Read bad reviews for fixable causes (slow delivery, confusing instructions) and good ones for what to emphasise. Fix quality before scaling, or scaling only produces more bad reviews. [v068, v069]
- **Tracking on the store.** Purchase must fire only on the order confirmation page; check with the Meta Pixel Helper extension. A Purchase event that fires on page load teaches Meta that every click converts. If a third-party checkout cannot carry the pixel, change the checkout. See `tracking-and-attribution.md`. [v025, v062]
- **Keep product information, FAQs, discount and shipping policies well documented.** Meta has been testing an AI assistant inside ads that answers product questions from the business's own information (in testing in 2025; availability unconfirmed). [v071]

## Judging results

- **ROAS is the primary metric,** because it reflects order value, at account, campaign, ad and offer level. Judge it against the store's break-even ROAS, not a round number. Click-through rate, hook rate and CPM only explain a ROAS result; never turn off a good-ROAS ad for a low click-through rate. See `analysis-and-troubleshooting.md`. [v107, v114, v128]
- **When scaling, judge absolute return.** $1,000 a month at 15x leaves $14,000 after ad spend; $100,000 a month at 4x leaves $300,000. ROAS falls as spend rises because Meta reaches the keenest buyers first. [v121, v128]
- **Do not prune the ad set to its single best ad.** Lower-ROAS ads reach other slices of the audience, and a high-spend ad with weak ROAS is often the one introducing the product while other ads close. Check the ad set's overall ROAS before and after removing it. [v005, v043, v064]
- **Decide on conversion volume, not elapsed time.** A store with a couple of sales a week may need a month or more per decision; one with thousands of sales a day can judge an ad in hours (45 purchases is a fair sample). Use a significance calculator when two ads are close, and compare months, not days. [v080, v107, v128]
- **Reported ROAS counts the first order only.** For subscription and repeat-purchase stores it understates the return; judge against lifetime value and back-end revenue. [v118, v137]
- **Reported purchases undercount.** Many buyers see an ad, check reviews, then buy later through search, direct or a marketplace. Keep view-through attribution on, run the Conversions API, and compare with back-end sales before concluding that performance fell. This matters most after the 2026 attribution change, a switch to "Acquire new customers" or a switch to incremental attribution, all of which lower reported numbers without lowering sales. [v006, v032, v068]
- **Results sliding for months despite steady new creative:** with fatigue, some new ads match or beat the old ones. If old and new trend down together, compare the product's reviews with competitors' before blaming the account. [v069]
- **Results collapse whenever budget rises:** either too few new ads are being made, or there is no headroom between current and maximum cost per purchase. At $20 with a $25 ceiling a store can perhaps double spend; with a $40-50 ceiling it may scale 10-20x. [v128, v134]

## Case studies

| Store | Before | Change | After | Lesson |
|---|---|---|---|---|
| UK puzzle-notebook brand, AOV about £27, 60-70% of sales in Q4 [v080] | Q4 2023: spend £499k, revenue £979k, ROAS 1.95x, cost per purchase £14.12, about 35,000 units | Many thin campaigns consolidated into one testing and one scaling campaign; awareness and traffic campaigns cut; one-step funnel; UGC video as main driver plus carousels and images; far more creative volume | Q4 2024: spend £788k, revenue £3.69M, ROAS 4.68x, cost per purchase £5.91, about 133,000 units, with CPMs about 20% higher | Consolidation and format mix. Stock-outs capped it; £5M+ was thought possible |
| US baby products, AOV $115, about 40% margin, break-even 2.5x [v114] | $7,000 a day, ROAS 3.2x, revenue about $800k a month; best ads were product images; hook rate 11.7% | One widely recognised creator paid $45,000 for three product-recommendation videos run as the brand's ads; same products, offer and budget | ROAS 5.9x, revenue $1.4M a month, hook rate just under 35%; fee recovered in about two weeks | Budgeting one week of ad spend for a creator most of the market recognises paid off. Spend was held because stock could not support more |
| US newborn clothing [v088] | $15,000 a month | A creator with about 175,000 followers was sent products and paid $800 for two review videos | ROAS up 263%; scaled to $65,000 a month | Small niche creators are cheap and effective |
| Niche DIY tools store [v058] | 30 days: spend $26,473, revenue about $107,000, ROAS 4.07 | Tiered offer without blanket discounts; explainer-first landing page in place of the homepage; demo-first creative; creators matched to each buyer segment | Month six: spend about $43,000, revenue about $202,000, ROAS 4.7; profit after ad spend from about $81,000 to $160,000 a month | A modest ROAS lift at much higher spend doubles profit. It took months |
| Mid-size brand with a hero product [v069] | Slow decline to unprofitable despite regular new ads | Found the hero product's reviews were mediocre next to competitors'; advertised better-reviewed products on the front end | Returned to profit, together with other changes | Check reviews when old and new ads decline together |
| Online women's jewellery store [v028, v073] | Broad targeting spent heavily on men buying one-off gifts | Value rule raising bids for women | Spend shifted towards women and the long-standing problem was fixed; a higher cost per purchase is the expected trade | Tell Meta what it cannot see |
| Agency client with an unknown staff member in its ads (business type not stated) [v074] | ROAS 2.5x | Swapped the person for a creator known to part of the market; content otherwise similar | ROAS 6.5x | The face matters |
| Tech products store with a mixed account history [v113] | Meta appeared confused about who converts | Set "Industry" to E-commerce plus Technology; duplicated campaigns and turned off the originals | 32% more sales at the same spend | Cheap to try; the effect cannot be cleanly attributed |

Reference points: the source agency's clients (about 60% ecommerce) averaged above 4x ROAS in Q4 2024, and three brands part-owned and fronted by a major celebrity reached 10-12x in industries where about 4x is the benchmark. [v088, v133]

## Outdated advice to ignore

| Old rule | Current rule | Why it changed |
|---|---|---|
| Choose between an Advantage+ shopping campaign and a manual sales campaign, and retest every six months | One Sales campaign setup; it counts as an "Advantage+ sales campaign" when audience, budget and placements are left on Meta's defaults [v089] | Meta merged the two in 2025 |
| Separate cold and retargeting campaigns, plus add-to-cart retargeting ad sets | One ad set with warm and cold combined [v037, v043] | Custom audiences are only suggestions, so the ad sets overlapped; splitting fragments data and breaks impression planning |
| "Maximize number of conversions" by default, value only at high volume | "Maximize value of conversions" for any store with varying order values once purchases arrive steadily; number only while the account is new [v011, v008] | Meta otherwise chases the cheapest buyer |
| Optimise for add to cart to get out of learning | Optimise for Purchase; move up only as a measured test at very low volume [v029, v034] | Meta delivers exactly the event asked for |
| Exclude purchaser audiences to force new-customer delivery | "Acquire new customers" lifecycle setting or incremental attribution, and only when the segment breakdown shows a problem [v006] | Hand exclusions disrupted delivery in testing |
| Exclude past customers from cold campaigns to save money | Leave them in by default [v006, v128] | They repurchase and refer, and they are a small share of a broad audience |
| Purchaser audiences with a 180-day lookback | 730 days [v006] | Meta extended the window |
| Pay influencers for organic posts | Pay them to make ads the brand runs, ideally as partnership ads [v046, v114] | A post lasts a day or two; an ad asset runs for months |
| Switch off from about 20 December until January | Keep running with seasonal offers; pause only if the business cannot deliver [v103] | CPMs fall more than demand |
| Aim for 10x ROAS on the first order | Set the maximum at break-even on the first order and profit on repeat purchase [v128] | Low cost targets cannot scale |

Old habits owned by other files (ad counts per ad set, video versus static, budget step sizes, pixel warm-up campaigns) are in `platform-changes.md`.

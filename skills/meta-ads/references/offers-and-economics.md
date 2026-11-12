# Offers and economics

How to work out what an advertiser can afford to pay for a customer, how to raise that figure, and how to design the offer, price, funnel and landing page that the ads sell. Read this before judging any cost per result, before recommending a scale-up, and whenever results are poor and the cause may sit outside Ads Manager.

## Contents
- 1. Unit economics: inputs, formulas, worked examples
- 2. Break-even versus target, and reading live data against them
- 3. Raising customer value
- 4. Offer design: components, offer types, decision rules, case studies
- 5. Pricing and price testing
- 6. Urgency and scarcity, done honestly
- 7. Funnel choice by price point
- 8. Landing pages and ad-to-page match
- 9. Is it the offer, the creative, the page or the business model?
- 10. Validating an offer or product before building it
- Outdated advice to ignore

## 1. Unit economics: inputs, formulas, worked examples

Unit economics predict success on Meta better than targeting, creative or landing page. A cost per purchase, a click-through rate (CTR) or a cost per thousand impressions (CPM) cannot be called good or bad until you know what a customer is worth: "$30 per purchase" is excellent for one business and fatal for another. Get these numbers before reading the account. [v001]

### Inputs to ask the user for
| Input | Definition | If "it varies" |
|---|---|---|
| Average order value (AOV) | Money received in the first transaction: the order, the first service purchase, the first subscription or retainer payment | Total sales value ÷ number of customers |
| Number of purchases | Average purchases per customer over the lifetime (months retained for subscriptions) | Total purchases ÷ number of customers. With little data, estimate low and update |
| Gross margin % | Revenue minus direct costs only: cost of goods sold (COGS), manufacturer cost, direct labour. Leave overheads out; they are fixed, not marginal | Service: staff cost ÷ revenue that person services (3,000 a month for 6 clients at 2,000 each = 25% cost, 75% margin). Software and pure consulting can be near 100% |
| Lead-to-customer rate (lead gen) | Customers ÷ leads | Count from the CRM |
| Ad spend and new customers | Same period for both; new customers only | Take from the back end |

[v001, v137]

### Formulas
| Metric | Formula |
|---|---|
| Lifetime value (LTV, lifetime revenue) | AOV × number of purchases |
| Lifetime gross profit (LTGP) | LTV × gross margin % |
| Customer acquisition cost (CAC) | Ad spend ÷ new customers in the same period |
| LTGP:CAC ratio | LTGP ÷ CAC |
| Break-even cost per purchase (sales model) | AOV × gross margin % |
| Break-even return on ad spend (ROAS) | 1 ÷ gross margin % (40% margin = 2.5x; 50% = 2x) |
| Break-even cost per lead (CPL) (lead model) | First-transaction value × gross margin % × lead-to-customer rate |
| Allowable CPL from an allowable CAC | Allowable CAC × lead-to-customer rate |
| First-purchase ROAS (what Ads Manager shows) | AOV ÷ CAC |

Every business is one of two models: people pay directly (use cost per purchase) or a lead comes first (use CPL). [v001, v114, v137]

### Worked example: sales model
AOV $200, 5 purchases, 50% margin. LTV = $1,000. LTGP = $500. Spend $10,000 for 200 new customers: CAC = $50. LTGP:CAC = 10. Break-even cost per purchase = $200 × 50% = $100. [v001]

LTGP:CAC is not ROAS. With AOV $125, 6 purchases, 50% margin and a $50 CAC, LTGP is $375 and the ratio is 7.5 ($7.50 gross profit per $1 of ads), while Ads Manager shows 125 ÷ 50 = 2.5x because it sees only the first purchase. [v137]

### Worked example: lead model
First transaction $1,000, 50% margin, 20% of leads become customers: break-even CPL = $1,000 × 0.5 × 0.2 = $100. At 75% margin: $150. At 75% margin and a 10% close rate: $75. At 30%: $225. The close rate moves the ceiling as much as anything in the ad account. [v001]

Working back from lifetime value: a £75,000 average customer, an owner willing to spend 10% (£7,500) to win one, 1 in 12 leads closing: allowable CPL about £625. [v120]

### What moves the ratio (base example, ratio 10)
| Change | New ratio |
|---|---|
| CAC cut 25% (250 customers instead of 200) | 12.5 |
| AOV $200 → $300, purchases 5 → 8, margin 50% → 60% | 28.8 |
| Purchases 5 → 15 | 30 |
| Subscription: AOV halves to $100, purchases 5 → 23 | 23 |

Time is better spent raising customer value than shaving 15–20% off cost per result. [v001]

### Thresholds
- LTGP:CAC above 3:1: healthy, scale. Not 2:1, because gross profit still has to cover overheads, which grow with scale. Strong accounts run at 12:1, 20:1 and above. [v137]
- Gross margin: about 60% is preferred for ecommerce (easier advertising, more profit at scale). At 40%, break-even ROAS is 2.5x. [v114]
- A one-time purchase with about $20 profit per customer and no repeat is very hard to advertise profitably. Fix the model before the ads. [v001]
- Lead-to-customer rate for a service: about 20% is the normal expectation. 14% was judged acceptable at a £21,000 customer value. [v108, v110]

## 2. Break-even versus target, and reading live data against them

Break-even is a ceiling, not a target. Lower is better; the reason to compute it is to know the most the advertiser can pay. [v128, v454]

| Question | Rule | Why |
|---|---|---|
| Which break-even to start from? | Break-even on the first transaction (AOV × margin) | Cash-flow safe; profit comes from repeat purchases [v001] |
| When may cost exceed it? | Only with cash reserves and proven repeat revenue, judged on LTGP:CAC | Losing money on the first order can be very profitable, but the gap must be funded. Funded companies do it deliberately (a $9-a-month subscription accepting $80 CAC) [v001, v137] |
| What is the working target? | Clearly better than break-even before scaling: if break-even ROAS is 3x, reach about 4x, ideally near 5x, at the current budget | Cost per result rises with spend, because Meta reaches the most responsive people first [v061] |
| Payment plans, subscriptions | Discount LTV for failed payments and churn (one case: £1,560 nominal cut to £1,250) | Not everyone completes all payments [v108] |
| New account, small budget | Accept results down to break-even; treat 4x ROAS as a good outcome | The first goal is a break-even system that can be scaled, not maximum ROAS [v106] |

### Comparing live cost per result with the ceiling
| Live figure | Action |
|---|---|
| Well under (CPL $50–100 against a $225 ceiling) | Scale aggressively |
| Just under (CPL $200 against $225; cost per purchase $19 against $20) | Hold, or scale only a little. Build headroom first through customer value or better ads |
| ROAS has fallen to the floor while scaling | Hold the budget, improve offer and creative, then scale again |
| Over the ceiling | Loss on the first transaction. Acceptable only if LTGP:CAC stays above 3:1 and cash allows; otherwise fix value, offer or creative before spending more |

[v001, v107, v133]

Ask: "How much more could you afford to pay per customer than you pay now?" At $20 now with a $25 ceiling, spend can perhaps double. With a $40–50 ceiling it may go 10–20x, because the account can profitably reach less responsive people. Most advertisers have never calculated this. [v134]

Reading notes:
- Stated targets are often far too low. An $80 AOV at 50% margin allows up to $40 per purchase; owners ask for $8–16. A cost per purchase of 10% of AOV (10x ROAS) is rare and does not survive scale. Recompute the ceiling. [v128, v398]
- Acceptable ROAS depends on margin. 1.5x can be excellent for software or information products; a £27-AOV, high-margin product broke even at 1.4–1.5x. A business unprofitable at 10x has a problem outside the ads. [v042, v062, v080]
- At scale judge absolute profit, not ROAS: $1,000 a month at 15x leaves $14,000 after ad spend; $100,000 a month at 4x leaves $300,000. [v128]
- Ads Manager misses later payments on recurring billing (one account: 96,000 actual against 38,000 reported). Use back-end revenue for LTV and CAC. See `tracking-and-attribution.md`. [v061]
- Scaling steps and cadence: see `testing-and-scaling.md`.

## 3. Raising customer value

Cost per conversion has a floor set by the auction: advertisers reaching the same people pay roughly the same CPM whatever they sell, and halving an already decent cost per acquisition (CPA) is close to impossible. Customer value has no ceiling, and a customer worth 10x more usually costs only 3–4x more to acquire. [v120, v133]

The winners in an industry have the highest lifetime gross profit, not the lowest CAC, because they can outbid everyone. A $22 CAC against $35 of revenue per customer is a value problem, not a CAC problem. [v001, v062]

| Lever | How | Numbers |
|---|---|---|
| Repeat purchases (usually the biggest) | Email and SMS follow-up, reactivation, retargeting past buyers, comeback codes, samples, packaging inserts, service quality | Purchases 2 → 6 triples the ratio with no change to ads [v001, v137] |
| Recurring billing | Add a subscription or retainer version, even if few take it and each payment is smaller | AOV halved with purchases 5 → 23: ratio 10 → 23. Churn 4% → 2% doubles lifetime [v001, v137] |
| Higher AOV | Bundles of related items, tiers, order bumps, cross-sells, one-click upsells straight after purchase (no card re-entry) | AOV $30 → $60 lifts allowable CPA $15 → $30. AOV $80 → $120 lifts it $40 → $60, which may support about 5x the spend [v128, v398] |
| Price | Add value and charge for it; doubling delivered value often adds only 10–30% to delivery cost | Section 5 [v137] |
| Gross margin | Cheaper sourcing or delivery. Rarely triples, but check | One client fought to cut CPA from £8 to £7 while paying £21 a unit for goods available at £6–10 [v465] |
| Close rate (lead gen) | Faster, more persistent follow-up; better sales process | Close rate 10% → 30% triples allowable CPL. Follow-up alone gave 3x revenue from the same leads. See `lead-generation.md` [v001, v133] |
| Referrals and goodwill | Referral prompts; a small unannounced gift sent alone about 30 days after the first order | Reported: more sharing, cheaper later conversions [v088] |
| Ascension | Sell a higher tier to existing buyers; aim messaging at higher-spending segments | 6.5% of £3,000-tier buyers upgraded to a £21,000 tier within 5 months [v110, v120] |

Order of attack: repeat purchases, then AOV, then margin. Cost per result does not rise in proportion to order value: a $50 pair of shoes at a $30 CPA loses money, while a four-pair $200 bundle might cost $60–75 to sell. Lifting margin per customer from $26 to $30 does the same as forcing cost per purchase from $12 to $10, and is usually easier. [v001, v128, v328]

Store-specific order-value and repeat-purchase tactics: see `ecommerce.md`.

## 4. Offer design

The offer is the highest-leverage element. Order of importance, and of testing: offer, creative, headline, format, primary text, call-to-action button, description. A strong offer survives mediocre creative and setup; nothing rescues a weak one. Settings changes yield tens of percent; an offer change can cut cost per lead by half or far more. [v061, v107, v108]

An offer is the product plus everything around it, not the product with a discount attached. Value equation: value = (dream outcome × perceived likelihood of achieving it) ÷ (time delay × effort and sacrifice). Raise the top, shrink the bottom. [v061]

### The four components
| Component | What to do | Notes |
|---|---|---|
| The thing sold | Beat competitors on at least one of outcome, believability, speed, ease; they stack | "As good as" loses to a known brand |
| Guarantee | Result or we keep working free; result or money back; refund plus a competitor's product; durability (10 years where the norm is 2); delivery or installation time (72 hours where rivals take a week); result within 30 or 90 days | Raises perceived likelihood; strongest in sceptical markets; heavily under-used. Fear of paying out means the product needs work |
| Scarcity and urgency | Real limits on quantity and time | Section 6 |
| Proof | Reviews, testimonials, review-site score, accreditations, named clients, results on video | Easiest to add; matters most without an established brand |

[v061, v111]

### Offer types
| Type | Example | Fits when |
|---|---|---|
| Finance or payment plan | "£6 per week" instead of £1,250 up front | Expensive or urgent purchases, especially if rivals offer none [v108, v259] |
| Speed guarantee | Installed within 72 hours; "finished on time or 20% back" | Competitors are slow or unreliable [v108, v126] |
| Price-certainty guarantee | "We never charge more than our quote" | Overcharging is the known fear in the trade [v126] |
| Tiers and bundles | Entry, core ("most popular"), bulk; "ultimate starter bundle" | Distinct buyer segments; hobby niches. Bundles also blunt price comparison [v058, v259, v328] |
| Cheap paid first step (tripwire) | £85 assessment at 80% off | Multi-session services: full price is too big a first step, free attracts poor leads [v077] |
| Lower-priced tier | £3,000 done-with-you (DWY) programme beside a £21,000 done-for-you service | Ads work but most of the market cannot afford the main offer [v110] |
| Discount, buy one get one free, gift, bonus | 30% off until a date | Many near-identical competitors; always with a deadline [v058, v128] |
| Included support or maintenance | Check-ups in the price | Buyers fear being abandoned after purchase [v259] |
| Free consultation or quote | Free consultation plus 70% off, 30 places a month | The baseline first step for services. About 90% of competitors offer it, so pair it with a discount, guarantee or scarcity [v041, v133] |

### Decision rules
- Discount when many competitors sell near-identical products. With few direct rivals, sell on effectiveness and let larger tiers imply the discount through bulk value. [v058]
- Front-end price: go free or very cheap and trivial to deliver, or premium with a high-touch sales process. Mid-priced front ends are crowded, buyers expect more than an automated process, and the margin cannot fund a long sale. [v033]
- Local businesses: the offer is the main lever, since few local competitors advertise and almost none has a real offer. In crowded national markets, over-the-top guarantees have become familiar and pull less. [v077, v126]
- Unknown brands must offer clearly more than established ones, and every offer has to beat the competing ads the prospect also sees. Competitors copy offers, so re-test. [v061, v085, v259]
- If the same product is cheaper on Amazon, the campaign will not work. Differentiate by brand, features or product. [v128, v133]
- Frame around time saved, effort avoided and frustration removed, not only money. "Easy, fast, hassle-free" wins hook tests most often. [v058, v133]
- Keep one offer but write it for specific avatars and use cases, each with matching page wording (claimed uplift about 40% in ROAS). Execution: see `creative.md`. [v025, v128]
- Look for offers in competitor reviews (5-star: what to promise; 1-star: what to guarantee against) and in adjacent industries (a finance plan or subscription nobody in the niche has). [v085, v256]
- Start with one offer, the best seller or most profitable. When adding one, reuse proven ad concepts with the new call to action, then check the original offer's leads and revenue for cannibalisation. [v042, v110]

### Case studies
| Business | Offer change | Result |
|---|---|---|
| UK boiler installer, no brand, cold traffic | £1,250 up front → £6 a week for 5 years, plus 72-hour guaranteed installation, both leading every ad | CPL £90 → £6.50. 1 in 8 leads bought: CAC about £52. 30x on nominal LTV £1,560, 24x on £1,250 adjusted for failed payments. Scaled to £10,000 a day [v108] |
| Physiotherapy chain in a new city; full price and free guides had failed | £85 assessment sold direct at 80% off (£17), month-end deadline, about 40 places from real capacity | £29 per assessment sale; 1 in 3 took a plan worth about £780. CAC = (£29 × 3) − (£17 × 3) = £36, about 22x. Both clinics full in 60 days [v077] |
| B2B service at £128k a month, flat | Added a £3,000 DWY tier beside the £21,000 service | Leads 45 → 300+ a month; close rate 22% against 14%; original offer's leads down only 9%; £386k a month by month five [v110] |
| Niche DIY ecommerce | Blanket discounts → three tiers by buyer segment, with a new page, demo-first creative and creators | Spend $26k → $43k a month, ROAS 4.07 → 4.7, profit after ad spend about $81k → $160k. Took six months [v058] |

Owners often resist losing money on a first step (the physiotherapy owner did). Answer with the CAC arithmetic. [v077]

## 5. Pricing and price testing

- Margin funds marketing. When an account converts well but makes no money, raise price, add upsells or build a more valuable back end. [v025, v108]
- Raise price by adding value. In price-sensitive markets a bare increase is risky; use bundles and upsells instead. [v137, v328, v596]
- Small advertisers should not compete on price. It removes the margin that pays for ads. Compete on specificity, speed, guarantee or proof. [v025, v128]
- Framing:
  - Instalments turn an unaffordable lump sum into a trivial weekly figure. [v108]
  - Show the full price with the discount ("£85, 80% off"), not only the low figure. [v077]
  - A "from £3,000" anchor or a stated job size ("40K+ install") removes a cost objection and repels bargain hunters. [v041, v050]
  - Show the price in the ad when it is lower than the product's premium look suggests. [v050]
- A service that cannot afford to give a free consultation is priced too low. [v519]
- Price testing ranks with the offer among the larger levers, above structure tweaks. There is no price-specific procedure; run it as an offer test: [v004]
  - Change one variable; give each price its own matching page. [v084, v085]
  - Show the variants to the whole audience, not to separate segments. [v124]
  - Judge on ROAS, which reflects order value, rather than cost per purchase. For lead gen judge on lead-to-customer rate, since two offers with equal CPL can differ 2x in customers. [v084, v128]
  - Recompute break-even at each price; the ceiling moves with AOV.
  - Before launch, a waiting-list form can ask what people would pay (section 10). [v136]
- Test mechanics, duration and sample size: see `testing-and-scaling.md`.

## 6. Urgency and scarcity, done honestly

Urgency is a time limit. Scarcity is a quantity limit (stock, places, client slots). They are separate levers; both make delay cost the buyer something, and both are widely under-used. Without a deadline people intend to buy later and forget. [v061, v128]

| Rule | Detail |
|---|---|
| Be specific | State the incentive and the end date ("30% off, ends 30 June"). "Limited time" or "flash sale" with no size or date is weak. Every promotion needs an end date [v128, v244] |
| Use real limits | Derive the number from capacity or stock: "about 40 discounted assessments", set from four clinicians who can each take one or two a day; "only taking 4 new clients this month". Nearly every service has capacity limits and every product business has stock. Subscription software has no natural scarcity [v050, v077] |
| Never fake it | If there is no real end date, do not claim one; use real place counts or a launch bonus. Give a true reason for a sale, because a reason lowers scepticism [v103, v244, v519] |
| Say it everywhere | Primary text, image or video, headline, and a banner at the top of the landing page with the offer and time left [v244] |
| Rotate | After the deadline, run a different promotion: change the mechanic (30% off, then buy two get one free, then a free gift) and the reason (season, business birthday, local event), monthly or every one to two weeks. Few prospects notice consecutive sales; repeating the same discount is what wears out [v077, v128, v398] |
| Launches | Launch-only bonuses (extra support, extra calls) create urgency without a discount [v110] |

Trade-offs:
- A dated discount in an ad lifts short-term sales but ends the ad's life with the promotion; an evergreen winner can run all year. Choose deliberately. [v050]
- Price-led selling converts warm audiences who already wanted the product. It does not persuade cold audiences and wears the warm pool out, so keep it as part of a mix. [v050]

Sale-event operations: see `testing-and-scaling.md` and `ecommerce.md`.

## 7. Funnel choice by price point

Default to one step: ad to a page where the person buys or enquires. Each added step is another place to fail, and Meta now sequences ads to people at different stages inside one ad set. When a direct campaign fails, the usual cause is weak brand, offer, creative or copy, not a missing step. [v061, v064, v095]

| Price or customer value | Funnel | Why |
|---|---|---|
| Price or AOV under about $100 | Direct, one step; no lead magnet or awareness stage | Extra steps cost more than the customer is worth; impulse purchases need no warming [v080, v095] |
| Service sold as a multi-session commitment | Cheap paid first step sold directly, then upsell the plan | Full price is too large a first commitment; free brings poor leads [v077] |
| Above $100, into the thousands | Direct to the purchase or to a low-risk first step (consultation, quote, trial, call). If that fails after offer and creative work, add a lead magnet or webinar step with email follow-up | The added touch points build trust for a larger ask [v095, v250, v504] |
| Customer worth $1,000+ where trust, expertise or timing decides the sale | Conversion campaign plus the omnipresent content campaign | Repeated exposure has to be paid for. See `local-and-high-ticket.md` [v054] |
| Price above about $5,000 | Do not ask cold traffic to buy. Generate a lead, then sell through calls, proposals and follow-up, supported by repeated proof | One-step selling is unlikely to work [v033, v095] |
| Around $50,000 and above | Lead step plus sustained warming | High-consideration purchase [v095] |

- At high prices the ad asks for the first step, not the purchase. A £50,000–100,000 design project is advertised as a free consultation, and leads at £100 stay very profitable. [v133, v519]
- A new advertiser with nothing working often has the wrong funnel for the price: a $20,000 service in a $40-product funnel, or an awareness, then traffic, then conversion chain. [v378]
- Click-to-WhatsApp can replace the page-then-call sequence for higher-ticket or question-heavy offers. Usage is low in the US; in the UK it suits high-ticket; in India and Brazil it suits anything. See `lead-generation.md`. [v033, v051]
- Do not switch funnels every month or two. Improve each element of a proven funnel in turn. [v349]
- Lead magnets, webinars and call funnels: see `lead-generation.md`. Matching format to the size of the ask: see `creative.md`.

## 8. Landing pages and ad-to-page match

A weak page can sink good ads, and Meta prices the post-click experience into delivery: poor pages mean higher CPMs and fewer results. [v140, v253]

- Send traffic to a dedicated page for the product or offer in the ad, with one clear action. Not the homepage, not a generic multi-product page. [v021, v058]
- Match the page to the ad: the same promise in the same words, the same product appearance, similar images, colours and headline. An ad promising "installation within 48 hours" lands on a page that repeats it. Four offers need four pages; duplicate and edit the copy. Quick bounces signal low quality to Meta. [v084, v256]
- Open the page with a short explainer video: desired outcome, how it works, who it is for, why it beats alternatives. Keep the buy button and navigation reachable; forcing a video before them is penalised. A short quiz that recommends an option helps undecided visitors. [v058, v140]
- Remove the header menu and other distractions, but keep footer links and a way out. Dead ends and exit pop-ups cause policy trouble. See `account-health-and-policy.md`. [v058, v112]
- Put proof and supporting detail on the page. No surprise costs; a shipping fee that first appears at checkout breaks conversion. [v025, v118]
- During a promotion, show a banner at the top with the offer and time left. [v244]
- Avoid what Meta counts as low quality: thin or copied content, newsletter or exit-intent pop-ups (cookie notices are fine), anything the ad did not promise. Fixing these lowered CPM first, then cost per result. [v140]
- As of late 2026, turn off the "Personalized destinations" enhancement at ad level when the funnel depends on a specific page; otherwise Meta may send clickers to another URL on the site. Acceptable for a store with only product pages. [v012]
- Check which page fires the conversion event. See `tracking-and-attribution.md`.

Post-click benchmarks (older figures, still used for diagnosis):
| Step | Normal | Problem | Source |
|---|---|---|---|
| Link clicks → landing page views | 20–25% loss | 50%+ loss: slow page or accidental clicks | [v118] |
| Ecommerce purchases ÷ link clicks | 2–5% | Under 2% | [v118, v389] |
| Lead magnet opt-in rate | 20–30%; 40%+ is strong | Under 20% | [v389, v409] |
| Service enquiry rate | Above 3–5%; 10%+ for an easy ask such as a free consultation | Far lower is expected for high-ticket | [v389] |
| Add to cart → purchase | About half in a healthy example | 10 carts per purchase: checkout, delivery fees or speed | [v262, v409] |

## 9. Is it the offer, the creative, the page or the business model?

First rule out setup faults: a conversion event firing on page load, a performance goal set to clicks, a tiny audience. Then read the pattern. [v025, v353]

| Pattern in live data | Problem | Fix |
|---|---|---|
| No conversions at all after a fair test | Offer (or product, price, demand), not targeting | Differentiate, add a guarantee, speed up delivery, review price, communicate value [v025] |
| Some conversions, with low hook rate and low link CTR | Creative: people want the offer but the ads do not win attention. The most common case | New, more varied ads. See `creative.md` [v025] |
| Some conversions, with high CTR | Page or post-click: too little proof or information, a mismatch, something off-putting | Section 8 [v025] |
| Good CTR and poor post-click rate, from a curiosity-led ad that does not present the product | The ad: clicks are low intent | Make the ad state the product and offer [v118] |
| Plenty of conversions, unprofitable | Business model | Raise price, add upsells and back-end value. A comparatively easy fix, since ad, offer and page work [v025] |
| Plenty of conversions, profitable | Nothing | Scale if stock and capacity allow [v025] |
| Profitable at low spend, worse whenever budget rises | Too little new creative, too little headroom under the ceiling, or both | More ads; raise customer value [v134] |
| Acceptable CPL, few customers | Follow-up, sales process or offer quality | Compare offers on lead-to-customer rate. See `lead-generation.md` [v084] |
| Decent ads, but the business needs a multiple rather than 20–25% | Offer line-up | New tier or new offer [v110] |

- A fair test before blaming the offer: at least a couple of weeks and spend equal to a meaningful share of allowable CAC. About $500–600 with no sale on a $40 product is a real signal. Where $1,000–2,000 CAC is acceptable on a $10,000 customer, spend that first. [v353]
- High CPM is not a diagnosis. Valuable audiences cost more ($50 in a major city, $90 for some business services). Check post-click quality if CPM is well above the account's own norm. [v062, v140]
- If sustained creative work changes nothing, reassess the product and its demand. The standard is better than the alternatives, not merely acceptable. [v062, v133]
- Hook rate and CTR thresholds and the full diagnostic chain: see `analysis-and-troubleshooting.md`.

## 10. Validating an offer or product before building it

- Check the market in the Ads Library: list 10–20 competitors, search by advertiser, note whether they advertise, how many ads they run and which have run for months. Sort by "Impressions: high to low" where available, since a long-running ad may have had no delivery. If rivals with a comparable offer, price and quality advertise steadily, the channel works for the category. Rule out advantages you cannot copy (celebrity backing, a much lower price). Method: see `creative.md`. [v031, v318, v464]
- Waiting-list test for something that does not exist yet: [v133, v136]
  1. Advertise it as though available now. Advertising a waiting list depresses response and makes a good idea look bad.
  2. On the page, say it is out of stock, at capacity or being redesigned, and offer a list with first access and about 10% off at launch.
  3. Pass mark: cost per sign-up at or below 25% of the allowable cost per purchase. A $120 product at a 3:1 target allows $40 per purchase, so sign-ups must cost $10 or less. A service needing $80 leads needs sign-ups at $20 or less.
  4. $3–4 against a $10 mark is a clear winner. $25–30 means the economics will not work on Meta.
  5. The mark is conservative: 35–40% of a list typically buys at launch.
  6. Use the form to ask what price people would pay, how much they need and what they would use it for.
- On a small budget the first goal is proof of concept, then break-even, then scale. Expect the early months to run near break-even. [v042, v340]
- Before scaling, confirm stock and delivery capacity. Holding spend steady beats scaling into a stock-out that forces campaigns off. [v080, v114]

## Outdated advice to ignore
| Old rule | Current rule | Why it changed |
|---|---|---|
| Target about 10x ROAS, or a cost per purchase of 10% of AOV | Compute break-even from AOV, margin and close rate; work to a target with headroom; judge the business on LTGP:CAC above 3:1 | 10x is rare, collapses at scale and ignores repeat revenue [v001, v128] |
| Base the affordable cost on the first transaction only | Use lifetime gross profit, while knowing whether the first transaction covers its cost | Repeat revenue holds the profit; competitors with higher customer value outbid you [v001, v137] |
| Fix weak results by shaving cost per result or adjusting targeting and settings | Fix the offer, then creative, and raise customer value | Targeting is largely automated; CAC has a floor, customer value does not [v061, v107, v133] |
| Warm people with awareness or traffic campaigns, retarget in layers, then ask for the sale | One-step direct offer by default; add steps only where price demands | Delivery sequences ads inside one ad set; each step adds cost and a failure point [v064, v095, v349] |
| Anything over about $100 needs a lead magnet or webinar first | Go direct to the purchase or a low-risk first step; add a magnet if that fails; warming becomes necessary above about $5,000 | Most current campaigns are one step; failures trace to offer and creative [v095, v504] |
| A free consultation or quote is a strong offer | It is the baseline; add a guarantee, real deadline, limited places or a discounted paid first step | About 90% of competitors offer the same [v133, v519] |
| The offer is the product plus a discount | Build it from differentiation, guarantee, scarcity or urgency, and proof; use tiers and bundles | Blanket discounts cut margin and do not differentiate [v058, v061] |
| Send ad traffic to the homepage, or one page for every ad | One matched page per offer | Congruence lifts conversion; Meta penalises poor post-click experience [v058, v084] |
| Deadlines and limited places look cheap; or use a vague, permanent "limited time" | Real, specific limits in every promotion, rotated | They reliably lift response; vague claims are weak and false ones dishonest [v077, v244] |
| Judge a subscription business on in-platform ROAS | Judge on back-end revenue per customer | Meta does not see later payments [v062, v137] |

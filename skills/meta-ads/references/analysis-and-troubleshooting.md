# Analysis and troubleshooting

How to read live Meta ads numbers, decide whether something is working, locate the constraint and choose the fix. Read this whenever account data is on the table: an audit, a routine review, a "why did results drop" question, or a decision to pause, keep or scale.

## Contents
- The deciding metric and the supporting ones
- Metric formulas and benchmarks
- Check the data before trusting it
- How much data is enough
- The order to walk the funnel
- Reading ads inside one ad set
- Breakdowns
- Pattern → likely cause → check → action
- Account audit: maturity levels and checklist
- Review cadence and alerts
- Meta's in-product advice
- Outdated advice to ignore

## The deciding metric and the supporting ones

Pick one primary metric per account and make keep, pause and scale decisions on it. Everything else is diagnostic. [v107, v118]

| Business | Primary metric | Why |
|---|---|---|
| Sells online and passes accurate purchase values | ROAS (return on ad spend) | It reflects order value, which cost per purchase hides. [v128] |
| Leads, bookings, registrations, or any case where revenue is not known at the conversion | Cost per result for the deepest funnel event that is tracked accurately | Conversions look equal at the point of conversion, so cost is the fair comparison. [v065, v118] |
| Lead generation with a qualified-lead event | Cost per qualified lead, not cost per lead | Some ads produce many cheap, poor leads and look best on raw cost per lead. [v008] |

Rules attached to the primary metric:

- Judge it against the account's own break-even, not a generic "good" number. A cost per purchase, CPM (cost per 1,000 impressions) or CTR (click-through rate) cannot be called good or bad until you know average order value (AOV), gross margin, repeat rate and, for leads, the close rate. Ask for these first. Formulas are in the table below; the full treatment is in `offers-and-economics.md`. [v001]
- Secondary metrics (CPM, hook rate, CTR, cost per click, frequency, landing page view rate, conversion rate) explain why the primary metric is where it is and tell you what to make next. They do not decide. An ad with a worse CTR and a better ROAS wins; an ad set with a higher CPM and a lower cost per conversion wins. Never turn off a good-ROAS ad because its CTR or watch time is low. [v107, v111, v133]
- Proxy metrics cannot be used to call a test early. A higher-CTR ad often has a worse ROAS, and the highest hook rate in an ad set can belong to the worst cost per purchase. [v005, v065, v118]
- Use the primary metric to compare campaigns, offers, countries, test cells and time periods. Inside one consolidated ad set, read spend allocation as well (see "Reading ads inside one ad set"). [v043, v065]
- In-platform ROAS counts only what happens inside the attribution window, usually the first transaction. For subscriptions and repeat-purchase businesses it understates the return (example: about 4x reported against roughly 20x once retention is counted). Judge those accounts on lifetime value and back-end revenue. [v062, v118]
- ROAS falls as spend rises, at every budget level. When deciding how far to scale, judge absolute profit: $100k a month at 5x returns far more than $10k a month at 10x. Still choose between individual ads on ROAS. [v121, v128]
- If a large share of purchases comes from existing customers, the blended ROAS overstates new-customer acquisition. Check the audience segment breakdown before praising a number. [v006, v037]

## Metric formulas and benchmarks

Compute rates from raw counts. Use link clicks everywhere, never "Clicks (all)", which counts unmuting, "See more" taps and carousel swipes (one account showed 3.87% all-click CTR against 0.36% link CTR). Hook rate has historically been a custom metric; as of October 2026 hook rate, hold rate and ThruPlay appear as native video metrics in Meta's creative tools. If the data source does not return hook rate, compute it. [v007, v118, v389]

| Metric | Formula in plain terms | Benchmark | How to read it |
|---|---|---|---|
| ROAS | purchase conversion value ÷ amount spent | No universal target. Break-even ROAS = 1 ÷ gross margin (40% margin → 2.5x). 1.5x can be excellent with no cost of goods; 3–5x is a normal good result. | Compare with break-even and with the same account last month. Expect it to fall with scale. [v042, v114] |
| Cost per result | amount spent ÷ results of the optimised event | Break-even cost per purchase = AOV × gross margin. Break-even cost per lead = first-sale value × gross margin × lead-to-customer rate. | Scale only when there is clear headroom under break-even, because cost rises with spend. [v001] |
| LTGP:CAC | lifetime gross profit per customer ÷ (ad spend ÷ new customers) | Above 3:1 is the bar for scaling | The real health metric; not the same as ROAS. See `offers-and-economics.md`. [v137] |
| CPM | amount spent ÷ impressions × 1,000 | None. $50 in New York, $90 for a B2B service and $100 in California in a lucrative niche are all normal. | Not a KPI and largely uncontrollable. Compare only with the same account's history. [v004, v062] |
| Frequency | impressions ÷ reach | Cold or mixed audience: fatigue often starts at 2–2.5; keep under about 2.5. Near 4 or above: act at once. Warm-only: up to about 6–8 for most businesses; very engaged content audiences tolerate 12+. | An average that hides a spread: at 2.5, many people are at 1 and the best prospects at 6–7. Meta's figure: after about 4 exposures conversions can fall about 45%. [v115, v118] |
| Hook rate | 3-second video plays ÷ impressions | Under 5% poor; 5–10% okay; over 10% good; the best ads reach 25–35%, usually with a recognised creator. | Video against video only (images and carousels show near zero). Varies by industry and runs low in B2B, so also compare with the account average. [v038, v114, v118] |
| Video average play time | native metric | No fixed number | Judge against video length; meaningless when all videos are very short. Low watch time with a good ROAS is fine. [v111, v118] |
| Link CTR | link clicks ÷ impressions | Under 0.5% poor; about 0.9% okay; over 1% decent; 1.5% very good; 2%+ excellent | Industry-dependent. Images normally out-click videos without out-converting them. [v118, v262] |
| CPC (link) | amount spent ÷ link clicks | No current benchmark in the source. 2020 reference points: about $0.50 in health and fitness, about $5 in insurance. | Read with link CTR; it is the same signal priced by CPM. [v389] |
| Landing page view rate | landing page views ÷ link clicks | 75–80% is normal (a 20–25% loss); losing 50% or more is a fault | Low rate = slow page or accidental clicks. [v118] |
| Click-to-purchase rate (ecommerce) | purchases ÷ link clicks | 2–5% normal; under 2% poor; 0.5–0.7% clearly broken | Varies widely by price. 0.5% against 2.5% is five times the purchases for the same spend. [v118, v389] |
| Opt-in rate (free lead magnet page) | leads ÷ link clicks | At least 20%; 20–30% average; aim for about 40%; 50% is excellent (2020 figures) | Below 20% points at the page or the magnet. [v389, v409] |
| Enquiry rate (service page) | leads ÷ link clicks | Above 3–5%; 10%+ for an easy ask such as a free consultation; much lower for high-ticket (2020 figures) | [v389] |
| Add-to-cart to purchase | adds to cart ÷ purchases | 10 adds per purchase is too many | Points at checkout, delivery fees or delivery times. [v409] |
| Results per ad set per week | count of the optimised event, last 7 days | Meta's stated need is 50; many ad sets leave learning at 20–40 | The reason to consolidate. [v034] |
| Share of spend in learning | spend in learning-phase ad sets ÷ total spend, last 7 days | 39% was called too high, in an account that was testing heavily | High = too many edits or too many ad sets. Shown in "Account overview". [v122] |

## Check the data before trusting it

- The most recent 48–72 hours are partly modelled and can be over- or under-stated; yesterday's figure may simply be wrong. Keep decisions outside that window. [v133]
- Conversions keep arriving for up to a week or more after the spend that caused them, because attribution windows are still open. Recent days tend to look worse than they will finish, and switching things off early understates them. [v146]
- Daily results swing with weather, sport, news and paydays, and day-to-day consistency is not achievable. One expensive day is noise. A cost that stays high and keeps climbing for a full week or more is a signal. A 20% rise in cost per conversion is not an emergency: diagnose calmly, do not rebuild. [v015, v107, v133]
- Compare this month with last month. For a seasonal business compare with the same month last year, not with a different season. New ad accounts are more volatile. [v107, v133]
- Attribution changed in spring 2026: click-through now needs a link click, and likes, comments, "See more" taps and video plays of 5 seconds or more moved to a 1-day "engage-through" category. Reported conversions fell most for video-heavy, long-sales-cycle accounts. Do not compare periods either side of the change and conclude performance fell; check store or CRM numbers. See `tracking-and-attribution.md`. [v032]
- An ad set on incremental attribution, or on "Acquire new customers", will report worse ROAS than it did before by design. Do not compare it with standard-attribution figures. [v006, v072]
- Conversion value sometimes stops feeding into Ads Manager, which blanks ROAS. Treat a sudden blank or zero as a reporting fault first. [v118]
- Confirm the conversion event fires only on the order-confirmation or thank-you page. A Purchase or Lead event that fires on landing-page load makes every click look like a conversion and trains Meta to chase raw traffic. A cost per result that looks impossibly cheap is the tell. [v025]
- Meta's numbers and back-end numbers never match exactly. Two ads are wrong by a similar degree, so relative comparisons still hold; judge the business on overall return across channels. [v133]

## How much data is enough

Decide on conversion volume, not elapsed days. Ten conversions in 20 minutes say as much about an ad as ten conversions in three months. "Seven days" is only a rough average. [v004, v128]

| Volume | What you can conclude |
|---|---|
| 2–3 conversions on an ad | Nothing. Not a winner and not a loser; extend or rerun. [v005, v118] |
| About 3–6 conversions a week in the ad set | A new ad or test needs about a month. Identifying the best of several ads can take months. [v004, v025, v042] |
| 1–2 conversions a day | A five-ad test takes a month or more. Test one ad at a time. [v005] |
| Dozens to hundreds a week | A clear answer in about 3–14 days. [v005] |
| About 200 purchases a day | Same-day decisions. [v025] |
| Thousands a day | Hours. An ad with 45 purchases is already a fair sample. [v080] |

- For "A beats B" use a statistical significance calculator: no significance means too early; about 90% confidence means act. Ten conversions at $11 against two at $18 is not significant (one more conversion for the second ad brings it to about $12). Fifteen conversions against three cannot be decided by eye either. [v128, v133]
- The window for evaluating recent performance follows the same logic: last 3 days with dozens to hundreds of conversions in that window, last 7 days as the middle default, last 14 or 28 days when a conversion arrives every couple of days. Never use the lifetime or "Maximum" range, because old good results hide a recent decline. [v026]
- Small budgets may need about three months to show whether the approach works. Long sales cycles (kitchens, remodelling) need 3–6 months before leads from month one turn into revenue. [v014, v385]
- The learning phase lasts about 24–48 hours after a launch or significant edit and results are most volatile in it. Do not judge inside it. Edit an ad set at most once every 7 days (7–14 on small budgets) and batch the changes. See `campaign-setup.md`. [v034, v042]

## The order to walk the funnel

1. Get the targets: break-even cost per result or ROAS, and the maximum the business can pay for a customer. Without them stop and ask. [v001]
2. Read the primary metric at account level, then campaign, then ad set, over a window with enough conversions and outside the last 72 hours.
3. Classify the situation with the five-way map below. It tells you which part of the system to look at before any metric detail. [v025]
4. If the problem is in the ads or the page, walk the stage table from top to bottom and stop at the first stage that is clearly weak.
5. Check frequency and the trend over time for fatigue or decay.
6. Run the breakdowns (audience segments first).
7. Read individual ads last, using spend allocation and the hook-and-body patterns.

| What the account shows | The problem is | Fix lives in |
|---|---|---|
| No conversions at all | The offer. Meta is good enough at finding people that this is almost never targeting. | `offers-and-economics.md` |
| Some conversions, fewer than wanted, with low hook rate and low CTR | The creative. This is the most common case. | `creative.md` |
| Some conversions with a high CTR | The landing page or post-click experience | `offers-and-economics.md` |
| Plenty of conversions, not profitable | The business model: price, upsells, back-end value | `offers-and-economics.md` |
| Plenty of conversions, profitable | Nothing. Scale if the business can deliver. | `testing-and-scaling.md` |

| Stage | Metric | A weak number points to |
|---|---|---|
| Auction | CPM against the account's own history | A contested or seasonal auction (not a fault), or low ad quality and a poor post-click experience |
| Attention | Hook rate (video) | The first 3 seconds |
| Interest | Link CTR, cost per link click | Creative, message, offer strength, proof |
| Arrival | Landing page views ÷ link clicks | Page speed; accidental clicks from low-quality placements |
| Conversion | Conversions ÷ link clicks | Landing page, ad-to-page match, surprise costs, weak offer |
| Checkout | Adds to cart against purchases | Shipping fees and times, checkout bugs, optimising for add to cart |
| Back end | Lead-to-customer rate, repeat purchase | Follow-up speed, sales process, lead quality, lifetime value |
| Repetition | Frequency over time | Fatigue |

Run this chain on campaigns that work too; it shows where the next gain is. Before blaming a stage, rule out the few setup mistakes that still sink campaigns: an audience made far too small by hard constraints, a performance goal of link clicks, landing page views, reach or impressions inside a Sales or Leads campaign, and delivery concentrated on Audience Network. Beyond those, structure and targeting tweaks give little; the order of leverage is offer, then creative, then headline, format, primary text, call-to-action button, description. [v107, v133, v389]

## Reading ads inside one ad set

Since the Andromeda ad retrieval system (in most accounts by late 2025), Meta picks the ad per person and sequences ads inside one ad set. That changes how ad-level numbers are read. [v055, v064]

- After the first few days Meta concentrates most budget on 1–3 ads, even with 20 live. That is normal. Where Meta puts the money is itself evidence of what works. [v048, v064]
- An ad with a lot of spend and a poor cost per result or ROAS is often the top-of-funnel ad that introduces people, while low-spend, high-ROAS ads close them. Pausing it usually makes the others worse. This is the usual explanation for "I paused four ads to back the winner and the winner collapsed". [v043, v065]
- Rule: do not pause an ad inside an ad set because its own ROAS is lower. Pause ads Meta has stopped spending on, and add new ads beside the ones getting spend. If a similar new ad takes the budget from an old high-spend ad, Meta has judged the new one better and the old one can go. Replace like for like by funnel stage so the ad set still covers awareness, evidence and call to action. [v064, v066]
- Do not whittle an ad set down to one "best" ad. Lower-ROAS ads that still get spend are winning conversions from other slices of the audience. [v005]
- Never turn off the best ad to force spend onto others; results usually tank. [v048]
- Pair hook rate with the primary metric to brief new video (needs a real sample; the source examples had 33 and 64 conversions): [v038, v118]
  - High hook rate, poor cost per result: good hook, weak body. Reuse the hook and make less of that body.
  - Low hook rate, strong cost per result: weak hook, excellent body. Splice a top hook onto this body and run it as a new ad; it is often the best performer in the ad set.
  - High hook rate, play time clearly below other videos: the hook does not connect to what follows. Keep it and rework the body.
  - With the same body and different hooks, the higher hook rate nearly always wins. Across different bodies the link is looser, so check the primary metric.
- A static with a low CTR and a good ROAS converts once clicked but is not stopping the scroll: keep it and test a version with stronger colour or clearer product focus. A video with a strong CTR and a weak ROAS has a good hook and a weak body. [v024]
- Meta's quality, engagement and conversion ranking labels are weak evidence. Profitable ads can be "below average". Treat a below-average label on a costly ad as a hint to make fewer like it, nothing more. [v024, v409]

## Breakdowns

Ignore any breakdown row with one or two results. In a Sales or Leads campaign optimised for a real conversion, Meta has already moved budget toward what converts cheaply, so a breakdown is mostly insight for messaging and creative. Act on it only when it shows a real problem or reveals something Meta cannot see. [v010, v047]

| Breakdown | What to look for | What to do |
|---|---|---|
| Audience segments (new audience, engaged audience, existing customers) | The share of spend and results going to people who already know or have bought from the business. Examples: about 40% of spend and over half of purchases in a "cold" ad set; 59 of 93 purchases from existing customers. "Unknown" means segments are not defined. | Define segments first ("Advertising settings" → "Audience segments": engaged audience and existing customers). A warm share is normal and grows with the customer base. Act only if it is large and the goal is new customers; see the pattern table. [v006, v037, v043] |
| Placement | Where results come from. Feeds, Stories and Reels on Facebook and Instagram normally carry the account. In traffic, engagement or awareness campaigns, look for spend pooled in Audience Network. | Real conversion campaign: leave it alone. Non-conversion campaign: move to Sales or Leads if tracking allows; otherwise apply a value rule such as "Audience Network −90%" per ad set, or use account-level "Placement controls". Manual placement selection at ad set level is being removed (from September 2026). See `campaign-setup.md`. [v010, v047] |
| Platform | Facebook against Instagram results on similar spend | Insight into where the offer lands, not an instruction to exclude. If one platform or Stories shows clearly poor ROAS, down-bid it with a value rule and re-check. [v010, v118] |
| Age and gender | Cost per result by band, and whether spend is drifting to a group the business does not want | Meta already shifts budget to the cheap bands. To win a dearer band, make creative that features and speaks to it. Call out one group in the copy only when it is about 93% of results; 83% is not enough. Use value rules when a group is worth more or less in ways Meta cannot see (close rate, repeat purchase). Gender can no longer be a hard limit (November 2026); a −90% value rule is the workaround, for real problems only. See `targeting.md`. [v002, v024, v118] |
| Country or region | Cost per result and ROAS by market; leads from outside the service area | Location is the one targeting input that is still a hard control, so it is worth splitting: separate campaigns per country to compare or control markets, or, for the same product and offer everywhere, one campaign with an ad set per country and a campaign budget so Meta moves money between markets (ROAS 2.8x → 3.7x in one case). Out-of-area leads: fix the location control and add a location question to the form. [v011, v043, v094] |
| Time (day, week, month) | Trend shape: slow fade, fast collapse or sudden step; seasonality; weak days | Do not react to single days. Lean into seasonal peaks and cut back off-season instead of evening out spend. For lead generation, when leads arrive matters to the business but not to Meta: consider a schedule (needs a lifetime budget) so leads land when they can be called. See `campaign-setup.md`. [v052, v107] |
| Attribution settings | How results split between click-through, engage-through and view-through | Use it to explain gaps with back-end numbers and shifts after the 2026 change. See `tracking-and-attribution.md`. [v032] |
| Website URL | Clicks and conversions per site link | If one destination converts much better, make it the main destination. [v125] |

## Pattern → likely cause → check → action

| Pattern | Likely cause | Check | Action |
|---|---|---|---|
| No conversions at all | The offer. Second: tracking or optimisation set wrongly. | Is the event firing on the right page? Is the performance goal the real conversion, not link clicks or landing page views? Is the audience tiny from hard constraints? Are there clicks? | Rework the offer (differentiate, reduce risk with a guarantee, review price, add value). Later tests cannot be judged until conversions flow. See `offers-and-economics.md`. [v025, v039] |
| High CPM | Usually a valuable, contested audience or a seasonal auction (Q4 demand). Sometimes low ad quality: Meta charges more for a poor post-click experience and for ads people hide. | Is cost per result fine? Then stop. Otherwise compare with the account's own history, and review the page for copied or thin content, pop-ups, a forced video before the buy button, and promises the page does not keep. Check the ads for clickbait, hyperbole and engagement bait. | Do not chase a lower CPM; the reliable way to get one is to reach less valuable people. Clean up the page and ads if quality is the issue (CPM drops first, then cost per result). Otherwise improve the economics. [v004, v062, v140] |
| Low hook rate (under 5%, or well under the account's video average) | The first 3 seconds do not stop the right person | Compare video with video. Which ads have the highest hook rates, and what do they open with? | Record new hooks for the existing body, modelled on the top hooks; open with the outcome or the problem, not an introduction; use a creator the audience recognises. See `creative.md`. [v038, v058, v104] |
| Low link CTR (under 0.5%) with a decent hook rate | The ad gets attention but does not persuade: the offer is unattractive, or there is too little proof, especially for cold audiences. On statics, a weak visual. | Hook rate and play time acceptable? Is the offer stated clearly? Any proof in the ad? | Strengthen the offer; add testimonials, results and reviews; for statics test stronger colour and clearer product focus. If the primary metric is good, leave the ad alone. [v024, v118] |
| Clicks but no conversions (good CTR, poor conversion rate) | The landing page: mismatch with the ad, surprise costs, missing proof. Or a curiosity-led ad that does not present the product, so the clicks are low intent. Or a campaign optimised for clicks. | Conversion rate against the benchmarks. Does the page repeat the ad's product, look and promise? Is the performance goal a conversion? Is traffic going to a homepage? | Fix ad-to-page match, show full costs early, add reviews; send traffic to a dedicated page with one action. If the ad is bait, fix the ad before blaming the page. See `offers-and-economics.md`. [v021, v025, v118] |
| Link clicks far above landing page views (50% or more lost) | Slow page, or accidental clicks from low-quality placements | Page load speed. Placement breakdown: is spend on Audience Network? Is this a traffic-type campaign? | Speed up the page. Move to a Sales or Leads objective with a conversion goal; down-bid or remove Audience Network. [v010, v118] |
| Results fading slowly over weeks or months | Ad fatigue: frequency rising while results fall. If fresh ads fade too: offer fatigue, or the product is losing to competitors on reviews. | Frequency at campaign level, then ad level. Are new ads being added regularly? With fatigue, some new ads match or beat old ones; if old and new all trend down together, it is not fatigue. Read the product's reviews against competitors'. | Fatigue: add creative that looks clearly different (format, style, person, pace). Offer fatigue: change the offer (discount structure, guarantee, different product). Reviews: fix the product or lead with a better-reviewed one. [v069, v115, v121] |
| Results collapsing fast after launch (days to two weeks) | The ads only convert people who were about to buy. Meta serves those first, then moves outward to less keen people. | How long did it last? A few days: only hot audiences convert. One to two weeks: only people already comparing products. Check the audience segment breakdown for a heavy early warm share. | Make ads that work on less aware people: lead with the problem, then the solution, then the product. Improve the offer. Run them to the whole audience; do not segment by awareness. Not a targeting or settings problem. [v124, v128] |
| Sudden drop with no change made | Often noise or a reporting artefact; sometimes delivery has become stuck | Is the drop inside the last 72 hours? Was an ad disapproved, pushing spend to weaker ads? Did conversion value stop reporting? Does the back end show the same drop? Is frequency high? | If it is real and frequency is not high: duplicate the campaign or ad set, run the copy and pause the original, which restarts learning (one account went 5x → 2x → 5x). Never run both together. If that fails, check fatigue, then seasonality, then a competitor's new offer. [v100, v121, v133] |
| Not spending the budget | A cost per result goal or bid set below what results really cost; an audience too small from stacked hard constraints; purchaser audiences excluded in the audience controls; duplicate ad sets overlapping in the auction; at very large budgets, too little creative | Bid strategy and any cost goal. Estimated audience size. Exclusions. Identical campaigns running in parallel. | Raise or remove the cost goal (a realistic goal still spends less by design). Remove hard constraints. Use the customer lifecycle option instead of exclusions (one test fell from $200 to $50 a day with exclusions). Consolidate duplicates. At big budgets add new creative or campaigns. [v006, v121, v139] |
| Learning limited | Too few results per ad set per week (Meta states 50; 20–40 often suffices), usually from splitting budget over many ad sets or from constant edits | Results per ad set in the last 7 days. Number of ad sets. Edit history. Is the campaign profitable anyway? | In order: improve results at the same budget; consolidate campaigns and ad sets; stop editing more than once a week (ad sets have left learning limited just by being left alone); only if the real event cannot reach roughly 20–25 a week, optimise for the next event up the funnel and compare over a month. Do not raise budget on an unprofitable campaign to escape it; exiting is worth perhaps 10–20%, not a rescue. See `campaign-setup.md`. [v013, v034] |
| Frequency climbing | Spend is high for the audience size, the ads are few or look alike, or budget was scaled without adding creative | Frequency by campaign and by ad. Number of distinct ads. Reach against audience size (2022 heuristic: 80,000 reached of 4 million at frequency 2.09 means the ads are not engaging; 80,000 of 350,000 is fine). | Add visually distinct ads so people see different ads, not one ad repeatedly; scale creative with budget. High total frequency across varied creative is acceptable for big-decision offers; repeats of the same ad are the problem. A paused, fatigued ad can return after about 6 months. [v115, v122, v262] |
| New ads getting no spend | Existing winners keep the budget; or the new ad is a near-duplicate and Meta enters only one of them in the auction | Is the new ad clearly different in format, look or opening? How many conversions does the ad set get per week? | Make it genuinely different. Force delivery with "Push delivery to this ad" (ad level; default 20% of daily budget for 7 days; in about half of accounts in October 2026), or the creative testing tool (2–7 ads; change the comparison metric to cost per lead or purchase). A separate testing campaign only once volume is clearly past 100 conversions a week. See `testing-and-scaling.md`. [v005, v044, v048] |
| Poor lead quality | Meta optimises literally for the cheapest form fill; the form is too easy; follow-up is slow | Cost per qualified lead by ad. Form type. Time from lead to first call. Out-of-area or fake details? | Make only qualified leads count (conditional logic on instant forms; a separate thank-you page event on websites); form type "Higher intent" with SMS one-time passcode; pass lead values and optimise for value; call within 5 minutes. Some bad leads always remain. See `lead-generation.md`. [v008, v011, v133] |
| Too much spend on existing customers | Meta retargets inside every campaign because existing customers convert cheapest; common for established brands and one-time-purchase products | Audience segments breakdown: share of spend and purchases from existing customers | Leave it if the business values repeat sales. Otherwise set customer lifecycle to "Acquire new customers" at ad set level (do not also exclude the engaged audience), or switch the ad set to incremental attribution. Matching is roughly 50% accurate and reported ROAS will get worse; that is the trade for incremental growth. See `targeting.md`. [v006, v072] |
| Good ROAS that falls when scaled | Normal: each budget step reaches less responsive people. A sharp, immediate fall even at low spend means the ads only convert warm and hyper-responsive buyers. A collapse of 90% or more straight after a budget rise is a platform bug seen in some accounts (August 2026). | Headroom between current cost per result and the maximum affordable. Size and pace of the increases. How many new ads are produced each month. Did results drop to near zero? | Step up, and hold at the last level that met target; that is the current ceiling. Raise the ceiling with better ads, more creative volume, a better offer or higher customer value, then step again. For the bug: duplicate at the higher budget and turn the original off. See `testing-and-scaling.md`. [v016, v026, v134] |
| One ad has most of the spend and a poor ROAS | It is probably the top-of-funnel ad | Do the other ads in the ad set show strong ROAS on low spend? | Leave it on. Add new ads of the same type and let Meta choose. [v043, v064] |
| Plenty of conversions, still unprofitable | Unit economics, not ads | Break-even against actual cost per result; AOV, margin, repeat rate, close rate | Raise price, add upsells or a recurring offer, improve follow-up. Cost per result has a floor set by competition; customer value does not. See `offers-and-economics.md`. [v025, v133] |
| Reported conversions fell in 2026 with no change in the back end | The attribution change (link clicks only for click-through) | Attribution settings breakdown; store or CRM totals | Keep the widest default windows; judge on back-end data. See `tracking-and-attribution.md`. [v032] |
| Many campaigns, declining results, nothing clearly working | Budget and data spread too thin for Meta or the advertiser to learn | Count campaigns and ad sets; conversions per ad set per week | Find the best offer, products and ads and turn most of the rest off. Full reset: one campaign, one ad set, Advantage+ audience, best offer, best past ads, untouched for a week. [v080, v107, v121] |

## Account audit: maturity levels and checklist

### Five maturity levels

Place the account on this scale from its live ads and landing pages, then recommend the step to the next level. Higher levels are mainly about creative range and how well the offer and page match each ad. [v021]

| Level | What the account looks like | Step up (what the next level has) |
|---|---|---|
| 1 | Ads repurposed from TV or billboards, corporate statics, no call to action, hashtags in the ads | Ads made for the platform with one clear offer and call to action |
| 2 | Decent ads, broken after the click: a generic multi-product page, or a product that looks different from the ad | A dedicated landing page per ad or product, congruent with the ad, with one action |
| 3 | One creative style repeated, a vague call to action, one expensive hero video with statics as an afterthought | A range of formats and styles; a specific call to action |
| 4 | 70–80 active ads mixing UGC (user-generated content), high production, creator partnerships and review statics, all made for the platform, but one offer and one landing page for everyone | The offer reframed per pain point and customer type; pages matched to ads |
| 5 | 300+ active ads in a very wide range of styles; the same offer reframed for each avatar and pain point; demographic call-outs; landing pages that match each ad's framing | Keep the cadence |

### Checklist

Work top to bottom; earlier items make later ones unreadable if they are wrong.

1. **Economics.** Break-even cost per result or ROAS is known, and LTGP:CAC is above 3:1. There is headroom between current cost and the maximum affordable. [v001, v137]
2. **Tracking.** Pixel and Conversions API both send events; conversion events fire only on confirmation pages; purchase values are passed. Recurring revenue that Meta cannot see is accounted for. See `tracking-and-attribution.md`. [v025, v062]
3. **Optimisation.** Sales or Leads objective. The performance goal is the real conversion, never landing page views, link clicks, reach or impressions. Stores with varying order values use "Maximize value of conversions". Lead accounts count only qualified leads. Attribution windows are left at the widest defaults. [v011, v032, v045]
4. **Structure.** Few campaigns. Splits exist only for different product ranges, locations, offers that only warm people may see, the omnipresent content strategy, or testing at sufficient volume. No identical duplicates running side by side. No traffic or awareness campaigns "supporting" sales. See `campaign-setup.md`. [v026, v043, v080]
5. **Volume and stability.** Results per ad set per week against the 50 guide; share of spend in learning; edits no more often than weekly. [v034, v122]
6. **Targeting.** Location control matches where the business operates. No stacked hard constraints. Audience segments are defined, customer and email lists uploaded, website purchaser audiences extended to 730 days. [v006, v070]
7. **Segment mix.** Share of spend and results on existing customers, read against the growth goal. [v037]
8. **Creative.** Number of live ads (the aim is 20+ good, distinct ads per ad set; four very different ads plus regular additions is an acceptable start). Mix of formats (static, video, carousel) and styles (UGC, founder, demonstration, testimonial, creator partnership). Coverage of funnel stages. Rate of new creative. Whether any partnership ads exist, since they are often the best ad in an account. [v013, v043, v044]
9. **Fatigue.** Frequency by campaign and ad against the benchmarks, with the trend in the primary metric. [v115]
10. **Post-click.** Dedicated page per offer, congruent with the ad, no surprise costs, proof present. "Personalized destinations" is off where a planned funnel matters, because it sends clickers to other URLs and muddies page analysis. [v012, v021]
11. **Testing.** Share of spend on tests (10–20% when campaigns are profitable, up to 50%, 100% when nothing works). Tests are big swings (offer, angle, style, hook), not button colours. A written test queue at large budgets. [v005, v039, v121]
12. **Automation.** Automated rules use a recent time range (not "Maximum") and do not overlap. "Automatic adjustments" is off. [v052, v122]
13. **Meta's recommendations.** Opportunity score and open items, filtered as described below. [v122]
14. **Outside the account.** Reviews against competitors, speed of lead follow-up, stock and delivery capacity. Do not recommend scaling into a stock or capacity limit. [v069, v114, v133]

Common findings: too many campaigns with budget spread thin (consolidating is often the fastest early win); nearly all ads in one format; at large accounts, much of the spend on underperformers that should simply be switched off. Rank recommendations by leverage: offer, creative and customer value first, settings last. [v080, v107, v121]

## Review cadence and alerts

| Budget | How often to look | How often to change |
|---|---|---|
| Small (under about $3,000 a month) | An hour or two a month in the account is enough; 30–45 minutes a day is over-managing | At most every 7–14 days, in batches; about one meaningful test a month |
| Large ($100,000+ a month) | Several times a day; things break faster and a disapproved ad can redirect a lot of spend | Move budget to winners quickly, even within a day, when the data is conclusive |

Between those, scale the cadence to conversion volume: the more conversions per day, the shorter the review window can be. [v014, v042, v121]

- A useful daily summary for an agent with API access: spend, impressions, CPM, ROAS, cost per result, link CTR, conversion volume, budget pacing and audience segment performance, plus a short list of issues. Alert on a ROAS drop of more than 20% or a cost per result above a set ceiling. An alert means investigate; because recent data is unreliable and a 20% move is often temporary, it does not mean act the same day unless volume is high. See `mcp-playbooks.md`. [v017, v133]
- Monthly: compare with last month and, for seasonal businesses, the same month last year. Expect Q4 CPMs to rise with advertiser demand (about 20% higher year on year in one Q4), and January to be cheaper. [v080, v107, v133]
- Between changes, spend the time on creative and offline analysis (for example hook rate against ROAS, then recombine), not on more edits. [v042]

## Meta's in-product advice

Meta's recommendations are mostly sound because Meta earns more when advertisers succeed, but they are tuned to the average advertiser and cannot see the business. Follow them by default, override them when you can name the reason, and do not override them on the strength of old habits. [v043, v133]

- **Opportunity score** (0–100; "Account overview", and the "Actions" column in the tables). It measures how closely the setup matches Meta's best practice, not results; a perfectly scored campaign for an unwanted product still fails. Moving from about 60 into the 90s probably helps, and it is most useful when results are below target. 100 is not required if each deviation is deliberate. Meta reports a 12% median fall in cost per result for advertisers who applied its recommendations. Use the predicted gain to prioritise: 27–45% is worth acting on; a small gain on a working ad can wait. [v024, v097, v122]
- **Campaign score** is the same idea for one campaign at setup. It drops when hard limits are added. If results are poor and the score is low, fixing the score is a sensible first move. See `campaign-setup.md`. [v089]
- **"Automatic adjustments"** lets Meta apply its recommendations itself. Leave it off: not every recommendation should be taken, and the fixes that matter (new creative, tracking) are ones Meta cannot do. [v122]
- **AI business assistant** (in Ads Manager for most accounts as of 2026). Good for a quick read of a campaign, industry benchmark comparisons, creative ideas and account issues, where it is the first port of call (Meta cites a roughly 20% better resolution rate for common issues). Quality is mixed: it has recommended settings that were already on, and it favours low-impact changes. Filter everything through fundamentals. See `account-health-and-policy.md`. [v007, v024]
- **Budget prompts.** Be most sceptical of any advice to spend more. Raise budget when results are already good and the business can handle the volume. Do not raise it to reach 50 conversions a week on a campaign that is unprofitable or unproven; get it profitable small, then scale. Business limits (stock, capacity) outrank the algorithm. [v034, v122, v133]
- **Ads Creative Studio** shows why creatives miss editable "minimum performance thresholds" and compares them with industry top performers. Use it as an idea source for variations of winners. [v007]

| Recommendation | Verdict |
|---|---|
| Set up the Conversions API | Do it; it applies to every campaign optimising for an off-Meta action. [v122] |
| Creative fatigue flagged on an ad | Verify with frequency and how long it has run; if confirmed, pause it and add new creative. [v122] |
| Create more ads when only one or two are live | Do it. [v122] |
| Combine ad sets | Right for direct-offer campaigns; ignore for the omnipresent content strategy, which needs many ad sets. [v122] |
| Switch to "Maximize value of conversions" | Right for new builds with varying order values. Test it elsewhere before switching a long-running winner. [v024] |
| Use Advantage+ placements | Right for real conversion campaigns; not for traffic, engagement or awareness. [v047] |
| Turn on Advantage+ audience | Generally right; check it is not already on. [v024, v133] |
| Add creative enhancements | Low impact (Meta's own estimate was about 3% for the standard bundle). Review each one; skip on already-edited ads and on images of real work. See `creative.md`. [v024] |
| Increase budget | Only under the conditions above. [v122] |
| Run a traffic campaign first in a new account (usually from a rep) | No. Run Sales or Leads from day one. [v025, v133] |

## Outdated advice to ignore

| Old rule | Current rule | Why it changed |
|---|---|---|
| Inside an ad set, pause the ads with the worst ROAS and keep the best | Pause the ads Meta stops spending on; keep ads that still get spend | Meta sequences ads within an ad set and personalises per person, so a "poor" ad may be feeding the others. [v005, v065] |
| Give every ad 7 days, then decide | Decide on conversion volume and significance | Seven days is hours too long for some accounts and months too short for others. [v004] |
| High CPM means the targeting is off: broaden or switch audiences | CPM is not a KPI. Check ad and page quality, then judge on cost per result | Valuable audiences cost more at auction, and targeting inputs are now mostly suggestions. [v062, v140] |
| Poor results mean the wrong audience; test interests and lookalikes | Look at offer, creative and page | Advantage+ audience and open targeting handle delivery; targeting is rarely the cause unless the audience is tiny. [v095, v107] |
| Trim weak placements, ages or genders seen in a breakdown | Leave conversion campaigns alone; steer with messaging or value rules | Meta already reallocates; manual placement and gender limits are being removed (2026). [v002, v010] |
| Keep cold and warm in separate campaigns so each can be measured | One ad set, read through the audience segment breakdown | Custom audiences are suggestions, so "cold" and "warm" ad sets reach the same mix. [v037] |
| More than 5–6 ads in an ad set is too many | 20+ distinct ads is the aim; expect 1–3 to take the spend | Andromeda matches ads to individuals. [v043] |
| Fix learning limited by raising the budget | Improve results, consolidate, stop editing | More spend on an unprofitable campaign only loses more. [v034] |
| Use a frequency cap of about 2 to stop fatigue | Add distinct creative | The source records frequency controls only in Awareness campaigns; Sales and Leads campaigns have none. [v105, v115] |
| Compare today's numbers with pre-2026 numbers, or quote CTR (all) | Use link clicks and like-for-like attribution periods | Click-through attribution now requires a link click. [v032] |
| Quality ranking labels show which ads to cut | Use the primary metric and spend allocation | Working ads are often labelled below average. [v409] |
| Use the "Inspect" tool to check auction overlap | Count identical or overlapping ad sets and consolidate | The tool was retired. [v189] |
| When results drop, change something today | Wait out the 72-hour data window and normal fluctuation, then diagnose in order | Recent data is modelled and daily swings are noise. [v133] |

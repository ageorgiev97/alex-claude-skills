# Campaign setup

How to build the account and each campaign: how many campaigns, ad sets and ads; objective; conversion location; performance goal and event; budget; bidding; attribution; placements; scheduling; learning; and a setting-by-setting checklist. Read it before creating, restructuring or auditing the structure of a campaign.

## Contents
- Three facts behind every rule
- Structure: the decision table
- When to split into more campaigns or ad sets
- Ads per ad set
- Objective and buying type
- Conversion location and performance goal
- Which event to optimise for
- Number or value of conversions
- Budget: level, type, amount
- Bid strategy
- Attribution setting
- Placements
- Scheduling
- Learning phase, learning limited, how often to edit
- Campaign score
- Account-level settings to set once
- Checklist: Sales and Leads campaigns (late 2026)
- Structure by budget level
- Outdated advice to ignore

## Three facts behind every rule

1. **Meta optimises literally.** It finds people likely to take exactly the action named in the ad set's performance goal and conversion event. Ask for link clicks and you get clickers, including accidental clicks and bots; ask for add-to-carts and you get cart-adders, not buyers. Meta's own figure: a sales campaign optimised for the Purchase event gets 74% more sales at the same budget than one optimised for link clicks. [v025, v107]
2. **Most targeting inputs are suggestions.** Only "Controls" (location, minimum age, languages, excluded custom audiences) are hard limits. Custom audiences, lookalikes, age range, gender and interests under "Suggest an audience" are hints that Meta goes beyond, so ad sets that differ only in their suggestions reach much the same people. One "cold" ad set with no custom audiences spent about 40% of nearly $80,000 on engaged audience and existing customers. See `targeting.md`. [v043, v037]
3. **Conversions per ad set per week decide the rest.** They set how well delivery optimises and how fast anything can be judged: 70 conversions a week in one ad set optimises fully; spread over 10 ad sets (7 each) it struggles to leave learning. Splitting also causes auction overlap: Meta plans a run of impressions per person (for example 4–5 within 24–48 hours) and cannot plan it across several ad sets or campaigns reaching the same person. Bidding against yourself is the minor problem. [v043, v026]

## Structure: the decision table

**Default as of late 2026: one campaign per product range or offer, one ad set, cold and warm audiences together, many diverse ads, and new ads tested inside that ad set.** The scaling campaign plus testing campaign pair, the default in 2025, is now an option for high-volume accounts only.

"Conversions" means weekly results of the event the ad set optimises for (purchases if the goal is purchases), per ad set.

| Weekly conversions and budget | Campaigns and ad sets | Budget level | Performance goal and bidding | How new ads are tested |
|---|---|---|---|---|
| Under about 20–25; tiny (up to $20/day) and small (up to about $100/day) budgets | 1 campaign, 1 ad set, 1 offer (best seller or most profitable) | Campaign budget (same as ad set budget with one ad set) | Number of conversions on the final event, "Highest volume". Move up a funnel event only under the event rule below | Add clearly different ads to the same ad set in batches; force spend to one ad at a time with "Push delivery to this ad" if needed; about one meaningful test a month |
| About 25–50 | Same | Same | Final event. Sales with varying order values: switch to value once purchases are steady | "Push delivery to this ad", one ad at a time; or add distinct ads and watch where spend goes |
| About 50–100 | 1 campaign, 1 ad set per product range | Campaign budget | Value for sales; a qualified-lead event or lead values for leads | Creative testing tool inside the ad set (2–7 test ads). The sources give no firm line in this band; hold off on a separate testing campaign until volume is clearly past 100 a week |
| 100–200 or more; large budgets ($100,000/month and up) | One campaign per product range, offer or market, one ad set each unless splitting by location; optional testing campaign with 10–30% of budget | Campaign budget in main campaigns; ad set budgets in a testing campaign with several ad sets | Value for sales; conversion leads or lead value fed from the CRM (customer relationship management system) for leads; value rules on top | Creative testing tool, ideally inside the testing campaign; winners move to the main campaign |

How the conflicts in the source material resolve:

- **One campaign or two.** In 2025 a scaling campaign plus a testing campaign (about 80/20) was the default, because new ads placed beside proven winners got no spend. The 2026 guidance returns to one campaign and one ad set, limits the testing campaign to accounts with 100–200 or more weekly conversions and larger budgets, and since October 2026 uses "Push delivery to this ad" to force spend to a new ad without a second campaign or split data. Under 50 conversions a week, never split. [v005, v014, v048]
- "Push delivery to this ad" was in about half of accounts in October 2026. Without it, use the creative testing tool or add distinct ads to the ad set. See `testing-and-scaling.md`. [v005]
- **Testing share of spend:** 10–20% when campaigns are profitable, up to 50% for aggressive growth, close to 100% when nothing works yet. [v005, v004]
- One 2026 source also lets very large accounts separate campaigns by funnel stage. Treat it as a large-budget exception; the default at every size is funnel stages mixed in one ad set. [v014, v043]

## When to split into more campaigns or ad sets

| Reason | How to split | Why it is valid |
|---|---|---|
| Different product ranges or service lines (hats and shoes, not red hats and blue hats) | Separate campaigns | Each needs its own optimisation and message, and can be paused when out of stock or at capacity [v043] |
| Countries, to compare markets or fix spend per market | Separate campaigns per country | Location is a hard control, so this is the one audience test that is real [v043] |
| Countries, same product and offer, goal is best total return | One campaign, one ad set per country, campaign budget | Meta shifts budget between markets through the month. Nine country campaigns merged this way went from 2.8x to 3.7x return on ad spend (ROAS) in 30 days [v094] |
| Multi-location local business | Separate ad sets or campaigns per city or area | Location is a hard boundary [v043] |
| Offer or message only warm people may see (customer-only upsell, warm-only sale) | Separate ad set with hard custom-audience targeting | The default setup also shows it to cold people. See `targeting.md` [v037] |
| Customer value of $1,000 or more, trust-based or high-ticket sale | Add an omnipresent content campaign (10–14 ad sets, one ad each) beside the conversion campaign | Different goal, deliberately different structure. See `local-and-high-ticket.md` [v054] |
| Creative testing at high volume | Separate testing campaign | Only at the volumes in the decision table [v048] |

- Do not split by interest versus lookalike versus open targeting, by cold versus warm, by funnel stage, or by product within one range, and never run duplicate copies of a campaign to scale. Each divides conversions between ad sets that reach the same people. A general catalogue campaign may span all ranges; see `ecommerce.md`. [v043, v026]
- Funnel stages live inside the one ad set: put introduction ads (founder story), evidence ads (demonstration) and closing ads (testimonials, strong call to action) together and Meta sequences them per person. [v043, v064]
- **Reset for an over-complicated account:** switch everything off, build one campaign with one ad set, the best offer and the best existing ads, and leave it for a week. Add complexity back gradually. [v107]
- Deviating from Meta's default structure triggers warnings tuned to the average advertiser. Ignore them when following a deliberate strategy with a stated reason, not because of old habits. [v043]

## Ads per ad set

- Run as many good, clearly different ads as can be produced. The old cap of 5–6 is gone; 20 or more live ads is the usual aim and 30–50 is fine when quality holds. [v008, v043]
- Different means different formats and styles, not colour variants; near-duplicates may be treated as one ad with only one entering the auction. See `creative.md`. [v044]
- On small budgets do not launch everything at once, because each ad needs spend to be tested. Start with 2–4 very different ads and add a batch at each edit window. [v055, v044]
- Copy variants go inside one ad (up to 5 primary texts, 5 headlines, 5 descriptions), not in separate ads. [v043]
- Expect most spend to land on 1–3 ads. Do not switch off the top ad to force spend elsewhere, or pause a high-spend ad only because its own cost per result looks poor. See `analysis-and-troubleshooting.md`. [v048, v043]

## Objective and buying type

- **Buying type: "Auction".** "Reservation" locks a lower cost per 1,000 impressions (CPM) by using weaker prospects and placements and offers only awareness and engagement. [v049, v164]
- **Sales or Leads in over 90% of cases.** Sales when people buy directly and the purchase is tracked. Leads when a call, quote, enquiry or visit sits between click and sale, or the sale lands more than 7 days after the click (the longest attribution window). [v029, v091]
- The objective cannot be changed later; rebuild the campaign. [v091]
- A new ad account uses Sales or Leads from day one. A traffic or engagement campaign "to warm up the pixel" produces fewer conversions even in a new account. [v025, v095]

| Objective | Legitimate uses |
|---|---|
| Traffic | Conversion cannot be tracked (third-party checkout, ticketing or marketplace page); a blog post read for its own sake; Instagram profile visits [v091, v087] |
| Engagement | Message conversations; Facebook Page likes; the omnipresent content campaign in niche or small local markets [v087, v054] |
| Awareness | Big brands with no direct conversion path; the omnipresent content campaign [v091] |
| App promotion | Apps only: installs, or app events when revenue comes from in-app purchases [v087] |

## Conversion location and performance goal

The performance goal (ad set level) matters more than the objective. Objective and conversion location only decide which goals are offered; the goal decides what delivery optimises for. [v087, v045]

- **Pick a single conversion location.** Many accounts default to a combined one ("Website and app", "Website and calls", "Website and instant forms"), which locks the goal to "Maximize number of conversions". Choosing "Website" alone unlocks "Maximize value of conversions". [v045, v029]
- **Inside a Sales or Leads campaign never choose** "Maximize number of landing page views" or "link clicks" (it becomes a traffic campaign), or "daily unique reach" or "impressions" (an awareness campaign). [v049, v087]
- If unsure and the objective is right, keep the default goal. [v087]

| Objective and location | Performance goal |
|---|---|
| Sales, Website | "Maximize value of conversions" when order values vary and are passed back; otherwise "Maximize number of conversions"; event Purchase |
| Leads, Website | "Maximize number of conversions" on a Lead or qualified-lead event; "Maximize value of conversions" when lead values are sent |
| Leads, Instant forms | "Maximize number of leads"; "Maximize number of conversion leads" when the CRM is integrated and the downstream event falls inside the attribution window |
| Leads, Messenger or Instagram | Locked to "Maximize number of leads" |
| Leads or Engagement, WhatsApp or message destinations | "Maximize number of conversations" |
| Traffic, Website | "Maximize number of landing page views" if the pixel is on the page; "link clicks" only when nothing can be tracked |
| Awareness | "Maximize reach of ads" |

[v087, v049, v045]. Lead locations, forms and conversion leads: `lead-generation.md`.

## Which event to optimise for

**Rule: optimise for the deepest funnel event that (a) is tracked accurately, (b) happens within 7 days of the click, and (c) reaches about 20–25 conversions a week in the ad set.** When the deepest event falls short, step up one at a time: purchase, else booked call, else webinar attendee, else registrant. [v013, v091]

- Meta's stated requirement is 50 results a week per ad set. In practice ad sets often leave learning at about 20–40 a week, which is why 20–25 is the working floor. [v034, v013]
- Stay on the final event while it is within reach: at about 20 purchases a week with a realistic path to more, do not move up. First improve offer and creative at the same budget and consolidate ad sets so all conversions land in one. [v034]
- Move up only when the real event is far below the floor and will stay there (7 purchases a week against 35 add-to-carts; high-ticket offers; a business content with 5–10 sales a week). Expect the ratio from the upper event to the final one to worsen. Run it as a test, about a month each way, and compare final sales or qualified leads. [v034]
- For leads, go deeper than "Lead" where possible: fire the optimised event only for qualified respondents (a separate thank-you page event such as "Submit application", or conditional logic that closes an instant form on disqualifying answers). The effect is small on day one and large after 30–90 days. See `lead-generation.md`. [v008, v011]

## Number or value of conversions

"Maximize number of conversions" treats a $30 buyer and a $300 buyer as equal and chases the cheaper one. "Maximize value of conversions" favours people predicted to spend more: often fewer purchases, higher revenue and ROAS. [v011, v045]

| Situation | Choice |
|---|---|
| Sales, order values vary and are passed back (pixel plus Conversions API), purchases arriving steadily | Value. This is the default for new builds [v011, v024] |
| Sales, brand-new account with no conversion data, or a handful of purchases a week | Number first; switch to value once there is conversion history [v008, v013] |
| Sales, one product at one price bought once | Number; value adds nothing, and an upsell or dearer option is the better fix [v045] |
| Leads, all worth about the same | Number [v049] |
| Leads, values differ and are sent per lead (separate thank-you pages per service or per qualifying answer) | Value. Example: roof replacement $20,000 at a 1-in-5 close rate = $4,000 a lead; repair $2,000 at 50% = $1,000 a lead [v045] |
| Long-running campaign performing well on number | Leave it; test value in a new ad set and switch only on clear evidence [v024] |

The sources give no numeric floor for value optimisation, only "some conversion data" and "not a handful a week". The option is not in every account. [v008, v045]

## Budget: level, type, amount

**Campaign budget or ad set budget**

- **Default: "Campaign budget"** (formerly CBO, then Advantage campaign budget). It is the Advantage+ default and with one ad set it is identical to an ad set budget, which stays greyed out until there are several ad sets. [v089, v049]
- With several ad sets, keep campaign budget when they sell the same thing and Meta should allocate (the country case); use ad set budgets when spend must be forced or equal: an omnipresent content campaign (campaign budget must be off), a testing campaign with several ad sets, or markets that each need a fixed amount. [v094, v054, v085]

**Daily or lifetime**

- **Daily budget, essentially always.** A lifetime budget fixes an end date and spends unevenly, and extending it means a new campaign and a new learning phase. [v026, v049]
- Features that require a lifetime budget: ad scheduling by day and hour, the frequency "Target" option and ad sequencing (the last two are awareness or engagement features). [v052, v057, v105]
- "Campaign spending limit" and an end date are optional safety nets for accounts that are not checked daily. [v029]

**How much to start with**

- No universal number. Use an amount that could be lost without financial harm but is large enough to sting, derived from what the business can pay to acquire one customer (see `offers-and-economics.md`). Too small a budget does not reduce risk; it starves Meta of data. [v015, v029]
- Do not size the budget to reach 50 conversions a week. Prove offer and creative at a low budget, in learning limited if necessary, then scale. [v034, v122]
- Reference points: small = under $3,000 a month (about $100 a day); tiny = $600 a month or less ($20 a day). [v042]
- Raising budgets after launch: `testing-and-scaling.md`.

## Bid strategy

| Option | Use |
|---|---|
| "Highest volume" (campaign bid strategy, default) | Nearly everyone, including most lead generation and all small budgets [v029, v014] |
| "Cost per result goal" (ad set, under the performance goal) | A goal, not a cap. A realistic figure makes Meta spend less when results cannot be had at that cost (off-season, weak days, auction spikes), so spend, conversions and learning speed fall: a $100 daily budget may spend $30–40. An unrealistically low figure stops delivery. Suits hands-off advertisers and thin margins; usually left empty. Risky on click-optimised campaigns [v139] |
| "ROAS goal" | Bids on conversion value; only available when values vary (greyed out otherwise) [v029] |
| "Bid cap" | Not for beginners; can go wrong [v029] |

Optimising for the right event, and for value where it applies, is the bidding decision that matters most; it can multiply ROAS. [v004]

## Attribution setting

- Location: ad set > "Attribution" > attribution model; "Show more options" for the windows. [v032]
- **Model: "Standard".** "Incremental" changes delivery as well as reporting, makes reported results look worse and suits larger advertisers with big customer bases. See `tracking-and-attribution.md`. [v013, v006]
- **Windows: keep the widest** (7-day click-through, 1-day engage-through, 1-day view-through). Meta learns only from conversions it can attribute, so narrower windows remove training data, most of all for considered purchases. Narrow only when other heavy channels, such as large email sends, clearly inflate Meta's numbers. [v032, v146]
- Do not change attribution on an ad set that is performing; use new settings in new ad sets. [v283]

## Placements

- **Sales or Leads campaign optimised for a real conversion event: all placements (Advantage+ placements).** Meta spends only where conversions happen, so trimming from the placement breakdown is not recommended. [v047, v010]
- **Anything not optimised for a conversion** (awareness, traffic, engagement, or a click, reach or impression goal): keep Facebook and Instagram feeds, Stories and Reels; remove Audience Network, Messenger and Threads, because Meta otherwise buys the cheapest inventory. Then untick "Allow limited spend to excluded placements" (up to 5% of budget per excluded placement). [v047]
- **As of late 2026 Meta is removing ad-set-level placement, platform, device and operating-system controls** (rolling out from September 2026). Where they are gone: (1) move to Sales or Leads wherever conversions can be tracked; (2) use account-level "Placement controls" under Advertising settings > Account controls (a short list including Audience Network; may also be removed); (3) apply a value rule with criteria type Placement, such as "Audience Network −90%", per ad set. Value rules cannot remove Threads or Messenger. See `targeting.md`. [v010, v002]
- Leave brand safety and inventory filters at their defaults unless a corporate policy requires otherwise. [v049]

## Scheduling

- Run continuously with no end date. [v049]
- Ad scheduling needs a lifetime budget: campaign > Budget > "Lifetime budget" > "Show more settings" > "Ad set scheduling", then in the ad set "Run ads on a schedule". Use it mainly for lead generation where speed of response matters (for example Monday to Friday, 9 to 5, for a business-to-business sales team): Meta values a lead equally at 2 a.m. on Saturday, the business does not. Rarely useful for ecommerce. [v052]
- Leave "Budget scheduling" off at launch; any change to delivery timing needs a specific reason. [v029, v065]

## Learning phase, learning limited, how often to edit

| Fact | Detail |
|---|---|
| What starts learning | A new ad set; a significant ad set edit (targeting, placements, optimisation); adding or editing an ad; some campaign-level changes; a large budget jump [v034, v129, v026] |
| Typical length | About 24–48 hours; almost nothing at thousands of conversions a day, much longer on small budgets [v042, v034] |
| Meta's stated exit requirement | 50 results in 7 days per ad set, counted on the performance-goal event [v034] |
| In practice | Many ad sets exit at about 20–40 a week; none with 50 or more a week has been seen stuck [v034] |
| Reported alternative | 10 conversions in 3 days, an in-account message in some accounts in late 2024, never documented. Do not assume it applies [v129] |
| "Learning limited" | Not enough results to exit. Not an emergency: profitable ad sets run in it. Exiting adds perhaps 10–20% when results are already decent [v034] |
| Budget changes | About 3% a day is unlikely to restart learning; a large step does and takes a day or two to settle [v026] |
| After learning | Delivery keeps improving with accumulated conversions (better at 1,000 than at 100), so history has value [v129] |
| Health check | Account overview shows the share of the last 7 days' spend in learning ad sets; a high share (39% in one example) means too many edits [v122] |

**Fixing learning limited, in order:** (1) improve offer and creative so the same budget converts more; (2) consolidate (five ad sets at 15 purchases a week become one at 75); (3) move up one funnel event, only under the event rule; (4) stop editing. Do not take Meta's "increase budget" fix when the campaign is unprofitable (at 0.6x ROAS against a 3x need, exiting changes nothing) or when the business cannot handle more orders or leads. Ad sets have gone from learning limited to active with no rise in conversions, only by being left alone. [v034]

**How often it is safe to edit**

| Conversion volume | Gap between batches of changes |
|---|---|
| Hundreds or thousands a day | Results are readable within hours; still give new ads about 2 days [v085] |
| High volume | 5 days at the shortest [v026, v025] |
| Most accounts | Once every 7 days per ad set [v034] |
| Low volume, small budgets | 10–14 days; at about 5–6 conversions a week a new ad may need a month to judge [v042] |

- Batch changes into the edit window: add the five new ads together at the end of the week, not one a day, then wait again. Each edit interrupts per-person impression sequences already paid for. [v034, v025]
- Do not over-correct into never touching the account. New ads must replace fatigued ones, and re-entering learning once a week is harmless. [v095]
- Do not change optimisation settings (budget level, attribution, performance goal) on a strong performer. [v024, v283]

## Campaign score

- A 0–100 score in the right-hand panel during setup. 100 means every Meta-recommended setting is on; it lists what costs points and offers "Apply" buttons. [v089]
- Hard limits lower it (a hard age limit cost about 8 points in one demo, missing catalogue data 12, removing placements a little). Adding suggestions does not. [v089]
- When audience, budget and placements are all on their Advantage+ settings the campaign shows "Advantage+ sales campaign" or "Advantage+ leads campaign" as on. Advantage+ is a state of one unified setup, not a separate campaign type. [v029, v089]
- A high score is fine; 100 is not required when each deviation has a reason. When results are poor and the score is low, restoring recommended settings is a sensible first move. [v089, v029]
- The account-level opportunity score: `analysis-and-troubleshooting.md`.

## Account-level settings to set once

Under Ads Manager > All tools > "Advertising settings":

- **Audience segments:** define "Engaged audience" and "Existing customers" so the audience-segment breakdown works; otherwise it shows only "unknown". See `targeting.md`. [v037, v033]
- **Social information:** tick "Allow Meta to combine likes and reactions for similar ads". No downside; not in every account. [v052, v078]
- **Value rules** and **Placement controls** are created here and applied per ad set. See `targeting.md`. [v028, v010]

## Checklist: Sales and Leads campaigns (late 2026)

Build in Ads Manager, never by boosting from the app. Labels and defaults vary by account, and newer options may be missing.

**Campaign level** [v029, v049, v089]

| Setting | Sales | Leads | Reason |
|---|---|---|---|
| Buying type | "Auction" | Same | Reservation trades impression quality for a lower CPM |
| Objective | Sales | Leads | Sets the available performance goals; cannot be changed |
| Special ad categories | Declare if financial products, employment, housing, social issues or politics might apply | Same | Not declaring risks rejections and an account ban. See `account-health-and-policy.md` |
| Catalogue ("Advantage+ catalog") | Off for a first build | n/a | Advanced. See `ecommerce.md` |
| Budget strategy | "Campaign budget" | Same | Default; identical with one ad set |
| Budget type and amount | Daily; amount per "How much to start with" | Same | Flexible, no forced end |
| Campaign bid strategy | "Highest volume" | Same | Controls reduce delivery and data |
| Spending limit, budget scheduling, A/B test | Off | Off | Not needed at launch |
| Audience segment reporting | Engaged audience and existing customers defined | Same | Shows whether spend reaches new people |

**Ad set level** [v029, v049, v045]

| Setting | Sales | Leads | Reason |
|---|---|---|---|
| Conversion location | Single: "Website" | "Website" or "Instant forms" | A single location unlocks all performance goals. See `lead-generation.md` |
| Performance goal | Value when order values vary and purchases are steady; else number | Number (website); number of leads or conversion leads (forms); value when lead values are sent | Meta optimises for exactly this |
| Dataset | Correct pixel, plus Conversions API | Same for website leads | Bad data misdirects optimisation |
| Conversion event | Purchase | Lead, or better a qualified-lead event | Deepest event with enough volume |
| "Cost per result goal" | Empty | Empty | Throttles spend and learning |
| Attribution | "Standard", widest windows | Same | More attributed conversions to learn from |
| Value rules | None at launch | None at launch | Add later from real customer-value data |
| Customer lifecycle strategy | "Get conversions from all audiences" | n/a | Change only for a diagnosed problem. See `targeting.md` |
| Dynamic creative | Off | Off | Limits the ad set to one ad |
| Schedule | No end date | Same | Long-running ad sets keep improving |
| Controls: location | Everywhere the business can serve, no more, no less | Same; local = city plus radius, and untick "Reach more people likely to respond to your ads" | Hard limit; Meta concentrates spend where it works; leads that cannot be served are worthless |
| Controls: minimum age, languages, exclusions | 18 unless the law requires more; all languages; none | Same | Every hard limit shrinks delivery |
| "Suggest an audience" | Optional: customer and email lists, age range, a few interests | Same; more useful because Meta cannot see lead quality | Gives a new account a starting direction |
| "Further limit the reach of your ads" | Do not click | Do not click | Makes suggestions hard limits; needs a specific reason |
| Placements | All (Advantage+) | All | See Placements |
| Name | By settings, e.g. "UK – broad – 25–55" | Same | Readable later |

**Ad level** [v049, v029, v012]

| Setting | Recommended (both objectives) | Reason |
|---|---|---|
| Identity | Check Facebook Page, Instagram account and Threads profile | Common error |
| Ad setup | "Create ad", manual upload | Existing posts lack a call to action |
| Format | "Single image or video" or carousel; "Flexible" was Sales and App only when last described | See `creative.md` |
| Multi-advertiser ads | Leave on | No measurable difference in tests |
| Destination | One website URL, the page built for this offer | See `offers-and-economics.md` |
| "Personalized destinations" | Off, unless the site is only product pages | Meta may send clicks to another page and break the funnel |
| Browser add-ons (call, WhatsApp buttons) | "None" | One path to one action |
| Site links, promotions, products | Off for a single-page funnel | Keeps visitors on the intended page |
| Media | Purpose-made vertical (9:16) and square versions via "Replace" | Most impressions are vertical or square |
| Text | Several primary texts and headlines (up to 5 each); review each AI variation | Meta matches text to the person; AI copy can be wrong |
| Creative enhancements | Review each per ad; re-check after every edit, duplicate or preview | They can switch themselves back on. See `creative.md` |
| "Optimize text per person" | On; off in regulated industries | Rearranged wording can breach advertising rules |
| "Push delivery to this ad", creative testing | Off at launch | For later tests. See `testing-and-scaling.md` |
| Tracking | Correct pixel ticked | Events must reach the right dataset |
| Instant form (Leads only) | Built here | See `lead-generation.md` |

Review takes about 30 minutes, longer for first ads. After publishing, leave the campaign alone until the first edit window.

## Structure by budget level

| | Small (about $100 to $3,000 a month) | Large (about $100,000 a month) |
|---|---|---|
| Structure | 1 campaign, 1 ad set, 1 offer | Campaigns per product range, offer or market; testing campaign allowed with 10–30% of budget |
| Targeting | Broad; optional suggestions; no hard limits | Still broad; audience segments defined; value rules for segments worth more |
| Optimisation | Final event, number of conversions, "Highest volume" | Value; for leads, CRM-fed conversion leads or value |
| Testing | About one meaningful test a month, one variable | Continuous; answers in days or hours; fixed weekly creative output |
| Management | Edits every 7–14 days; 1–2 hours a month in the account | Checked often; fatigue can arrive within days |
| Objectives | Sales or Leads only | Same, plus an omnipresent content campaign where it fits |

[v014, v042]

## Outdated advice to ignore

| Old rule | Current rule | Why it changed |
|---|---|---|
| Separate cold and warm (retargeting) campaigns or ad sets | One ad set reaching both | Custom audiences are suggestions, so both reach the same mix and split the data [v043, v037] |
| One ad set per interest or lookalike; 1 warm plus 4 cold ad sets | No audience tests; split only by location | Interests and lookalikes are suggestions, so the test is not real [v043] |
| Separate top, middle and bottom-of-funnel campaigns | Funnel-stage ads mixed in one ad set | Meta sequences ads per person since the Andromeda update [v043, v064] |
| Scaling campaign plus testing campaign as the default (2025) | One campaign; test inside the ad set; testing campaign only at 100–200+ conversions a week | Split data hurts low-volume accounts, and new tools force spend to new ads in place [v005, v048] |
| No more than 5–6 ads per ad set | 20 or more distinct ads | Delivery is personalised per person and needs variety [v008, v043] |
| A separate ad for each headline or primary text | Text variations inside one ad | Five slots per field; separate ads become unmanageable [v043] |
| New accounts start with traffic or engagement to warm up the pixel | Sales or Leads from day one | Click data does not train conversion delivery [v025, v095] |
| The campaign objective is the key setting | The performance goal and event are | The objective only narrows the options [v087] |
| Choose between an Advantage+ shopping campaign and a manual campaign | One unified setup per objective | Meta merged them, rolling out from late 2025 [v089] |
| Ad set budgets as the working default | Campaign budget by default; ad set budgets to force spend | The unified setup defaults to it, and one ad set makes them equal [v089] |
| Budget must reach 50 conversions a week; raise spend to exit learning | Start affordable; exit through better ads and consolidation | Learning limited is survivable; scaling an unprofitable campaign is not [v034] |
| Optimise for add to cart or landing page views to exit learning | Final event if it reaches about 20–25 a week; one step up only as a tested last resort | Meta delivers the upper action, not buyers [v013, v034] |
| Edits allowed every 3 days (2024 learning change) | One batch every 7 days, longer on small budgets | 2026 guidance still cites 50 a week and sets a 7-day rhythm [v034] |
| Keep sales campaigns on number of conversions unless volume is high | Value by default when order values vary and purchases are steady | Number chases the cheapest buyers [v011, v008] |
| Trim placements from the breakdown; pick platforms per ad set | All placements for conversion campaigns; value rules or account controls where needed | Conversion optimisation handles it, and ad-set controls are being removed [v010] |
| Duplicate a winning campaign to scale it | Raise the budget of the existing campaign | Duplicates split data and overlap in the auction. See `testing-and-scaling.md` [v026] |

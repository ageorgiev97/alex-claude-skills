# Targeting: who sees the ads

How to set and audit an ad set's audience as of late 2026: which inputs are hard limits and which are only suggestions, how warm and cold audiences are combined, when to exclude or separate, and how to steer delivery with value rules. Read it before building or reviewing an audience, before answering "should we retarget, exclude or narrow?", and whenever ads are reaching the wrong people.

## Contents
- Operating model
- Hard limits and suggestions (status table)
- Default audience setup
- Location
- Age and gender, including the November 2026 gender change
- Custom audiences
- Lookalikes, interests and open targeting
- Audience segments
- Warm and cold combined: retargeting today
- Exclusions and customer lifecycle
- Value rules
- Audience size
- Checks to run on live data
- Outdated advice to ignore

## Operating model

The default is one broad ad set per campaign that reaches warm and cold people together. Put only real business constraints in "Controls" and treat everything else as an optional hint. [v043, v037, v033]

- Most audience inputs are suggestions, so ad sets built around different interests, lookalikes or warm audiences reach largely the same people. Splitting them divides the conversion data: one ad set with 50 conversions a week learns better than two with 25, and 70 a week in one ad set optimises fully while 7 a week in each of ten struggles to leave learning. [v043, v037]
- Overlapping ad sets also stop Meta planning each person's impressions as one sequence (for example 4–5 impressions within 24–48 hours). That costs more than "bidding against yourself", which is minor. [v043]
- In accounts with conversion history Meta largely ignores suggestions. An ad set with many suggestions and one with none gave the same results and the same split across new, engaged and existing people. [v070]
- Targeting is rarely why a campaign fails. See `analysis-and-troubleshooting.md` before changing the audience. [v025, v061]

The advertiser's remaining jobs:

1. Get the hard limits right, location above all.
2. Give Meta data it cannot see: uploaded customer and email lists, audience segment definitions, accurate conversion signals.
3. Tell Meta who is worth more or less with value rules. This is the current form of targeting.
4. Segment the market in the creative, not in the settings. Make separate ads for each sub-group (use case, industry, location, age group) and keep the audience broad; Meta finds each sub-group from the ad. To reach an older group that the breakdown shows is costlier, make ads that feature and address that group. Do not split audiences by awareness or funnel stage. See `creative.md`. [v121, v124, v024]

By budget: small budgets use one broad ad set with no hard constraints and no value rules yet. Large budgets (about $100,000 a month and up) stay broad, define audience segments and steer with value rules; small audiences cause most big-budget problems. [v014, v121]

## Hard limits and suggestions (status table)

The ad set "Audience" section has two parts. "Controls" are boundaries Meta will not deliver outside. "Suggest an audience" (Advantage+ audience) holds hints that Meta starts from and may go beyond or ignore. [v076, v029]

| Input | Where | Status as of late 2026 |
|---|---|---|
| Location (include and exclude) | Controls | Hard. The only behaviour is people living in or recently in the area, so some leakage occurs. [v117, v097] |
| Minimum age | Controls > "Show more controls" | Hard. Selectable 18 to 25 only; there is no maximum. [v076, v002] |
| Languages | Controls | Hard. [v076] |
| Excluded custom audiences | Controls | Hard. [v119, v092] |
| Account-wide controls | "Advertising settings" > "Account controls" | Hard, on every campaign (for example nobody under 21; a limited list of placements). [v076, v010] |
| Custom audiences and lookalikes (inclusion) | Suggest an audience | Suggestion by default. Can be made hard: "Further limit the reach of your ads" > "Switch setup", then untick "Use as a suggestion". Not in every account. [v002, v037] |
| Age range | Suggest an audience | Suggestion by default. Through 2025 it could be made hard the same way. The November 2026 source confirms custom audiences and minimum age in the switched setup and does not mention age range, so check the account before relying on it. [v052, v076, v002] |
| Gender | Suggest an audience | Suggestion only, in all campaigns, since November 2026. The hard option was removed. [v002] |
| Detailed targeting (interests, behaviours, demographics) | Suggest an audience | Always a suggestion; cannot be made hard. Detailed targeting exclusions were retired (no new use from 29 July 2024; existing ad sets until 31 January 2025). [v010, v052, v119] |
| "Choose an audience for each ad creative" (age and gender per creative) | Ad level | Suggestion only. New in November 2026. [v002] |
| Placements, platform (Facebook only or Instagram only), device, operating system | Ad set | Being removed, rolling out from September 2026. See `campaign-setup.md`; the value rule workaround is below. [v010, v002] |

Consequences:

- A custom audience added in the normal setup does not make a retargeting ad set; Meta also serves cold people. [v052, v037]
- Do not tick "Further limit the reach of your ads" by default. Meta warns of worse results (messages shown include 7.2% and 33% lower cost per result with Advantage+ audience) and the campaign score falls (100 to 66 after making age hard in one demo). Adding suggestions does not lower the score. [v076, v089]
- Stacking is safe with suggestions and breaks with hard limits: a hard 180-day website audience plus an age range, an interest and one country gave an estimated reach under 10. [v093]
- Declaring a special ad category removes some ad set targeting options. With broad targeting that costs little, so always declare when it applies. See `account-health-and-policy.md`. [v112]
- Sales campaigns may offer a choice at the top of the audience section between finding prospective customers (default; still includes some retargeting) and retargeting people who interacted with your products. Keep the default. [v089]

## Default audience setup

Controls:

- Location: everywhere the business can serve, no more and no less. See "Location".
- Minimum age: 18 unless there is a legal reason (for example 21). It is a compliance control, not a targeting lever. [v076, v070]
- Languages: empty unless the business can serve only one language community in a multilingual area (for example French-only in Canada). [v076]
- Excluded custom audiences: none by default.

Suggestions (optional; Meta ignores poor ones, so the downside is small):

- Age range: the typical buyer range, kept wide (about a 20-year span, never under 10 years). [v076, v132]
- Gender: "All" unless customers are 80–90% or more one gender. At 60/40 leave All. [v076, v029]
- Detailed targeting: none, or a handful of obvious interests or behaviours, all in one ad set. Check each option's category: to reach buyers of marketing services choose the interest, not the job title or employer of the same name. [v076, v132]
- "Describe your audience": the newer default inside detailed targeting (rolling out; buggy as of April 2026). Enter a description of the ideal customer (up to 2,000 characters, no sensitive topics), click "Generate options", then add all or some. It saves time and surfaces unfamiliar options, but its output is still suggestions, so the effect on delivery is small. "Use original options" switches back. [v035]
- Custom audiences: add all major warm audiences. This gives Meta more direction than interests, and lists from outside Meta are the most valuable part. [v076, v089]

| Situation | Setup | Why |
|---|---|---|
| New ad account, little conversion data | Controls plus an age range, a few interests and all custom audiences as suggestions | Meta has no history of who converts; suggestions give a starting direction. Fully open targeting struggles here. [v076, v070] |
| Account with conversion history | The same hybrid, or open targeting (location and age 18+ only) | Meta effectively ignores suggestions once it has data; the choice matters little. [v070, v076] |
| $100,000 a month or more | Open or very broad | Small audiences cause fatigue and delivery problems. [v121] |
| Local business | Radius only; no interests, or only very large ones; lookalikes at 10% if used | Small populations cannot take narrowing. See `local-and-high-ticket.md`. [v126] |
| Lead generation with poor quality or a group that never converts | In order: feed lead quality back to Meta and stay broad; add suggestions; value rules; hard limits last | Meta cannot see lead quality unless told, so inputs matter more for leads than for sales. See `lead-generation.md`. [v089, v052] |
| Omnipresent content campaign | Its own rules (warm audiences as the suggestion, frequency cap, many ad sets) | See `local-and-high-ticket.md`. [v054] |

Open targeting works best when the campaign optimises for purchases, the product has broad appeal and the account has substantial conversion history (older guidance said about 1,000 conversions; the bar has been falling). Refusing ever to add a suggestion is no longer sensible, because a wrong suggestion costs nothing. [v076, v132, v177]

## Location

- Target where the business can actually serve or ship. Do not narrow a national business to its "best" cities; Meta concentrates spend where buyers are and still finds buyers elsewhere. Do not widen a local business to get a bigger audience. [v029, v132]
- International businesses: list core markets (about 8–10 countries in one example), not the whole world, because cheaper countries absorb delivery. [v029, v131]
- Local businesses: city pin plus a radius (default "+25 mi"; from city only up to 50 miles) based on how far customers or the business will travel. Check the map for awkward geography and for the wrong entity being selected. [v076, v117]
- Local businesses should untick "Reach more people likely to respond to your ads" under location. It also reaches people merely interested in the area, and leads you cannot serve are worthless. Meta will warn of worse results (6.7% in one demo). [v049]
- Location is the one audience variable still worth splitting, because it is a hard limit: separate campaigns per country to compare markets, and separate ad sets or campaigns per city for multi-location local businesses. A single-country business uses one ad set for the whole country. [v043]

Out-of-area delivery. Meta removed the "people living in this location" option, so recent visitors are included. If more than about 5% of leads or impressions come from outside the service area, use one or both fixes: [v117, v097]

1. Geofence. Add the target area (for example city plus 15 miles), then add each surrounding town with a radius that just touches the target circle (10–12 miles in the example) and set it to "Exclude location", working all the way round. People who live in an excluded zone and visited are dropped. A few residents who visited an excluded zone are lost too, which is acceptable. This can cut wasted spend from 20–30% of budget to about 2–5%.
2. Call-out. Open the primary text by naming the locals ("New Yorkers, ..."). Only people who identify with the place respond, and those conversions train delivery toward residents.

A qualifying location question on an instant form also stops out-of-area leads being counted. See `lead-generation.md`. [v011]

## Age and gender, including the November 2026 gender change

What changed: in November 2026 Meta removed gender from the hard-limit setup in every campaign. Gender can still be chosen under "Suggest an audience", but Meta states it will show ads beyond the selected gender when it expects better performance. The new ad-level option "Choose an audience for each ad creative" is also only a suggestion. Nothing at ad set level can now confine delivery to one gender. [v002]

What to do:

1. Check whether there is a problem, using the gender breakdown on spend and on the real conversion. Most advertisers need no action: Meta moves budget toward the gender that converts, and some buyers of the other gender are real (gift buyers). [v002]
2. If the unwanted gender takes meaningful spend and does not buy (the usual case is men engaging and commenting on ads for a women-only product), apply a value rule that decreases the bid for that gender by 90%. [v002]
3. If both genders buy but one is worth more over time, raise the bid for the more valuable one with a value rule. Do not try to exclude the other. [v028, v073]

Age works the same way. Minimum age is for legal limits only; an age range is a suggestion. When Meta keeps delivering to an age group that never converts (for example leads from over-55s who never become clients), first improve the conversion signal, then use an age value rule, and only then consider a hard age range if the account still offers it. [v076, v052, v089]

## Custom audiences

Custom audiences are still required even without separate retargeting: they define the audience segments, they are needed when you do retarget directly, and uploaded lists give Meta data it cannot otherwise see. Keep the pixel and all conversion events installed for the same reason. [v037]

Create them in "All tools" > "Audiences" > "Create audience" > "Custom audience". Always choose the broadest action and the longest retention. Meta already knows who inside the audience is hottest (yesterday's visitor, the person who watched most of a video) and serves them first, so a narrow or short-window audience only gives up reach. [v076, v054]

| Audience | Setting | Retention | Notes |
|---|---|---|---|
| Website visitors | "All website visitors" | 180 days (the maximum given; default 30) | Needs the pixel. Updates automatically. [v076] |
| Website purchasers | Purchase event | Up to 730 days (raised from 180 in 2026) | Update older 180-day purchaser audiences. [v006] |
| Customer list | Upload CSV or TXT, or sync (for example Mailchimp) | No window; can cover years | Minimum 100 people. Email is the key identifier; more columns (phone, name, city) improve matching, which runs at roughly 40–50%. Add a customer value column so Meta can favour people like the highest spenders. Set the "audience label" (existing customer, qualified lead, disqualified lead, high value, low value). Upload customers and non-buying subscribers as separate lists. Uploaded files do not update; re-upload regularly. [v076, v054, v142] |
| Video viewers | "People who viewed at least 3 seconds of your video" | 365 days | Select many relevant videos and keep adding. One audience per offer if offers differ clearly. [v076, v054] |
| Lead form | "People who opened this form" | 90 days (maximum) | Only if instant forms are used. [v054] |
| Instagram account | "Everyone who engaged with this professional account" | 365 days | [v076] |
| Facebook Page | "Everyone who engaged with your Page" | 365 days | [v076] |
| Others if used | App activity, catalogue, offline activity, shopping, Instant Experience | Longest available | [v076] |

Meta already knows its own video viewers, engagers and pixel-tracked visitors and retargets them by default, so those audiences add little to delivery (still create them; it takes minutes and feeds the segments). Uploaded lists matter most: Meta cannot know that someone bought two years ago or arrived through another channel unless told. They are especially useful as a starting signal in new accounts. [v070, v089, v037]

Narrower audiences (visitors of specific pages, added to cart but not purchased, top 25%, 10% or 5% by time spent, form opened and submitted) are for specific funnel-stage work, not the default setup. [v076]

## Lookalikes, interests and open targeting

- Lookalikes are rarely built by hand now. Meta in effect builds them from the custom audiences added as suggestions and from conversion data. [v076, v054]
- Remaining use: when Meta is not finding the right people, which is more likely in lead generation (a lead can look fine to Meta and convert badly later) than in sales. Add a lookalike of real customers as a suggestion; it will not hurt. [v076]
- To create one: "Audiences" > select the source custom audience > create lookalike > choose location and percentage. The percentage is a share of the country's users, so size is fixed by country: United States 1% is about 2.8 million, United Kingdom 1% about 400,000. Use 1% in large countries, about 2% in the UK, 8–10% in a small country such as Ireland, 10% for a local business. Source people need not be in the target country, which helps when expanding. [v076, v126]
- A lookalike is a cold audience. Never count it as warm, and remove lookalikes from a hard warm-only ad set. [v076, v131]
- Interests and behaviours are suggestions only. Do not run one interest per ad set, and do not test interests against lookalikes against open targeting in separate ad sets: the audiences overlap so heavily that the test is not real. [v043, v076]

## Audience segments

Meta sorts everyone reached into new audience (cold), engaged audience (warm, not bought) and existing customers. Define the segments in every account: the breakdown is the main way to read who the ads reach, and the customer lifecycle setting depends on them. [v033, v006]

Set up: "All tools" > "Advertising settings" > "Audience segments", then choose custom audiences for "Engaged audience" and "Existing customers". [v043, v037]

- Engaged audience: all website visitors, Facebook Page and Instagram engagers, video viewers, lead form openers, email subscribers who have not bought, app users.
- Existing customers: the customer list (uploaded or synced from the store) and people who fired the Purchase event.
- Everyone else counts as new audience.

Read it: Ads Manager > "Breakdown" > "Audience segments" at campaign, ad set or ad level shows spend, results, cost per result and frequency per segment. Only "Unknown" means the segments are not defined. A small uncategorised remainder is normal. [v037, v043]

What it shows:

- "Cold" ad sets retarget anyway. In one ad set with no custom audiences, about 40% of just under $80,000 went to engaged and existing people, who produced more than half of 942 purchases at a clearly lower cost. In another, 59 of 93 purchases came from existing customers, 9 from engaged and 20 from new. [v037, v043]
- A "warm" and a "cold" ad set built with suggestions usually show nearly the same split, which is the evidence for combining them. [v064, v043]
- The split follows audience sizes. A new business shows little warm spend; the warm share grows with the customer base. [v037]
- Check it whenever return on ad spend (ROAS) is used to judge new-customer acquisition: a strong figure may be mostly existing customers. [v006, v043]

Defining segments was introduced as reporting only, with no effect on delivery. A 2026 source also credits it with helping Meta allocate budget across the three groups; treat that as unconfirmed, and define the segments in any case. [v033, v089]

## Warm and cold combined: retargeting today

Default: no separate retargeting campaign or ad set. One hybrid ad set reaches cold, warm and existing people and Meta sets the balance. [v037, v043, v033]

- Meta retargets inside "cold" ad sets and serves cold people inside "retargeting" ad sets, so two such ad sets are in effect one campaign competing with itself. [v037]
- Budget moves by itself: as warm audiences and the customer base grow, Meta shifts spend toward them. Separate campaigns need that done by hand. [v037]
- Ready buyers get a closing ad at once while others are warmed up first, inside the same ad set. See `campaign-setup.md`. [v064, v043]

The ads must therefore make sense to both warm and cold people. Put introduction, proof and call-to-action ads in the same ad set. See `creative.md`. [v037, v043]

A separate warm ad set or campaign is still justified only when:

| Case | Example |
|---|---|
| The offer may be seen only by warm people or customers | A discount for the warm list only; an upgrade from a low-priced product to a high-ticket one. [v037, v142] |
| The message makes sense only to people at one funnel stage | Ads that refer to a webinar the person attended; proof ads for leads who have not bought (leads minus purchasers). [v037, v076, v119] |
| A customer is worth $1,000 or more and needs repeated exposure before buying | Run an omnipresent content campaign beside the direct-offer campaign. See `local-and-high-ticket.md`. [v092, v054] |

Not good reasons: wanting warm results reported separately (use the audience segment breakdown), abandoned-cart ad sets (they break Meta's planned multi-impression delivery), or habit. Most ecommerce businesses should not customise messages by warm and cold. [v092, v142]

How to build a true warm-only ad set: [v037, v052, v092]

1. Ad set > Audience > "Further limit the reach of your ads" > "Switch setup". Meta warns against it, and not every account has the option.
2. Add the custom audiences and untick "Use as a suggestion". If it stays ticked the ad set behaves like the normal hybrid.
3. Leave age, gender and detailed targeting open and remove lookalikes. Extra criteria only shrink a small audience.
4. If a cold ad set runs beside it and those people must not see a different offer, exclude the same custom audiences in the cold ad set's Controls.
5. After any edit, confirm the box is still unticked; the older equivalent setting switched itself back on. Reach far above the audience size means delivery has gone beyond the audience. [v202]

Delivery is never 100% confined; a few people outside the audience still see the ads. [v037]

## Exclusions and customer lifecycle

Default: exclude nobody. Customers buy again and buy related products, leave positive comments that help the ads, and refer others when reminded. They are a small share of a broad audience, and exclusions tend to interfere with delivery. [v076, v176, v142]

Use a custom audience exclusion (Controls > exclude custom audiences) when a group must not see something: [v076, v119]

- existing customers who paid full price while a discount runs, or a new-customer-only offer;
- isolating a funnel stage, such as leads who have not bought, by excluding purchasers;
- the cold ad set that runs beside a hard warm-only ad set.

Too much spend on existing customers is typical for established brands, long-running accounts and one-time-purchase products. Diagnose with the audience segment breakdown, and act only if a large share of spend or purchases goes to existing customers. Options in order of preference: [v006]

| Option | What it does | Caveats |
|---|---|---|
| Customer lifecycle: "Acquire new customers" (ad set level, sales campaigns; new in October 2026). The default is "Get conversions from all audiences" | Excludes existing customers as defined in audience segments | Matching is only about 50% accurate, so it is not a guarantee. Reported ROAS and cost per acquisition will worsen because existing customers are the cheapest conversions; accept that for incremental growth. Do not also exclude the engaged audience: yesterday's website visitor is the best prospect. |
| Incremental attribution (ad set attribution model) | Softer: optimises for conversions that would not have happened anyway | Reported results drop. Suited to larger advertisers with big customer bases. See `tracking-and-attribution.md`. [v006, v013] |
| Excluding purchaser custom audiences in Controls | Hard exclusion | In testing this disrupted delivery badly: ROAS fell and spend dropped (for example from $200 to $50 a day). Avoid for this purpose. |

## Value rules

A value rule tells Meta to bid more or less for a defined group of people, placements or conversion locations. It does not include or exclude anyone; it changes what Meta will pay in the auction, so the audience stays broad and consolidated in one ad set. [v028, v073]

Why it is needed: Meta optimises only for what happens inside the attribution window (7-day click at most). It cannot see lifetime value (LTV), repeat purchase, refunds or lead-to-client close rate unless that data is sent back, which most advertisers do not do. "Maximise value of conversions" handles order value inside the window; value rules cover what comes after. [v028, v011]

Where and which campaigns:

- Create: Ads Manager menu > "Advertising settings" > "Value rules" > "Create a rule set" (also reachable from the ad set's "Value rules" section). Available in nearly all accounts by 2026. [v028, v002, v052]
- Apply: creating a rule set does nothing. On each ad set, open the "Value rules" section, enable it and choose the rule set. Repeat for every ad set that needs it, including new ones. Different ad sets can use different rule sets or none, which suits product ranges with different buyers. [v002, v028]
- Campaign types: as of 2026 it works on sales, leads and other objectives, and may matter more for leads than for ecommerce. At launch in 2025 it was limited to Sales and App campaigns with a conversion-based performance goal, and the section disappeared when the goal was changed to something like landing page views; if the section is missing, check the performance goal. Do not use value rules in an omnipresent content campaign. [v028, v073, v054]

| Element | Detail |
|---|---|
| Criteria type "Audience" | Age, gender, location, mobile operating system, device platform (desktop or mobile). [v028, v052] |
| Criteria type "Placement" | Seven categories, including feeds, stories, reels and Audience Network. Threads and Messenger cannot be singled out. [v010] |
| Criteria type "Conversion location" | For example website against instant forms against messaging apps. [v028, v052] |
| Criteria per rule | Up to two combined (for example women aged 45 and over). [v028, v073] |
| Rules per rule set | Up to 10. Order matters: a person who matches several rules gets only the first that applies; adjustments do not compound. [v073] |
| Adjustment | "Increase bid by" or "Decrease bid by" a percentage. The maximum decrease is 90%. The sources give no ceiling for increases; examples run to +80%. [v002, v028] |
| Acknowledgement | You must confirm that overall cost per result may increase. [v073] |
| Naming | Name each rule by its effect ("Women +80%", "Men -90%"). [v028, v002] |

What to encode:

- Differences in customer value that appear after the attribution window: repeat purchase, retention, LTV, refund rate. [v013, v028]
- Lead-to-customer close rate by segment or by conversion location. [v013, v014]
- Priorities Meta cannot know: a new location where the business wants presence, or a younger group wanted for long-term brand reasons. [v073, v070]
- A hard preference that used to be a targeting control (gender, placement, platform, device). [v002, v010]

What not to encode:

- Where purchases or leads already come from inside the window. Meta already optimises for that, so a rule copying it adds nothing. [v013]
- Guesses. Spend 90–120 minutes in the customer relationship management system (CRM), the ad account and any third-party tracking working out what each age, gender, location and device group is worth, and set the percentage from that: a group worth 70% more gets about +70%. If the groups do not differ meaningfully, do not use value rules. [v028, v073, v013]
- Both directions for one pair. Meta recommends adjusting one way only: raise women or lower men, not both. [v074]

If the data is thin, start near +20% and move in steps while watching the mix. In one illustration +20% for women moved a 50/50 purchase split to 65% women. [v074]

| Situation | Rule |
|---|---|
| Women's jewellery brand; many buyers are men buying one-off gifts, while women repurchase and have far higher LTV | Gender: women, increase (+50% to +80% in the examples). A 10% higher cost per purchase is a good trade if women are worth 2.4 times as much. [v028, v073] |
| Customers aged 35 and over are about 30% more valuable (close rate, retention, repeat orders) | Age: all bands from 35 up, +30%. Under-35s still see ads. [v033] |
| Lead generation where one age band (for example 45–54) converts to clients best | Age: that band, increase by the measured difference. [v052] |
| Website leads close better than instant-form leads | Conversion location: website, increase. [v028] |
| One region retains customers better, or a new branch needs presence | Location: that area, increase. [v028, v073] |
| Under-35s refund more; customers on one mobile operating system are worth more | Age or mobile operating system: adjust by the measured gap. [v028] |
| Two priorities in one rule set | Rule 1 "Women +50%", rule 2 "Age 35+ +25%". A 40-year-old woman gets +50% only. [v073] |

Workarounds for removed controls. A 90% decrease means other advertisers bid about ten times as much for those impressions, so delivery to that group nearly stops. It is not an absolute exclusion. [v002]

| Removed control | Rule | Notes |
|---|---|---|
| Hard gender targeting | Criteria type Audience > Gender > the gender you do not want > "Decrease bid by" 90% ("Men -90%") | Apply to each affected ad set, and only where the breakdown shows a real problem. [v002] |
| Excluding Audience Network or other placements | Criteria type Placement > the category > 90% decrease ("Audience Network -90%") | Most needed on traffic, engagement and awareness campaigns, where Meta chases the cheapest inventory. On sales and leads campaigns optimised for real conversions, act only on a clear problem in the breakdown. The better fix is a Sales or Leads objective wherever the conversion can be tracked. See `campaign-setup.md`. [v010] |
| Facebook-only or Instagram-only delivery; dropping Stories | Decrease the bid on the placement categories to avoid | Favours a platform without a hard cut. [v010] |
| Device and operating system selection | Device platform and mobile operating system are rule criteria, so the same method applies | [v010, v028] |

After applying, expect the overall cost per result to rise, because cheaper conversions from the down-weighted group are given up. Re-check the breakdown and back-end value once there are enough conversions, confirm the favoured group really is worth more, and adjust the percentage or the group. You can also aim copy and creative at the more valuable group. [v073, v052, v028]

Skip value rules in beginner and small-budget accounts; get the offer, creative and tracking right first. [v049, v014]

## Audience size

- With suggestions as the default there is no minimum size to engineer. Business reality comes first: 50,000 people is fine if that is the real service area. [v132, v126]
- Size matters when inputs are hard. A warm-only ad set, or a local radius with hard criteria stacked on it, can be too small to deliver, so keep hard ad sets to as few criteria as possible. [v093, v126]
- Small audiences fatigue faster. Local businesses and warm-only ad sets need more frequent creative refreshes. See `creative.md`. [v126]
- At large budgets go as broad as possible. [v121]

## Checks to run on live data

| Question | Check | Action |
|---|---|---|
| Is the campaign reaching new people? | "Audience segments" breakdown: spend and conversions by segment | If "Unknown", define segments. If existing customers dominate and growth is the goal, use the customer lifecycle setting. |
| Are two ad sets really different audiences? | Compare their segment splits | If they match, consolidate. |
| Is delivery going to the wrong gender or age? | Gender and age breakdowns on spend, real conversions and back-end value | If a group takes spend without converting, apply a value rule. Do not build a rule from in-window cost per result alone. |
| Are leads coming from outside the area? | Lead locations in the CRM; region breakdown | Above about 5%: geofence, call-out copy, location question on the form. |
| Is a "retargeting" ad set really warm-only? | "Use as a suggestion" unticked; reach against audience size | Fix the setting, or fold the ad set into the main one if there is no warm-only offer. |
| Are hard limits costing delivery? | Ad sets with the switched setup, exclusions or a narrow hard age | Remove limits that have no legal, service-area or offer reason. |
| Is the value rule attached and still right? | "Value rules" section on every ad set; segment mix before and after | Attach to new ad sets; revise percentages from back-end data. |

## Outdated advice to ignore

| Old rule | Current rule | Why it changed |
|---|---|---|
| Run a cold campaign plus a separate retargeting campaign or ad set | One hybrid ad set; separate only for warm-only offers, stage-specific messages or an omnipresent content campaign | Custom audiences are suggestions, so both ad sets reach the same mix and split the data. [v037, v043] |
| Untick the expansion option on every ad set that has a custom audience | Leave custom audiences as suggestions; make them hard only for a true warm-only ad set | The hybrid performs better and manages itself. [v037, v142] |
| One interest or lookalike per ad set, tested side by side | All suggestions in one ad set; do not test audiences against each other (location excepted) | Suggestions overlap almost completely, so the test is not real. [v043, v076] |
| Lookalikes are the best cold audience; build many | Rarely build them; add one as a suggestion when Meta is finding the wrong people | Meta extrapolates from custom audiences and conversion data. [v076] |
| Hard-target one gender when the product is for men or women | Not possible since November 2026. Use a value rule (-90%, or an increase for the valuable gender) | Meta removed the hard gender option. [v002] |
| Hard-target or exclude as the first fix for "wrong people" | Fix the conversion signal, then value rules, then hard limits last | Hard limits reduce delivery flexibility, and several are gone. [v052, v002] |
| Exclude purchasers to force new-customer acquisition, or to save money | Leave customers in; if they take too much spend use customer lifecycle "Acquire new customers" or incremental attribution | Customers repurchase and refer, and hard purchaser exclusions disrupted delivery in testing. [v006, v076] |
| Build narrow, recent warm audiences (7-day add to cart, 25% video viewers) | Broadest action, longest retention (3-second viewers 365 days; all visitors 180 days; purchasers up to 730 days) | Meta already prioritises the hottest people inside a large audience. [v076, v006] |
| Keep cold audiences above 500,000 people (250,000 for local) | No minimum to engineer; set real limits and stay broad | Those rules belonged to hard-constraint targeting. [v132, v126] |
| Narrow with stacked interests or detailed targeting exclusions | Interests are always suggestions; detailed targeting exclusions were retired in 2024–2025 | Meta removed the hard options. [v119, v052] |
| Choose "people living in this location" for local businesses | Not available; geofence with excluded surrounding areas and name the location in the copy | Meta merged the location options. [v117, v097] |
| Restrict placements or platforms at ad set level | Being removed from September 2026; use placement value rules, account-level placement controls or a conversion objective | Meta is removing ad set placement, platform, device and operating system controls. [v010] |
| Separate audiences per funnel or awareness stage | One ad set with ads for every stage | Meta sequences ads per person, which beats a fixed manual funnel. [v043, v124] |
| Never add any targeting input | Suggestions are harmless and help new accounts; open targeting is one option, not a rule | Poor suggestions are ignored and good ones help. [v076] |
| Value rules only on Sales and App campaigns; start at +20% | On leads and other objectives as of 2026; set the percentage from real customer value, using +20% only when data is thin | The feature was extended after its 2025 launch. [v028, v013] |

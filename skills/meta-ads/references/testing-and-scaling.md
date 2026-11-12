# Testing and scaling

How to introduce and judge new ads, offers and angles, what to do with the ads inside a live ad set, and how to raise budgets without breaking a campaign. Read it before recommending a test, pausing an ad, or changing a budget.

## Contents
- Principles behind every rule
- Which testing method to use
- Settings for each method
- What to test, and in what order
- Does this test have enough data?
- Ads inside a live ad set after Andromeda
- What to do with winners
- Budget split between testing and scaling
- Is a budget increase safe? (preconditions)
- Scaling method 1: automated rules
- Scaling method 2: manual steps
- Step size and cadence by budget level
- Duplication and the August 2026 budget-increase bug
- When scaling fails
- Big budgets ($100,000+ a month)
- Sale events and seasonality
- Outdated advice to ignore

## Principles behind every rule

- **Conversion volume sets the clock, not days.** Judge a test or a budget change by how many conversions of the optimised event have arrived since it started. Ten conversions carry the same information whether they took 20 minutes or three months. [v004, v005]
- **One primary metric decides.** Use return on ad spend (ROAS) where order values are tracked, cost per result (cost per purchase or lead) otherwise. Click-through rate (CTR), hook rate and cost per 1,000 impressions (CPM) explain a result afterwards; they cannot call a test early, because a higher-CTR ad often has the worse ROAS. [v005, v014, v065]
- **Testing costs short-term performance.** Live ads are survivors, so most new ads lose to them, and the budget they take pulls account results down while the test runs (plan for a 10–20% hit lasting a couple of weeks). The return is the occasional outlier that performs far better and carries much more spend. Test deliberately, not constantly. [v005, v048, v039]
- **Keep conversions in one place.** Each extra campaign or ad set splits conversion data, slows learning and stops Meta planning how many impressions each person gets (auction overlap). Prefer methods that test inside the main ad set. [v005, v033, v026]
- **Delivery is personalised.** Andromeda (Meta's ad retrieval system, live in most accounts since late 2025) picks ads per person and sequences them, so an ad set is a portfolio serving different people, not a contest to find one winner. [v005, v055]

## Which testing method to use

Count conversions per week of the event the ad set optimises for (purchases if the performance goal is purchases, not all conversions). [v048]

| Weekly conversions (optimised event) | Budget guide | Method | Avoid |
|---|---|---|---|
| Under ~15 (up to 1–2 a day) | Tiny to small (under ~$3,000/month) | Add clearly different ads to the same ad set and let Meta allocate. About one meaningful test a month, one variable. When a big change must get a verdict, use "Push delivery to this ad", one ad at a time, with a long duration | Separate testing campaign. Batches of 5 ads in the creative testing tool (a month or more to resolve) |
| ~15–50 | Small to mid | Same ad set. "Push delivery to this ad", one ad at a time, for big changes. Creative testing tool only now and then, few variants, longer duration | Separate testing campaign: under 50 a week the split starves both sides |
| 50–100 | Mid | The sources give no firm line. Stay with the in-ad-set tools; the creative testing tool becomes practical as volume reaches dozens a week | A testing campaign until volume is clearly past 100 a week |
| 100–200+ (dozens to hundreds) | Mid to large | Creative testing tool in batches of 2–7 ads (answer in about 3–14 days). A separate testing campaign with 10–30% of budget is also fine; the strongest setup is the testing tool inside a testing campaign | Constant testing when campaigns are profitable: it lowers short-term results |
| Thousands a day | $100,000+/month | As above, with a written queue of tests; results arrive in hours to a day | Unplanned testing: time is lost between tests |

Volume decides when volume and budget disagree: a high-ticket account with a large budget but only a handful of conversions a week belongs in the top row. A separate testing campaign is ruled out at small budgets whatever the volume. Budget terms: tiny is $600 a month or less, small is under $3,000 a month, big is $100,000 a month or more. [v005, v014, v048]

Rules that override the table:

- **Near-duplicate variants always need the creative testing tool.** Ads that differ only in hook, text overlay, background or colour may be treated by Andromeda as one ad, with one entered in the auction and the rest starved (not every time, but it happens). At low volume, test two variants and extend the duration. [v044, v039]
- **Clearly different ads usually need no tool.** Image versus video, or UGC (user-generated content) versus founder-led, are treated as distinct; add them to the ad set. Use a tool only if they get no spend and a strict verdict matters. [v044, v048]
- **Short campaigns get no formal test.** For a campaign lasting days or a couple of weeks, or a one-off sale, add the ads and let budget go to the best performer. Exception: a sale repeated every few months, where learning which creative works has future value. [v005, v048]
- **Accept concentration** on one or two ads when the budget is very small (it gives the best short-term result, and Meta spreads spend across more ads as budget rises) or the audience is most of the population (fatigue is far off). [v048]
- **Small budgets test less and model more.** The goal is proof that the offer converts, then profit to reinvest. Borrow proven formats from competitors and reuse organic posts with above-average engagement. See `creative.md`. [v042, v014]
- **Availability, as of late 2026.** "Push delivery to this ad" was in about half of accounts in October 2026. Where it is missing, add ads to the ad set or run the creative testing tool with few variants. The two tools cannot run in the same campaign at the same time. [v005]

## Settings for each method

### A. New ads into the same ad set
- Add ads that look clearly different from the live ones; small tweaks (a background colour) get no spend. [v048]
- Add them as one batch, not one a day: each new ad is a significant edit that restarts learning, so change an ad set no more than about once every 7 days (7–14 on small budgets). See `campaign-setup.md`. [v034, v042]
- A new ad that gets no spend usually means Meta predicted it would not beat the winners. Meta is often right, not always: existing ads carry accumulated likes and comments that tilt delivery toward them. Keep producing until something earns spend; several rounds are normal. [v048, v085]
- Never switch off the best performer to force spend onto new ads. Results usually collapse. [v048, v005]

### B. "Push delivery to this ad" (newest; rolling out)
- Path: ad level > Ad setup > "Show more settings" (under multi-advertiser ads) > "Push delivery to this ad". [v005]
- Settings: share of the daily budget for the test ad (default 20%) and duration (default 7 days). When it ends, the ad competes normally with the rest. [v005]
- Set the duration from conversion volume: at a few conversions a week, about a month. If the pushed ad finished with around 3 conversions, there is no verdict; extend or rerun. [v005, v004]
- Why prefer it: no separate ad set or campaign, so no fragmented data, and existing winners keep running. [v005]
- Reserve it for big changes (new format, style, hook, customer type or angle), not cosmetic tweaks. [v005]

### C. Creative testing tool
- Path: ad level, "Creative testing" section below the ad creative setup > "Set up test". [v048, v044]
- Number of test ads: 2–7 as of late 2026 (the limit was 5 earlier in the year). [v013]
- Budget: all of the ad set budget or a share of it. Meta splits the audience into equal, non-overlapping segments and divides the test budget evenly, so each ad is guaranteed delivery and the comparison is clean. [v013, v048]
- Duration: default 7 days. Shorten with hundreds of conversions a day; lengthen with a handful a week. [v048]
- "How do you want to compare performance": the default is cost per engagement. Change it to cost per lead, cost per purchase or ROAS, the metric the campaign optimises for. [v013, v048, v044]
- If Meta warns that the key metric was changed or the test cannot reach a result, the budget multiplied by the duration is too small: raise the budget, extend the duration, or cut the number of variants. [v044, v039]
- The test ads appear under the parent ad; put a different creative in each and keep everything else identical. [v048]
- At the end, Meta usually moves spend to the winner. Check that it did, then turn off the losing near-duplicates. [v044]
- Inside a single low-volume campaign the tool takes budget from the existing winner and gets hard to manage after many rounds. Use it selectively there. [v048]

### D. Separate testing campaign (high volume only)
- Preconditions: 100–200+ optimised conversions a week, not a short-term campaign, and not a small budget. [v048, v014]
- Build: same objective and the same broad warm-plus-cold audience as the main ("scaling") campaign, one ad set, new unproven ads only. Ad set budgets are often used to force spend. [v063, v085]
- Budget: 10–30% of the total; more when there are no winners yet (see the budget split table). [v014, v061]
- Move winners into the scaling campaign. [v048, v063]
- Two campaigns reaching the same people is a known cost, accepted for faster learning. [v048]

## What to test, and in what order

Test the biggest lever first. Significantly different results need significantly different inputs.

| Order | Variable | Notes |
|---|---|---|
| 1 | Offer, including which product or service | A campaign with no conversions at all is almost always an offer problem, and nothing later can be judged until conversions flow. Compare offers at campaign level on ROAS or cost per result; each offer needs a matching landing page. See `offers-and-economics.md`. [v039, v085, v084] |
| 2 | Angle (the main reason to buy) | One angle per ad. Round 1: one ad per angle (for example 5), keep the top 2. The winning angle is often not the one assumed. [v040, v039] |
| 3 | Style | UGC, creator or partnership, founder-led, demonstration, testimonial, animation. Test a batch per style; one UGC ad says nothing about UGC. Format (image, video, carousel) is no longer a contest: run formats together. [v039, v085] |
| 4 | Hook (first 3 seconds of video) | High leverage: a hook rate moving from 8% to 33% puts the message in front of about 4 times as many people. Record 2 bodies and many hooks, test about 5 hooks on one body in the creative testing tool, then move the winner into the main ad set. [v039, v044] |
| 5 | Small variables: headline, primary text, description, button, colours | Worth about 10% at most, so only after 1–4. Copy variants go in the text slots of one ad (up to 5 primary texts, 5 headlines, 5 descriptions), not in separate ads. Detail tests on a proven winner (overlay, background) still belong in the creative testing tool: a 10–15% difference is worth knowing. [v039, v043, v044] |

- Change one variable per test and hold the rest constant, or the result cannot be attributed. [v085, v014]
- Write the hypothesis first ("creator ads will beat our statics") and ask whether a win would substantially change results. If not, skip the test. [v085, v133]
- Do not test audiences in separate ad sets. Interests, lookalikes and custom audiences are suggestions, so the ad sets reach the same people. Location is the exception because it is a hard control. See `targeting.md`. [v043]
- Test settings (value optimisation, a different optimisation event) in a new or separate campaign for about a month and compare overall results. Do not change a long-running winner without that evidence. See `campaign-setup.md`. [v034, v024]

## Does this test have enough data?

Work through this in order, using spend and conversions of the optimised event per ad since the test began (pulling them is covered in `mcp-playbooks.md`).

1. **Exclude noise.** Ignore the first 24–48 hours after launch (learning phase) and treat the last 48–72 hours as provisional, because Meta models recent data. [v025, v133]
2. **Check each variant's conversion count** against the reference points below.
3. **Run a significance check** on the two variants (any free statistical significance calculator). At 85–90% confidence, act. No significance means wait. [v085, v128]
4. **Weigh the distance from target.** Slightly over target (say $35 against a $30 maximum) earns more time. At double the target, call it early. [v085]

| Evidence | Verdict |
|---|---|
| 2–3 conversions on an ad | No data. Extend or rerun. [v005, v004] |
| 3 ads sharing 6 conversions in 7 days | Not enough. [v133] |
| 10 conversions at $11 against 2 at $18 | Not significant; one more conversion would put the second ad near $12. [v133] |
| 15 conversions at a slightly higher cost against 3 cheaper ones | Cannot be decided by eye; run the calculator. [v128] |
| About 45 purchases on an ad | A fair sample. [v080] |
| Cost per result at 2x target after a normal window | Stop it. [v085] |

| Conversion volume | Expected time to a verdict |
|---|---|
| ~2,000 purchases a day | Hours; still give new ads about 2 days. [v085] |
| Dozens to hundreds a week | 3–14 days. [v005] |
| 1–2 a day | A month or more for 5 ads, so test one at a time. [v005] |
| ~5–6 a week | About a month per new ad. [v042, v106] |
| ~3 a week | Leave the test about a month. [v004] |
| A few a week across several ads, high ticket | Months; small budgets may need about 3 months to know whether the approach works. [v025, v014] |

When unsure, wait. A slightly longer test costs less than killing an ad that could have produced for months. [v085]

## Ads inside a live ad set after Andromeda

Expect concentration: out of 5–20 ads, 1–3 take most of the spend. That is normal. Within an ad set, where Meta puts the money is the signal; ROAS and cost per result are for comparing campaigns and offers. [v065, v064]

| Ad state | Action | Why |
|---|---|---|
| Gets spend, strong ROAS | Keep. Make variations and more ads like it | It is working. |
| Keeps getting spend, weak ROAS of its own | Keep. Judge the ad set as a whole | It may be the introducing (top-of-funnel) ad that the high-ROAS ads close after, or it converts a slice of people the others miss. Pausing it often makes the "good" ads worse. [v005, v043, v065] |
| Best performer | Never pause it to push spend elsewhere | Results usually collapse. [v048] |
| No spend, or spend has stopped, after the first days of learning | Pause it and add a new ad | Meta has judged it the underperformer; this is the ad to cut. [v065, v064] |
| Lost its spend to a newer, similar ad | Pause the old one | Meta found a better ad for the same role. [v064] |
| Results falling while frequency climbs | Pause and replace; it can return after about 6 months' rest | Ad fatigue. See `creative.md`. [v122, v115] |
| Losing near-duplicate after a creative test | Turn off | It adds nothing the winner does not. [v044] |
| Product out of stock, service at capacity | Pause | Business needs outrank optimisation. [v080] |

- Do not split-test down to one "perfect" ad. Lower-ROAS ads left running capture extra conversions from other parts of the audience. [v005]
- Replace like for like: when an introducing-style ad goes, add another of that kind, so the ad set still covers every stage from first contact to close. [v064]

## What to do with winners

- Leave the settings alone. Do not change optimisation, attribution or structure on a campaign that is performing; use new settings on new campaigns. [v024, v283]
- Extend the winner before it fatigues: new hooks on the same body (swap the first 3–5 seconds), then visual variations (background, person, edit style). See `creative.md`. [v007, v116]
- Study why it won and brief the next batch from that. Gains compound over rounds and are not visible from one. [v065]
- Change creative by duplicating the ad, not by editing the live one, so its history stays clean (older advice, not contradicted). After duplicating or editing an ad, re-check its creative enhancements, which can switch back on. [v012, v351]
- Keep producing. One winning ad will not hold at a much higher budget for long. [v065]

## Budget split between testing and scaling

| Account state | Share of spend on testing |
|---|---|
| Nothing works yet, no winners | Up to 100%. [v005] |
| Unprofitable or weak results | Most of the budget; there is no point scaling ads that do not work. [v063] |
| Profitable and stable | 10–20%. [v005] |
| Normal working range | 10–50%, occasionally up to 60%. [v005] |
| Separate testing campaign at large budgets | 10–30%. [v014] |

Leaving campaigns alone gives the best short-term numbers; testing finds the ads that allow scale. More ambition means more testing, up to an even split. A large agency reference point is 30–40% of spend on testing. [v005, v004]

## Is a budget increase safe? (preconditions)

Every row must pass. A failed row means hold the budget and fix that item first. When all pass, pick method 1 or 2 and take the step size from the budget-level table.

| Check | Pass condition | Why |
|---|---|---|
| Profitable now | Primary metric meets target at the current budget | Spending more does not make ads work; low spend is not why results are bad. Never raise budget to exit learning or to rescue a weak campaign. [v061, v034] |
| Known limit | Break-even or maximum acceptable cost per result (or minimum ROAS) is calculated. See `offers-and-economics.md` | Every threshold below depends on it. [v001] |
| Headroom | Clear gap to that limit: with a 3x requirement, be near 4–5x; with a $225 acceptable cost per lead, $200 leaves almost no room, $100 leaves plenty | Meta reaches the most responsive buyers first, so cost per result rises with every step. [v061, v001, v124] |
| Enough recent data | Target met over a window matched to volume: 3 days with dozens or more conversions in that window, 7 days as the default, 14–28 days when conversions come every couple of days | One good day is noise. [v026] |
| Settled | Out of the learning phase; 5–10 days since the last manual step | A large step restarts learning, which takes a day or two, then several days of data are needed. [v026] |
| Capacity | Stock, staff and lead follow-up can absorb more volume | Stock-outs and idle demand waste the gain. [v080, v122] |
| Creative in reserve | New ads ready to add | More budget means higher frequency and faster fatigue. [v065, v014] |
| Budget type | Daily budget on the existing campaign | Daily budgets adjust and extend cleanly; automated rules only act on them. [v026, v109] |

Treat Meta's own "increase your budget" recommendations with more scepticism than any other in-platform advice; they can serve Meta more than the advertiser. [v024, v122]

## Scaling method 1: automated rules

Small, frequent, conditional increases. Use it for advertisers who react to daily swings, for accounts with many campaigns, and for hands-off management. It is slower than manual steps. [v026]

Path: tick the campaign > "More" > "Automated rules" > "Create a new rule" > "Custom rule". [v026]

| Field | Scale-up rule | Scale-down rule |
|---|---|---|
| Action | "Increase daily budget by" 3% | "Decrease daily budget by" 3% |
| Limit | "Maximum daily budget cap" as a ceiling | "Minimum daily budget" floor |
| Action frequency | "Once daily" (the default is every 12 hours) | "Once daily" |
| Condition | Cost per result "is smaller than" the target, or website purchase ROAS "is greater than" the target when order values vary | Cost per result "is greater than" a higher threshold |
| Extra condition | Keep the default "Lifetime impressions is greater than 8,000" | Same |
| Time range | Last 3, 7, 14 or 28 days by volume (see the data row above). Never the default "Maximum" | Same as the scale-up rule |
| Schedule | "Daily" (runs between midnight and 1 a.m.) | "Daily" |

- Use a percentage, not a fixed amount: $10 is negligible at $1,000 a day. [v026]
- 3% a day rarely restarts learning and still compounds (1.03^30 is about 2.4 times the budget in a month if the rule fires daily). 5% or 7% is possible; do not go much above 7% daily. 30% a day breaks campaigns. [v026, v052]
- "Maximum" covers up to 37 months, so an old good average keeps the rule firing while the last week is terrible. [v026, v109]
- Leave a hold band between the two thresholds so the budget is not moving every day. Example: below $50 scale up, $50–75 hold, above $75 scale down. [v026]
- The impressions condition stops the rule acting on a new campaign with a few misleadingly cheap conversions. [v109]
- Rules apply only to campaigns that are active and on daily budgets. Review rules regularly; overlapping rules produce surprises. [v109, v052]

## Scaling method 2: manual steps

Larger steps, less often, with the percentage shrinking as the budget grows. Faster, but each step is more likely to disturb results, so someone must be watching and ready to add creative. [v026, v109]

- Example ladder (per day): $50 > 100 > 150 > 200 > 300 > 400 > 500 > 650 > 800 > 1,000. [v026]
- Wait 5–10 days between steps: 7 as the norm, 10 with low conversion volume, 5 with high volume, never sooner than 5. [v026]
- Expect a wobble for a day or so after each step. Judge on the roughly 7-day average. [v026]
- If results held, or slipped slightly and remain within target, step again. If they worsened beyond target, hold or step back to the previous level. [v026]
- Do not automate this method with rules, and never apply 20% increases daily. [v026, v109]
- Stepping reveals the ceiling. Example with a required 4x ROAS: $50 a day 6.0x, $100 5.2x, $150 4.9x, $200 4.6x, $300 4.3x, $400 4.1x, so the current ceiling is about $400 a day. Going beyond it takes a better campaign (creative, offer), not more budget. [v026]
- At the ceiling, also compare profit after ad spend at each level; sometimes a lower budget earns more. [v230]

## Step size and cadence by budget level

There is no fixed percentage. The old "10–20% at a time" limit is obsolete: Meta's own tooling has shown increases of 70–120% that do not restart learning. What matters is the absolute jump in people Meta must find. [v095, v014]

| Current daily budget | Manual step |
|---|---|
| Under ~$50 | Doubling or more is fine ($3 > $10, $10 > $20). [v014, v095] |
| ~$50 | +100%. [v026] |
| ~$100–400 | +33–50%. [v026] |
| ~$400–1,000 | +20–30%; do not double $800 to $1,600. [v026] |
| Several thousand and above | Smaller again. At $100,000 a month even +20% is a big jump; $10,000 > $20,000 a day in one step is too much; about +10% at $10,000 a day (older example). [v014, v095, v326] |

| Situation | Cadence |
|---|---|
| Automated rules | Once daily, 3% (up to 7%). [v026] |
| Manual, evergreen campaign | Every 5–10 days. 10% once a week is far too slow. [v026, v097] |
| Time-limited sale or event | Raise budget hard while it works; re-entering learning is not a disaster and a higher cost per result is an accepted risk. [v097, v095] |
| $100,000+ a month | Move budget toward winners as soon as the data is conclusive, even several times a day, but keep each step small. [v121, v014] |

Never jump many times over in one move (for example 10x from $20–100 a day). Results usually worsen sharply, the budget gets pulled back, and the ceiling stays unknown. [v026]

## Duplication and the August 2026 budget-increase bug

- **Do not scale by running copies.** Never run an identical duplicate campaign or ad set beside the original. The cost is not bidding against yourself (thousands of advertisers already target the same people); it is that Meta cannot plan per-person impressions or personalise across duplicates, and conversion data is split. Raise the budget of the existing campaign. [v026, v109]
- **The bug.** In August 2026, in a number of accounts, raising the budget of an existing winning campaign or ad set made results collapse (down 90% or more, or to zero) instead of the usual mild rise in cost per result. The sources do not say whether it has been fixed. [v016]
- **How to tell it from a normal step.** Normal: a day or so of wobble, then a slightly higher cost per result. Bug: results fall off a cliff straight after the increase. [v016, v026]
- **Workaround.** Duplicate the campaign or ad set at the higher budget and turn the original off. Never leave both, or several duplicates, running. Expect the duplicate to redistribute spend oddly (former top ads may get none), and re-check creative enhancements on the duplicated ads. [v016, v012]
- **Default when not affected.** Scale the existing campaign: it keeps its learning and the account stays simple. [v016]
- **Duplicate-and-replace as a reboot.** When a campaign that was performing drops suddenly with no visible cause and frequency is not high, duplicate it, run the copy and pause the original. This restarts learning and often restores results (one example went from 2x back to 5x). If it does not, check fatigue, seasonality and competitor moves. [v100]

## When scaling fails

"Cannot scale" means cost per result jumps or ROAS falls each time the budget rises. It is almost never a targeting or settings problem. [v128, v134]

| Check | Sign | Fix |
|---|---|---|
| Ad strength | Results drop sharply and at once, even at low spend | The ads only convert warm people and the small group of cold buyers ready to buy anything in the category. Make better ads and offers, pitched at people who are less aware. [v026, v124] |
| Creative volume | Few new ads a month, or only when results dip | Produce far more. An ad that is the best of 10 carries about $100 a day; reaching about $1,000 a day may take the best of 100. [v134] |
| Headroom | Current cost per result sits close to the maximum affordable | Raise customer value (repeat purchase, order value, close rate) so more can be paid. See `offers-and-economics.md`. [v134, v001] |
| Ad fatigue | Frequency near 4 or rising with falling results | Add visually different creative. [v115, v065] |
| Offer fatigue | Results fall despite fresh creative, usually at high spend | Rotate the offer: discount structure, guarantee, different range. [v121] |
| Audience size | Local or niche market with a fixed population | A real cap; expand locations or accept the level. [v133] |
| Budget-increase bug | Collapse straight after the increase | Duplicate at the higher budget, original off. [v016] |
| Stock or capacity | Best sellers sold out, leads not followed up | Fix supply before spend. [v080] |
| Wrong yardstick | ROAS fell but profit after ad spend rose | ROAS always falls with scale. Decide on absolute profit and choose the cap deliberately: $100,000 a month at 5x returns far more than $10,000 at 10x. [v121, v128] |

At the ceiling, hold the budget, improve the campaign, then step again. A 20–30% ROAS gain at low spend can open room for several times the budget. True ceilings exist but usually sit far above $1,000 a day; an account that stalls at a few hundred dollars a day has an ad or economics problem, not a ceiling. [v107, v061, v230]

## Big budgets ($100,000+ a month)

- Fatigue is the main workload. New creative may be needed several times a week (up to 4 in extreme cases), and ads can tire in days in a niche audience. Keep creative in reserve and a fixed production cadence, for example 12 new ads a week across three proven types. [v014, v121]
- Keep two or three alternative offers ready for when the current one tires. [v121]
- Decisions come in near real time: a test can conclude within a day, so work from a written plan. [v121, v014]
- Check the account several times a day. One disapproved ad can divert spend to weaker ads. If the budget is not being spent, add new creative or new campaigns. [v121]
- Structure does not get more complicated with budget. Large accounts more often need simplifying: keep the best products, creatives and offers and switch the rest off. [v121]
- Targeting stays broad; segment in the message, not the audience. See `targeting.md`. [v121]
- Consider incremental attribution and third-party tracking for decisions. See `tracking-and-attribution.md`. [v014]

## Sale events and seasonality

- Do not run formal tests around a big one-off sale such as Black Friday and Cyber Monday. Add the ads and let Meta allocate. [v005]
- Scale faster than usual while the sale is working, and plan stock first: a peak-season account can be capped by stock-outs, not by ads. [v097, v080]
- Lean into seasonality. Spend much more in strong periods and much less in weak ones; evening out spend, or spending more to fix a weak month, lowers the full-year result. [v107, v128]
- Do not switch off from 20 December by reflex. From about 21 to 31 December advertiser competition drops and CPMs fall; 26–31 December behaves almost like Black Friday. Use dated, reason-given offers. [v103]
- If the business cannot deliver over a holiday, pause. If demand is low but not zero (older advice), cutting to about 20% of normal budget restarts more smoothly than a full pause of 7 days or more, which restarts learning. [v265]
- Heavy discount ads convert people who already know the brand; they do not scale to cold audiences, so keep non-sale ads running alongside. [v050]
- Offer mechanics, urgency and scarcity are in `offers-and-economics.md` and `ecommerce.md`.

## Outdated advice to ignore

| Old rule | Current rule | Why it changed |
|---|---|---|
| Pause the ads with the worst ROAS or cost per result in an ad set | Keep ads that still get spend; pause ads Meta has stopped spending on | Meta sequences ads per person; a weak-looking ad may feed the strong ones or convert a different slice. [v005, v065] |
| Scaling campaign plus testing campaign as the default for everyone | Test inside the main ad set; a testing campaign only at 100–200+ optimised conversions a week | Splitting starves low-volume accounts, and in-ad-set tools now force delivery to new ads. [v005, v048] |
| No more than 5–6 ads per ad set; test in rounds of 6 | As many good, distinct ads as can be produced; 20+ is normal. See `creative.md` | Andromeda matches ads to individuals. [v043, v008] |
| Separate ad sets to test interests, lookalikes and open targeting | One ad set; split only by location | Targeting inputs are suggestions, so the ad sets overlap. [v043] |
| A separate ad per headline or primary text | Text variation slots inside one ad | Ad counts explode otherwise. [v043] |
| Pick the winning format (image or video) | Run formats together | Meta matches format to person and moment. [v039] |
| Judge tests after a fixed 7 days, or early on CTR | Judge on conversions of the optimised event and the primary metric | Volume, not time, makes data. [v005, v004] |
| Raise budgets 10–20% at a time | Large steps at small budgets, small steps at large ones, or 3% daily by rule | Meta tolerates bigger steps; the absolute jump is what matters. [v095, v014] |
| Scale by duplicating winning campaigns or ad sets side by side | Raise the existing budget; duplicate only to replace (bug or reboot) | Auction overlap and split data. [v026, v016] |
| Avoid the learning phase at all costs | Accept re-entry when adding ads or stepping budget; just do not edit constantly | Learning lasts about 24–48 hours and is not a disaster. [v095, v034] |
| Raise budget to reach 50 conversions a week and exit learning | Get profitable at a small budget first | Exiting learning does not rescue an unprofitable campaign. [v034, v122] |

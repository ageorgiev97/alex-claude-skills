# MCP playbooks

How to work on a live ad account through a Meta Ads MCP server: finding the tools, pulling the right data, computing the metrics the strategy files refer to, the standard workflows, and the protocol for making changes. Read this before the first tool call of any account task.

## Contents
- 1. Find out what the server can do
- 2. Facts the API cannot give you
- 3. Data pulls
- 4. Computed metrics
- 5. Reading the data without fooling yourself
- 6. Playbooks
  - A. First look at an account (audit)
  - B. Weekly or monthly review
  - C. "Results dropped": investigation
  - D. Creative analysis and brief
  - E. Test readout
  - F. Budget and scaling decision
  - G. Building a new campaign
  - H. Lead quality problem
  - I. Spend going to existing customers
  - J. Placement or audience problem
  - K. Scheduled monitoring
- 7. Change protocol
- 8. What usually has to be done in Ads Manager by the user
- 9. Report templates

---

## 1. Find out what the server can do

Several Meta Ads MCP servers exist and their tool names differ. Before anything else, look at the tools that are actually connected and sort them into capabilities. Do not call a tool by a name remembered from this file; use the names the server shows.

| Capability | Meta's own server (`ads_*` tools, beta since spring 2026) | Community servers in the Pipeboard style | If missing |
|---|---|---|---|
| List ad accounts | `ads_get_ad_accounts` | `get_ad_accounts`, `get_account_info` | Ask the user for the account ID |
| List campaigns, ad sets, ads with settings | `ads_get_ad_entities` | `get_campaigns`, `get_adsets`, `get_ads`, `get_*_details` | Ask for an export |
| Creative content (text, media, link) | via ad entities | `get_ad_creatives`, `get_ad_image` | Ask the user to paste copy or screenshots |
| Performance data with breakdowns | `ads_insights_performance_trend` and related `ads_insights_*` tools | `get_insights` (object, time range, level, breakdown) | Ask for an Ads Manager export |
| Anomaly and benchmark signals | `ads_insights_anomaly_signal`, `ads_insights_industry_benchmark`, `ads_insights_auction_ranking_benchmarks`, `ads_get_opportunity_score` | usually none | Compute from raw insights |
| Tracking health | `ads_get_dataset_details`, `ads_get_dataset_quality`, `ads_get_dataset_stats`, `ads_get_errors` | sometimes pixel listing only | Ask the user to check Events Manager |
| Create campaign, ad set, ad | `ads_create_campaign`, `ads_create_ad_set`, `ads_create_ad` | `create_campaign`, `create_adset`, `create_ad`, `create_ad_creative`, `upload_ad_image` | Give the user the build sheet (playbook G) |
| Edit, pause, activate | `ads_update_entity`, `ads_activate_entity` | `update_campaign`, `update_adset`, `update_ad` | Give exact instructions for Ads Manager |
| Catalogue | `ads_catalog_*` | rarely | - |
| Help articles | `ads_get_help_article` | - | - |

These names come from public descriptions of the servers and may have changed. Treat the table as a guide to what to look for.

Then establish, once per session:

1. **Read-only or read-write.** Meta's server has permission tiers (read-only, read-write, and one that includes financial actions). If the write tools are absent or fail on permissions, work in advisory mode and hand the user instructions.
2. **Which account.** If more than one is returned, ask which. Never guess from a name.
3. **Account basics:** currency, time zone, account status, spend cap, and whether anything is in a disapproved or restricted state. All money figures in the report use the account currency.
4. **Money units.** Meta's API usually expresses budgets and bids in the currency's minor unit (a daily budget of `5000` is 50.00), while spend in performance data is in major units. Servers differ on whether they convert. Check against a budget the user can confirm before writing any budget.

## 2. Facts the API cannot give you

Ask for these when the task depends on them, in one short message, and proceed with stated assumptions if the user doesn't know:

| Needed for | Ask for |
|---|---|
| Any judgment of "good" or "bad" | Gross margin; average order value (stores) or first-sale value and lead-to-customer rate (lead generation); whether customers buy again |
| Scaling decisions | Stock or delivery capacity; cash limits; the target or maximum cost per customer |
| Lead generation | What happens to leads afterwards: how fast they are contacted, how many qualify, how many buy (ideally by campaign or form) |
| Reconciling numbers | Revenue or customer counts from the store, CRM or payment system for the same dates |
| Offer and funnel questions | The landing page URL or a description of the offer, price and guarantee |
| History | Changes made recently outside the MCP (edits, new site, price change, promotions, stock-outs) |

Compute the break-even figures from the answers (formulas in `offers-and-economics.md`) and state them at the top of any analysis. If the user cannot give a margin, say which conclusions depend on it.

## 3. Data pulls

### Structure and settings (pull first)

For every active campaign, and anything paused in the last 30 days that spent money:

- Campaign: name, status, objective, buying type, budget level and amount (campaign or ad set), bid strategy, special ad category, start date.
- Ad set: status, performance goal (the API's `optimization_goal`), conversion event and where it is counted (`promoted_object`: pixel or dataset and event), conversion location, attribution setting, budget, schedule, targeting (locations, age, gender, custom audiences included and excluded, whether Advantage+ audience is on), placements, learning status if exposed, any value rules or cost goals if exposed.
- Ad: status, format, creative ID, the text fields, call to action, destination URL, whether it is a partnership ad, review status and any disapproval reason.

This alone answers the first audit questions: is the performance goal the real conversion, is the structure fragmented, are there hard limits, how many ads and of how many kinds.

### Performance

Ask for the same field set at each level so the numbers reconcile:

| Group | Typical API field names |
|---|---|
| Delivery | `spend`, `impressions`, `reach`, `frequency`, `cpm` |
| Clicks | `inline_link_clicks` (or `link_click` inside `actions`), `inline_link_click_ctr`, `cost_per_inline_link_click`. Avoid `clicks` and `ctr`: they count every kind of click. |
| Post-click | `landing_page_view` inside `actions` |
| Conversions | `actions` and `cost_per_action_type` filtered to the campaign's own conversion (purchase, lead, complete registration, schedule, and so on); `action_values` and `purchase_roas` for value |
| Video | 3-second plays (`video_view` inside `actions`), `video_thruplay_watched_actions`, `video_p25_watched_actions` … `video_p100_watched_actions`, `video_avg_time_watched_actions` |

Field names vary by server; some return friendlier labels. If a field is not returned, say the metric is unavailable instead of substituting a similar one.

**The result that counts** is the event the ad set is optimised for. When `actions` lists several purchase or lead types (pixel, on-Facebook, "omni"), use one consistently, preferably the one matching the ad set's conversion event, and say which. Adding them together double counts.

### Time windows

| Purpose | Window |
|---|---|
| Current state | Last 7 days and last 14 days, both ending 2–3 days ago |
| Baseline | Last 30 days; last 90 days for trend and for low-volume accounts |
| Trend | Daily or weekly rows (a time increment of 1 or 7) over 30–90 days |
| Seasonal businesses | The same weeks a year earlier |
| A specific change | Equal-length periods before and after, skipping the first 2–3 days after the change |

The latest 48–72 hours are incomplete: conversions are still being attributed and part of the data is modelled. Show them if asked, but don't base a judgment on them.

Scale the window to conversion volume. If the last 7 days hold fewer than about 20 conversions for the thing being judged, widen the window until there are enough, or say there isn't enough data.

### Breakdowns

Pull a breakdown only to answer a question; each one multiplies the rows.

| Question | Breakdown (typical API name) | What to look for |
|---|---|---|
| Where did the money go by surface? | `publisher_platform`, `platform_position` | Audience Network or another placement absorbing spend at poor cost per result; mostly matters for campaigns not optimised for conversions |
| Who is being reached? | `age`, `gender` | Spend concentrated in a group the business knows is worth less (needs back-end knowledge to act on) |
| New or existing customers? | Audience segments: new, engaged, existing (name varies; often `user_segment_key`). Requires the segments to be defined in the account's Advertising settings; otherwise it returns "unknown". | Share of spend and purchases going to existing customers |
| Which markets? | `country`, `region` | Markets with very different cost per result inside one ad set |
| Device | `impression_device`, `device_platform` | Rarely actionable now that device selection is going away; useful for landing page problems on mobile |
| When? | time increment by day; `hourly_stats_*` if offered | Day-of-week patterns for lead response; never a reason for hourly budget fiddling |
| How were conversions attributed? | attribution setting or `action_attribution_windows` (`7d_click`, `1d_view`, `1d_ev`) | Share that is view-through or engage-through; a high share with weak back-end numbers suggests over-reporting |

How to act on each breakdown is in `analysis-and-troubleshooting.md`. The short version: a breakdown showing where conversions already come from is not a reason to restrict the audience, because Meta is already optimising towards it. Act only when the business knows something Meta cannot see, or when a placement is clearly junk.

### Practical points

- Page through results. A default limit of 25 rows silently hides most of a large account; the total of the rows should match the account total for the period.
- Pull ad-level data for the ad sets that matter, not the whole account, when there are hundreds of ads.
- Keep the raw figures you quote. If the conversation is long, write the working table to a file so later steps use the same numbers.
- Ad names are the user's labels, not facts. Check format and content from the creative itself where possible.

## 4. Computed metrics

| Metric | Formula | Notes |
|---|---|---|
| Cost per result | spend ÷ results | Results = the optimised event |
| ROAS | conversion value ÷ spend | Compare with break-even ROAS = 1 ÷ gross margin |
| Hook rate | 3-second video plays ÷ impressions | Video only. Above 10% fine, below 5% poor |
| Hold rate | ThruPlays ÷ 3-second plays | Whether the body keeps people after the hook; compare within the account |
| Link click-through rate | link clicks ÷ impressions | Below 0.5% poor, above 1% decent, 1.5% very good, 2% and above excellent |
| Landing page view rate | landing page views ÷ link clicks | 75–80% is normal; under 50% is a fault |
| Click-to-conversion rate | results ÷ link clicks | Stores: 2–5% normal, under 2% weak. Dividing by landing page views instead separates page-load loss from what the page itself converts |
| Cost per landing page view | spend ÷ landing page views | Useful when conversions are too few to compare ads |
| Frequency | impressions ÷ reach | Over the window pulled; a 30-day figure is naturally higher than a 7-day one |
| Share of spend | entity spend ÷ parent spend | Where Meta is choosing to put the money |
| Existing-customer share | spend (or purchases) in the existing-customer segment ÷ total | Needs defined audience segments |
| Conversions per week per ad set | results ÷ weeks | Compare with the 50 a week Meta wants and the 20–25 a week working minimum |
| Profit after ad spend | conversion value × gross margin − spend | The figure that scaling decisions should use |

Mark these as computed in reports. If Meta's server returns its own hook rate or benchmark fields, prefer those and say so.

## 5. Reading the data without fooling yourself

- **Decide the deciding metric first** (ROAS or cost per result for the optimised event) and judge on that. Use the others only to explain.
- **Count conversions before comparing.** Two ads with 3 and 5 conversions are not different, and 10 against 2 is still not a significant gap. Use the reference points and the significance check in `testing-and-scaling.md` ("Does this test have enough data?"): 2–3 conversions on an arm is no data, about 45 is a fair sample, and a result at double the target cost after a normal window can be stopped. On low-volume accounts say "not enough data yet" and give the date or count when it will be.
- **Inside one ad set, spend allocation is the signal.** Meta shows different ads to the same person in sequence. An ad with heavy spend and a weak cost per result may be the first touch that makes the others convert, so don't recommend pausing it on its own numbers. Ads that Meta has stopped spending on are the ones that are safe to pause.
- **Compare like with like.** Same attribution setting, same event, same window length. Periods that straddle the 2026 attribution change, a switch to incremental attribution, or the switch to "Acquire new customers" are not comparable: reported results fall even when real results don't.
- **ROAS falls as spend rises.** Compare periods at similar spend, or compare profit after ad spend.
- **Platform numbers are not bank numbers.** Where the user has back-end figures, put them next to Meta's. Long sales cycles and recurring revenue are under-reported; heavy spend on existing customers flatters ROAS.
- **Check the dull explanations first:** a tracking fault, a paused ad set, a budget change, a disapproved ad, a stock-out, a promotion ending, a holiday, the normal Q4 CPM rise.

---

## 6. Playbooks

Each lists what to pull, what to check, and what to hand back. Load the named reference file for the judgment calls.

### A. First look at an account (audit)

Read `analysis-and-troubleshooting.md` (audit checklist, maturity levels).

1. Account basics (section 1) and the facts from section 2.
2. Structure and settings pull. Check, in order:
   - **Tracking:** is there a pixel or dataset with the conversion event firing; is the Conversions API connected; event match quality if the server exposes it. Are reported purchases or leads plausible against what the user says the business gets?
   - **Performance goal:** every Sales or Leads ad set optimising for the real conversion, not link clicks, landing page views, reach or an upper-funnel event without a volume reason.
   - **Fragmentation:** number of active campaigns and ad sets against weekly conversions. Count conversions per ad set per week. Many ad sets with a few conversions each is the most common structural fault.
   - **Hard limits:** narrow audiences, exclusions, restricted placements on conversion campaigns, old-style retargeting or lookalike ad sets.
   - **Budgets and bidding:** cost goals throttling spend, lifetime budgets without a reason, duplicated campaigns competing with each other.
3. Performance pull: 30 and 90 days at campaign and ad set level; 30 days at ad level for the main ad sets.
   - Deciding metric against break-even, by campaign.
   - The funnel chain for the main ad sets (hook rate → link click-through → landing page view rate → conversion rate): find the weakest link.
   - Creative inventory: how many active ads, how many formats and styles, how concentrated the spend is, how old the top spenders are, frequency trend.
4. Breakdowns: audience segments (if defined), placement for anything not conversion-optimised.
5. Report with template 9.1. Give the maturity level and the three changes that matter most. Typical order of value: fix tracking → fix the performance goal → consolidate → broaden creative → offer and economics.

### B. Weekly or monthly review

1. Same pull each time: last 7 days against the previous 7 and the last 30 (shifted back 2–3 days), campaign and ad set level; ad level for the main ad sets.
2. Report: spend, results, deciding metric against target; what changed and whether it is outside normal variation; fatigue signals (deciding metric worsening while frequency rises on the top spenders); new ads and whether they are getting spend; budget pacing.
3. Recommend no change when nothing warrants one. For a small account the right weekly answer is usually "leave it; next creative goes in on <date>".
4. Cadence by size: accounts with a handful of conversions a week are judged monthly; large accounts weekly or faster.

### C. "Results dropped": investigation

Read `analysis-and-troubleshooting.md` (pattern → cause → action).

1. Pin down the claim: which metric, which entity, from when. Pull daily rows for 30–60 days at account and campaign level and find the break point.
2. Decide what kind of drop it is:
   - **Step change on one day:** look for a cause on that day. Ask about and check: edits (budget, audience, ads paused or added), ad disapprovals, tracking changes or site releases, payment failure or spend cap, promotion ending, stock-out, attribution setting change. A budget increase followed by collapse matches the scaling fault reported in August 2026 (see `testing-and-scaling.md`).
   - **Slow slide over weeks:** fatigue (frequency rising on the same top ads), offer fatigue, or season. Compare with last year if the business is seasonal.
   - **Spend dropped, efficiency held:** delivery problem (cost goal too tight, audience too narrow, disapprovals, learning limited).
   - **Reported results dropped, back end didn't:** tracking or attribution, not performance.
3. Locate it: all campaigns or one; all ads or the main one; one placement, country or segment.
4. Walk the chain for the affected entity before and after: CPM, link click-through, landing page view rate, conversion rate. The first link that moved is where the cause is.
5. Report the most likely cause with the evidence, what was ruled out, one recommended action, and what would confirm it. Avoid restructuring a campaign in response to a few bad days.

### D. Creative analysis and brief

Read `creative.md`.

1. Pull ad-level performance for 30–90 days with creative details. For each ad record format (static, video, carousel, catalogue), style (founder, creator, UGC, testimonial, demonstration, and so on), angle or pain point, hook (first line and first scene, if known), spend share, deciding metric, hook rate and link click-through.
2. If the content can't be read through the MCP, ask the user to paste the copy or describe the top five ads. Don't infer style from ad names alone.
3. Summarise:
   - what the money is going to and what that says about what works;
   - the gaps in coverage: formats, styles, customer types, awareness stages or objections with no ad;
   - good hook with weak result (rework the body), weak hook with good result (new hooks on that body);
   - top spenders showing fatigue.
4. Brief the next batch: a small number of ads that differ from each other and from what is live, each with its angle, format, hook options, the proof it uses and the call to action. Include creator partnership ads if the account has none. Add new hooks for proven videos as the cheap volume.
5. Say how the new ads should enter the account (playbook E) and when they can be judged.

### E. Test readout

Read `testing-and-scaling.md`.

1. Identify what was tested, the method (ads added to the ad set, "Push delivery to this ad", creative testing tool, separate campaign) and the dates.
2. Pull results per arm on the deciding metric, with conversions per arm and spend per arm.
3. Verdict by evidence: leave out the first 1–2 days and the last 2–3; check conversions per arm; run a significance check on the two arms and act at about 85–90% confidence; otherwise extend, and say for how long at the current rate. Secondary metrics can explain a result but cannot decide it.
4. Next step: a winner in a testing campaign moves into the main ad set as a new ad (or stays, if added in place). Turn off losing near-duplicates. In a consolidated ad set, leave distinct lower-ROAS ads that still get spend, and pause the ones Meta has stopped spending on.
5. Record what was learned in a sentence that can guide the next brief.

### F. Budget and scaling decision

Read `testing-and-scaling.md`.

1. Check the preconditions with data: deciding metric better than break-even with room to worsen; stable over the last 2–4 weeks at current spend; fresh creative available; frequency not already high; no stock, staffing or cash limit (ask).
2. Pull the spend-versus-efficiency history (weekly spend and deciding metric for 90 days) to see how the account has reacted to earlier increases.
3. Recommend a step sized to the budget level and a date to review it, or an automated rule with a cap. State the expected fall in efficiency and the profit logic.
4. If results collapsed after a recent increase, see the workaround in `testing-and-scaling.md` before suggesting another.
5. If the preconditions fail, say what has to improve first (usually creative or the offer) instead of offering a smaller increase.

### G. Building a new campaign

Read `campaign-setup.md`, plus `lead-generation.md` or `ecommerce.md`.

1. Confirm the facts: offer, destination, conversion event and that it is tracked, locations served, daily budget, special ad category.
2. Write a build sheet and show it before creating anything:

```
Campaign   name · objective · budget level and amount · bid strategy · special category
Ad set     name · conversion location · performance goal · event · attribution setting
           locations · minimum age · languages · audience suggestions (if any)
           placements · schedule · value rules to apply (if any)
Ads        for each: name · format · media · primary texts · headlines · description
           call to action · URL (with tracking parameters) · enhancements on/off
```

3. After approval, create everything **paused**. Media usually has to be uploaded or reachable at a public URL first; if the server can't upload, list what the user must add.
4. Read back what was created from the API and compare it with the sheet. Defaults are sometimes applied silently (placements, attribution, enhancements, Advantage+ options).
5. List what the API could not set (section 8) with click paths, and ask the user to review and switch on.
6. Set the first review point by expected conversion volume, not a date picked from habit.

### H. Lead quality problem

Read `lead-generation.md`.

1. Pull lead campaigns: performance goal, conversion location (instant form, website, messaging, calls), form type if exposed, cost per lead trend, placement and age breakdowns.
2. Ask what "bad" means: fake details, unreachable, out of area, can't afford, not interested. Each has a different fix.
3. Usual order of fixes: qualify inside the form so unqualified people never count as a lead → "Higher intent" with SMS verification → optimise for a deeper event (qualified lead, booked call) once it reaches about 20–25 a week → feed CRM outcomes back → value rules for segments that close better → speed of follow-up, which is often the real problem.
4. Warn that cost per lead will rise; the measure is cost per qualified lead or per customer.

### I. Spend going to existing customers

Read `targeting.md` and `ecommerce.md`.

1. Check that audience segments are defined (if the breakdown returns "unknown", the user must define engaged audience and existing customers in Advertising settings, and should upload customer lists).
2. Pull the audience segments breakdown for 30 days: share of spend and of purchases by new, engaged and existing.
3. If the existing-customer share is small, leave it. If it is large and the business needs new customers, the options in order of preference are in `targeting.md` (customer lifecycle setting, incremental attribution, exclusions last). Warn that reported ROAS will fall after the change because existing customers are the cheapest conversions.

### J. Placement or audience problem

Read `targeting.md`.

1. Pull placement and platform breakdowns, or age and gender, for 30 days on the deciding metric.
2. Separate two cases. The campaign is not optimised for conversions → move it to a conversion goal if tracking allows; otherwise keep it off junk placements. The campaign is conversion-optimised → act only when a segment gets real spend with clearly worse results and the business agrees it is worth less.
3. The current tool is a value rule that lowers the bid for that segment (up to 90%), applied to each ad set. This usually has to be set up by the user in Ads Manager; give the path from `targeting.md`.
4. Re-pull the breakdown after enough conversions to see the effect.

### K. Scheduled monitoring

When the user wants a recurring check, keep it to a fixed, small report:

- Yesterday and the trailing 7 days: spend, results, deciding metric against target, CPM, link click-through, budget pacing.
- Alerts worth raising: deciding metric worse than target by a set margin over 7 days (for example ROAS down more than 20%, or cost per result above a ceiling the user sets); spend far off budget; an ad or account disapproved or restricted; a top ad's frequency passing the fatigue range with results falling; tracking going quiet (spend with no events).
- No automatic changes unless the user has defined the rule and its limits in advance (for example "pause any ad that spends 3× target cost per result with no conversion"). Report what was done each time.

---

## 7. Change protocol

Anything that creates, activates, pauses or edits affects real money and a learning system that punishes churn.

1. **Read before writing.** Fetch the object's current state immediately before changing it. Don't act on values remembered from earlier in the conversation.
2. **Propose in exact terms.** Object type, name and ID, field, current value → new value, and the reason. For budgets include currency and period ("daily budget €40 → €55").
3. **Wait for an explicit yes** to that specific proposal. A general "go ahead and optimise" is approval to propose, not to spend. Approval of one change does not carry to the next batch.
4. **Prefer the reversible move.** Pause instead of delete. Create paused instead of live. Add a new ad instead of editing a live one: editing restarts learning, can lose the ad's accumulated engagement, and can switch creative enhancements back on.
5. **Batch.** Put the week's changes into one sitting per campaign, then leave it. Several small edits over consecutive days keep it permanently relearning.
6. **Verify.** Read the object back after the call and confirm the change took and nothing else moved. Report failures and partial results plainly.
7. **Log.** Give the user a dated change note: what changed, why, the review date and the number that will decide whether it worked.
8. **Don't touch what is working.** No edits to a profitable campaign's audience, performance goal, attribution setting or bid strategy without a test that says to. Switching a proven campaign's optimisation is a test, not housekeeping.

Never do these without the user asking for them specifically: activate something that has never run, raise a budget, remove an account-level limit, delete anything, change the payment or account settings.

## 8. What usually has to be done in Ads Manager by the user

MCP servers expose only part of the product. Expect to hand these over with a click path from the relevant reference file, and ask the user to confirm when done:

| Task | Where the detail is |
|---|---|
| Value rules (create the rule set, then enable it on each ad set) | `targeting.md` |
| Defining audience segments (engaged audience, existing customers) and uploading customer lists | `targeting.md` |
| Customer lifecycle setting ("Acquire new customers") | `targeting.md`, `ecommerce.md` |
| Instant forms: form type, questions, conditional logic, SMS verification, booking | `lead-generation.md` |
| Creative enhancement toggles and "personalized destinations" | `creative.md` |
| "Push delivery to this ad" and the creative testing tool | `testing-and-scaling.md` |
| Partnership ads and Creator Marketplace | `creative.md` |
| Automated rules | `testing-and-scaling.md` |
| Conversions API setup, event match quality, CRM connection | `tracking-and-attribution.md` |
| Appeals, business verification, support | `account-health-and-policy.md` |

If a server does expose one of these, use it under the change protocol.

## 9. Report templates

### 9.1 Account audit

```
ACCOUNT AUDIT: <account> · <dates> · <currency> · attribution: <setting>

Verdict
  <Two sentences: is it working against break-even, and the main constraint.>

Numbers
  Spend <x> · Results <n> · Cost per result / ROAS <y> · Break-even <z> (from margin <m>)
  Per campaign: <name> spend · results · deciding metric · share of spend

Maturity: Level <1–5>: <one line why>

Findings (most valuable first)
  1. <What the data shows, with figures> → <why it matters> → <action>
  2. …
  3. …

Leave alone
  <What is working and should not be edited.>

Plan
  Now:       <changes to make, who makes each>
  Next:      <creative or offer work, with a brief if asked>
  Review on: <date or conversion count>

Not visible
  <Margins, back-end revenue, lead outcomes, creative content, etc. that were not available.>
```

### 9.2 Periodic review

```
<period> vs <previous period> (both ending <date>, most recent days excluded)

Spend <x> (<±%>) · Results <n> (<±%>) · Deciding metric <y> (<±%>) vs target <t>
Read: <normal variation | real change because …>

Creative: <top ads by spend with deciding metric; fatigue signals; new ads getting spend or not>
Actions: <none | the one or two changes proposed, with reasons>
Next check: <date>
```

### 9.3 Change note

```
<date> · <account>
Changed:  <object name (ID)>: <field> <old> → <new>
Why:      <evidence in one line>
Expect:   <what should happen, including any short-term dip>
Judge on: <date or conversion count> by <metric and threshold>
Undo:     <how to reverse it>
```

### 9.4 Test readout

```
Test:    <what differed> · method <…> · <dates>
Arms:    <name> spend · conversions · deciding metric   (repeat per arm)
Verdict: <winner | no difference | not enough data: needs about <n> more conversions, ~<time>>
Why:     <supporting metrics, one line>
Next:    <what happens to each arm; what to test next>
```

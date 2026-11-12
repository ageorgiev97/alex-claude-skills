---
name: meta-ads
description: Expert Meta (Facebook / Instagram) ads strategy and hands-on account work, current to November 2026 - Andromeda, the unified Advantage+ setup, value rules, and the 2026 targeting-control and attribution changes. Use this skill whenever the user asks to audit, analyse, diagnose, plan, build, test, scale or fix Meta, Facebook or Instagram ads; mentions Ads Manager, campaigns, ad sets, ROAS, CPA, CPL, CPM, hook rate, creatives, lead forms, pixel or Conversions API; asks things like "why did my results drop", "should I raise the budget" or "what ads should I make"; wants ad copy, hooks, creative briefs or offers for paid social; or whenever a Meta Ads MCP server's tools are available or about to be called, even if the user doesn't name the skill. General knowledge of Meta ads from before 2025 is out of date in ways that lose money, so consult this skill before advising.
---

# Meta Ads

Strategy and operating knowledge for advertising on Meta (Facebook, Instagram, Messenger, WhatsApp, Threads), written to be used with a Meta Ads MCP server: read the live account, diagnose it, recommend changes, and make them when the user approves.

## How to use this skill

1. Read "What changed" and "Operating model" below before giving advice. They replace habits that were correct until about 2024 and now cost money.
2. For anything beyond a quick answer, open the reference file for the task (see "Reference files"). The exact numbers, setting names and click paths are there, not here.
3. With an MCP connected, follow `references/mcp-playbooks.md` for what to pull, how to compute the metrics, and how to make changes safely.

### Sources and currency

The knowledge is synthesised from about 250 videos by one practitioner whose agency manages a large volume of Meta spend, weighted towards 2026. Where older and newer advice conflict, this skill states the newer advice as the rule.

- Tags such as `[v043]` in the reference files cite the source video. A lower number is newer: v001–v047 are 2026, v048–v100 are 2025 to early 2026, v101–v139 are 2024, higher numbers are older. If two statements ever conflict, prefer the lower number. `references/sources.md` maps tags to titles and links.
- Platform facts are as of November 2026. Meta rolls features out account by account and renames them often. If the account doesn't show an option described here, say so and use the fallback; if the user's account shows something newer, trust the account.
- The thresholds are a practitioner's working rules, not guarantees from Meta. Present them that way, and let the account's own history override a generic benchmark.

## What changed (read first)

| Old habit | Current practice (late 2026) |
|---|---|
| Many campaigns and ad sets split by interest, lookalike, placement and funnel stage | One campaign, one ad set, warm and cold audiences together, many different ads. Split only for a named reason. |
| Targeting is the main lever | Delivery is personalised per person (the "Andromeda" system, broadly live since late 2025). The ads themselves do the targeting; most audience inputs are only suggestions. |
| Separate retargeting campaigns, lookalike stacks, one interest per ad set | Retargeting happens inside the one ad set. Custom audiences go in as suggestions. Separate warm campaigns only for a warm-only offer or message. |
| 3–6 ads per ad set | The cap is gone. Aim for many genuinely different ads (20+ at scale). Near-duplicates are collapsed into one. |
| Pause the ads with the worst ROAS inside an ad set | Don't. Meta sequences ads per person, so a low-ROAS ad may be feeding the high-ROAS ones. Pause what Meta has stopped spending on. |
| Hard-exclude genders, placements, devices | Gender is no longer a hard control (November 2026) and manual placement, platform and device selection is being removed (from September 2026). Steer with value rules instead. |
| Warm up a new pixel with traffic or engagement campaigns | Optimise for the real conversion (Sales or Leads) from day one. |
| "Raise the budget 20% every few days" | Step size depends on budget level: large jumps are fine at tiny budgets, small ones at large budgets. Or automated rules at about 3% a day. |
| "More volume" lead forms, add friction later | The default is moving to "Higher intent" forms with SMS verification and conditional logic that screens out unqualified people, so Meta learns only from good leads. |
| Video is the best format | Statics now win for most advertisers; keep several formats in the same ad set and let Meta allocate. |
| Test with separate ad sets per creative | Use the ad-level tools ("Push delivery to this ad", the creative testing tool) or a testing campaign at high volume. |
| Click-through attribution counts any click | Since 2026 it counts link clicks only; other interactions fall in a new 1-day "engage-through" category. Reported numbers across the change are not comparable. |

The full changelog, the glossary of current feature names and the complete list of reversed advice are in `references/platform-changes.md`.

## Operating model

1. **Economics before ads.** Work out what a customer is worth and what the business can pay to get one before judging any metric. Break-even cost per purchase = average order value × gross margin. Break-even cost per lead = first-sale value × gross margin × lead-to-customer rate. Break-even ROAS = 1 ÷ gross margin. Without these, a CPM, CTR or CPA is neither good nor bad. "Plenty of conversions but no profit" is a business-model problem that no account change fixes; raising customer value (order value, repeat purchase, subscription, close rate) usually beats shaving cost per result. See `references/offers-and-economics.md`.

2. **Leverage order: offer, then creative, then everything else.** The large wins in the case studies come from a better offer or a different kind of ad, not from settings. Structure, targeting, budgets and tracking need to be not-wrong; after that they move results by tens of percent, while offer and creative move them by multiples. When an account is weak, look at the offer and the ads before the settings.

3. **Meta optimises literally for what you ask.** The performance goal matters more than the objective. A Sales campaign told to maximise link clicks behaves like a traffic campaign. Ask for the real outcome: purchases (or purchase value) for stores, qualified leads for lead generation, using the deepest funnel event that still gets about 20–25 conversions a week. Then improve the signal: screen out unqualified leads before they count, feed CRM outcomes back, and use value optimisation where order values differ.

4. **Consolidate.** Conversions per ad set are what the system learns from, and overlapping ad sets compete with each other and disturb the sequence of ads each person sees. Default to one campaign with one ad set. Legitimate reasons to split: different product ranges or offers, different countries or service areas, a warm-only offer, a testing campaign at high conversion volume, and the omnipresent content campaign for high-ticket trust-based sales (a deliberate exception, see `references/local-and-high-ticket.md`).

5. **Targeting is broad, with few hard limits.** Hard limits ("Controls"): the locations you can serve, a minimum age, languages, and custom-audience exclusions. Everything else (age range, gender, interests, custom audiences, lookalikes) is a suggestion Meta may go beyond. When Meta spends on people who are worth less to the business for reasons it cannot see (lifetime value, close rate), adjust bids with value rules rather than restricting the audience. See `references/targeting.md`.

6. **Creative volume and diversity is the main ongoing job.** Diversity means different formats (static, video, carousel) and different styles (founder, creator or partnership, UGC, testimonial, demonstration, and so on) aimed at different customer types, pain points and awareness stages. Twenty background-colour variants are one ad. Creator partnership ads are the most reliably strong single lever. New hooks on a proven video are the cheapest way to make new ads. See `references/creative.md`.

7. **One metric decides; the rest explain.** ROAS (stores) or cost per result for the deepest tracked event (lead generation) decides whether something worked. CPM, CTR, hook rate and frequency only help explain why. Never pause something with a good primary metric because a secondary metric looks weak, and never keep something with a bad primary metric because its CTR is high.

8. **Judge by conversion volume, not days.** A handful of conversions is no evidence, however long it took. An account with 3 conversions a week needs about a month to answer a question that an account with hundreds a day answers by the afternoon. The last 2–3 days of data are incomplete and partly modelled; one bad day is noise.

9. **Leave it alone.** Each significant edit restarts learning. Make changes in batches, roughly weekly at most, less often on small budgets. A small account needs 1–2 hours a month inside Ads Manager; time beyond that is better spent on creative and the offer.

10. **Test deliberately, scale with headroom.** Testing lowers short-term results, so spend a set share on it (about 10–20% when things are profitable, far more when nothing works) and reserve it for big differences: offer, angle, style, format, hook. Scale only when results are comfortably better than break-even, because cost per result rises with spend. See `references/testing-and-scaling.md`.

11. **Meta's numbers are a model; the back end is the truth.** Pixel plus Conversions API is the minimum. Meta under-reports long sales cycles and recurring revenue and can over-report on existing customers. Reconcile with the store, CRM or bank before big decisions. See `references/tracking-and-attribution.md`.

12. **Filter Meta's own advice.** Opportunity score, the AI business assistant, in-product prompts and reps are useful for finding setup faults and are tuned to the average advertiser. Be sceptical of anything that amounts to "spend more", and don't switch on automatic adjustments.

13. **Fit the advice to the business.** What is right for a store with 500 purchases a week is wrong for a clinic with 5 leads a week. Establish business type, price point, budget and weekly conversion volume before recommending structure or tests.

## Working with a Meta Ads MCP

`references/mcp-playbooks.md` has the detail. The shape of every task:

1. **Discover.** Look at which tools the connected server offers and whether they can write. Confirm the ad account if there is more than one. Tool names differ between servers; map them to capabilities rather than assuming.
2. **Orient.** Establish business type, the deciding metric, the break-even figures and the monthly budget. The API cannot tell you margin, lifetime value, close rate, lead quality, stock or what the CRM shows. Ask for the few of these the task depends on; don't interrogate.
3. **Pull.** Account settings and structure first, then performance at campaign, ad set and ad level over several windows (7, 14, 30 and 90 days), then breakdowns where a question calls for one. Leave the most recent 2–3 days out of judgments.
4. **Diagnose in this order:** tracking sanity → economics → setup faults (wrong performance goal, fragmented structure, hard limits) → the funnel chain (hook rate → link click-through → landing page view rate → click-to-conversion rate) → creative mix → who and where the money went (audience segments, placements).
5. **Recommend.** A few changes ranked by expected effect, each with the evidence, the action, and what to check afterwards and when. Say what you could not see.
6. **Change, only with approval.** State exactly what will change (object, field, from → to) and wait for a clear yes. Create things paused. Pause, never delete. Batch the changes and record them.
7. **Follow up.** Name the date or conversion count at which the change can be judged.

## Quick reference

### Default setup for a conversion campaign

| Setting | Default | Deviate when |
|---|---|---|
| Objective | Sales or Leads, including in a brand-new account | Awareness only for the omnipresent content campaign or very large brands |
| Performance goal | The real conversion: maximise number of conversions on Purchase or Lead; maximise value of conversions for stores with varied order values once purchases are steady | Never link clicks, landing page views, reach or impressions inside a Sales or Leads campaign |
| Conversion event | Deepest funnel event with about 20–25+ conversions a week | Step one event up the funnel only when volume is below that |
| Structure | One campaign, one ad set | See operating model, point 4 |
| Audience | Advantage+ audience; hard controls only for location, minimum age, language | A demonstrated problem; prefer value rules to hard limits |
| Placements | All placements | For anything not optimised for a conversion, keep off Audience Network |
| Budget | Daily budget, set at campaign level | Ad set budgets to force spend in a testing campaign; lifetime budget only where ad scheduling needs it |
| Bidding | Highest volume, no cost goal | A cost-per-result goal for thin margins or hands-off accounts |
| Attribution setting | The default (7-day click, 1-day view, 1-day engage-through) | Incremental attribution for large advertisers with big customer bases |
| Ads | Several formats and styles in the same ad set; start with about 4 very different ads and keep adding | - |
| Creative enhancements | Review each one; switch off those that rewrite text, alter people or redirect the destination | Re-check after every edit, duplicate or preview, because they switch themselves back on |

Detail: `references/campaign-setup.md`.

### Structure and testing by conversion volume

| Optimised conversions per week | Structure | How to introduce new ads |
|---|---|---|
| Under about 50 | One campaign, one ad set, one offer. No separate testing campaign: the split starves both sides. | Add clearly different ads to the same ad set and let Meta allocate. For a big change that needs a verdict, "Push delivery to this ad", one ad at a time. About one meaningful test a month on very small budgets. |
| About 50–100 | One campaign per offer or product range | The same in-ad-set tools; the creative testing tool (2–7 ads) becomes practical as volume reaches dozens a week |
| 100–200 and above | Campaigns per product range, offer or market; a separate testing campaign is reasonable | Creative testing tool in batches, or a testing campaign with roughly 10–30% of budget; a fixed weekly production rhythm |

Near-identical variants (same ad, different hook or overlay) need the creative testing tool at any volume, because delivery may treat them as one ad.

### Benchmarks (diagnostic only)

| Metric | How it is computed | Reading |
|---|---|---|
| Hook rate | 3-second video plays ÷ impressions | Above 10% fine, below 5% poor; creator ads can reach 30%+ |
| Link click-through rate | Link clicks ÷ impressions (never "all clicks") | Below 0.5% poor, above 1% decent, 1.5% very good, 2% and above excellent |
| Landing page view rate | Landing page views ÷ link clicks | Losing 20–25% is normal; losing 50%+ points to page speed or junk placements |
| Click-to-purchase rate (stores) | Purchases ÷ link clicks | 2–5% is normal; below 2% is weak |
| Frequency | Impressions ÷ reach | Cold audiences: above about 2.5 with falling results suggests fatigue. Warm audiences tolerate 6–8. |
| CPM | Spend ÷ impressions × 1,000 | Not a goal. High CPMs are normal in expensive markets and often mean a better audience. |

Detail and the full set: `references/analysis-and-troubleshooting.md`.

### What the pattern usually means

| Pattern | Likely cause | Where to work |
|---|---|---|
| Spend but no conversions at all | Offer, price or product; or broken tracking | Check tracking first, then the offer |
| Some conversions, low hook rate or click-through | Creative | New styles, formats, hooks |
| Strong hook rate, weak result | Good opening, weak body or offer | Rework the body; keep the hook |
| Good click-through, few conversions | Landing page, checkout or ad-to-page mismatch | Page and funnel |
| Conversions arrive but there's no profit | Unit economics | Order value, repeat purchase, price, close rate |
| Results fall slowly while frequency climbs | Creative fatigue, then offer fatigue | Visibly different ads; later, a restructured offer |
| Results collapse when budget rises | Ads only convert the warmest buyers | Better ads and offer for colder people; scale in smaller steps |
| Sudden drop with no change made | Tracking fault, season, stock, a platform bug, attribution change | Rule these out before touching the campaign |
| Cheap leads, poor quality | Meta is optimising for form fills | Qualify inside the form, verify phone numbers, feed back outcomes |
| Great ROAS that doesn't show in the bank | Spend going to existing customers | Audience segments breakdown, then the customer lifecycle setting |

### Scaling in one paragraph

Scale the existing campaign; never run duplicates side by side. Preconditions: profitable with headroom below break-even, enough fresh creative, and no stock or capacity limit. Either automated rules (raise about 3% a day when recent cost per result is under target, with a cap, plus a mirror rule that lowers it) or manual steps every 5–10 days, starting as high as +100% at very small budgets and tapering to about +20% or less as spend grows. Expect ROAS to fall as spend rises and judge by absolute profit. Detail: `references/testing-and-scaling.md`.

### By business type

| Business | Deciding metric | Read |
|---|---|---|
| Online store | ROAS, then profit after ad spend | `references/ecommerce.md` |
| Lead generation (forms, calls, quotes) | Cost per qualified lead or booked call, then cost per customer from the CRM | `references/lead-generation.md` |
| Local business | Cost per booking or enquiry within the service area | `references/local-and-high-ticket.md` |
| High-ticket, expertise or trust-based (customer value roughly $1,000+) | Cost per qualified call, judged over months | `references/local-and-high-ticket.md` (omnipresent content campaign) |
| Small budget (under about $3,000 a month) | Cost per conversion against break-even | One campaign, one ad set, one offer; model proven competitor ads; be patient |

## Reference files

Read the one or two that match the task. Each begins with a contents list.

| File | Read it when |
|---|---|
| `references/mcp-playbooks.md` | Any task that touches a live account through an MCP: tool mapping, data pulls, computed metrics, the audit / weekly review / drop investigation / test readout / scaling / launch playbooks, the change protocol, report templates |
| `references/analysis-and-troubleshooting.md` | Reading performance data, benchmarks, breakdowns, the pattern → cause → action table, audit checklist and maturity levels |
| `references/platform-changes.md` | You are unsure whether a practice or feature is current; the user mentions a feature name you don't recognise; before repeating anything you "know" about Meta ads |
| `references/campaign-setup.md` | Building or restructuring campaigns: objectives, performance goals, budgets, bidding, learning phase, setting-by-setting checklists |
| `references/targeting.md` | Audience questions: controls versus suggestions, custom audiences, retargeting today, customer lifecycle, value rules |
| `references/creative.md` | Deciding what ads to make, writing hooks, scripts, copy or creator briefs, reviewing an ad, creative enhancements, fatigue |
| `references/testing-and-scaling.md` | Whether a test has enough data, which testing method to use, what to do with winners and losers, whether and how to raise budget |
| `references/offers-and-economics.md` | Unit economics, break-even targets, lifetime value, offer design, pricing, funnel choice by price, landing pages |
| `references/lead-generation.md` | Lead campaigns: instant forms, qualification, booking, messaging and WhatsApp, lead quality, follow-up |
| `references/ecommerce.md` | Stores: value optimisation, existing customers, order value, sale events, omnichannel |
| `references/local-and-high-ticket.md` | Local, service and high-ticket businesses; the omnipresent content campaign; brand and organic |
| `references/tracking-and-attribution.md` | Pixel and Conversions API checks, event choice, attribution windows and the 2026 change, incremental attribution, gaps against back-end numbers |
| `references/account-health-and-policy.md` | New accounts, policy and disapprovals, restricted or disabled accounts, support routes, Meta's own recommendations |
| `references/sources.md` | The user asks where a claim comes from |

## Reporting findings

Lead with the answer, in the user's terms. A good account review has this shape:

```
Verdict        One or two sentences: is it working, and the single biggest issue.
The numbers    Spend, results, cost per result or ROAS for the period, against the
               break-even or target. State the window and the attribution setting.
What's wrong   3–5 findings, most valuable first. Each: what the data shows
               (with the figures), why it matters, what to do.
What's fine    The things to leave alone, so they don't get "fixed".
Do next        The ordered actions, who does each (you through the MCP, or the
               user in Ads Manager with the click path), and when to judge them.
Couldn't see   What the data didn't show and what the user needs to supply.
```

Keep recommendations few. Ten suggestions get none done; three ranked ones get done. Say how confident the data allows you to be: with 6 conversions in the window, say so rather than drawing a conclusion.

## Guardrails

- **Spending money needs a yes.** Creating, activating, pausing, or changing a budget, bid or audience on a live account affects real spend. Describe the exact change and get explicit approval first; approval for one change does not cover the next. Create new objects paused so the user reviews them before they spend.
- **Don't act on thin data.** No pausing, scaling or declaring winners on a day's results or a few conversions. If the honest answer is "too early", give it, with the point at which it will be answerable.
- **Leave winners untouched.** Don't edit a live ad or ad set that is performing; edits restart learning and can re-enable creative enhancements. Add new things beside it.
- **Report only what the data shows.** If the MCP doesn't return a metric, say so; don't estimate it silently. Mark computed metrics as computed. Keep Meta-reported results distinct from back-end results.
- **Stay inside the policies.** No invented testimonials, results or scarcity. Avoid copy that asserts personal attributes about the reader ("Are you overweight?"). Flag special ad categories (credit, employment, housing, social issues and politics, and similar regulated areas) before building. See `references/account-health-and-policy.md`.
- **Date what you say about the platform.** Features and names move. When something here may have changed, say "as of late 2026" and suggest checking the account.
- **Know the edge of the knowledge.** This skill covers Meta. For cross-channel budget questions give the Meta view and say that's what it is.

# Platform changes, current names and reversed advice

What changed in Meta ads between 2024 and November 2026, what each current setting is called and where it lives, and which older rules are now wrong. Read this before giving any advice from memory about structure, targeting, placements, creative volume, testing, attribution or lead forms, and whenever an account shows an option you do not recognise.

## Contents
- How to use this file
- Changelog, newest first
- Glossary of current names
- Old name to current name
- What did not change
- Outdated advice to ignore (master table)

## How to use this file

- Where a habit from general knowledge disagrees with this file, this file wins. Where this file disagrees with what the live account shows (an option missing, renamed or moved), the account wins: say what you see and adapt.
- Meta rolls features out unevenly and they are often buggy at first. Before recommending a feature, check that the account has it. Entries say "rolling out" or "some accounts" where that was reported.
- Dates are when a change was reported, not official release dates. Within 2025 the sources carry few firm dates, so the split between the two halves of 2025 follows the order in which changes were reported and may be off by a few months.
- Each entry points to the reference file that owns the detail. This file only says what changed and what to do about it.

Abbreviations: ROAS = return on ad spend; CPM = cost per 1,000 impressions; CTR = click-through rate; CPA = cost per acquisition; CAPI = Conversions API; LTV = customer lifetime value; OPC = omnipresent content campaign; ASC = Advantage+ shopping campaign; CBO / ABO = campaign / ad set budget optimisation; UGC = user-generated-style content.

## Changelog, newest first

### 2026, second half (July to November)

| When | What changed | Practical consequence | Detail |
|---|---|---|---|
| Autumn 2026 (about November) | Gender removed from the hard audience controls in all campaigns. A gender selection is now only a suggestion ("We'll also show ads beyond your selected gender when it's likely to improve performance"). A new ad-level option, "Choose an audience for each ad creative" (age and gender per creative), is also only a suggestion. | Targeting can no longer confine delivery to one gender. If one gender is a proven problem (engages but never buys), apply a value rule that decreases its bid by 90%, the maximum. Otherwise let Meta allocate. [v002] | `targeting.md` |
| Autumn 2026 (poll in October) | Static images now win more often than video. Poll: static 54%, video 38%, other 8% (video led with 44%, then 53%, then 60% in earlier years). Agency data shows Meta giving statics more budget inside mixed-format ad sets. | Keep several formats in each ad set and raise the share of statics (a cheaper route to volume), each one aimed at a specific buyer slice. Keep video for new concepts and for expertise offers to cold audiences. [v003] | `creative.md` |
| October 2026, rolling out (about half of accounts) | "Push delivery to this ad": ad level > Ad setup > "Show more settings". Reserves a share of daily budget (default 20%) for one new ad for a set period (default 7 days), after which the ad competes normally. | New ads can be tested inside the existing ad set, one at a time, without a separate testing campaign. It and the creative testing tool cannot be active in the same campaign at the same time. [v005] | `testing-and-scaling.md` |
| Autumn 2026 | Customer lifecycle setting at ad set level in sales campaigns: "Get conversions from all audiences" (default) or "Acquire new customers". Website purchase custom audiences can now look back 730 days (was 180). | Leave the default unless the audience-segment breakdown shows a large share of spend or purchases going to existing customers. Switching makes reported ROAS worse. Update purchase audiences to 730 days. [v006] | `targeting.md`, `ecommerce.md` |
| Autumn 2026 | Ads Creative Studio (All tools > Advertise): creative insights against editable "minimum performance thresholds", comparison with industry top performers, and "Scale top creatives" (new video hooks, subtitles, AI voiceover; image resize, animate, restyle). Hook rate, hold rate and ThruPlay are native metrics. | Use it to make variations of proven winners and check every output. Hook rate no longer needs a custom metric. [v007] | `creative.md`, `analysis-and-troubleshooting.md` |
| Autumn 2026 | Meta One subscription replaces or extends Meta Verified, per platform: Essential ($14.99/month), Advanced ($50/month), Expert, Max. Human support cases start at Advanced (1 a month). | Advanced is the suggested tier for businesses that depend on Meta, for the verified badge and human support. [v009] | `account-health-and-policy.md` |
| September 2026 onward, rolling out | Ad-set placement controls, platform choice (Facebook only or Instagram only), and device and operating-system targeting are being removed. | Small effect on Sales or Leads campaigns optimised for a real conversion. Large effect on traffic, engagement and awareness campaigns, where Meta buys the cheapest inventory (Audience Network). Fixes, in order: move to Sales or Leads; account-level placement controls; a value rule by placement at -90% (Threads and Messenger cannot be handled this way). Check Breakdown > Placement before and after. [v002, v010] | `campaign-setup.md`, `targeting.md` |
| Autumn 2026 (about September) | Creative enhancements switch themselves back on when an ad is duplicated, edited (even just the text) or previewed. New enhancement "Personalized destinations" lets Meta send clickers to a different URL on the site. | Re-open the enhancements after touching any ad, especially in regulated industries. Turn "Personalized destinations" off whenever the funnel depends on a specific landing page. [v012] | `creative.md` |
| By autumn 2026 | The creative testing tool accepts 2 to 7 test ads (was 2 to 5). | Larger batches are possible, but only at high conversion volume. [v005, v013] | `testing-and-scaling.md` |
| Summer 2026 | Scaling bug in a number of accounts: raising the budget of a winning campaign or ad set made results collapse by 90% or more. | If that happens, duplicate at the higher budget and turn the original off. This is a temporary workaround, not a return to scaling by duplication. [v016] | `testing-and-scaling.md` |
| Summer 2026; global rollout expected about October 2026 | Instant forms can end with a calendar booking: form ending > Additional action > "Book time" > paste a scheduling link (Calendly and GoHighLevel at launch). Newly created forms only. | Call-booking funnels can run on instant forms. The lead is captured even if no slot is booked. [v018] | `lead-generation.md` |
| Summer 2026 | An official Meta MCP connector for Claude exists: reads the account, uploads creative, creates campaigns, ad sets and ads, reports results. [v020] | See the change protocol before writing anything. | `mcp-playbooks.md` |

### 2026, first half (January to June)

| When | What changed | Practical consequence | Detail |
|---|---|---|---|
| Mid 2026 | Meta AI business assistant is inside Ads Manager for most accounts (colour-wheel icon, left side). It analyses selected campaigns, compares with industry benchmarks, suggests changes (some one-click) and handles account issues. | Use it for analysis and ideas and as the first stop for account problems. Filter its advice: it recommends settings already on, low-impact enhancements, and budget increases. [v007, v024] | `account-health-and-policy.md`, `analysis-and-troubleshooting.md` |
| First half of 2026 | Disabled-account recovery gains a new route: facebook.com/business/help > AI business assistant (or "Get support") > work through its steps, then ask for a human agent. | Use after "Request review". Complete business verification in advance. [v027] | `account-health-and-policy.md` |
| Spring 2026, rolling out quickly | Attribution redefined. Click-through now requires a link click (before, any click on the ad opened the 7-day window). New "engage-through" category, 1 day, holds likes, comments, shares, media clicks, "see more" clicks and video plays of 5 seconds or more. View-through stays at 1 day. | Reported conversions fall, most for video-heavy and long-sales-cycle accounts (one campaign: 415 link clicks against 1,179 clicks of all kinds). Do not compare periods across the change; check back-end sales. Keep the widest windows. [v032] | `tracking-and-attribution.md` |
| First half of 2026 | Ads Library adds sorting by "Impressions: high to low" and an "Active and inactive" filter. | Rank competitor ads by impressions plus run time, not run time alone. [v031] | `creative.md` |
| Spring 2026, some accounts | "Describe your audience": free text (up to 2,000 characters) that Meta's AI turns into detailed targeting options. Buggy at launch. | Low value. The output is still only a suggestion. Treat as a time saver. [v035] | `targeting.md` |
| Early 2026 | Value rules are in nearly all accounts and work with leads, sales and other objectives. Criteria: age, gender, location, conversion location, device, mobile operating system, placement. Up to 2 criteria per rule and 10 rules per set; increase or decrease the bid by a percentage (decrease up to 90%). | The main steering tool now that most targeting inputs are suggestions. Use it for value Meta cannot see (LTV, close rate, refunds), with percentages from real data. [v028, v033] | `targeting.md` |
| Early 2026 | Creative testing tool at ad level ("Creative testing" > "Set up test"): guaranteed delivery to each test ad, non-overlapping audience splits, default 7 days, default comparison metric cost per engagement. | Change the metric to cost per lead or purchase. Use for detail and hook tests on winners. [v044, v048] | `testing-and-scaling.md` |
| Early 2026 | "Maximize value of conversions" becomes the standard choice for new sales campaigns with varying order values. The option stays hidden until the conversion location is a single location such as "Website". Also usable for website leads when different lead values are passed back. | Needs pixel plus CAPI sending values. Do not switch a long-running winner without test evidence. [v024, v045] | `campaign-setup.md`, `ecommerce.md` |
| Early 2026 | Threads is listed as a fifth platform in placements (with Facebook, Instagram, Audience Network, Messenger). | Nothing to do in conversion campaigns: leave all platforms on. [v047] | `campaign-setup.md` |

### 2025, second half

| When | What changed | Practical consequence | Detail |
|---|---|---|---|
| Late 2025 (announced December 2024) | Andromeda, Meta's new ad retrieval system, is live for the vast majority of advertisers. It selects ads per individual instead of per interest group. Near-duplicate ads may be treated as one ad, with only one entering the auction. | Many distinct ads per ad set (20+ as the aim), funnel stages mixed in one ad set, a simple structure. Budget concentrating on 1 to 3 ads is normal. A results drop is not automatically Andromeda: rule out seasonality and Q4 CPM inflation first. [v044, v055] | `creative.md`, `campaign-setup.md`, `testing-and-scaling.md` |
| Late 2025 | Frequency cap added to the Engagement objective. | The omnipresent content campaign can use Awareness (broad markets) or Engagement (niche or local markets). [v054] | `local-and-high-ticket.md` |
| Late 2025, some accounts | Ad sequencing reaches the Auction buying type (was Reservation only). Requires Awareness or Engagement objective, ad set budgets, frequency control and a lifetime budget. | Optional. The omnipresent content campaign still uses separate ad sets with daily budgets. [v054, v057] | `local-and-high-ticket.md` |
| Late 2025 | WhatsApp becomes a main surface. Leads: conversion location WhatsApp with "Maximize number of conversations" (not available in Europe, where Ads Manager forces link clicks). Sales: "Message destinations" with "Maximize number of conversions" and the Purchase event. Status ads and promoted Channels exist but not for everyone. Business AI on WhatsApp is in testing. | Worth testing where buyers have questions before buying and in WhatsApp-heavy countries. [v051] | `lead-generation.md` |
| 2025 | Incremental attribution: a second attribution model at ad set level ("Standard" or "Incremental"). It changes delivery as well as reporting: Meta shows fewer ads to people it predicts would convert anyway. At launch only for Sales campaigns with a website conversion location optimising for purchases; if the option is missing, the setup does not qualify. | For larger advertisers with big customer bases, not beginners. Reported results look worse and cannot be compared with standard attribution. [v013, v072] | `tracking-and-attribution.md` |
| 2025 | Leads campaigns gain: conversion location "Website and instant forms" in one ad set (Meta picks per person); flexible form delivery (on by default); "Follow up with leads" chat on Messenger or Instagram; end-page actions including WhatsApp chat and promo codes. | Test the combined location if unsure which to use. Leave flexible form delivery on unless legally required fields must always show. [v067] | `lead-generation.md` |
| 2025 | Value rules begin rolling out. [v073] | See the early 2026 entry for the current state. | `targeting.md` |
| 2025 | Meta's Reels guidance: build vertical 9:16, sound on, inside the safe zone (Meta figures: +13% ROAS, -16% CPA). | Vertical is the first asset to make. [v066] | `creative.md` |
| 2025, in testing | Business AI inside ads: the ad answers product questions by voice or tappable question chips, recommends products and can offer discounts. Nothing to configure yet. | Keep product information, FAQs, discount and shipping policies documented. Aimed at lower-ticket sales. [v071] | `ecommerce.md` |

### 2025, first half

| When | What changed | Practical consequence | Detail |
|---|---|---|---|
| 2025, staggered over about 6 months; the norm by late 2025 | Advantage+ structure unified. No more choice between "Advantage+ shopping campaign" and "manual sales campaign", or between "tailored" and "manual" leads campaigns. One three-level setup; audience split into "Controls" (hard) and "Suggest an audience" (soft); manual targeting reached through "Further limit the reach of your ads" > "Switch setup". | Advantage+ is now a state, shown as on when audience, budget and placements all follow Meta's defaults. Hard targeting needs a specific reason. Click paths in older tutorials no longer match. [v076, v089] | `campaign-setup.md`, `targeting.md` |
| 2025 | Campaign score (0 to 100) in the right-hand panel of campaign setup, with "Apply" buttons. | A high score is fine; 100 is not required when each deviation is deliberate. If results are poor and the score is low, fix the score first. [v029, v089] | `campaign-setup.md` |
| 2025 (limited testing at first; standard practice by 2026) | Instant forms: autofill can be switched off per contact field, and "Require SMS verification to submit form" is added. | Both raise cost per lead and raise contactability. SMS verification is the stronger of the two. [v011, v083] | `lead-generation.md` |
| 2025 | Omnichannel ads: sales campaign > ad set > Conversion location > "Website and in-store". Needs physical stores, CAPI sending offline conversions, and an event match quality of at least 4.8. | Test for any business with both online and store sales (Meta's test: 16% lower cost per omni purchase). [v086] | `ecommerce.md` |
| 2025 | Threads ads begin as a limited test with image ads. | See the early 2026 entry. [v090] | `campaign-setup.md` |
| 2025 | Creator Marketplace opens up (All tools > Engage audience > Creator Marketplace; covers Facebook and Instagram by 2026). | The standard route to creators for partnership ads. [v013, v081] | `creative.md` |
| 2025, rolling out | "Allow Meta to combine likes and reactions for similar ads" (Advertising settings > Social information). | Turn on in every account that has it. [v052, v078] | `campaign-setup.md` |
| 2025 | Meta states budgets can rise in larger steps without re-entering learning. | The 10-20% scaling rule no longer holds. [v097] | `testing-and-scaling.md` |
| 2025 | Opportunity score reaches more accounts. | Follow it when results are below target; filter it otherwise. [v097] | `analysis-and-troubleshooting.md` |
| Early 2025 | Meta loosens content moderation (US first). | No change to ad tactics. Ad policy stays stricter than organic policy. [v098] | `account-health-and-policy.md` |

### 2024

| When | What changed | Practical consequence | Detail |
|---|---|---|---|
| Late 2024, rolling out | Awareness campaigns get "Frequency control" with "Cap" or "Target". Target needs a lifetime budget and a run longer than 7 days. | Cap stays the choice for the omnipresent content campaign. [v054, v105] | `local-and-high-ticket.md` |
| Late 2024, some accounts, undocumented | In-account message that the learning phase exit requirement moves from 50 conversions in 7 days to 10 in 3 days. | Do not rely on it. 2026 material still gives Meta's stated requirement as 50 results a week per ad set, with exits commonly at 20 to 40. Plan with 50. [v034, v129] | `campaign-setup.md` |
| 2024 | Opportunity score (Account overview), "Actions" column, and the share of spend in learning phase. "Automatic adjustments" toggle. | Leave "Automatic adjustments" off. [v122] | `analysis-and-troubleshooting.md` |
| 2024 | Site links: ad level > "Ad sources" > "Site links" (minimum 3; website conversion location; Facebook feed only at launch). | Optional. Leave off when the funnel depends on one landing page. [v049, v125] | `creative.md` |
| 29 July 2024 to 31 January 2025 | Detailed targeting exclusions retired (no new use from July 2024; existing ad sets stopped by end of January 2025). | Interests and behaviours cannot be excluded. [v119] | `targeting.md` |
| 2024 | "Audience controls" plus "Advantage+ audience" replace the original audience options and become compulsory for many accounts. | Start of the hard-limit versus suggestion split. [v132] | `targeting.md` |
| 2024 | "Cost per result goal" field replaces the older cost cap and bid cap options. | A target, not a cap. Mostly left empty. [v139] | `campaign-setup.md` |
| Late 2024 | Ad account "Industry" setting (Advertising settings > Industry). | Set it accurately; it only affects new or duplicated campaigns. [v113] | `account-health-and-policy.md` |

### Before 2024, still shaping the interface

| When | What changed | Practical consequence | Detail |
|---|---|---|---|
| 2023 | Location options reduced to "people living in or recently in this location". | Local businesses get out-of-area leads; target the area and exclude its surroundings. [v097, v117] | `targeting.md`, `local-and-high-ticket.md` |
| 2022 | Renames: CBO to "Advantage campaign budget", "Lowest cost" to "Highest volume", automatic placements to "Advantage+ placements". Thousands of detailed targeting options removed. [v234, v236] | See the name table below. | `campaign-setup.md` |
| 2021 (iOS 14.5) | 28-day attribution windows removed; 7-day click is the maximum. Pixel-only tracking misses conversions. | Long sales cycles are under-reported in Ads Manager. Pixel plus CAPI is the minimum. [v015, v146] | `tracking-and-attribution.md` |

## Glossary of current names

Names in quotes are as they appear in Ads Manager as of late 2026.

### Campaign and delivery

| Name | Meaning | Where |
|---|---|---|
| Andromeda | Meta's ad retrieval system, the first stage of delivery; narrows candidate ads per individual. Not a setting. | Nowhere in the interface |
| "Advantage+ sales campaign" / "Advantage+ leads campaign" | A state, not a campaign type: shown as on when audience, budget and placements all follow Meta's defaults. | Campaign setup |
| Campaign score | 0-100 rating of how closely one campaign follows Meta's recommended setup. Hard targeting and restricted placements lower it. | Right-hand panel in campaign setup |
| Opportunity score | 0-100 account-level list of "Performance recommendations", each with points and a predicted gain. A high score means the setup matches Meta's practice, not that results are good. | Ads Manager > Account overview; "Actions" column |
| Buying type | "Auction" (use this) or "Reservation" (locked lower CPM bought with lower-quality inventory). | Campaign level |
| "Campaign budget" / "Ad set budget" | Campaign budget lets Meta distribute spend across ad sets; ad set budget fixes spend per ad set. | Campaign level > Budget |
| Campaign bid strategy | "Highest volume" (default), "Cost per result goal", "Bid cap", "ROAS goal". | Campaign level |
| Conversion location | Where the conversion happens: "Website", "Website and app", "Website and calls", "Website and in-store", "Website and instant forms", "Instant forms", "Message destinations", WhatsApp, calls. A single location unlocks more performance goals. | Ad set > Conversion |
| Performance goal | What Meta optimises for. "Maximize number of conversions", "Maximize value of conversions", "Maximize number of conversations", "Maximize reach of ads". Choosing link clicks, landing page views, impressions or daily unique reach turns any campaign into a traffic or awareness campaign. | Ad set > Conversion |
| Dataset | The pixel (browser side) and Conversions API (server side) event source. | Ad set > Conversion; Events Manager |
| Attribution setting | Model "Standard" or "Incremental"; windows: click-through 7 days (or 1), engage-through 1 day (or none), view-through 1 day (or none). | Ad set > Attribution > "Show more options"; Breakdown > "Attribution settings" |
| "Cost per result goal" | Optional target cost per result (a target, not a cap). | Ad set, under the performance goal |
| Learning / "Learning limited" | Learning: volatile period after launch or a significant edit (adding an ad counts), about 24-48 hours. Learning limited: too few results to exit; not fatal. | Ad set delivery status |
| "Frequency control" | "Cap" (strict maximum) or "Target" (average). Awareness and Engagement objectives only. | Ad set |
| Ad sequencing | Delivers ads in a set order. Auction availability limited; needs lifetime budget. | Ad set, budget section |
| Ad scheduling | "Run ads on a schedule" by hour and day. Lifetime budgets only. | Campaign Budget > "Ad set scheduling"; ad set > Budget & schedule |
| Automated rules | Scheduled rules that change budgets or status on conditions. Default look-back is 37 months: always change it. | Ads Manager > "More" > "Automated rules" |
| Special ad categories | Declaration for financial products and services, employment, housing, social issues, elections or politics. | Campaign level |

### Audience and placements

| Name | Meaning | Where |
|---|---|---|
| "Controls" | Hard limits: location, minimum age (18-25), excluded custom audiences, languages, "exclude catalog interactions". | Ad set > Audience |
| "Suggest an audience" (Advantage+ audience) | Hints Meta may go beyond: custom audiences, lookalikes, age range, gender, detailed targeting. | Ad set > Audience > show settings |
| "Further limit the reach of your ads" > "Switch setup" | The manual-targeting route. Inputs gain a "Use as a suggestion" tick box, ticked by default; untick it to make a custom audience a hard limit (2025 material shows the same box for age range; confirm in the account). Detailed targeting can never be made hard, and since autumn 2026 neither can gender. Meta warns and the campaign score drops. Not in every account. | Ad set > Audience |
| "Describe your audience" | Free-text description that generates detailed targeting suggestions. | Ad set > Audience > suggested audience > Detailed targeting |
| "Reach more people likely to respond to your ads" | Extends location to people interested in the area. Untick for local businesses. | Ad set > Controls > Location |
| Audience segments | "New audience", "Engaged audience", "Existing customers". Defined from custom audiences; used for reporting and by the lifecycle setting. "Unknown" in the breakdown means they are not defined. | Advertising settings > Audience segments; campaign "Audience segment reporting"; Breakdown > "Audience segments" |
| Customer lifecycle | "Get conversions from all audiences" or "Acquire new customers" (excludes existing customers; matching is roughly 50% accurate). | Ad set, sales campaigns |
| Value rules | Bid adjustments by segment, grouped in rule sets. The first matching rule applies; rules do not compound. Creating a rule set does nothing until it is applied to each ad set. | Advertising settings > Value rules > "Create a rule set"; ad set > "Value rules" |
| "Choose an audience for each ad creative" | Age and gender per creative; suggestion only. | Ad level |
| Advantage+ placements | All platforms and placements, Meta allocates. The only ad-set option once manual controls are removed. | Ad set > Placements |
| Account-level placement controls | Short list of placements that can be blocked for the whole account (Audience Network, Marketplace, right column and others). May be removed later. | Advertising settings > Account controls > Placement controls |
| Audience Network | Third-party apps and sites; the lowest-quality inventory. | Placement / platform breakdown |

### Ads and creative

| Name | Meaning | Where |
|---|---|---|
| Partnership ads | Ads that run from both the brand's and a creator's account. | Ad level, toggle under the ad name |
| Creator Marketplace | Meta's free directory for finding and contacting creators. Needs a professional Instagram account linked to a Page; some accounts must request access. | All tools > Engage audience > Creator Marketplace (also in Meta Business Suite) |
| Text options | Up to 5 primary texts, 5 headlines and 5 descriptions in one ad. "Optimize text per person" lets Meta combine and reposition them. | Ad level |
| Creative enhancements | Per-asset automatic edits: "Visual touch-ups", "Text improvements", "Enhance CTA", "Enhance media text", "Add overlays", "Add animation", "Flex media", "Music", "Add video effects", AI image variations, translation. They can re-enable themselves. | Ad level > ad creative |
| "Personalized destinations" | Lets Meta choose a different page on the site for each clicker. | Ad level > Destination |
| "Browser add-ons" | Extra buttons (WhatsApp, call, Instagram Direct) shown on the landing page. | Ad level > Destination |
| "Multi-advertiser ads" | Lets the ad appear alongside other advertisers' ads. Leave on; little effect. | Ad level > Ad setup |
| Site links | Extra labelled links under the headline. | Ad level > "Ad sources" |
| Flexible ad format | One ad holding up to 10 creatives that Meta shows singly or as a carousel; Sales and App promotion objectives only. It is a format, so it can sit beside normal ads (unlike dynamic creative, which takes over the ad set). | Ad level > Format > "Flexible" |
| Creative testing | Built-in A/B test of 2-7 ads with guaranteed delivery. | Ad level, below the creative: "Set up test" |
| "Push delivery to this ad" | Forces a share of budget to one new ad for a set time. | Ad level > Ad setup > "Show more settings" |
| Ads Creative Studio | Creative insights and AI variation tools. | All tools > Advertise |
| Hook rate / hold rate | Native video metrics since 2026. Hook rate = 3-second video plays divided by impressions; hold rate and ThruPlay sit beside it. | Ads Manager columns |
| "Allow Meta to combine likes and reactions for similar ads" | Pools social proof across near-identical ads. | Advertising settings > Social information |

### Leads, commerce and account

| Name | Meaning | Where |
|---|---|---|
| Instant form types | "More volume", "Higher intent" (adds a review step), "Rich creative". | Ad level > Instant form > Form type |
| "Conditional logic" | Routes answers; a disqualifying answer can "close the form" so the person never counts as a lead. | Instant form > Questions |
| SMS verification | "Require leads to verify phone number with one-time passcode (SMS)". The lead must enter a texted code before the form submits. | Instant form > Form type "Higher intent" |
| "Book time" | Calendar booking at the end of an instant form. | Form ending > Additional action |
| Omnichannel ads | Optimise for online and in-store purchases together; column "Purchases (website and in-store)". | Ad set > Conversion location > "Website and in-store" |
| Business portfolio | The business account that owns pages, ad accounts and datasets. | business.facebook.com |
| Advertising settings | Account-level hub: value rules, audience segments, account controls, social information, industry. | Ads Manager > All tools |
| Meta AI business assistant | In-product assistant for analysis, recommendations and account issues. | Ads Manager, left side; facebook.com/business/help |
| Meta One | Paid subscription with verification and support tiers. | Per platform |

## Old name to current name

| If you think of | It is now |
|---|---|
| Business Manager | Business portfolio |
| Advantage+ shopping campaign (ASC) | Advantage+ sales campaign (a state of the one Sales setup) |
| Tailored leads campaign / manual leads campaign | One Leads setup; "Advantage+ leads campaign" when defaults are kept |
| Original audience options | "Controls" plus "Suggest an audience"; manual via "Switch setup" |
| Detailed targeting expansion | Permanently on; detailed targeting is always a suggestion |
| CBO / "Advantage campaign budget" | "Campaign budget" |
| "Lowest cost" bidding | "Highest volume" |
| Cost cap | "Cost per result goal" |
| Automatic placements | "Advantage+ placements" |
| Pixel (as the thing you select) | "Dataset" |
| Offline event sets | Datasets (Events Manager prompts to migrate) |
| "Engaged-view" attribution | "Engage-through" (label still appears in some views) |
| Click-through = any click | Click-through = link click only |
| Meta Verified | Meta One |

## What did not change

Do not over-correct. These still hold as of late 2026:

- Offer first, creative second; settings are hygiene. [v061, v107]
- Optimise for the real conversion event with a Sales or Leads objective from day one. [v025]
- Location, minimum age, languages and exclusions are hard limits and must be set correctly. [v029]
- Custom audiences and customer lists are still needed: to define audience segments, to give Meta data it cannot see (its own lookback is limited), and for the rare true retargeting ad set. [v037]
- Pixel plus Conversions API, with events firing only on confirmation pages. [v025]
- Daily budgets over lifetime budgets, except for ad scheduling, frequency "Target" and sequencing. [v026, v052]
- Do not scale by running identical duplicate campaigns side by side. [v026]
- Judge on ROAS or cost per conversion, by conversion volume, not by days or secondary metrics. [v004, v005]
- Meta's recommendations are tuned to the average advertiser: follow by default, override with a reason, and be sceptical of any advice to spend more. [v024, v043]

## Outdated advice to ignore

The master table across all topics. Left column: what older material (and general training knowledge) says. Middle: the rule as of late 2026.

### Structure and setup

| Old rule | Current rule | Why it changed |
|---|---|---|
| Run a cold campaign and a separate warm or retargeting campaign (or ad set). | One hybrid ad set reaching warm and cold together. Build a retargeting-only ad set only for an offer or message that cold people must not see, using "Switch setup" with "Use as a suggestion" unticked. | Custom audiences are suggestions, so "cold" and "warm" ad sets show the same spend split and compete with each other. In one "cold" ad set about 40% of spend and over half of purchases went to warm and existing people. [v037, v043] |
| Several ad sets per campaign, one interest or lookalike each, to find the best audience. | One ad set. Do not test audiences against each other. Location is the only targeting variable worth splitting (countries, or cities for multi-location businesses). | Interests and lookalikes are suggestions, so the ad sets overlap and the test is not real. Location sits in "Controls". [v043, v076] |
| Separate top, middle and bottom-of-funnel campaigns with manual retargeting between them. | Put introduction, proof and call-to-action ads in the same ad set. | Meta sequences ads per person inside one ad set. [v043, v055] |
| Choose between Advantage+ shopping and a manual sales campaign (or tailored versus manual leads); experienced advertisers pick manual. | One setup per objective. Keep Meta's defaults and deviate only for a named reason. | The campaign types merged in 2025; manual control moved to ad set level. [v049, v089] |
| Two campaigns by default, scaling and testing, split about 80/20. | One campaign, one ad set, many ads. A separate testing campaign only at 100-200+ optimised conversions a week or large budgets (10-30% of spend). Below about 50 a week, test inside the ad set. | Splitting starves each ad set of conversions; the creative testing tool and "Push delivery to this ad" now force spend to new ads without a second campaign. [v005, v014, v048] |
| The campaign objective is the key setting. | The ad-set performance goal is. The objective only narrows the list of goals. | A Sales campaign set to link clicks or landing page views behaves like a traffic campaign. [v045, v107] |
| Warm up a new account or pixel with traffic or engagement campaigns. | Run Sales or Leads campaigns optimised for the real event from day one. | Meta optimises literally; clicks teach it to find clickers, bots included. [v025, v463] |
| Optimise for add to cart or landing page views so the ad set can exit learning. | Optimise for the lowest-funnel event that reaches about 20-25 a week. Move up a step only when that is unrealistic, and treat it as a test. | Upper-funnel optimisation finds cart-adders, not buyers. "Learning limited" is not fatal. [v013, v034] |
| "Maximize number of conversions" for every sales campaign. | "Maximize value of conversions" for stores with varying order values, once the account has some conversion data. | Otherwise a $30 buyer and a $300 buyer count the same and Meta chases the cheaper one. [v008, v011, v024] |
| Raise the budget to get out of "Learning limited". | Improve offer and creative at the same budget, consolidate ad sets, stop tinkering. Never raise budget on an unprofitable campaign for this reason. | Exiting learning adds perhaps 10-20% to a campaign that already works; it does not rescue one that does not. [v034] |
| Edit whenever needed (or every 3 days under the 2024 learning-phase message). | Batch changes, no more than once every 7 days (5-10 days depending on conversion volume). | Meta plans impression sequences per person; edits interrupt them and restart learning. [v025, v034] |
| Ad set budgets as the default. | Campaign budget is the default setup. Use ad set budgets to force spend (testing campaign, omnipresent content). | Campaign budget is part of the Advantage+ state and the campaign score. [v085, v089] |
| Restrict placements by hand at ad set level (for example feeds only, or Instagram only). | Leave all placements on for conversion campaigns. For a proven placement problem use a value rule (-90%) or account-level placement controls. | Ad-set placement and platform controls are being removed from September 2026. [v002, v010] |
| Run traffic or awareness campaigns with Audience Network removed at ad set level. | Move to Sales or Leads wherever a conversion can be tracked. Otherwise block Audience Network at account level or down-bid it 90% with a value rule. | Same removal; non-conversion campaigns now drift to the cheapest inventory unless blocked another way. [v010] |
| Target by device or operating system. | Value rules by device or mobile operating system. | Device and OS targeting is being removed. [v010, v028] |
| Frequency caps exist only in Awareness campaigns. | Engagement has a frequency cap too. Nothing reports one for Sales or Leads yet. | Added in late 2025. [v054, v105] |
| Collapse the omnipresent content campaign into one ad set with ad sequencing and a lifetime budget. | Keep 10-14 ad sets with one ad each, equal daily budgets and a frequency cap. Sequencing is optional. | A fixed order repeats, needs a lifetime budget, and most accounts lack the feature; a mixed order works. [v054, v057] |

### Targeting

| Old rule | Current rule | Why it changed |
|---|---|---|
| Targeting makes or breaks results; stack narrow interests. | Broad targeting with correct "Controls". Suggestions are optional hints, most useful in a new account. Poor results are an offer or creative problem. | Meta's delivery finds buyers better than manual selections; inputs are suggestions anyway. [v029, v107] |
| Lookalikes are the best cold audience. | Rarely needed. Add customer lists and warm audiences as suggestions instead. A lookalike of real customers can still go in as a suggestion when lead quality is poor. | Meta effectively builds lookalikes itself from those signals. [v076] |
| Pure open targeting with no inputs at all, in every account. | Open targeting suits accounts with plenty of purchase data. In a new account add an age range, a few interests and all custom audiences as suggestions. | Poor suggestions are ignored and good ones give a new account direction, so the downside is small. [v029, v076] |
| Value rules only work in Sales and App campaigns, by age, gender, operating system or location. | They work with leads, sales and other objectives, and also by conversion location, device and placement. | Coverage widened between 2025 and 2026. [v028, v073] |
| Adding a custom audience makes a retargeting ad set. | It is a hint unless "Use as a suggestion" is unticked under "Switch setup". | Custom audiences sit in the suggestion section. [v037, v052] |
| Selecting a gender or an age range limits delivery to it. | Gender is only ever a suggestion (autumn 2026). An age range is a suggestion unless made hard through "Switch setup". The only age limit in "Controls" is minimum age (18-25), meant for legal restrictions. | Meta moved these inputs out of the hard controls. [v002, v089] |
| When Meta reaches the wrong people, tighten targeting. | First a value rule; only then the hard-targeting override. | Value rules keep the ad set broad and consolidated while shifting bids. [v002, v052] |
| Build value rules from where purchases already come from. | Use them only for value Meta cannot see: LTV, repeat purchase beyond the attribution window, lead-to-client rate, refunds. | Meta already optimises for what it can see. [v013] |
| Exclude interests or behaviours. | Not possible. | Detailed targeting exclusions were retired in 2024-25. [v119] |
| Use "people living in this location" for local businesses. | Target the area, exclude the surroundings, and untick "Reach more people likely to respond to your ads". | The option was removed; delivery includes people recently in the area. [v049, v097] |
| Keep custom audiences narrow and recent. | Use the widest windows: 180-day visitors, 365-day engagers and viewers, 730-day website purchasers. | Larger signals help Meta more; the purchase lookback was extended. [v006, v076] |
| Exclude past purchasers with a custom-audience exclusion to force new customers. | Default: exclude nobody. If existing customers take too much spend, use "Acquire new customers" or incremental attribution. | Excluding purchaser audiences in controls disrupted delivery badly in testing (spend and ROAS collapsed). [v006] |
| Avoid declaring a special ad category because it restricts targeting. | Declare whenever in doubt. | With broad targeting the restriction costs little; not declaring risks the account. [v029, v112] |
| Omnipresent content targets warm audiences as hard limits, or cold audiences with interests. | Add all warm custom audiences as suggestions and leave everything else open; small budgets keep delivery mostly warm. | Same suggestion logic. [v054] |

### Creative and testing

| Old rule | Current rule | Why it changed |
|---|---|---|
| No more than 5-6 ads per ad set. | As many good, clearly different ads as can be produced; 20+ is the aim and 50+ is fine. Small budgets need not run them all at once. | Andromeda matches ads to individuals, so diversity is what delivery uses. Near-identical ads do not count. [v008, v043, v055] |
| Find the single best ad and pause the rest; pause ads with a worse ROAS or CPA. | Inside an ad set, keep ads that still receive spend even if their own numbers look worse. Pause ads Meta has stopped spending on. Never pause the winner to force spend elsewhere. | A high-spend, low-ROAS ad is often the introduction ad feeding the ones that close; lower-ROAS ads capture other audience slices. [v005, v043, v064] |
| A separate ad for each headline or primary text. | Up to 5 primary texts, 5 headlines and 5 descriptions inside one ad. Separate ads are for different creative. | Ad counts become unmanageable otherwise, and Meta picks text per person. [v043, v097] |
| Test small variations (background colour, overlay, hook) as ordinary ads side by side. | Use the creative testing tool for detail tests; add only clearly different ads directly. | Andromeda may treat near-duplicates as one ad and starve the rest. [v044] |
| Judge a test after a fixed number of days, or early on CTR. | Judge on the main metric once there is enough conversion volume; low-volume accounts may need a month. | Three conversions prove nothing, and proxy metrics do not predict ROAS. [v004, v005] |
| Video is the best format. | Run statics and video together; statics now take the larger share in many accounts. | Shorter attention, video drop-off before the call to action, and statics standing out in video-heavy feeds. [v003] |
| If you can make only one ratio, make 1:1; design for sound off. | Make vertical 9:16 first and design for sound on, keeping captions. | Reels is where delivery has moved. [v015, v066] |
| Switch all creative enhancements off (or accept them all). | Decide per creative, and re-check after every edit, duplication or preview. "Personalized destinations" off for planned funnels. | Enhancements help some assets, damage others, and re-enable themselves. [v012, v036] |
| In the Ads Library, the oldest still-active ads are the winners. | Sort by "Impressions: high to low" and prefer ads that also have a long run time. | Many live ads receive no spend, so age alone proves nothing. [v031] |
| Pre-run ads under the Engagement objective to collect likes. | Do not. Turn on combined likes and reactions. | Engagement optimisation finds engagers, not buyers. [v078] |
| Choose creators by reach and pay for an organic post. | Choose by audience fit, get ad usage rights, run as partnership ads. | An organic post is worth about a day; an ad can run for months. [v019, v023] |

### Scaling, leads, tracking and analysis

| Old rule | Current rule | Why it changed |
|---|---|---|
| Raise budgets by no more than 10-20% at a time. | Step size depends on budget: up to +100% from very small budgets, about +20-30% at several hundred a day, smaller again at large budgets, every 5-10 days. Or automated rules at about 3% a day. | Meta allows larger steps without re-entering learning; a fixed percentage is too slow when small and too big when large. [v014, v026, v097] |
| Scale by duplicating winning campaigns or ad sets. | Scale the existing campaign. The only exception is the 2026 scaling bug: duplicate once at the higher budget and turn the original off. | Duplicates split conversion data and break per-person frequency planning. [v016, v026] |
| Instant forms: "More volume" with as little friction as possible. | Default more accounts to "Higher intent" plus SMS one-time passcode plus conditional logic. Exception: a new booking form can start without extra friction to build volume. | Meta learns from whoever submits; low friction teaches it to find low-quality leads. [v008, v011, v018] |
| Optimise for all leads and sort quality afterwards. | Send Meta a qualified-lead event (conditional logic on forms, or a separate thank-you page) and report cost per qualified lead. | Meta only sees the event it is sent. [v008, v011] |
| Call-booking funnels need a website. | Instant forms with "Book time" are a valid route. | New in 2026. [v018] |
| A click in "7-day click" means any click; compare this year's numbers with last year's. | Click-through means link click. Do not compare periods across the spring 2026 change; verify against back-end data. | Attribution was redefined. [v032] |
| Use click-only attribution to be safe. | Keep 7-day click, 1-day engage-through and 1-day view. Narrow only when other heavy channels clearly inflate Meta's numbers. | Many buyers convert without clicking, and Meta needs the conversion data to optimise. [v032, v068] |
| The pixel alone is enough. | Pixel plus Conversions API. | Privacy changes hide a large share of browser-side conversions. [v013, v015] |
| Low CPM is good and rising CPM is a problem. | Judge on ROAS or cost per conversion. A higher CPM can mean a better audience. | CPMs rise with demand everywhere; Instagram CPMs now exceed Facebook's. [v004, v022] |
| Build a custom metric for hook rate. | Hook rate and hold rate are native. | Added in 2026. [v007] |
| Disabled account: request review, then wait. | Request review, then use the AI business assistant route to reach a human agent, then the Meta rep. | New support path in 2026. [v027] |

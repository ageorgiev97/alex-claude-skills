# Tracking and attribution

How conversion data reaches Meta, how to check it, what each attribution window counts as of late 2026, and how to reconcile Meta's numbers with a store or CRM (customer relationship management system). Read it before comparing API figures with back-end figures, before judging a sudden change in reported results, and whenever tracking is in doubt.

## Contents
- Why tracking comes first
- What must be installed
- How to check it is working
- Event match quality
- Which events to track and which to optimise for
- Qualified events
- Feeding CRM and offline outcomes back
- The attribution setting (late 2026)
- Incremental attribution
- What a Meta-reported number means
- Why Meta and the back end differ
- Reconciliation procedure
- Third-party attribution
- Recent data: modelling and delay
- Outdated advice to ignore

## Why tracking comes first

Meta's delivery system learns from the conversions it receives: who converted, when, and what each was worth. The same data drives every pause, keep and scale decision. Bad data therefore fails twice: Meta optimises toward the wrong people, and the analyst turns off winners and keeps losers. [v065, v008]

It is also an easy edge. Many advertisers, including large ones, run tracking incompletely, and privacy regulation (hardest in the EU) keeps removing signal, so the gap between good and poor data inputs is widening. [v053, v074]

## What must be installed

| Component | Requirement | Why |
|---|---|---|
| Meta pixel (browser side) | On the site with all conversion events before the first campaign launches. Created under "Data sources" in business settings; selected in the ad set as the "Dataset". | Minimum for any Sales or Leads campaign that sends people to a website. Install it even if website visitors are never targeted as an audience. [v037, v030, v029] |
| Conversions API (CAPI, server side) | Running alongside the pixel and sending the same conversion events. Both, not either. | The pixel alone misses many conversions since Apple's privacy changes. CAPI catches purchases that did not follow a straight click-and-buy path or came after a time gap. The pair is more accurate than either alone. [v068, v074, v015] |
| Conversion values | Purchase value sent with every Purchase. For lead generation, an estimated value per lead type where value optimisation is used. | Needed for "Maximize value of conversions" and for return on ad spend (ROAS) reporting. [v045, v087] |
| A checkout or booking flow that can fire events | If a third-party checkout cannot carry the pixel, change the checkout. | Meta cannot optimise for an event it never receives. [v062] |

Setup notes:
- Events Manager's overview offers a one-click CAPI setup on some website platforms; on others it is technical. A freelancer will set up pixel plus CAPI from about $20. Recommend that over leaving it half done. [v013, v061, v084]
- Meta's own estimate for adding CAPI, shown in opportunity score, is about 13% lower cost per result (approximate). [v122]
- CAPI is irrelevant to instant-form campaigns because the conversion happens inside Meta. In-app conversions are tracked at close to 100%; website conversions were put at about 70% in 2022. [v122, v240]
- Sales campaigns that convert in WhatsApp or another message destination and optimise for Purchase still need pixel plus CAPI so Meta can see who buys. [v051]
- A new pixel needs no "warm-up" with traffic or engagement campaigns. Optimise for the real conversion from day one. See `campaign-setup.md`. [v025]

## How to check it is working

Run in this order. Steps 1 to 3 need a browser or the user; the rest can be done from data.

1. **Events fire on the right page.** With the free Chrome extension "Meta Pixel Helper", walk the funnel: the landing page fires only PageView on load, Purchase fires only on the order-confirmation page, Lead fires only on the thank-you page. [v025]
2. **No conversion event fires on page load.** A Purchase or Lead event on the landing page is a fairly common fault. Meta then believes every click converts and optimises for raw traffic, including bots and spam accounts. A pixel with no conversion data is better than one fed false conversions, so pause and fix before spending. [v025]
3. **The right dataset is selected.** Check the pixel ID in the ad set's "Dataset" field and in the ad's tracking section; an ad set pointed at the wrong pixel reports and learns nothing. [v049, v029]
4. **Events Manager is clean.** Open Events Manager > overview and work through the errors and recommendations (custom event issues, a prompt to "migrate your offline event sets" to datasets, event match quality). Repeat regularly, not once. [v074, v061]
5. **Counts roughly match the back end.** Compare conversions in Ads Manager with CRM lead counts or store orders for the same period. A rough match means tracking is probably accurate. [v061]
6. **Values are arriving.** Purchase conversion value sometimes stops feeding through, which blanks ROAS while purchases still count. Treat that as a reporting fault, not a performance collapse. [v118]
7. **The pixel is locked to your domains.** Anyone can copy a pixel ID and fire it from spam sites, polluting the data. Events Manager > Data sources > pixel > Settings > "Traffic permissions" > create an allow list of your domains (2023 click path; verify the current interface). [v206]

Patterns in account data that point to broken tracking:

| Pattern | Likely cause |
|---|---|
| Results almost equal to link clicks or landing page views | Conversion event firing on page load [v025] |
| Meta reports far more conversions than the back end holds | Event on the wrong page, or pixel firing from other domains [v025, v206] |
| Purchases counted but conversion value and ROAS blank | Value feed dropped [v118] |
| Meta reports far fewer than the back end across all campaigns | Pixel only with no CAPI, low event match quality, or a structural gap (see "Why Meta and the back end differ") [v062] |

## Event match quality

Event match quality (EMQ) is Meta's score, shown in Events Manager, for how well the events you send can be matched to people. The standard is simply "high", and the fix when it is low is to implement the recommendations Events Manager lists. [v053, v061]

- The typical faulty states are pixel without CAPI, or CAPI with weak match quality. Check both. [v062]
- One hard threshold is given: omnichannel ads (website plus in-store optimisation) require a score of at least 4.8, with CAPI sending offline conversions. If CAPI data or match quality degrades, performance drops even while the feature stays available, so fix issues immediately. See `ecommerce.md`. [v086]
- The source gives no other numeric target. Do not invent one; report the score Events Manager shows and whether Meta flags it.
- The same principle applies to uploaded customer lists: more identifier columns (email, phone, name, city) give a better match rate. See `targeting.md`. [v076]

## Which events to track and which to optimise for

Track every step; optimise for one.

| Funnel stage | Event | Fires where | Use |
|---|---|---|---|
| Page load | PageView | Every page | Baseline and audiences. The landing page should fire nothing else on load. [v025] |
| Product interest | Add to cart, Initiate checkout | On the action | Diagnosis and audiences. Not an optimisation target by default. [v029, v076] |
| Sale | Purchase, with value | Order-confirmation page only | Optimisation event for Sales campaigns. [v029] |
| Lead | Lead | Thank-you page only | Optimisation event for Leads campaigns when all leads are worth about the same. [v025, v049] |
| Qualified lead | A separate event such as "Submit application" | Thank-you page shown only to qualified respondents | Preferred optimisation event when lead quality varies. [v008] |
| Booking or registration | Schedule, Complete registration | Confirmation step | Optimisation event for call and webinar funnels. [v049, v013] |
| Customer (offline) | CRM or offline conversion via CAPI | Sent from the CRM | "Conversion leads" optimisation and true cost per customer. [v087, v084] |

Rules for the optimisation event (full treatment in `campaign-setup.md`):
- Optimise for the event furthest down the funnel that you can track accurately and that happens inside the attribution window, which is at most 7 days after a click. Meta is literal: ask for cart-adders and it finds cart-adders. [v091, v029]
- That event needs volume. Use the lowest-funnel event that reaches about 20 to 25 conversions a week: purchase, else booked call, else webinar attendee, else registrant. [v013]
- Move up the funnel only when the real event cannot get there (for example 7 purchases a week against 35 add-to-carts). Treat it as a test over about a month and expect the ratio of the upstream event to purchases to worsen. At around 20 a week with room to grow, stay on the real event. [v034]
- Services with a call or proposal stage optimise for the lead, not the sale, because the sale falls outside 7 days and passes through offline steps that are hard to match back to a click. [v091]

## Qualified events

Rule: only send the optimisation event for people you would want more of. Meta sees only the event it receives. If every form fill is a "Lead", Meta finds the cheapest people who fill forms, and they are disproportionately poor quality. [v008, v011]

- **Website forms.** Add a qualifying question (budget tier, timeline, location, industry). Route qualified respondents to thank-you page A, which fires a distinct event (for example "Submit application"). Route the rest to thank-you page B, which fires Lead or another event. In the ad set, select the event that fires only on page A. [v008, v011]
- **Instant forms.** Use conditional logic so a disqualifying answer closes the form and the person never registers as a lead. See `lead-generation.md`. [v011]
- **Values instead of a yes/no.** For website lead campaigns, send different values per lead type and optimise for value. Estimate value as deal size times close rate at the point of capture: a full roof replacement at $20,000 with a 1-in-5 close rate is $4,000 per lead; a repair at $2,000 with a 50% close rate is $1,000. Separate thank-you pages carry the different values. [v045]
- **Reporting.** Report cost per qualified lead, not cost per lead. Some ads produce many leads and few qualified ones. [v008]
- **Timing.** The effect is small on day one and large after 30 to 90 days, because the learning compounds. Do not judge the switch in the first week. [v008]

For sales, the equivalent is passing order values and optimising for value so a $30 buyer and a $300 buyer are not treated as equal. See `ecommerce.md`. [v011]

## Feeding CRM and offline outcomes back

Meta cannot see what happens after the attribution window or off the site: lead-to-customer close rate, refunds, repeat purchases, lifetime value. There are three ways to supply it, in order of strength. [v028]

1. **Send CRM or offline conversions back through CAPI** and optimise for them. For instant forms the performance goal is "Maximize number of conversion leads". It needs a CRM integration, and the downstream conversion must fall inside the attribution window. If it is set up, use it; if not, "Maximize number of leads" is acceptable. This is the recommended route at large lead-generation budgets. [v087, v014]
2. **Keep lead statuses current.** Conversion-leads optimisation is useless if nobody marks which leads converted. Updating statuses in Meta's Leads Center is enough for instant-form leads; otherwise update the CRM. Sales teams tend to skip this, so check it is happening. [v084]
3. **Value rules.** When importing CRM data is impractical (it is fiddly and most advertisers do not do it), encode what the CRM shows as bid adjustments by segment. See `targeting.md`. [v028, v013]

Other points:
- Use the fed-back data for decisions too. Compare offers on lead-to-customer rate, not cost per lead (CPL): two offers with the same CPL can differ twofold in conversion to customer. [v084]
- In leads campaigns, lead quality is invisible to Meta unless conversion leads is set up. That is why feeding quality back and staying broad ranks above adding targeting restrictions. [v089]
- Upload customer and email lists so Meta holds data the pixel cannot: older contacts, offline buyers. See `targeting.md`. [v065]

## The attribution setting (late 2026)

A conversion is reported, and used for optimisation, only if it happens inside the ad set's attribution setting. The setting is per ad set, so two ad sets in one account can count differently. Read the actual setting before comparing them. [v072, v032]

Where: ad set > "Attribution" section > under attribution model, "Show more options". The model is "Standard" (default) or "Incremental". Under Standard there are three windows. In 2025 the same control sat in the ad set's Conversion section under "Show more options" > "Attribution setting"; either layout is the same setting. [v032, v072]

| Category | A conversion counts when the person... | Options | Keep at |
|---|---|---|---|
| Click-through | clicked the link to the ad's main destination (a website, or a destination inside Meta such as an Instagram profile or WhatsApp) and converted within the window | 7 days or 1 day | 7 days |
| Engage-through | did not click the link but liked or reacted, commented, shared, clicked into the media, clicked "see more", or played the video for at least 5 seconds (97% of it if shorter than 5 seconds), and converted within 1 day | 1 day or none | 1 day |
| View-through | was shown the ad with no engagement and no link click, and converted within 1 day | 1 day or none | 1 day |

The 2026 redefinition (rolled out from spring 2026; described then as not yet in every account): [v032]
- Before, "click" meant any click on the ad, including social and media clicks, and any of them opened the 7-day window. Now only a link click does.
- Everything removed from click-through moved into engage-through, which has a 1-day window. A person who also clicked the link counts as click-through, not engage-through.
- What disappears from reports: conversions that came 2 to 7 days after a like, comment, share, expand or video play with no link click.
- Size of the effect depends on creative and sales cycle. In one video-heavy campaign, clicks (all) were 1,179 against 415 link clicks, almost three times as many; image-heavy campaigns showed a smaller gap. Expect the largest drop in reported conversions for video-heavy accounts with long, considered purchases, and little change for fast-converting offers.
- The older label "engaged-view" (a narrower, video-based 1-day category) still appears in some views, and was still the wording in use in September 2026, while it is replaced by engage-through. Treat it as the same slot when reading data. [v032, v013]

Rules:
- Keep the widest windows: 7-day click, 1-day engage-through, 1-day view-through. Meta needs as many conversions as possible attributed back to the ad to learn, and a narrower window loses the most for expensive, considered purchases. [v032, v146]
- Check that view-through is not set to none. Defaults vary by campaign setup, and click-only measurement misses buyers who never click; Gen Z is twice as likely to buy without clicking. [v068, v074]
- Narrow only when Meta consistently reports more than the back end holds because other channels (large email sends, organic) are converting people anyway. Remove 1-day view first. Almost never cut click-through to 1 day. [v146, v032]
- Do not shrink windows to make Meta agree with Google Analytics. The two measure different things. [v146]
- Do not change the attribution setting on an ad set that is performing well; a settings change risks its results. Apply new settings to new ad sets. [v283]
- The maximum click window is 7 days. The 28-day windows are gone. [v146, v087]
- Do not compare a period or campaign under the old click definition with one under the new and conclude performance fell. Check actual sales or leads in the back end first. [v032]

To see the split, use Breakdown > "Attribution settings" at campaign, ad set or ad level. One example under the old definitions: of 37 results, 29 were 1-day click, 3 were 2-to-7-day click and 5 were in the remaining 1-day category (most likely 1-day view). After the change, expect the click figures to fall and engage-through to rise. [v032]

Which setting to choose at build time is in `campaign-setup.md`.

## Incremental attribution

What it does: Meta uses models that predict whether a conversion was caused by the ad, optimises delivery for those incremental conversions, and shows fewer ads to people it predicts would have converted anyway. It changes delivery, not only reporting. [v072]

Where: the same attribution section; switch the model from "Standard" to "Incremental". As described in 2025 it appeared only on Sales campaigns with a website conversion location optimising for purchases (catalogue sales included) under "Maximize number of conversions", with value optimisation in testing. If an ad set does not qualify, the option is not shown. Eligibility may have widened since. [v072]

| Question | Answer |
|---|---|
| Who should use it | Larger advertisers with big customer bases or warm audiences, and multi-channel businesses that suspect Meta is being credited for sales that email, search or repeat custom would have delivered. [v013, v072] |
| Who should not | Beginners. Smaller advertisers may test it, but it is aimed at accounts with a large existing customer base. It is also pessimistic for long purchase cycles. [v013, v074] |
| What happens to reported numbers | Reported purchases and ROAS fall, sometimes sharply, because conversions judged to have happened anyway are no longer counted. That is expected and does not mean performance fell. [v072, v074] |
| How to compare | Never set an incremental figure beside an earlier standard figure. Judge the switch on back-end sales, as with any attribution change. [v072, v032] |
| Evidence | Meta's test data: 46% more incremental conversions for advertisers using it. [v072] |
| How it relates to other tools | A softer alternative to the "Acquire new customers" lifecycle option, which also lowers reported ROAS. See `targeting.md`. [v006] |

Notes:
- Incremental reporting still includes non-click conversions. Meta's example for one ad set: 23 purchases at 1-day click, 34 once engaged views were added. Columns also split "all conversions" from "first conversion" (23 and 19 in that example). [v072]
- Non-incremental spend is not pure waste: reminders and repeated exposure have value. [v072]
- It is fine to test and switch back, and results should improve as the account learns. Where the existing ad set is a strong performer, run the test in a new ad set and leave the original alone. [v072, v283]

## What a Meta-reported number means

| Number | Meaning | Not the same as |
|---|---|---|
| Results / purchases / leads | Tracked events that Meta matched to an ad interaction inside that ad set's attribution setting. A claim of involvement. | Orders or leads the store or CRM assigns to Meta on a last-click basis. [v133, v146] |
| Purchase conversion value, ROAS | Tracked value of those purchases inside the window. For subscriptions and recurring billing, the first transaction only. | Lifetime revenue, or total store revenue. [v118, v062] |
| Link clicks | Clicks to the ad's destination. The only clicks that open the click-through window. | "Clicks (all)", which includes unmuting, "see more" and carousel swipes. [v118, v032] |
| Leads on instant forms | Form submissions inside Meta, tracked at close to 100%. | Contactable or qualified leads. [v240] |

## Why Meta and the back end differ

The two will never match exactly. Some gap in either direction is normal; most accounts under-report rather than over-report. [v146, v109]

| Cause | Direction in Meta | Normal? | What to do |
|---|---|---|---|
| Sales cycle longer than 7 days | Under. Example: about £2,000 spend, Meta saw £3,000 revenue, actual £15,000. | Yes, for considered purchases and services | Do not judge on in-platform ROAS alone; use back-end revenue. [v075, v072] |
| Subscriptions and recurring billing | Under. Example: £96,000 generated, £38,000 reported. A £97-a-month product at £23 per purchase shows about 4x but is nearer 20x with retention. | Yes | Judge against lifetime value. [v062, v118] |
| People who buy without clicking: they see the ad, check reviews, search the brand, go direct or buy on a marketplace | Under. Only the 1-day engage-through and view-through windows catch any of it. | Yes, and growing | Keep those windows on; watch total store revenue. [v068] |
| Tracking loss from privacy changes, pixel without CAPI, low match quality | Under | Partly; the avoidable part is a fault | Install CAPI, fix Events Manager issues. [v015, v062] |
| Sale closed offline (call, proposal, in store) | Under, or absent | Yes unless CRM data is sent back | Send offline conversions; optimise for the lead. [v091] |
| Multi-touch journeys: Meta claims any conversion with an ad touch in its window; analytics tools credit one channel, usually the last click | Meta higher than Google Analytics for the same orders | Yes. This is a difference of model, not over-reporting. | Do not "fix" it by shrinking windows. [v133, v146] |
| Heavy email, organic or repeat-customer sales that convert anyway | Over. Some accounts are over-reported by 30 to 80%. | Common in established brands | Check the "Audience segments" breakdown, drop 1-day view, or test incremental attribution. [v109, v146, v006] |
| Conversion event on the wrong page, or pixel fired from other sites | Over | No. A fault. | Fix before any other decision. [v025, v206] |
| 2026 click redefinition, or a switch to incremental attribution | Step down in reported conversions on the date of the change | Yes | Compare back-end figures across the change. [v032, v072] |
| Modelled recent data | Either | Yes | Leave out the last 3 days. [v133] |

A typical journey that produces honest disagreement: ad click on Monday, brand search on Wednesday, newsletter sign-up for a discount, purchase from an email on Saturday. Analytics credits email, Meta credits itself, and every touch contributed. [v133, v121]

## Reconciliation procedure

1. Align the comparison: same date range ending at least 3 days ago, same event (orders against purchases, CRM leads against leads), and note each ad set's attribution setting. [v133, v032]
2. Compare totals. A rough match means tracking is probably sound. [v061]
3. Split Meta's figure with Breakdown > "Attribution settings". Click-through conversions are the ones a last-click tool could also see; engage-through and view-through never appear there. [v032]
4. If Meta is persistently lower, work down the table above: sales cycle, recurring revenue, missing CAPI, match quality, offline closes. Where the gap is structural, estimate the average under-report (for example 30%) and apply it when reading ROAS, but improving the data is the better fix. [v068]
5. If Meta is persistently higher, check event firing first, then the share of spend and purchases going to existing customers and the weight of email and organic. The "Audience segments" breakdown needs segments defined in advertising settings, and its matching is only about 50% accurate. [v006]
6. Use Meta's numbers for relative decisions. Two ads are likely to be inaccurate to a similar degree, so the one that is 20% better is still better. Judge the business on total return across channels over a longer horizon. [v133]
7. At very large budgets (the example given is $20M a month) a positive in-platform ROAS is not a realistic target, because the window never captures long-horizon effects. [v121]

## Third-party attribution

Purpose: follow customers past Meta's 7-day window and first transaction, and assign credit across channels.

| Monthly spend | Recommendation |
|---|---|
| A few hundred dollars, or about $30 a day | Not worth it. Pixel plus CAPI and a back-end comparison are enough. [v121, v128] |
| About $5,000 to $10,000 and up | Worth adding, especially with long sales cycles, recurring billing or several active channels. [v128, v084] |
| $100,000 and up | Treat as essential. Many channels (email, SMS, other social, offline) make credit muddy, and Meta can be over-credited. [v121] |

Cheaper partial substitutes:
- A unique landing page URL per campaign, ad set or ad, tracked in Google Analytics. More accurate than URL tracking parameters (UTMs) in 2022 tests. The drawback is that none of this data reaches Meta's optimisation. [v240]
- URL parameters at ad level, optional, for Google Analytics users. [v049]
- A promo code delivered at the end of an instant form, which ties later purchases to the lead campaign. [v067]
- Keeping the conversion inside Meta (instant forms), which gives near-complete tracking at the cost of lead quality. [v240]

## Recent data: modelling and delay

- Meta models conversion data, most heavily in the latest 48 to 72 hours, and can over- or under-estimate. Yesterday's numbers may simply be wrong. Do not base decisions on them, and mark the last 3 days as provisional in any report. [v133]
- Results often arrive a week or more after the spend that produced them, because people take time to decide and often need several impressions first. Recent days therefore understate performance, and campaigns judged or switched off too early look worse than they were. [v146]
- After a budget change, allow about 7 to 10 days before judging, partly for the learning phase and partly for this reporting lag. [v326]
- Choose the analysis window by conversion volume: last 3 days only with dozens or hundreds of conversions in that window, 7 days as the default, 14 or 28 days when conversions come every couple of days. Never the maximum range. See `analysis-and-troubleshooting.md`. [v026, v052]
- When the user's store figure for a recent day disagrees with the API figure, re-pull after the period has settled before treating it as a tracking fault.

## Outdated advice to ignore

| Old rule | Current rule | Why it changed |
|---|---|---|
| Use 28-day click and 28-day view windows | Maximum is 7-day click, 1-day engage-through, 1-day view-through | The long windows were removed with Apple's privacy changes. [v146] |
| A "click" conversion follows any click on the ad | Click-through requires a link click; other interactions are engage-through with a 1-day window | 2026 attribution change. [v032] |
| The pixel alone is enough | Pixel plus Conversions API, both sending accurate events | Browser-side tracking loses too much. [v015, v068] |
| Run traffic or engagement campaigns first to season a new pixel | Optimise for the real conversion from day one | Those campaigns teach Meta to find clickers, not buyers. [v025, v463] |
| Judge on clicks only and discount view-through | Keep 1-day view-through and engage-through on | More people buy without clicking. [v068, v074] |
| Shorten windows, or use 1-day click, so Meta matches analytics | Keep the widest windows; accept that the models differ | Narrow windows starve optimisation of data. [v146, v032] |
| Count every form fill as the Lead to optimise for | Send the optimisation event only for qualified leads | Meta is literal and chases the cheapest form-fillers. [v011, v008] |
| Optimise for add to cart or landing page views to exit the learning phase | Optimise for the real event; move up only when it cannot reach about 20 to 25 a week | Upstream optimisation finds upstream behaviour. [v013, v129] |
| Check results daily and react | Ignore the last 48 to 72 hours; judge on weekly windows or longer | Recent data is modelled. [v133] |
| Meta showing more than analytics means Meta over-reports | Different attribution models; most accounts under-report | Meta counts involvement, analytics counts last click. [v133, v146] |
| Domain verification and aggregated event measurement as launch steps (2021 to 2022) | Absent from the 2024 to 2026 material; follow what Events Manager currently asks for | Tied to an old interface. [v256] |

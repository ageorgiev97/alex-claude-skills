# Account health and policy

How to set up a business account and ad account, start spending on a new account, stay inside Meta's advertising policies, and respond to disapproved ads and restricted or disabled accounts. Also covers the support routes that exist as of late 2026 and how to treat Meta's own advice. Read it when onboarding a new advertiser, writing or reviewing ads in a sensitive niche, handling a disapproval or a disable, or when a Meta rep, the AI assistant or an in-product score recommends a change.

## Contents
- How enforcement works
- Set up the business account and ad account
- Start spending on a new account
- Policy triggers and safe rewording
- Special ad categories and regulated industries
- When an ad is disapproved
- When the account is restricted or disabled
- Protect the account in advance
- Support routes as of late 2026
- Meta's own advice: what to follow and what to filter
- Outdated advice to ignore

## How enforcement works

- **Review is automated first and often wrong.** The system protects the user experience and prefers a false positive to a missed violation. An agency with 1,000+ ad accounts still has several disabled every month and nearly always gets them back. Assume any account that advertises long enough will be disabled at some point, and treat it as a process to run, not an emergency. [v027, v133, v243]
- **Disapprovals add up like strikes.** Enough of them, including incorrect ones, get the whole ad account disabled. Each disapproval is an account-level risk, not just one lost ad. [v112, v098]
- **The share of ads disapproved matters.** Working estimate (from 2021, never confirmed by Meta): about 30% or more of new ads disapproved is a real risk; 50–60% makes a disable very likely. New accounts are the most fragile because the base is small: 4 of 5 ads disapproved is 80%. [v330]
- **History buys leniency.** Accounts with years of history and large spend are rarely disabled (their ads can still be disapproved) and get better rep access. New, low-spend accounts, and regions with more policy abuse, are treated more strictly. [v330, v243]
- **"Is it true?" is not the test.** Meta's own "not allowed" examples include "Be your own boss", "Make $1,000 every month" and "Lose 5% of your body weight in a month". Real, verifiable results still get disapproved. Judge each ad from Meta's side: could it mislead a user or put them off? [v112, v243]
- **Copy is scanned hardest.** Primary text and headline are the easiest places for the automated review to flag a phrase. The same claim inside an image or video is flagged less often. [v112]
- **Customer experience is enforced too.** Meta surveys buyers about their purchase experience. An average below roughly 2 out of 5 for some weeks brings a warning, then ad restrictions or a ban. Slow delivery, poor quality and no support (typical of dropshipping) are how accounts get there. [v316]
- **Poor quality is taxed before it is banned.** Clickbait, sensational claims, engagement bait, disruptive pop-ups, thin pages and ad-to-page mismatch raise CPM (cost per 1,000 impressions). See `analysis-and-troubleshooting.md`. [v140]

## Set up the business account and ad account

A business portfolio (formerly "Business Manager") holds the Facebook Page, Instagram profile, ad account, pixel or dataset and team access. Set one up even for a single ad account: it is what makes scoped access, verification and recovery possible. [v030]

1. **Create it** at business.facebook.com while logged in to Facebook or Instagram: "Create an account", about a minute. If the link drops you straight into Meta Business Suite, a portfolio already exists (often created unknowingly) and is probably not set up properly. Fix that one; Meta limits how many portfolios one person can create. [v030, v049]
2. **Add assets** in Business Suite > "Settings" > the asset type > "+ Add". [v030, v049]

| Asset | Your own business | Agency or contractor | Notes |
|---|---|---|---|
| Facebook Page | "Add an existing Facebook Page" (moves ownership into the portfolio) or "Create a new Facebook Page" | "Request shared access to a Facebook Page"; a page admin approves | A Page is required to advertise on Facebook |
| Instagram | "Add Instagram account", then log in | — | Professional accounts only; a personal account is converted |
| Ad account | "Create a new ad account" or "Add an existing ad account" (paste the ID shown beside the account name in Ads Manager) | "Request access to an ad account in another portfolio"; the client admin approves | Anyone who has ever boosted a post already has an ad account |

3. **Ownership rule:** the business owns its own assets in its own portfolio. Agencies request access and leave ownership with the client, so the account stays in the client's portfolio. [v030]
4. **New ad account fields:** set the name, time zone and currency correctly at creation, then add the payment method. Time zone and currency are very hard to change later. [v049, v030]
5. **People:** "Invite people" > the email tied to their Facebook profile > partial or full (admin) access > assign assets with per-asset permissions (ad account: full control or manage campaigns only; Page: full control or only ads, content, community activity, messages). Never share login details; grant scoped access. Invite yourself and assign yourself every asset, because the portfolio is separate from your personal profile and owners who skip this cannot reach their own assets. [v030, v049]
6. **Pixel or dataset:** create it under "Data sources" in settings. See `tracking-and-attribution.md`. [v030]
7. **Industry:** Ads Manager menu > "Advertising settings" > "Industry" > "Add industry"; choose one or two that fit. Meta says it uses this for features, guidance and support. The screen says changes "won't affect active campaigns", which implies (an inference, not Meta's statement) that it feeds optimisation of new ones, so after saving, create new campaigns or duplicate the existing ones and turn off the originals. One account with a messy history saw 32% more sales at the same spend after doing this, though relaunching alone can move results. [v113]
8. **Verification and security:** complete Meta business verification and turn on two-factor authentication with an authenticator app, not SMS (see "Protect the account in advance"). [v027, v133]
9. **Ad transparency** (advertiser, payer, beneficiary) at ad set level is mandatory in some regions and optional in others; fill it in where asked. [v029]
10. **Build in Ads Manager on a computer.** Never boost posts from the Facebook or Instagram apps: boosting from an iOS device costs about 30% more because Apple treats it as an in-app purchase, and boosts lack the controls over audience and optimisation. [v025]

## Start spending on a new account

A new account performs worse and swings more than a seasoned one because Meta has no conversion history for it. The cure is to feed it real conversions in a stable, simple setup. Nothing else "warms" an account. [v025, v141, v133]

| Do | Why | Source |
|---|---|---|
| Use the Leads or Sales objective, with the performance goal set to the conversion you actually want (lead or purchase), from day one | Meta optimises literally; the system only learns who converts by being asked for conversions. A conversion campaign beats a traffic campaign on conversions even in a brand-new account | [v025, v095] |
| Start with one campaign, one ad set, several ads, one offer (the best seller or most profitable product) | Small budgets produce few conversions; splitting them stops the ad set learning and stops you drawing conclusions | [v025] |
| Verify tracking before spending: with the "Meta Pixel Helper" Chrome extension, confirm the landing page fires only PageView, Purchase fires on order confirmation, Lead fires on the thank-you page | A conversion event firing on page load teaches Meta that every click converts, so it chases raw traffic and bots. No conversion data is better than false data | [v025] |
| Set hard limits only where they are real (serviceable location, legal minimum age); age range, gender and a few interests are optional suggestions that may help while there is no data. See `targeting.md` | The account has no history to tell Meta who converts, and suggestions cost little because Meta can go beyond them | [v029, v070] |
| Start with a budget you can afford to lose but that would sting, large enough to produce data. See `campaign-setup.md` | Prove the offer and creative small, then scale; a budget that is too small starves Meta of data | [v029, v025] |
| Launch, leave it 5, 7 or 10 days, then make all changes in one batch | Learning restarts after each significant edit (usually 24–48 hours); constant tinkering keeps the ad set in learning | [v025] |
| In a new account or a sensitive niche, add ads in small groups: 1–2 first, wait for approval, then add similar ones | Keeps the disapproval rate low while the account has no history. Ad review usually takes about 30 minutes, longer for an account's first ads | [v330, v049] |

| Do not | Why | Source |
|---|---|---|
| Run Traffic or Engagement campaigns first to "warm up" the pixel or account | You get clickers and engagers, including bots and fake accounts, and no conversion learning. Reps suggest it because a large results number keeps new advertisers spending | [v025, v133] |
| Pick "landing page views", "link clicks", "impressions" or "daily unique reach" as the performance goal inside a Leads or Sales campaign | It then behaves like a Traffic or Awareness campaign whatever the objective says | [v029, v049] |
| Buy a "seasoned" or aged ad account | It violates Meta's terms, and such accounts are more likely to be shut down than a fresh one | [v027] |
| Raise the budget to exit the learning phase before the offer and creative are proven | Spending 5–10x more on an unprofitable campaign multiplies the loss; get profitable small, then scale | [v133, v122] |
| Abandon an existing account just because its history is messy | Old conversion data for products you still sell is worth keeping; set "Industry" and relaunch instead. Start fresh only when the history is old and worthless | [v113] |

Expectations to set: early results in a new account are weak and volatile and are not evidence that Meta ads do not work. No conversions at all points to the offer; some conversions with weak click-through points to creative (see `analysis-and-troubleshooting.md`). A 10x ROAS (return on ad spend) target is unrealistic for a new account on a small budget; aim for break-even first, then scale. Accounts get easier as conversion data accumulates, with clearly better results after one, two and three years. [v025, v070, v106]

## Policy triggers and safe rewording

Five policies account for nearly all bans, and advertisers usually break them without realising. Categories flagged constantly: health and fitness, career improvement, make-money and business opportunity. [v112, v098]

| Policy | What triggers it | How to stay clear | If hit |
|---|---|---|---|
| Unrealistic outcomes (health, weight loss, income) | Specific results or income promises, even true ones | Tone results down to modest examples; keep strong numbers out of primary text and headline; avoid trigger phrases | Usually reversed on review if you can substantiate the outcome |
| Personal attributes / discriminatory practices | Copy that asserts or asks about family status, religion, national origin, health, finances and similar ("Are you ...?"); often accidental (divorce lawyers, baby products, services for expats) | Third-person framing; call out by location, interest or life event instead | Reword the ad; an account disabled for content judged discriminatory is rarely recovered |
| Non-functioning landing page | Broken page, form or buy button; URL pointing to a different product than the ad; pop-ups that fire on leaving and block navigation; dead-end pages | Re-test pages after every site edit; double-check URLs; keep footer links (contact, privacy policy, terms); exit-intent pop-ups triggered before the click are allowed | Can disable an account without warning (seen with an exit pop-up) |
| Personal health and appearance | Imagery or copy that creates negative self-perception; tight close-ups of a body part, even positive ones (perfect teeth) | Zoom out to show more of the person; more clothing on models; third-person or study-based copy | Harder to get an account back from than the others |
| Unacceptable business practices | Written for scams, but used as a catch-all when something looks slightly off; the most trigger-happy policy | Little can be done in advance | Request review; reinstatement is highly likely for legitimate ads |

[v112, v027]

Other triggers:
- **Engagement bait** (asking people to like, comment, share or tag to get something) violates policy and puts the account at risk. [v078]
- **Shouty attention tactics**: ALL CAPS, strings of exclamation marks, waving-hand or "turn sound on" devices. They work, and Meta penalises them. [v330]
- **Before and after**: side-by-side before/after of bodies, physiques or cosmetic results gets disapproved, and even hair-salon before/afters are a risk. For non-body transformations such as kitchens, show before then after in sequence in a video. [v015, v041, v111]
- **Fake testimonials with AI actors**: an AI actor must never claim to have used the product or got results. Script them as a third party passing on true, verifiable facts. [v056]
- **Misleading post-click experience**: surprise shipping costs, long undisclosed delivery times, a page that does not deliver what the ad promised. [v243, v140]
- **Meta's own edits**: creative enhancements can alter claims and visuals, and they can switch back on whenever an ad is duplicated, edited or even previewed. In regulated industries, re-check them after touching an ad. [v012]

Rewording examples (the pattern: remove "you" plus an attribute, describe the outcome in everyday terms, shrink the number):

| Risky | Safer | Source |
|---|---|---|
| "Are you a parent of a newborn?" | "Parents of newborns love our ..." | [v112] |
| "Are you getting divorced?" | A third-person statement about the group: "People like X have done well with ..." | [v112] |
| "Are you suffering from anxiety?" | "Young men who are anxious often struggle with ..." | [v104] |
| "Do you have excess body fat?" | "People with excess body fat have found ..." or "Studies show ..." | [v112] |
| A question that dwells on the reader's problem | A statement about the product and its benefit: "Our product helps fix bad posture" | [v356] |
| "Have you ever thought about installing solar panels?", "Are you in the market for a new home?" | "Ever thought about installing solar panels?", "In the market for a new home?" (minimum fix when a question keeps being rejected) | [v380, v356] |
| A 20 lb first-month weight-loss result | A modest real result (6 lb in the first month); or "fit into a smaller pair of jeans", "get beach ready" | [v112, v286] |
| "Make $1,000 every month", "Be your own boss" | Not allowed in Meta's own examples; drop the promise and show a toned-down real example | [v112, v098] |
| A 60x ROAS client result in the primary text | A 12x (or 5–6x) example; put stronger true figures (a 19–20x screenshot) inside the video or image, not the copy | [v112, v098] |
| "guaranteed return", "investment opportunity", "make money", "weight loss" | Plain-language descriptions of the outcome; longer wording is fine | [v286] |
| Call-outs by medical, political, religious, ethnic or low-income traits | Call-outs by location, life event or interest: "West Londoners", "Moving home?", "Soccer fans" | [v356] |

Rules for using these:
- They are for ads that actually comply and are being misread by the automated review. Claims must still be true. Do not use rewording or the copy-to-creative move to hide a real violation. [v286, v112]
- When an ad touches both personal attributes and outcome claims (most health and weight-loss ads), dial back further than either rule alone requires. [v112]
- Test a bold claim as one ad among six or seven safe ones, so a disapproval barely moves the account's rate. [v330]
- When ads keep being rejected, add a copy variation with no personalisation at all. [v356]

## Special ad categories and regulated industries

- **Categories:** financial products and services (credit), employment, housing, and social issues, elections or politics. Requirements vary by country. [v112, v029]
- **Where:** campaign level, "Special ad categories". It applies to every campaign type, including awareness and content campaigns that do not sell directly. [v029, v054]
- **Rule: if in doubt, declare.** Running these ads undeclared is very likely to get the account disabled, and recovery from that is very hard. Over-declaring is the cheaper mistake. [v112]
- **Cost of declaring:** some ad set targeting options are removed. That matters little now that broad targeting with Advantage+ audience is the standard setup. [v112, v076]
- **Audit live campaigns**, not only new ones, for missing declarations. [v112]
- **Age-restricted products:** use the minimum-age control (18 to 25) for legal limits such as 21+. Account-wide limits (for example nobody under 21 ever sees the ads) sit under "Advertising settings". These are compliance controls, not targeting levers. [v076, v070]
- **Where wording is legally fixed:** turn off "Optimize text per person" (Meta may move and combine text fields) and review every creative enhancement, since Meta may alter claims and visuals. [v012, v052]
- **Instant forms in regulated industries:** set "Flexible form delivery" to manual so required disclaimers and questions always show, and use the custom disclaimer field. See `lead-generation.md`. [v067, v130]

## When an ad is disapproved

1. Read the policy reason Meta gives (it is not always stated reliably). It decides whether to reword or to contest. [v112]
2. Check the mechanical causes first: the landing page loads, the form and buy button work, the URL goes to the product in the ad, there is a way to navigate off the page. [v112]
3. If the ad complies, request a review. Manual review overturns the large majority of wrongful disapprovals (about 99% in one agency's experience, 2021), but takes days to weeks. [v286]
4. If a trigger is visible, do not keep resubmitting the same ad, since disapprovals accumulate against the account. Reword using the table above, move strong claims from copy into the creative, or zoom out the imagery, and submit the new version. [v112, v286]
5. Watch the account's overall disapproval rate while this is going on. Hold back similar ads until one version is approved. [v330]
6. Check delivery. When an ad is disapproved, its spend shifts to the remaining, possibly weaker ads; at large budgets this goes wrong fast. [v121]
7. The rejected-ads record is in Account Quality (the name and location may have changed since the source). [v243]

## When the account is restricted or disabled

The source process is for a disabled ad account; the same routes are the ones available for a restriction. Triage first, because it sets expectations and the wording of the appeal. [v027, v112]

| Situation | Recoverable? | Approach |
|---|---|---|
| Disabled with no rule broken | Nearly always | Say you were flagged for X, did not do it, and that an error occurred |
| Minor rule broken | Often | Say you have reviewed the policies, understand the breach, it was minor and will not recur; ask for reinstatement |
| Serious violation (prohibited product, content judged discriminatory, undeclared special ad category) | No, or very hard | Start a new account and fix the practice |

Steps, in order. Steps 2 to 4 can run while step 1 is pending. [v027]

1. **"Request review"** in the disable notification. Supply what is asked. Cite the reason Meta gave, say which policy you think was misread, mention anything that could have triggered it (for example someone gaining access), attach screenshots, and say why the account matters to the business. Reviews usually go to a human queue: often a few weeks, sometimes no reply, sometimes an instant automated rejection. [v027, v169]
2. **Meta AI business assistant** (the current first move after the review request): go to facebook.com/business/help while logged in, open the assistant, or "Get support" if the assistant is not shown. Ask why the account was disabled and what will get it back.
   - Occasionally the assistant solves it alone, for example by revealing failed payments or an outstanding balance; paying it reinstates the account.
   - The real aim is a human. Follow the suggested steps, then say you have tried them and ask what to do next; it usually offers a support agent, or you can ask for one. Availability depends on region, spend level and account age.
   - Human agents can often reinstate the account during the chat. Explain as in step 1. If the agent cannot help, close the chat and start again to get a different agent; this can take several attempts.
   - An agent may say the review has been expedited or a note added. The effect is unclear, and it cannot hurt. [v027, v169]
3. **Email your Meta rep** (the title changes: marketing expert, marketing pro) and ask them to look into it or speed it up. They often cannot help, and sometimes can. [v027]
4. **Complete Meta business verification**, if the portfolio is still accessible, then appeal again. Appeals that failed have succeeded after verification. [v027]
5. **Paid support case:** a Meta One subscription from the Advanced tier up includes human support cases (see "Support routes"). This route is newer than the method above. [v009]
6. **If Meta confirms a permanent disable:** stop appealing. The only remaining route is legal action, which only makes sense for very large spenders. Create a new ad account, and a new business portfolio if that was taken down too. Audit the old practices against the policies named in the notice first. Expect slower, weaker results for a while because the conversion history is lost; you can still advertise. [v027, v169, v133]

Do not:
- Pay an "ad account recovery" service. The usual outcome is money lost, no recovery, and a risk of further restrictions on connected assets. Deal with Meta directly, or through an agency you already work with that has a higher-level Meta relationship. [v027]
- Buy an aged or agency ad account as a replacement. [v027]
- Panic-rebuild everything on day one. Wrongly disabled accounts usually come back. [v027, v133]

## Protect the account in advance

- Complete full Meta business verification now. It lowers the chance of a disable and makes recovery easier. [v027]
- Use two-factor authentication with an authenticator app, not SMS; hacking is one of the routes to a disabled account. [v133]
- Give people scoped access through the portfolio; never share logins. [v030]
- Declare special ad categories whenever there is doubt, on live campaigns too. [v112]
- Keep the disapproval rate low: add ads in small groups in new accounts and sensitive niches, and isolate bold claims among safe ads. [v330]
- Re-test landing pages, forms and buy buttons after every website change; keep footer navigation; no pop-ups that block leaving. [v112]
- Keep the purchase experience good (delivery times as stated, real support), because buyer feedback scores can restrict ads. [v316]
- No engagement bait and no shouty formatting. [v078, v330]
- After duplicating or editing an ad, re-open creative enhancements and confirm unwanted ones are still off. [v012]
- Accept calls from Meta reps when offered, so there is a named contact to escalate to later. [v027, v133]
- If the business depends on Meta, consider the Meta One Advanced tier for the human support case. [v009]
- Lock the pixel to your own domains (Events Manager > pixel settings > "Traffic permissions" > allow list). See `tracking-and-attribution.md`. [v206]
- Keep advertising steadily and cleanly: years of spend history are themselves protection, and consistency in what the account advertises also helps optimisation. [v330, v113]

## Support routes as of late 2026

| Route | Where | Good for | Limits |
|---|---|---|---|
| "Request review" | The disapproval or disable notification | The formal appeal; always do it first | Slow (days to weeks); sometimes an automated rejection |
| Meta AI business assistant | Inside Ads Manager for most accounts (colourful wheel icon on the left) and at facebook.com/business/help | Instant first answer on account issues (why disabled, failed payments, spend limits, delivery errors); campaign analysis, benchmarks, creative ideas | Fixes a minority of account issues on its own; advice needs filtering (see next section) |
| Human support agent | Through the assistant, or "Get support" | Reinstating a wrongly disabled account during the chat; expediting a review | Not offered to everyone: depends on region, spend and account age; quality varies, so retry for another agent |
| Meta rep | Email the rep from any call you accepted | Escalating a disable; technical questions on newer features | Larger spenders get one (threshold unknown); quality rises with spend; optimisation advice is mixed |
| Meta One subscription | Paid, per platform (Instagram, Facebook, WhatsApp) | Human support cases (from the Advanced tier), verified badge, impersonation protection | Case allowance depends on tier |
| Existing agency with a partner-level Meta relationship | Your agency | Escalation through dedicated partner reps | Only for accounts the agency already manages |
| Paid "recovery" services | Third parties | Nothing | Avoid |

[v009, v024, v027]

Meta One tiers (replaces or extends Meta Verified; as described in October 2026). [v009]

| Tier | Price | Support cases | Other contents |
|---|---|---|---|
| Essential | $14.99/month | None listed | Verified badge, impersonation protection, enhanced link sheet |
| Advanced | $50/month | 1 human support case per month | Adds featured-in-feed (Facebook), optimised search, bold follow button and follow invites (Facebook), clickable links in posts and Reels (Instagram 4 per month, Facebook 8), shared Instagram access (4 seats), 500 WhatsApp broadcast credits |
| Expert | Not stated | 5 per month | — |
| Max | Not stated | Unlimited | 5,000 WhatsApp broadcast credits |

Advanced is the recommended tier for most businesses that depend on Meta: the badge builds trust for expertise-based offers, and the support case covers account issues. [v009]

Using the AI business assistant for analysis: tick the campaign and make sure its ad sets and ads are also selected, then open the assistant and use a suggested prompt or your own ("how do I decrease my cost per lead"). It remembers earlier conversations, compares results with industry benchmarks, and can sometimes apply a change with one click. "Account Center accounts" in its output means Facebook and Instagram users. A new account reads far above benchmark cost while it is still learning (one example: 154% above, and already improving). For account issues, Meta's figure is about 20% (reported once as the share of issues the assistant resolves, once as the improvement in resolution rate): use it first because it is instant, and expect to need a human most of the time. [v007, v024]

## Meta's own advice: what to follow and what to filter

Default position: Meta's recommended settings are mostly right, because Meta earns more when advertisers succeed. Follow them unless there is a specific reason not to, and apply a filter to the two kinds that serve Meta more than the advertiser: spend more, and optimise for something other than the real conversion. This applies equally to reps, the AI business assistant, opportunity score, campaign score and in-product warnings. [v133, v024]

| Recommendation | Verdict | Reason and conditions |
|---|---|---|
| Use Advantage+ audience; do not hard-limit reach; audience too small | Follow | Meta's targeting beats manual limits in most accounts. See `targeting.md` [v133, v097] |
| Advantage+ placements on Sales and Leads campaigns | Follow | Meta only buys placements that convert when optimising for conversions; manual placement selection is being removed anyway (rolling out since September 2026). See `campaign-setup.md` [v010, v133] |
| Set up Conversions API alongside the pixel; fix Events Manager warnings | Follow | Better data improves optimisation; quoted about 13% lower cost per result. See `tracking-and-attribution.md` [v122, v074] |
| Switch to "Maximize value of conversions" (sales with varying order values) | Follow for new builds | Do not switch a long-running winner without a test result. See `campaign-setup.md` [v024] |
| Creative fatigue flag on an ad | Verify, then act | Check frequency and how long the ad has run; if confirmed, bring in new creative [v122] |
| Create more ads; diversify formats; new hooks on winners | Follow | Matches current creative practice. See `creative.md` [v024, v007] |
| Combine ad sets | Follow for direct-offer campaigns | Ignore for the omnipresent content strategy, which needs many ad sets by design. See `local-and-high-ticket.md` [v122, v131] |
| Increase the budget | Filter hard | Valid only when results are already good and the business can deliver more. Never to exit learning on an unproven offer, never beyond capacity [v122, v024, v133] |
| Run Traffic, or optimise for landing page views, on a new account | Reject | Produces a large results number and fewer conversions [v133, v141] |
| Add creative enhancements | Low impact; review one by one | Meta's own estimate for "standard enhancements" was about 3% lower cost per result. Decline on already-edited video and text-heavy images; avoid AI backgrounds that depict work a service business did not do; fine for product images. See `creative.md` [v024, v097] |
| "Automatic adjustments" (Meta applies recommendations itself) | Leave off | Not every recommendation should be taken, and Meta cannot do the real fixes such as new creative [v122] |
| "Personalized destinations" | Turn off when the funnel depends on a specific page | Meta may send clickers to a different URL; acceptable for stores with only product pages [v012] |
| A setting the account already has, or advice that contradicts the data | Ignore | The assistant sometimes recommends things that are already on [v024] |

Scores: opportunity score (0–100, under "Account overview", also the "Actions" column) and campaign score measure how closely the setup matches Meta's best practice, not results. A perfectly scored campaign for an unwanted offer still fails. Moving from about 60 to the 90s usually helps; 100 is not required when each deviation has a reason. Use the predicted gain to prioritise: 27–45% is worth acting on, a small gain on a working ad can wait. [v122, v029, v097]

Reps: take the call, keep the contact, use them for escalation and for technical questions on newer features such as incremental attribution. Treat their optimisation advice like any other recommendation in the table. [v027, v074, v133]

## Outdated advice to ignore

| Old rule | Current rule | Why it changed |
|---|---|---|
| Warm up a new account or pixel with Traffic or Engagement campaigns before running conversions | Run Leads or Sales campaigns optimised for the real conversion from day one | Traffic clicks do not train conversion optimisation; Meta delivers exactly the action requested [v025, v095] |
| Avoid declaring a special ad category unless certain, because it limits targeting | Declare whenever in doubt | Broad targeting is standard now, so the cost is minor, while an undeclared category can end the account [v112] |
| After a disable, go straight to the support form or live chat link at the bottom of the Business Help Center | Request review, then use the AI business assistant at facebook.com/business/help to reach a human, then the rep, then verification | The assistant is now the gateway to human support and sometimes resolves the issue itself [v027] |
| A business portfolio is only needed with several ad accounts, pages or people | Always set one up | It holds ownership, scoped access, the pixel and verification, and boosting from the apps costs more for less control [v030, v025] |
| Meta Verified as the name of the paid badge subscription | Meta One, sold in tiers; human support starts at Advanced | Product replaced or extended in 2026 [v009] |
| New account: use interests as hard boundaries, avoid Advantage+ shopping campaigns, 2–3 ads per ad set at most | One Advantage+ Leads or Sales campaign, one ad set, several ads, targeting inputs as optional suggestions | Campaign types merged into one Advantage+ structure, and detailed targeting can no longer be a hard limit [v025, v076] |
| Raise the budget until the ad set exits the learning phase | Prove the offer and creative at a small budget; campaigns can perform while "Learning limited" | The spend-more recommendation serves Meta first [v133, v122, v219] |
| Follow Meta's guidance of no more than 6 ads per ad set | Ad sets with 20+ diverse ads are normal. See `creative.md` | The Andromeda retrieval system matches ads to individuals, so more distinct ads help [v055] |
| Build social proof with an Engagement campaign or by asking for likes and comments | Launch directly in a Leads or Sales campaign; winners accumulate social proof | Engagement bait breaks policy, and paid engagement is mostly not likes or comments [v078] |
| Dropping "you" from a question is enough ("In the market for a new home?") | Prefer third-person framing for anything touching a personal attribute | Newer guidance is to avoid direct second-person questions and statements altogether [v112] |

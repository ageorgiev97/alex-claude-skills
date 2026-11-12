# Lead Generation

Lead campaigns end to end: where to capture the lead, how to build the instant form, how to qualify leads so Meta only learns from good ones, the website and messaging equivalents, the call, lead magnet and webinar funnels, feeding CRM outcomes back, and follow-up. Read it when planning, building or auditing any campaign whose result is a lead, a booking or a conversation rather than an online purchase.

## Contents
- The principle: Meta optimises literally
- Allowable cost per lead
- Where to capture the lead (conversion location and performance goal)
- Instant form type: the current rule
- Instant form setup, field by field
- Conditional logic: disqualify before the lead counts
- Calendar booking inside the form
- Website lead funnels and qualified-lead events
- Messaging and WhatsApp lead campaigns
- Funnels: booked calls, lead magnets, webinars
- Feeding CRM outcomes back
- Follow-up rules
- Lead quality problem table
- Benchmarks and case studies
- Outdated advice to ignore

## The principle: Meta optimises literally

Meta finds the cheapest people who will trigger the event you optimise for, and it only sees the events you send. If every form fill counts as a lead, delivery drifts to people who fill in forms easily, and those are disproportionately poor prospects. Every lever in this file is a way of making the optimised event mean "a lead this business wants". [v008, v011]

- Make the counted event a qualified, reachable lead (conditional logic, SMS verification, a qualified-only website event).
- Tell Meta what it cannot see: which leads became customers (CRM feedback), which lead types are worth more (lead values, value rules), when someone can answer the phone (scheduling).
- Report on cost per qualified lead and cost per customer, not cost per lead (CPL). Two offers with the same CPL can differ 2x in lead-to-customer rate, and some ads produce mostly junk. [v008, v084]
- Expect little change on day one and a large one after 30–90 days, because the learning compounds. [v008]

Use the Leads objective when there is a step between the click and the sale (call, quote, visit, proposal) or the sale lands outside the 7-day click window. Use Sales when the purchase happens online, quickly, and is tracked. Never pick landing page views, link clicks, reach or impressions as the performance goal inside a leads campaign; it then behaves like a traffic or awareness campaign. [v029, v087, v091] See `campaign-setup.md`.

## Allowable cost per lead

Break-even CPL = first-transaction value × gross margin × lead-to-customer rate. Example: $1,000 × 50% × 20% = $100. At 75% margin it is $150; at 75% margin and a 10% close rate, $75; at 30%, $225. Close rate moves the allowable CPL as much as anything in the ad account, which is why follow-up sits in this file. [v001]

CPL rises with spend, so scale only with headroom below break-even: $200 against a $225 limit leaves almost none; $50–100 allows aggressive scaling. [v001] Formulas: `offers-and-economics.md`. Scaling: `testing-and-scaling.md`.

## Where to capture the lead

Set at ad set level under "Conversion location". The location decides which performance goals are offered. [v087]

| Conversion location | Use when | Performance goal |
|---|---|---|
| "Website" | There is a decent landing page; you want a qualified-only event, lead values, or a self-booking calendar on the page | "Maximize number of conversions" on the qualified event; "Maximize value of conversions" once lead types carry different values |
| "Instant forms" | No website or a weak one; lowest CPL and most volume wanted; you want SMS verification, conditional logic or in-form booking | "Maximize number of leads"; "Maximize number of conversion leads" only if CRM outcomes flow back |
| "Website and instant forms" | Unsure which is better; Meta picks per user. The default in many accounts as of 2026; a simple switch worth testing | As above |
| WhatsApp | The market uses WhatsApp and buyers have questions before committing | "Maximize number of conversations" (in Europe click-to-WhatsApp is forced to "Maximize number of link clicks") |
| Messenger / Instagram | Lead capture inside those apps (little detail in the source) | Locked to "Maximize number of leads" |
| Calls | Not covered in the source material | — |

[v049, v067, v087]

Trade-off. Instant forms keep people on the platform: lower CPL (often much lower), more volume, often cheaper CPMs (cost per thousand impressions), no dependence on a weak site. Their weakness is quality, because contact details are prefilled and a lead can be submitted in two taps and forgotten. Website leads cost more and are more invested, and they depend on pixel and Conversions API tracking, whereas on-platform leads are recorded in full. [v083, v130, v240] With SMS verification, conditional logic and in-form booking, much of the quality gap can now be closed on the form itself; the agency behind this material is moving its own call-booking funnels from website to instant forms. [v011, v018]

If both locations run and CRM data shows website leads close better, apply a value rule with the "conversion location" criterion to bid more for them. [v028, v052] See `targeting.md`.

Which event to optimise: the lowest-funnel event that still produces at least 20–25 conversions a week (purchase, else booked call, else webinar attendee, else registrant). Meta ideally wants 50+ a week per ad set. [v013, v014]

Bid strategy: "Highest volume" for most lead generation. Add a cost per result goal only when the affordable CPL is known and lower volume is acceptable. [v029, v139] See `campaign-setup.md`.

## Instant form type: the current rule

Three form types exist: "More volume" (least friction), "Higher intent" (adds a review screen and carries the SMS verification option), and "Rich creative" (adds persuasive content). [v067, v130]

**Rule as of late 2026: when a person will follow up each lead (service, high-ticket, business-to-business, local), build the form as "Higher intent" with "Require leads to verify their phone number with a one-time passcode (SMS)" ticked, plus one conditional-logic qualifying question.** Reason: SMS verification forces a real phone number, removes bots and people who barely noticed they submitted; the qualifier keeps unfit people from ever counting as a lead. Both clean the signal Meta optimises on. [v008, v011]

Expect CPL to rise significantly and volume to fall. That is the intended trade: when more than half of leads are poor, paying 50–80% more per lead is well worth it. [v067, v083]

Exceptions and adjustments:

| Condition | Setup |
|---|---|
| Pure lead magnet or list building, nobody phones the lead | "More volume", name and email; phone optional, so no SMS step [v083] |
| New form using the "Book time" action | Start without added qualifiers to build conversion volume; add them only if bookings are poor or no-show [v018] |
| Older, less tech-savvy audience, or a country where SMS codes are unusual | Test SMS verification against autofill-off before committing; it can hurt here [v083] |
| Milder step wanted | Turn off autofill on email and phone: a noticeable but not massive CPL rise, better contactability [v067, v083] |
| Problem is trust or understanding, not junk (high-ticket, unfamiliar or sceptical market) | "Rich creative": higher CPL and lower volume than "More volume", significantly better conversion to customer; it adds persuasion rather than cutting people off [v130] |
| Existing low-friction form whose leads already convert well, with sales capacity to spare | Keep it and test the stricter form beside it instead of switching. The friction pays when quality is the real problem; fewer leads can leave sales idle [v083, v139] |

Notes:
- The friction cost is real: "Higher intent" also removes some people who fit but have low intent, whom a good salesperson could have converted. Accept that only because the counted leads become a far cleaner training signal. [v130]
- "Rich creative" was a separate form type when last described (2024). Check in the form builder whether it can be combined with SMS verification; do not assume.
- Raise quality with verification, autofill-off or a qualifier, not by making the form longer. [v067]
- SMS verification and autofill-off were in limited testing in 2025 and are treated as generally available in 2026; confirm the options exist in the account.

## Instant form setup, field by field

Path: Leads campaign > ad set "Conversion location" = "Instant forms" (or "Website and instant forms") > ad level, "Destination" > Instant form > "Create form". Build a unique form rather than a template. [v130]

A form cannot be edited once created. To change it, duplicate, amend and save as a new form, so check every field first. [v130]

| Section | Setting | What to do and why |
|---|---|---|
| Form name | — | Offer name plus a version marker, so forms can be compared later |
| Form type | "Higher intent" / "More volume" / "Rich creative" | Per the rule above. Switching type wipes much of the form |
| Form type | SMS verification | Tick "Require leads to verify their phone number with a one-time passcode" under "Higher intent" [v067] |
| First page | Flexible form delivery ("Allow Meta to adjust or remove form elements...") | Leave on "Optimize". Switch to manual only when elements must always appear: legal disclaimers, mandatory questions, regulated industries. A qualifier you rely on counts as a mandatory question [v067] |
| Intro | Background image (required) | Use the ad image or upload one. It must match the ad; a mismatch makes people leave. The form image measurably changes results [v130] |
| Intro | Greeting (keep on) | Headline restates the offer from the ad ("Sign up for your free ... call"). Paragraph sets expectations: "Enter your info and we'll be in touch within 24 hours". Say 24 hours, not "right away", which deters people who are busy now; then follow up far faster [v130] |
| Intro (Rich creative) | Benefits | Bullets, 57 characters each |
| Story (Rich creative) | "How it works" | Numbered steps; title 23 characters, description 54. Use when buyers do not know how to get started; write each step to sell |
| Story (Rich creative) | Products / Services | Carousel cards, title 20 characters. Only list other offers you would be equally happy to sell; they distract from the advertised one |
| Story (Rich creative) | Social proof | 2–5 review cards; also "Accredited by" / "Certified by" for safety-regulated trades. Use whenever you have it |
| Story (Rich creative) | Incentives | Offer plus deadline, only if the deadline is real |
| Questions | Custom questions (shown before contact fields) | Multiple choice, short answer or conditional logic. One qualifier is the default now; collect everything else on the call [v011, v130] |
| Questions | Prefill description | Say what to do and what happens next |
| Questions | Contact fields | Email and Full name are default. Add Phone number: "Add category" > "Contact fields" > Phone number, and keep it mandatory for service lead gen. Email-only follow-up rarely reaches people [v083, v130] |
| Questions | Autofill | Optionally deselect autofill for email and/or phone. Prefilled details can be 10–15 years old [v083] |
| Questions | Everything else | Ask the bare minimum (name, email, phone in 90%+ of cases). Extra fields cut volume heavily; get the address on the call [v130] |
| Privacy | Privacy policy URL (mandatory) | Must be a live URL, not a PDF. No website: publish a one-page site that hosts the policy |
| Privacy | Custom disclaimer | Regulated industries only |
| End page | Headline and description | Confirm the next step and prime the call: "We'll be in touch within 24 hours... please keep an eye out for our call" |
| End page | Additional action | "Go to website" (default); "View file" (delivers a lead magnet); "Call business" (urgent services; most still wait for the callback); "Book time" (see below); "chat via WhatsApp" (not in every account); "redeem a promo code" (niche) [v018, v067] |
| End page | Button text and link | Point it at something that sells before the call: "View portfolio" or "View testimonials" [v130] |
| Ad level, below the form | "Follow up with leads" (chat with leads from instant forms) | If the lead consents, a Messenger or Instagram chat opens with their details. Raises contact rate; needs staff or a chatbot to answer [v067] |
| Delivery | Leads by email | Leads can be emailed at a chosen frequency as well as landing in Leads Center or the CRM. Useful at low volume [v067] |

Treat the form as creative. Split test forms (image, copy, angle) by running separate ads with different forms. [v130]

## Conditional logic: disqualify before the lead counts

Purpose: an unfit person never submits, never appears as a lead, and never teaches Meta that people like them are a result. [v011]

1. Ad level > Instant form > "Create form" > Questions > turn on "conditional logic".
2. Add a multiple choice question.
3. For each disqualifying answer choose "Close form". The person sees the end page for non-leads; no details are submitted and no lead is recorded.
4. For each qualifying answer choose "Submit form". The person continues to the contact fields and the end page for leads.
5. Edit both end pages. Leads: next step and call priming. Non-leads: a polite "based on your answers we may not be the best fit" with a website link.

[v008, v130]

Design rules:
- Use realistic tiers, not a blunt two-option question. Example: budget "0–5k" closes; "5–10k" and "10–20k" submit. [v008]
- Qualify on what actually disqualifies in the sales process: budget, timeline (needs it tomorrow, or not for two years), location, industry, education, life stage (has a child of the right age). [v008, v011]
- A location question is the direct fix for out-of-area leads. [v011]
- Keep it to what is needed; every question costs volume. Further fit questions belong on the call. [v130]

## Calendar booking inside the form

End page > Additional action > "Book time" > paste the scheduling link (Calendly and GoHighLevel at launch, HubSpot next). Contact details prefill the booking, and the lead is still captured if they do not book. Works only on newly created forms. Global rollout was expected around October 2026; check the account. [v018]

Why: a booked call is a far better lead than a form fill, and this keeps the low cost and friction of an on-platform form.

- Start without extra qualifiers so the ad set builds volume; add them if bookings turn out poor or no-show.
- Keep calendar availability accurate.
- Use a specific call-to-action label ("Book time", "Schedule a demo").
- Send confirmations and reminders, and cancel slots that go unconfirmed.

[v018]

## Website lead funnels and qualified-lead events

The website equivalent of conditional logic is to fire the optimised event only for qualified respondents. [v008, v011]

1. Put the qualifying question in the website form (budget tiers, or the same qualifiers as above).
2. Send qualified respondents to thank-you page A, which fires the event you will optimise for (for example "Submit application").
3. Send unqualified respondents to thank-you page B ("sorry, we can only work with...", or a cheaper alternative), which fires a different event or none.
4. In the ad set: conversion location "Website", choose the dataset, and select the event that only page A fires.
5. Report cost per qualified lead from that event.

When lead types differ in value, switch the performance goal to "Maximize value of conversions" and attach a value to each event, estimated at capture as sale value × close rate. Otherwise Meta treats a $200 lead and a $5,000 lead as equal and chases the cheap one. [v045, v087]

| Case | Setup | Example |
|---|---|---|
| Several services | Separate landing and thank-you pages, each firing an event with its own value | Roof replacement $20,000 × 1-in-5 = $4,000 per lead; roof repair $2,000 × 50% = $1,000 per lead |
| One service | Budget question routes to two thank-you pages with different values | Low-budget page declines or points to a cheaper option |

Requirements: pixel plus Conversions API, so events and values arrive reliably. The performance goal dropdown only unlocks when the conversion location is a single location such as "Website". CPL may rise; total lead value should improve. [v045, v049] Event setup: `tracking-and-attribution.md`.

Page rules that matter for leads: one page per offer, repeating the ad's promise; no header menu; one action. Turn off site links, browser add-ons and "Personalized destinations" when the funnel depends on a specific page. [v012, v049, v084] See `offers-and-economics.md`.

## Messaging and WhatsApp lead campaigns

Click-to-WhatsApp replaces click > landing page > book call > wait. Automated first messages qualify the lead and a person takes over. It is less friction for the prospect and often cheaper to run than a sales-call funnel. [v033]

Fit: [v033, v051]
- Businesses that already answer many customer questions; offers with objections to clear first; higher-ticket, new or unfamiliar offers; funnels that struggle to convert cold traffic. It can replace the sales call or sit before it.
- Market dependent. The US uses WhatsApp far less (about a third of adults and growing). UK: better for high ticket than low ticket. India and Brazil: works for almost anything.
- Prospects expect fast replies. Do not run it without staff or automation to answer.

Setup: [v051, v087]
- Requirement: a WhatsApp Business account added to the business portfolio. A greyed-out WhatsApp option usually means this is missing.
- Leads campaign: ad set conversion location = WhatsApp, performance goal "Maximize number of conversations". In Europe privacy rules force "Maximize number of link clicks".
- If the sale itself can be tracked and happens quickly: Sales campaign, conversion location "Message destinations" with WhatsApp ticked, performance goal "Maximize number of conversions", event Purchase. Needs pixel and Conversions API. Available in Europe.
- Ad level chat builder: tailor the greeting (small effect). Call to action under the greeting: "None" normally; never "Visit website" (leaving the chat is usually a dead end); "Call now" only if you take inbound calls. Either customise the pre-filled message to match the offer or use "Frequently asked questions".
- Write the FAQs as the objections that stop people buying, where the answer moves them forward (minimum spend, programme length, case studies). Chat builder and FAQ choices change lead and conversion rates a lot; test them.

Also: ask for opt-in to marketing messages during or just after the first chat. Opted-in contacts form a list that works like email or SMS with higher engagement. [v051] Meta's "Business AI" for WhatsApp was in limited testing as of 2025.

## Funnels: booked calls, lead magnets, webinars

Match the funnel to the size of the ask. A free quote, consultation or survey can be advertised directly to cold audiences, however expensive the eventual sale, because the next step is small. Add a warming step when direct-to-offer is not working or lead quality is poor. Do not hop funnels every month; improve each element of a proven one. [v250, v349, v536] Funnel choice by price point: `offers-and-economics.md`.

### Booked calls

- Capture: instant form with "Book time", or a landing page with a self-booking calendar optimised for the schedule event, or an application form firing a qualified event. A self-booking calendar beats a contact form: more commitment, so fewer but much better leads, and no back-and-forth. [v008, v018, v589]
- Offer in the ad: one clear, low-barrier offer, named exactly ("Free kitchen design consultation", not "free consultation"). Never several offers in one ad. [v327, v365]
- Creative: a simple image often wins for a small ask such as booking a free call. A high-ticket ask to cold audiences needs longer video with proof. [v084, v096] See `creative.md`.
- Call length 25–45 minutes; 15 if its only purpose is to arrange a visit. [v587]
- Some bad bookings are inevitable even with heavy pre-qualification. Aim to raise the share contacted and converted. [v083, v107]
- For customer values around $1,000+ run the omnipresent content campaign alongside; prospects with many prior exposures close far more often. [v131] See `local-and-high-ticket.md`.

### Lead magnets

Flow: cold ad > opt-in page > thank-you page that doubles as a sales page > booking calendar, backed by email follow-up and ads to opt-ins who have not booked. [v250, v587]

- Magnet: something the market wants, high value, quick to consume, delivered automatically (guide, template, checklist, short video, quiz, pricing pack). It still has to be sold with benefit bullets. [v306, v587]
- Opt-in page: no header menu, the word "free", a headline naming the magnet, about four benefit bullets, an image, name and email only, one contrasting button, privacy link. Asking for a phone number here is premature and lowers conversion. [v587]
- Thank-you page: confirm delivery ("in your inbox in 10 minutes"), then a short video (about 50 seconds) that introduces the service and invites a no-obligation call, repeated in text below, with a large button. Momentum is highest right after opt-in. [v467, v587]
- Campaign: Leads objective, optimised for the Lead event on the thank-you page. Not traffic. [v167, v587]
- On-platform version: instant form with "View file" delivers the magnet; still push the contact into the CRM for follow-up. [v130]
- Creative: images and carousels suit a free sign-up. [v096]
- Cost: adding a magnet layer roughly doubles the cost of the eventual sales lead and takes longer to build; the gain is quality. [v467]
- Reaching only opt-ins with a follow-on pitch needs a true warm-only ad set: "Further limit the reach of your ads" > untick "Use as suggestion" on the custom audience. Added normally, a custom audience is only a suggestion. [v052] See `targeting.md`.
- Poor fit: low-priced impulse products, which cannot fund several steps; and cases where a cheap paid first step outperforms a free guide (a local physiotherapy chain got opt-ins that never became patients). [v077, v080]

### Webinars

- Flow: ad > registration > webinar > retargeting > email sequence > sales page. Suits high-end courses, coaching and services, not cheap products. [v349]
- Optimise for the lowest event with 20–25+ a week: purchase, else booked call, else attendee, else registrant. [v013]
- Sign-up ads: images plus some carousels. Registration is a small ask and long video loses people before the call to action. [v096]
- When the purchase cannot be tracked, judge on cost per registration. [v133]

## Feeding CRM outcomes back

Lead quality is invisible to Meta unless it is told. In order of preference: (1) feed outcomes back and stay broad; (2) add audience suggestions; (3) hard targeting, accepting higher CPL and lower volume. [v089]

| Mechanism | How | Condition |
|---|---|---|
| Conversion leads optimisation | Instant forms performance goal "Maximize number of conversion leads" | CRM integrated and tracking; the downstream conversion must fall inside the attribution window (7-day click at most) [v087] |
| Lead statuses | Keep statuses current in Meta's Leads Center (sufficient alone for instant form leads) or in the CRM | Conversion-leads optimisation is useless if sales do not mark outcomes; they tend not to, so chase it [v084] |
| Offline / CRM conversions | Send through the Conversions API | Lets you compare offers and ads on lead-to-customer rate [v084] |
| Lead values | "Maximize value of conversions" with a value per website event | Lead types differ in worth [v045] |
| Value rules | Bid up or down by age, gender, location, device, placement or conversion location | Only for what Meta cannot see, such as close rate by segment. Set the percentage from CRM data (35+ closes 30% better = +30%); plan 90–120 minutes of analysis [v013, v028] |
| Customer lists | Upload with an "audience label" (qualified lead, disqualified lead, existing customer, high value, low value) and a value column | Lists do not auto-update unless synced [v076] |

At large budgets, integrating the CRM and optimising for conversion leads or value is the expected setup; at small budgets plain highest volume on the right event is enough. [v014] Also connect the CRM so leads arrive automatically with a notification; speed depends on it. [v327] Check Ads Manager lead counts against the CRM. [v061] Implementation: `tracking-and-attribution.md`; value rules: `targeting.md`.

## Follow-up rules

Lead-quality complaints are usually follow-up problems. The biggest drop-off in most lead funnels is simply making contact. [v133, v327]

| Rule | Number |
|---|---|
| First call | Within 5 minutes, ideally 1–2 minutes. Hard limit 30 minutes, an hour at the outside. Never "by end of day" [v130, v133] |
| Persistence | Call twice a day for 14 days, plus email and SMS, until they answer or ask you to stop [v133] |
| Channel | Phone first. Email alone rarely reaches people (spam filters, forgotten submissions) [v130] |

- Case: a client at $15 per lead and a 4:1 return wanted $12 leads to reach 5:1. Changing only speed and persistence tripled revenue from the same leads (12:1), which then made $25–40 leads affordable and allowed scaling. [v133]
- SMS-verified leads are far more likely to pick up. [v083]
- Leads that arrive when nobody can call are worth less, but Meta values them equally. Ad scheduling fixes this (for example Monday–Friday 9–5 for business-to-business) and can double return for some businesses. It needs a lifetime budget, the main case where a lifetime budget is justified. [v052] See `campaign-setup.md`.
- Show ads to leads alongside calls and emails: testimonials and proof to people who submitted but have not bought; the original offer to people who opened the form and did not submit (this group grows with SMS verification). Lead form audiences keep 90 days at most. [v083, v132]
- Long sales cycles (a kitchen fitter: 3–6 months) mean leads from months 1–2 close in months 4–5. Do not judge lead quality early. [v385]
- High-value local services often hit capacity and pause ads. That is expected, not failure. [v120]

## Lead quality problem table

| Problem | Likely cause | Fix |
|---|---|---|
| Cannot reach leads; emails bounce or go unread | Autofilled details years out of date; two-tap submission | Phone mandatory; autofill off; SMS verification; call within 5 minutes [v083, v130] |
| Fake numbers, bots, spam | No verification | "Higher intent" + SMS one-time passcode [v011, v067] |
| "I never filled that in" / no interest | Effortless submission, low intent | SMS verification; autofill off; clearer greeting and end page; faster first call [v083, v363] |
| Real people, wrong fit (budget, industry, timing) | Every fill counts as a lead, so Meta finds the cheapest | Conditional logic closing the form; website: qualified-only event; state the price or job size in the ad ("40K+ install") [v008, v041] |
| Out-of-area leads | Location targeting includes people "recently in" the area; no location filter | Location qualifier; untick "Reach more people likely to respond to your ads"; ring of excluded locations when over about 5% of leads are out of area; open the copy by naming the locals [v011, v049, v117] |
| Wrong age band or segment never closes | Meta cannot see close rate | Value rules from CRM data; a lookalike of real customers as a suggestion; a hard age limit as last resort [v052, v076] See `targeting.md` |
| Many leads for the low-value service, few for the high-value one | All leads counted equally | Lead values with "Maximize value of conversions" [v045] |
| Leads arrive out of hours and go cold | No scheduling | Ad scheduling with a lifetime budget [v052] |
| Leads are genuine but do not close | Trust or understanding gap | "Rich creative" form; end-page button to testimonials or portfolio; proof ads to submitted leads; omnipresent content [v130, v132] |
| Instant form leads much worse than website leads | On-platform ease | Apply the form rule above; test "Website and instant forms"; value rule favouring website [v028, v067] |
| Booked calls do not show | No confirmation step | Reminders, confirmation, cancel unconfirmed slots; then add qualifiers [v018] |
| Free offer attracts freebie seekers | No commitment required | Cheap paid first step shown as a discount ("£85, 80% off") [v077] See `local-and-high-ticket.md` |
| Good CPL, poor sales | Slow or weak follow-up | Follow-up rules above [v133] |
| CPL far above break-even | Weak offer, not settings | Change the offer [v108] See `offers-and-economics.md` |

## Benchmarks and case studies

Compare against the account's own history first; these are orientation only.

| Measure | Figure | Source |
|---|---|---|
| Lead-to-customer rate, service business | About 20% is the usual aim; observed 12.5%, 14% (at £21k customer value) and 22% | [v108, v110] |
| Lead magnet CPL | Under about $3 is good; examples £1.17 (17,500 opt-ins) and £1.07 (17,422 leads). Business-to-business costs more (2019–2022 figures) | [v250, v528] |
| Opt-in page conversion | 20–30% average, 40%+ great, 50–60% excellent (older figures) | [v389, v587] |
| Service enquiry page conversion | Above 3–5% of link clicks; 10%+ for an easy ask such as a free consultation | [v389] |
| Booked call cost, agency's own account | About £25 on Facebook feed, £32 on Instagram feed, £42–44 elsewhere; best ad just over £30 | [v038, v047] |
| High-ticket local CPL | Roofer about $50 per lead, 1-in-5 close, $250 per customer on a $12,000 job | [v329] |

- Finance offer, UK boiler installer: reframing £1,250 up front as £6 a week cut CPL from £90 to £6.50; 1 in 8 leads bought; about £52 per customer; scaled to £10,000 a day and about 46,000 leads a month. The offer moved CPL by an amount no setting could. [v108]
- Lower-priced tier, business-to-business service: adding a £3,000 done-with-you offer beside a £21,000 done-for-you one took leads from about 45 to 300+ a month, closing at 22% against 14%; the original offer's leads fell only 9%. [v110]
- Interior design: customer worth about £75,000, closing 1 in 12, allowable CPL about £620, actual CPL under 10% of that. [v120]
- Local physiotherapy: £17 assessment (£85, 80% off) sold at £29 each; 1 in 3 became a roughly £780 customer; about £36 net per customer. [v077]

## Outdated advice to ignore

| Old rule | Current rule | Why it changed |
|---|---|---|
| Start every instant form on "More volume"; "Higher intent" is a last resort | "Higher intent" + SMS verification + a conditional-logic qualifier is the default for sales-followed leads | SMS verification arrived in 2025; Meta learns from whatever counts as a lead [v008, v011] |
| Add qualifying questions only after quality proves poor | Include one disqualifying question from the start in most service accounts | A closed form never registers as a lead [v011] |
| For quality, abandon instant forms for a website and calendar | Forms now carry verification, qualification and "Book time"; test "Website and instant forms" in one ad set | New form features, 2025–2026 [v018, v067] |
| Choose the manual leads campaign over the tailored one | One Advantage+ leads campaign setup with controls and suggestions | Structures merged in late 2025 [v089] See `campaign-setup.md` |
| Lookalike of past leads as the main cold audience; one interest per ad set | Broad with suggestions; lookalikes only when Meta is not finding the right people | Targeting inputs are suggestions [v076] |
| Separate retargeting campaign for opt-ins by default | Warm and cold together; warm-only needs a hard constraint and a specific reason | Custom audiences are suggestions unless made hard [v052] |
| Hard gender or placement limits to fix lead quality | Value rules (down-bid up to 90%) | Hard gender limits were removed and manual placement controls are being removed in 2026 [v002, v010] See `targeting.md` |
| Video for webinar and lead magnet sign-ups | Images and carousels for small asks | Long video loses people before the call to action [v096] |
| Call leads within a few hours or the same day | Within 5 minutes; twice daily for 14 days | Contact rate collapses with delay [v133] |
| Optimise for the opt-in regardless of volume | Lowest-funnel event with 20–25+ conversions a week | Meta optimises literally for the chosen event [v013] |

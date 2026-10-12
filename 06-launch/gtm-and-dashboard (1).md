# GTM Launch Plan, Riverty business-unit case

| Field | Value |
|---|---|
| Feature | Update Direct-Debit Bank Details in the Customer Portal |
| Goal | Behavior change / service deflection (self-service adoption) |
| Launch tier | M, Targeted |

## Goal & Audience
- **Goal:** Turn a currently unsupported online servicing task into self-service. Eligible Responsible Payers should be able to update the IBAN used for an existing installment plan without contacting Customer Service. The business objective is to reduce the share of **all newly created installment plans** followed by at least one manual phone or email contact by **10–15% relative** (from a 12% baseline to **10.8–10.2%**), without increasing direct-debit returns. This is a service-deflection goal, not acquisition or general awareness.
- **Target audience:** Responsible Payers (parents or self-paying customers) with an active, eligible installment plan who need to change their direct-debit bank account **after plan creation**. Do not target customers with no current need to change bank details. **Internal enablement audience:** Customer Service agents handling related requests.
- **Value proposition:** Change your bank details directly in the customer portal, review the new account information and receive confirmation without calling or emailing support.

## Launch Tier
- **M, Targeted:** A specific subset of existing customers benefits from the feature. Direct revenue impact is limited, while reduced manual servicing has operational value. Prioritize visibility at the point of need and appropriate support guidance; a broad paid-awareness campaign would be disproportionate. Launch impact depends on the actual share of manual contacts attributable to bank-detail changes, which must be validated rather than assumed.

## Channels
1. **Owned — Customer portal (primary; PM + Product Designer):** Show a clearly labelled **"Update Bank Details"** action within eligible installment-plan details, linking directly to the update flow. This is the only primary channel designed to prevent a manual contact at the moment of need. Measure eligible entry-point exposure, flow starts and successful updates.
2. **Owned — FAQ and help pages (secondary discovery; PM content owner, Customer Service Lead reviewer):** Explain eligibility, the update steps, confirmation, common errors and what to do when a plan is ineligible. Include direct links to the relevant customer-portal area. Measure traffic and click-through to the portal where trackable.
3. **Owned — Phone and email support (supporting behavior-change channel; Customer Service Lead):** Train agents to identify eligible requests and guide customers toward self-service instead of making manual changes, where appropriate. **A contact already made is not prevented by this channel**; monitor repeat contacts and future behavior, not just referrals.

## Enablement & Assets
| Deliverable | Accountable owner | Readiness requirement |
|---|---|---|
| Portal entry point, flow copy, confirmation and error-state content | Product Designer | Approved and tested for eligible and ineligible cases before launch |
| Portal implementation, eligibility logic and instrumentation | Engineering Lead (3 engineers) | Events for eligibility/exposure, start, success, failure and abandonment validated in test |
| FAQ and help-page update, including portal deep link | PM | Published at launch; wording reviewed by Customer Service Lead |
| Customer Service briefing, scripts and screenshots | Customer Service Lead | Agents briefed before rollout; clear escalation guidance for failures and ineligible plans |
| Payment reliability test plan and release QA | QA | Payment safeguards, negative paths and rollback readiness verified |
| Launch dashboard, contact categorization and experiment readout | PM (measurement owner), Engineering (data implementation) | Event definitions, denominators and control/treatment reporting agreed before pilot |
| Relevant compliance/permissions and localization review, if required | PM coordinates with respective business owners | Required approvals and capacity confirmed before go/no-go |

## Ownership, Budget & Timeline
- **Ownership & budget:** PM is accountable for GTM sign-off, stakeholder alignment, KPI definitions and rollout decisions. Engineering Lead owns implementation and eligibility checks; Product Designer owns UX and portal messaging; QA owns release testing; Customer Service Lead owns scripts and training. No incremental **paid-media** budget is planned. PM must confirm capacity for analytics, localization, compliance review, support enablement and content publication before launch; "no media spend" does not mean "no delivery effort."
- **Phase 1 — Beta/readiness (Weeks 1–3):** Build and test the core update flow, validate eligibility and payment safeguards, confirm analytics and contact categorization, and run a limited pilot. **Go/no-go:** core journey works, critical defects are resolved, instrumentation is verified, payment reliability tests pass, and Customer Service assets are ready.
- **Phase 2 — Targeted launch (Weeks 4–5):** Enable the feature for the agreed eligible population, publish portal guidance and FAQs, train agents, and review early uptake, failures and payment guardrails. Keep a control group where the experiment design requires one.
- **Phase 3 — Post-launch evaluation (Weeks 6–8):** Compare treatment and control on manual contacts, monitor adoption and direct-debit returns, investigate friction, and decide to expand, iterate or pause. **Do not declare the primary outcome proven before cohorts have completed the agreed post-creation contact-observation window and the required sample size is achieved** (experiment plan: approximately 4,800 newly created plans per group).

## Success Metrics
1. **Primary business metric — post-creation manual contact rate:** Number of **all newly created installment plans** with at least one phone or email contact during a **predefined, identical follow-up window** divided by all newly created installment plans in the same group/cohort. Baseline: **12%**; directional target: **10.8–10.2%** (10–15% relative reduction), with **10.2%** as the 15% target. Compare treatment with control, not just a pre/post headline. The observation window and attribution rules must be locked before the pilot. The goal is ambitious for a narrowly used feature; check that bank-detail-related contacts are frequent enough to plausibly move the overall rate.
2. **Adoption and diagnostic metrics:** Count successful self-service bank-detail updates; calculate **flow completion rate = successful updates / eligible update flows started**; monitor entry-point exposure, starts, error rates and abandonment. Where support contact reasons are reliably classified, track **self-service share of observed bank-detail-update demand = successful online changes / (successful online changes + manual bank-detail changes)**, with deduplication rules. Do **not** claim to know the percentage of *all desired bank-detail changes* completed online: unexpressed demand cannot be observed reliably.
3. **Guardrail — direct-debit return rate:** Compare treatment and control using an agreed denominator and payment observation window, including returns after updated IBANs are used for collection. The return rate must not worsen; QA/payment owners define the operational escalation threshold before rollout.
- **Bad signals / actionable triggers:** (a) Continued eligible bank-detail-related manual requests with low portal entry/usage → inspect placement, links and agent scripts; (b) elevated flow abandonment, validation failures or eligibility errors → investigate UX and technical defects; (c) self-service completions increase without a corresponding reduction in overall manual-contact rate → validate whether contacts were truly displaced, assess contact-reason mix and the feature's addressable share; (d) a material adverse trend in direct-debit returns versus control → pause further rollout and investigate with QA and payment owners. Numeric alert thresholds must be agreed before launch rather than invented afterward.
- **Likely post-launch decision:** **Expand** only if the manual-contact trend supports the goal, self-service completion is healthy and payment reliability is protected. **Iterate** if discovery or completion is weak. **Pause** if payment reliability or critical validation checks fail. The PM documents the evidence, uncertainty and decision at the end of the evaluation.

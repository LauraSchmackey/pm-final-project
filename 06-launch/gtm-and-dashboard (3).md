# GTM Launch Plan, Riverty business-unit case

| Field | Value |
|---|---|
| Feature | Update Direct-Debit Bank Details in the Customer Portal |
| Goal | Behavior change / service deflection |
| Launch tier | M, Targeted |

## Goal & Audience
- **Goal:** Enable eligible Responsible Payers to change the direct-debit IBAN for an existing installment plan in the customer portal instead of using phone or email support. Reduce the share of all newly created installment plans followed by at least one manual phone or email contact by 10–15% relative, from 12% to 10.8–10.2%, without increasing direct-debit returns. This is a service-deflection goal, not a general awareness campaign.
- **Target audience:** Responsible Payers (parents or self-paying customers) with an active, eligible installment plan who need to change their bank account after plan creation. Customer Service agents handling these requests are an internal enablement audience, not the customer target audience.

## Launch Tier
- **M, Targeted:** The feature addresses a specific servicing need among existing customers. Direct revenue impact is limited, but reducing avoidable manual contacts offers operational value. A targeted launch focused on discoverability at the moment of need is appropriate; broad paid promotion is not. The potential impact on the overall contact rate depends on how many current contacts concern bank-detail changes and must be validated.

## Channels
1. **Owned:** Display a clearly labelled "Update Bank Details" action within eligible installment-plan details in the customer portal. This is the primary channel: it reaches customers at the point of need, before they contact support. Product Manager and Product Designer own placement and copy; Engineering implements the entry point.
2. **Owned:** Use existing phone and email support interactions to guide eligible customers to the new self-service flow. Customer Service Lead owns scripts and agent training. This channel supports future self-service behavior but does not prevent the contact that has already occurred.
3. **Owned:** Update FAQs and help pages to explain eligibility, the steps to change an IBAN, confirmation and error handling, with direct links to the portal. Product Manager owns the content; Customer Service Lead reviews it. This is a secondary discovery channel for customers looking for help before contacting support.

## Enablement & Assets
Prepare the customer portal entry point, confirmation and error messages (Product Designer; Engineering implements), a Customer Service briefing and updated scripts with screenshots and escalation guidance (Customer Service Lead), and an updated FAQ with portal links (Product Manager). Engineering owns analytics instrumentation for eligible exposure, flow start, success and failure; Product Manager owns KPI definitions and reporting. QA validates the update flow, eligibility, failure cases and payment safeguards. Before launch, the PM confirms any necessary compliance/localization approvals and that all content, analytics and training are ready.

## Ownership, Budget & Timeline
- **Ownership & budget:** PM owns launch coordination, stakeholder sign-off, KPI definitions and rollout decisions. Engineering (3) owns portal integration, eligibility checks and tracking implementation. Product Designer owns the customer journey and portal copy. QA owns release testing and payment-safeguard checks. Customer Service Lead owns support scripts, agent training and operational escalation guidance. No additional paid-media budget is planned; existing channels and team resources will be used. PM must confirm capacity for analytics, FAQ publication, training, and any required legal/compliance or localization work before approval.
- **Timeline:** Phase 1 – Beta (Weeks 1–3): Build and test the feature, verify eligibility rules, successful and failed journeys, instrumentation and payment safeguards, and run a limited pilot. Proceed only when critical defects are resolved, tracking is validated and support guidance is ready.

Phase 2 – Launch (Weeks 4–5): Enable the feature for the agreed eligible audience, publish portal guidance and FAQs, and brief Customer Service. Monitor early usage, failures and payment reliability; retain an experiment control group where required.

Phase 3 – Post-launch (Weeks 6–8): Review manual contact rates, successful updates, flow completion and direct-debit returns. Compare treatment and control and decide whether to expand, iterate or pause. Complete the predefined post-creation observation window and reach the experiment sample-size requirement (approximately 4,800 plans per group) before claiming a conclusive primary-metric result; extend evaluation if needed.

## Success Metrics
- **Metrics:** 1. Primary: Percentage of all newly created installment plans followed by at least one phone or email contact within the same predefined post-creation observation window in treatment and control. Baseline 12%; target 10.8–10.2% (10–15% relative reduction). The 10.2% figure is the 15% relative-reduction target, not an assured effect from this single feature.
2. Adoption: Track successful self-service bank-detail updates, completion rate among eligible flows started, and the share of *observed* bank-detail changes handled online rather than manually where contact reasons are reliably identifiable. Also monitor exposure, starts, errors and abandonment; do not use all unobserved customer needs as a denominator.
3. Guardrail: Direct-debit return rates must not increase versus the control group over an agreed payment observation window, particularly after a changed IBAN is first used for collection.
- **Bad signal to watch for:** Eligible customers keep requesting manual bank-detail updates despite low portal usage (check entry-point discoverability and support guidance); high abandonment or failures (fix UX/technical issues); successful updates rise without an overall contact-rate improvement (check actual service deflection and contact-reason mix); or direct-debit returns worsen versus control (pause further rollout and investigate). Agree operational alert thresholds before launch.
- **Likely post-launch decision:** Expand if manual contacts fall and payment reliability is stable; iterate on placement, guidance or flow usability if adoption is weak; pause rollout if payment reliability worsens or critical defects occur. Document results and limitations before the decision.

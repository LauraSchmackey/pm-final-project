# GTM Launch Plan, Riverty business-unit case

| Field | Value |
|---|---|
| Feature | Self-service update of direct-debit bank details for eligible installment plans in the customer portal. The payer enters a new IBAN, reviews the details and receives confirmation of the update. |
| Goal | Conversion |
| Launch tier | M, Targeted |

## Goal & Audience
- **Goal:** Conversion, The feature turns a currently unsupported servicing task into self-service. The goal is to reduce the share of installment plans followed by manual phone or email contact by 10–15% relative, while enabling Responsible Payers to manage their bank details independently.
- **Target audience:** Responsible Payers with an eligible installment plan who need to change the bank account used for direct debit after the plan has been created.

## Launch Tier
- **M, Targeted**, The feature is relevant to a specific subset of existing customers rather than the full market. Its direct revenue impact is limited, but it has meaningful operational value by reducing avoidable service contacts. A targeted launch is sufficient to drive awareness among eligible customers. Without communication, customers may continue calling or emailing because they do not know the new self-service option exists.

## Channels
1. **Owned: Display the new "Update Bank Details" option directly within the installment plan details. Reach Responsible Payers at the moment they need to change their bank account and enable immediate self-service.**
2. **Owned: Use existing phone and email support interactions to direct eligible customers to the new self-service feature instead of processing bank-detail changes manually.**
3. **Owned: Update FAQs and help pages to explain how Responsible Payers can change their direct-debit bank details online, with direct links to the customer portal.**

## Enablement & Assets
Prepare a short customer-service briefing, updated support scripts, a portal announcement, and an FAQ explaining eligibility and the new bank-detail update flow. Include screenshots, error-handling guidance, and instructions for redirecting customers from manual support to self-service.

## Ownership, Budget & Timeline
- **Ownership & budget:** PM owns launch coordination, stakeholder alignment and success metrics. Engineering (3) owns portal integration and eligibility checks. Product Designer owns the customer flow and portal communication. QA owns testing, including payment reliability. Customer Service owns support scripts and agent training. No additional marketing budget required; existing channels and internal resources will be used.
- **Timeline:** Phase 1 – Beta (Weeks 1–3): Build and test the feature, validate eligibility and payment safeguards, and run a limited pilot.

Phase 2 – Launch (Weeks 4–5): Enable the feature for eligible customers, update portal guidance and FAQs, and brief Customer Service.

Phase 3 – Post-launch (Weeks 6–8): Monitor manual contact rates, self-service usage and direct-debit returns. Evaluate results and decide on further rollout or improvements.

## Success Metrics
- **Metrics:** 1. Primary: Reduce the post-creation manual contact rate across all newly created installment plans from 12% to 10.2% (15% relative reduction).
2. Adoption: Track the percentage of eligible bank-detail changes completed successfully through self-service.
3. Guardrail: Direct-debit return rate must not increase compared with the control group.
- **Bad signal to watch for:** Low feature adoption despite continued manual bank-detail requests, or an increase in direct-debit returns after customers update their IBAN.
- **Likely post-launch decision:** Iterate: Improve feature visibility and usability if adoption is low. Expand rollout if manual contacts decrease and payment reliability remains stable.

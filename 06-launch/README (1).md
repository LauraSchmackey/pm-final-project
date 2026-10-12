# Self-Service Bank Detail Updates for Installment Plans

> Enable Responsible Payers to update the direct-debit bank account for eligible installment plans in self-service instead of contacting customer support.

**Laura Schmackey PM Cohort Oct 2026** · https://github.com/LauraSchmackey/pm-final-project

Prototype: https://lovable.dev/preview/2VcaYgW19oXjcK8ztBFFODBCdyf59z74

---

## Final Project Deliverables

### Slide 5 · Strategy
- **Problem:** BFS needs to prevent growing product fragmentation from limiting the scalability of its installment-plan business. A standardized, configurable framework is the strategic direction, reducing the need for client-specific solutions.

One practical opportunity within this strategy is post-creation servicing. Responsible Payers currently cannot update their direct-debit bank details in the customer portal, even though the core system already supports this change. As a result, customers must contact support for a task that could be completed independently.
- **Value proposition:** For BFS clients, the broader value proposition is a standardized, configurable installment-plan framework that supports different customers, markets and use cases without requiring bespoke product setups.

For Responsible Payers, self-service bank-detail updates are a focused application of this direction. Customers gain more control over their existing installment plans, while BFS can reduce avoidable manual servicing without introducing new credit or risk logic.
- **Hypothesis:** Of approximately 316,000 installment agreements, 46,200 were followed by manual customer contact. This indicates a significant overall servicing opportunity, but the proportion attributable to bank-detail changes is not yet known.

I believe that enabling Responsible Payers to update direct-debit bank details through the customer portal will reduce bank-detail-related phone and email contacts without increasing direct-debit returns.

The broader product objective remains a 10–15% relative reduction in post-creation manual contacts. The contribution of this individual feature will be validated through a controlled experiment.

### Slide 6 · Research
- **Competitive analysis:** The current servicing journey reveals a clear self-service gap: Responsible Payers cannot update direct-debit bank details through the customer portal after creating an installment plan. Instead, they must contact customer support by phone, email or free-text message.

The underlying capability already exists in the core system. The opportunity is therefore not to develop new payment functionality, but to make an existing servicing process accessible through the portal.

This is an identified internal workaround rather than evidence of a validated competitive disadvantage. The frequency of bank-detail requests and their contribution to overall manual contacts still need to be quantified.
- **Journey map:** CURRENT JOURNEY

Installment plan created → Responsible Payer needs to change bank details → checks customer portal → no self-service option available → contacts support by phone or email → support manually processes the change.

MOMENT OF MISERY

A routine payment-management task requires manual assistance, although the underlying system already supports it.

PROPOSED JOURNEY

Open eligible installment plan → select Update Bank Details → enter account holder and new IBAN → validate and review masked details → submit → receive confirmation.

EXPECTED IMPROVEMENT

Complete the change independently without contacting customer support, while maintaining existing eligibility and payment-safety rules.

### Slide 7 · Blueprint
- **Roadmap:** NOW — 6–8 week pilot

Enable self-service bank-detail updates for eligible installment plans. The core-system capability already exists, making this a focused opportunity to reduce servicing friction without changing credit or risk logic.

NEXT — Following 1–2 sprints

Explore early repayment, additional payments and changing the due date of an installment.

LATER — Validated backlog

Consider more complex plan adjustments, including changing the number of installments or the regular debit date.

OUT FOR NOW

Exclude changes requiring new credit/risk logic or major core-system modifications.

PRIORITISATION RATIONALE

Start with an existing capability that addresses a clear self-service gap. Validate adoption, operational impact and payment reliability before expanding the servicing scope.
- **PRD highlights:** The first release enables Responsible Payers to update direct-debit bank details for eligible installment plans through the existing customer portal.

Core flow: Open eligible plan → enter account holder and IBAN → validate input → review masked account details → confirm submission → receive immediate confirmation.

The solution must handle invalid IBANs, ineligible plans and system errors. Existing eligibility rules and core-system payment logic remain unchanged.

The feature is intentionally limited to bank-detail updates. Early repayment, due-date changes and more complex plan adjustments remain outside the first release.

Success will be assessed through completed self-service updates, fewer bank-detail-related manual contacts and stable direct-debit return rates.
- **Prototype:** https://lovable.dev/preview/2VcaYgW19oXjcK8ztBFFODBCdyf59z74

### Slide 8 · Validation
HYPOTHESIS

Self-service bank-detail updates will reduce bank-detail-related phone and email contacts without worsening payment reliability.

CONTROL / TREATMENT

Control: Existing manual support process.

Treatment: Eligible Responsible Payers can update bank details through the portal, including validation, review and confirmation.

EXPERIMENT DESIGN

Randomise Responsible Payers 50/50, maintaining the same assignment across their installment plans. Analyse eligible plans by original assignment, including non-users.

PRIMARY METRIC

Percentage of eligible newly created installment plans with at least one bank-detail-related phone or email contact within 30 days.

BASELINE & MINIMUM DETECTABLE EFFECT

The feature-specific baseline is currently unknown and must be established before finalising the sample size. Target effect: 15% relative reduction.

The assumed 12% all-reason contact baseline must not be treated as the bank-detail-specific baseline.

SUPPORTING METRICS

Successful self-service updates without subsequent bank-detail support, with a proposed completion target of at least 70% of attempts. Track all-reason manual contact rates as a secondary business metric.

DURATION & SAMPLE

Recalculate sample size using the measured baseline, 5% significance and 80% power, accounting for repeat payers. Plan approximately eight weeks of recruitment, followed by complete 30-day contact and 60-day payment-safety observation.

GUARDRAIL

The upper one-sided 95% confidence bound for the increase in direct-debit return rate versus control must remain below +0.2 percentage points.

DECISION RULES

SHIP: At least 15% relative contact reduction, statistically significant benefit, ≥70% completion and safety guardrail passed.

ITERATE: Safety passes, but adoption or impact falls below target.

INCONCLUSIVE: Insufficient sample, incomplete observation or uncertain results.

STOP: Statistically supported contact-rate harm, safety-boundary breach or critical defect.

### Slide 9 · Launch
- **GTM:** GOAL

Drive adoption of self-service bank-detail updates among eligible Responsible Payers and reduce avoidable bank-detail-related manual support contacts.

The broader installment-plan product objective remains a 10–15% relative reduction in post-creation manual contacts across all plans (assumed baseline: 12%, target: 10.2–10.8%). This single feature contributes to that objective but is not expected to achieve it independently.

AUDIENCE

Responsible Payers with eligible installment plans who need to change the bank account used for direct debit.

LAUNCH TIER

M — Targeted launch. Limited direct revenue impact, but meaningful potential operational value through reduced servicing effort.

CHANNELS

Customer portal as the primary entry point, supported by FAQs, help pages and Customer Service referrals.

ENABLEMENT

Updated portal guidance, support scripts, agent training and analytics tracking. PM coordinates delivery with Engineering, Design, QA and Customer Service.

BUDGET

No additional marketing budget required. Launch through existing customer-facing channels.
- **Metrics:** Primary metric: Reduce the percentage of all newly created installment plans followed by at least one manual phone/email contact from 12% to 10.2–10.8% (10–15% relative reduction).

Adoption: Track successful self-service bank-detail updates, completion rate among started flows and the share of observed bank-detail change requests handled through self-service.

Guardrail: Direct-debit return rates must not increase compared with the control group.

PRIMARY FEATURE METRIC

Reduce the percentage of eligible newly created installment plans followed by bank-detail-related phone or email contact within 30 days. Target: 15% relative reduction versus control, subject to baseline validation.

ADOPTION

Track successful self-service bank-detail updates, completion rate among started flows and the share of observed bank-detail change requests resolved through self-service.

BROADER BUSINESS METRIC

Monitor the overall post-creation manual contact rate across all installment plans. The existing product-level objective is a 10–15% relative reduction from an assumed 12% baseline to 10.2–10.8%, supported by this and other self-service improvements.

PAYMENT SAFETY

Direct-debit return rates must remain within the defined experiment guardrail versus control.

BAD SIGNAL

Low adoption despite continued manual bank-detail requests, high flow abandonment, no measurable reduction in related support contacts or deteriorating payment reliability.

RESPONSE

Investigate discoverability, usability and eligibility issues. Pause rollout if payment reliability breaches the safety boundary.

### Slide 10 · Story
- **Friction + aha:** The biggest challenge was translating a broad servicing problem into a focused, measurable feature. It was tempting to address several customer pain points at once, but prioritization forced me to focus on what delivers real value with manageable effort.

The aha moment was realizing that updating bank details is already supported by our core system but not available in self-service. This makes it a genuine quick win without having to touch complex payment logic.
- **Takeaways / next:** I learned that prioritization is really about knowing what not to build. AI was helpful for structuring ideas and spotting gaps, but I still had to challenge its suggestions, especially when it came to our business processes and metrics.

Next, I'd test the prototype with real users, check whether my assumptions about manual contacts are correct, and see if the feature actually makes a difference before rolling it out further.

---

Submitted to the Product Management Certification learning platform · Product School.

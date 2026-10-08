# Roadmap, PRD & Prototype (Module 4)

## Your strategic anchors
- **Persona (M2), who are you solving for?:** Responsible Payer — a parent or self-paying customer who is financially responsible for an installment agreement and wants to manage it independently after setup.
- **Primary success metric (M3), your leading indicator:** Post-creation manual contact rate: reduce the share of installment agreements that require a call, email or free-text portal message after creation by 10–15% relative, while increasing completed self-service actions.
- **Moment of misery (M2), the specific friction blocking the goal:** After the agreement is created, the payer cannot independently check status or handle a payment issue, extension, shortening or adjustment. They have to contact support or the partner for something that should be manageable in self-service.
- **Guardrail metric (M3), what must not drop or break:** Payment reliability and useful flexibility must not worsen: direct-debit return rate must not increase, and legitimate extensions or shortenings must remain possible.

## Scan the backlog & set a human baseline
- **My instinctive “quick wins” before touching the AI (2 to 3 feature IDs + why):** Update Direct-Debit Bank Details - It directly replaces a manual post-creation support request, while the underlying bank-detail change already exists in the core system and only needs to be safely exposed in self-service.

## Audit, override & decide
- **Where did you override the AI? (feature + old vs. new score + why):** I would override B7 from Value 4 / Effort 4 / Major Project to Value 5 / Effort 2 / Quick Win. The bank-detail change already exists in the core system; the pilot does not need to change payment or booking logic, but to expose the existing capability securely in the customer portal. It directly enables a self-service action that currently requires manual support.
- **Did the AI over-value a Sales/Eng request your M2 interviews don’t support?:** Yes: B8 is strategically important as an enabler, but it should not displace a customer-visible self-service flow in the pilot. Responsible Payers do not contact BFS because they need a configurable rules engine; they contact us because they cannot change a payment date, adjust a plan, or understand what happens after a failed payment.
- **Did it underweight something your M3 cohort/funnel data strongly supports?:** Yes: B6 and B9 should be treated as especially important where M3 contact data shows returned direct debits and unresolved requests repeatedly creating calls, emails, or portal messages. A failed payment is a high-friction moment, and clear digital recovery options or at least transparent status directly reduce the need to ask support what to do next.

## Generate your interactive roadmap
- **My “Now” lane (this sprint), the 2 to 3 quick wins I’ll build first:** Change Direct-Debit Collection Date, Update Direct-Debit Bank Details, and Self-Service Funnel & Contact-Reason Tracking.
- **What I cut, and the “no” I’m protecting the scope from:** I cut Make an Extra Payment because partial-payment allocation and recalculation are complex, while it has a weaker direct impact on reducing manual customer contacts. I am protecting the pilot scope from major changes to core credit, risk, servicing, and payment-booking logic.
- **Prototype/roadmap screenshot link (paste into your deliverables):** _(not filled in)_

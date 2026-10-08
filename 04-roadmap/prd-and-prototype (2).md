# Update Direct-Debit Bank Details in the Customer Portal, Simplified PRD (StreamLine)

**Author:** Me · **Status:** Draft · **Target:** High-Fidelity Prototype · **Persona:** Responsible Payer — a parent or self-paying customer who is financially responsible for an installment agreement and wants to manage it independently after setup.

## 1. The Big Picture
- **Vision:** To eliminate avoidable manual support contacts when a Responsible Payer needs to update the bank account used for an installment plan.
- **Press release:** Today, BFS Health Finance launched self-service bank-detail updates for eligible installment plans in the customer portal. Responsible Payers can now submit a new IBAN directly in the portal instead of calling, emailing, or sending a free-text message.
The update uses BFS’s existing core-system capability and gives customers an immediate confirmation of the outcome. This makes a common payment-management task easier while protecting payment reliability.
- **Success metric:** Reduce the post-creation manual contact rate for installment agreements by 10–15% relative, while increasing completed self-service bank-detail updates.
- **Guardrail:** Direct-debit return rate must not increase after launch.

## 2. The Details
### User stories
- As a Responsible Payer, I want to update the IBAN for my eligible installment plan in the portal so that future direct debits use my new bank account without contacting support.
- As a Responsible Payer, I want to see whether my bank-detail update was submitted successfully so that I know what to expect next.
- As a Responsible Payer, I want a clear fallback when an update cannot be completed online so that I know how to resolve the issue.
### Screens to build
- 1. Installment-plan detail page with “Update bank details” entry point
- 2. Bank-detail update form
- 3. Success / error confirmation screen
### Functional requirements
- - The system must show the entry point only for authenticated payers with an eligible active direct-debit installment plan.
- - The system must allow the payer to enter the new IBAN and all fields required by the existing core-system process.
- - The system must validate required fields and the IBAN format before submission.
- - The system must send a valid update request to the existing core-system capability without changing payment or plan logic.
- - The system must show a clear success state after submission.
- - The system must show a clear error state and support route when submission fails or the plan is not eligible.
### Smart behaviors (Situation → Outcome)
- If the payer selects “Update bank details” for an eligible plan → show the update form.
- If a required field is empty or the IBAN format is invalid → block submission and show an inline error.
- If the core-system update succeeds → show a success confirmation.
- If the update fails or the plan is not eligible → do not change bank details; show an error and support route.
- If the payer leaves the form without submitting → no bank details are changed.
### Technical constraints
- - Reuse the existing customer-portal authentication and authorization.
- - Reuse the existing core-system bank-detail update interface/process.
- - No changes to payment booking, direct-debit return, dunning, credit, risk, or installment-plan calculation logic.
- - Do not store full IBAN data in portal analytics, logs, or confirmation messages.
- - Pilot scope is limited to one eligible installment plan per update.

## 3. The Logistics
### Features out
- - Real-time account-holder verification or Open Banking
- - New mandate or signature process
- - Changes to installment amount, term, payment due date, or collection date
- - Payment booking, returns, dunning, credit, risk, and core servicing changes
- - Bulk updates across multiple installment plans
- - Confirmation email, update history, and proactive return-payment automation
### Edge cases & safety guard
- - Ineligible or closed plan → hide or block the feature; do not submit an update.
- - Invalid or incomplete IBAN → prevent submission; retain no partial change.
- - Core-system timeout/error → do not claim success; show a retry/support message.
- - Duplicate click/submission → prevent duplicate update requests where possible.
- - Existing bank details → display only in masked form.
- - The system must never expose a full IBAN in notifications, analytics, or error messages.
### Decision log
- - Reused the existing core-system update capability to fit the 6–8 week pilot and avoid payment-logic changes.
- - Limited the pilot to a basic IBAN update and on-screen confirmation; notifications, verification, and history are deferred.
### Evals
- - Task completion: at least 80% of test participants can submit a valid bank-detail update without support.
- - Time on task: median completion time under 2 minutes for an eligible plan.
- - Safety: 0 test cases where an ineligible payer or plan can successfully submit an update; 0 full IBAN exposures in portal messages or analytics.

## MoSCoW scope
- **Must:** - Entry point on the eligible installment-plan detail page; - Simple form to submit a new IBAN; - Basic required-field and IBAN-format validation; - Handover to the existing core-system bank-detail update capability; - Clear on-screen success or failure message
- **Should:** - Masked display of the current IBAN; - Guidance on when the new bank details take effect; - Basic tracking of form opens, successful updates, and failures
- **Could:** - Confirmation email or portal notification; - Inline guidance for IBAN errors; - History of previous update requests
- **Won't (now):** - Real-time account-holder verification or Open Banking; - New direct-debit mandate or signature processes; - Updates to installment amounts, terms, or collection dates; - Changes to payment booking, returns, dunning, credit, risk, or core servicing logic; - Bulk updates across multiple installment plans; - Proactive automation after a direct-debit return

---
**Builder hook:** Build a working prototype based on this PRD. Use the User Story as the core flow, Functional Requirements as build constraints, and prioritize speed and clarity over visual complexity.

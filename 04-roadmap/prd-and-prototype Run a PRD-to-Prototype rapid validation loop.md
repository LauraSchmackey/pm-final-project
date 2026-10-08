# PRD & Prototype Sprint (Module 4)

## Pick & scope with MoSCoW
- **The “Now” feature I’m scoping (name + one-line core description):** Change Direct-Debit Collection Date, Update Direct-Debit Bank Details, and Self-Service Funnel & Contact-Reason Tracking.
- **My finalized Must-Haves (after overriding the AI):** Entry point on the installment-plan detail page: Eligible logged-in customers can see “Update bank details” for an active installment plan paid by direct debit.
Simple update form: Capture the new IBAN and any fields required by the existing core system.
Basic validation: Validate required fields and IBAN format before submission.
Use the existing core-system capability: Pass the update to the existing interface/process without changing payment booking, installment-plan, or servicing logic.
Clear success or failure message: Show immediately whether the update was submitted successfully; otherwise provide a clear error message and support route.
- **What I demoted from Must → Should/Won’t, and why:** I demoted confirmation emails, effective-date messaging, detailed tracking, and masked-bank-detail display to Should Have because the pilot can still solve the core problem without them: the payer can submit new bank details through the portal and see the result immediately.
I moved real-time account verification, Open Banking, new mandate/signature flows, bulk updates, and any changes to payment, booking, risk, or plan-management logic to Won’t Have (Now). These items add integration, compliance, and operational complexity that is not needed to validate whether self-service bank-detail updates reduce manual contacts within the 6–8 week pilot.

## Generate your Simplified PRD
- **One thing my PRD makes explicit that a vague brief would have missed:** The PRD makes explicit that this is not a new payment-management flow: it is a tightly bounded portal handoff for authenticated payers of eligible active direct-debit plans, with IBAN validation and explicit failure states—but no changes to booking, mandates, risk, or core servicing logic.

## Prompt-to-prototype sprint
- **Where did the prototype reveal a gap in my PRD logic? (what I had to update):** The prototype revealed that the PRD was too vague about the validation and confirmation journey. It required a valid IBAN and a success state, but did not specify when validation errors should appear, how the payer gains confidence that they entered the intended account, or whether they can review the change before submitting it.

I updated the PRD to add inline validation, bank-name feedback as a confidence cue, and a short review-and-confirm step before submission. This better protects against avoidable entry errors while keeping the pilot scope unchanged.
- **My prototype, as a link or a screenshot (publish or share from your tool; in Lovable that is Share → Share Preview, in Bolt Publish → Web. No share URL? Screenshot the working flow):** https://lovable.dev/preview/2VcaYgW19oXjcK8ztBFFODBCdyf59z74

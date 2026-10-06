# Simulated User Research Data
## BFS Health Finance — Driving Schools + Orthodontics

> **Note:** This dataset is synthetic and was created for training / workshop purposes. It is not based on confidential customer data.

**12 user-research notes · 10 product/ops issues · B2B2C installment offering**

---

## User Research Notes

### UXR-01 · Driving school owner, 2 locations, NRW
> "I don't actually want to manage installment payments at all. If a learner pays late or misses a payment, I don't want to chase them. The value for me would be knowing when I get paid and then being done with it."

### UXR-02 · Learner driver, 19, self-paying
> "At the beginning I roughly knew what the licence would cost. But then you keep adding lessons, special drives and exam fees. I'd rather know: what am I roughly paying per month, and how much could that still change?"

### UXR-03 · Parent of learner driver, paying the costs
> "My son signs up, but I'm the one paying. If the link or agreement only goes to him, it gets complicated. I want to receive the payment option directly and understand what I'm committing to."

### UXR-04 · Driving school manager, 8 employees
> "If my staff have to open a separate portal for financing and enter everything again, they won't use it. It needs to come from our driving-school software — customer, invoice, amount, done."

### UXR-05 · Driving school owner, rural area
> "A fixed financing amount on day one doesn't really work. Some learners need 20 lessons, others need 50. We simply don't know the final price at the beginning."

### UXR-06 · Driving instructor and co-owner
> "I want to be able to say during enrollment, 'You can also pay in installments.' But I don't want to become a credit advisor. As soon as learners ask about interest, term length or why they were declined, it needs to be clear who handles that."

### UXR-07 · Orthodontic practice manager, 4 practitioners
> "We talk about the treatment and the medical options, and then at some point the cost comes up and suddenly the whole conversation becomes about money. Installments help, but it can't make the patient conversation feel like a sales pitch."

### UXR-08 · Father of a 13-year-old orthodontic patient
> "I get a treatment plan, then invoices, and maybe some money back from the insurance later. I don't understand what the installment is actually based on — the full treatment cost, my co-payment or just this invoice?"

### UXR-09 · Orthodontist, independent practice
> "I don't want to explain why someone was accepted or rejected for installments. That's very uncomfortable for the patient relationship. The decision needs to clearly come from an external provider, not from us."

### UXR-10 · Billing specialist, orthodontic group practice
> "Treatment runs for two or three years. Amounts change, services are added or removed. If every new invoice creates a new installment plan, we'll end up with five contracts for one treatment."

### UXR-11 · Patient, 27, self-paying
> "I'd use installments, but only if I can immediately see the total amount, monthly payment, duration and any additional cost. If I have to create an account just to find that out, I'm gone."

### UXR-12 · Driving school + orthodontics interview synthesis
> "Across both groups, monthly predictability mattered more than having lots of different term options. Partners wanted to hand off payment management almost completely. The biggest difference: in driving schools the final total is often still unknown, while in orthodontics the treatment cost is more predictable but treatment plans, invoices, co-payments and reimbursements happen at different times."

---

## Simulated Product / Ops Issue Reports

### ISSUE-301 · Sev: Critical · Both verticals
**Payer and service recipient cannot be modeled separately.**  
Current flow assumes the person receiving the service is also the contractual payer. Breaks common cases such as parents paying for learner drivers or minors receiving orthodontic treatment.

### ISSUE-307 · Sev: Critical · Driving schools
**Installment plan assumes a fixed final invoice amount.**  
Driving-school costs increase dynamically as additional lessons, repeat exams or special drives are added. No supported flow for increasing the financed amount or adding later invoices to an existing plan.

### ISSUE-312 · Sev: High · Orthodontics
**Treatment plan, invoice amount and financed amount are not clearly distinguished.**  
Families interpret the quoted treatment cost as the amount being financed, even when the installment plan only covers the current private invoice or co-payment.

### ISSUE-318 · Sev: High · Both verticals
**Partner handoff requires duplicate customer and invoice entry.**  
School/practice staff must re-enter information already available in their vertical software. Interviewees say they would only use the offering consistently if initiation is embedded or pre-filled.

### ISSUE-324 · Sev: High · Orthodontics
**Insurance reimbursement timing is not represented.**  
Patients cannot easily understand how expected public/private insurance reimbursements interact with outstanding balances and installment amounts.

### ISSUE-329 · Sev: High · Driving schools
**No support for rolling or milestone-based costs.**  
Registration fees, individual lessons, special drives and exam costs occur at different points in the journey. A single financing trigger at enrollment does not map cleanly to the learner journey.

### ISSUE-335 · Sev: Medium · Both verticals
**Decline journey creates partner-service burden.**  
When an applicant is not eligible, the user returns to the school/practice without a clear explanation or next step. Staff receive financing questions they are not trained or expected to answer.

### ISSUE-341 · Sev: Medium · Both verticals
**Partner dashboard uses financial terminology unfamiliar to frontline staff.**  
Labels such as "debtor," "receivable assignment" and "plan modification" lead to support requests. Partners ask for terminology aligned with their daily workflow.

### ISSUE-348 · Sev: Medium · Orthodontics
**Changes to long-running treatment are difficult to reconcile with an active plan.**  
Treatment adjustments, cancellations or changed co-payments require manual service intervention and make it unclear which balance remains payable.

### ISSUE-354 · Sev: Low/Medium · Both verticals
**Customer communication appears under BFS/Riverty branding without enough partner context.**  
Some users do not recognize why they received a payment message. Partners want the practice/school name, invoice context and recognizable service information included without requiring fully customized communications.

---

## Optional Step 1 Baseline: Three High-Stakes Red Flags

1. **Payer and service recipient are often different people, but the current flow assumes they are the same person.**  
   This affects parents paying for learner drivers and parents financing orthodontic treatment for minors.

2. **Driving-school financing assumes a fixed amount even though the final licence cost is still changing.**  
   Extra lessons, repeat exams and additional fees can make the initial installment plan inaccurate or unusable.

3. **Orthodontic patients and parents struggle to understand what they are actually financing.**  
   Treatment cost, individual invoices, co-payments and insurance reimbursement are easy to confuse, creating transparency risk.

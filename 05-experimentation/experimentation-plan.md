# A/B Experiment Brief, Riverty business-unit case

## Parameters
| Parameter | Decision |
|---|---|
| Feature under test | Self-service update of direct-debit bank details for eligible installment plans in the customer portal. The payer enters a new IBAN, reviews the details and receives confirmation of the update. |
| Persona | Responsible Payer: a parent or self-paying customer who is financially responsible for an installment plan and wants to manage it independently after setup. |
| Expected outcome | Responsible Payers can update their direct-debit bank details in self-service, a capability that is currently unavailable. This should reduce the share of all installment plans followed by a phone or email contact by 10–15% relative. |
| Primary success metric | Percentage of all newly created installment plans followed by at least one manual contact via phone or email. |
| Baseline rate | Assumption: 12% of all installment plans are currently followed by at least one phone or email contact. The available data does not show which share of these contacts relates specifically to bank-detail changes. |
| Guardrail metric | Direct-debit return rate after customers update their bank details. |
| Guardrail boundary | The direct-debit return rate must not increase by more than 0.2 percentage points compared with the current baseline. |
| Second guardrail | · |
| Minimum Detectable Effect | 1.8 percentage points, corresponding to a reduction from 12% to 10.2%, or 15% relative. |
| Sample size per arm | Approximately 4,800 newly created installment plans per group, based on 95% confidence and 80% statistical power. |
| Traffic split | 50% control group and 50% treatment group. |
| Test duration | Six to eight weeks, or until each group contains at least 4,800 installment plans. |
| Significance threshold | p < 0.05, corresponding to 95% confidence, with 80% statistical power. |

## Control vs. Variant
- **Control (A):** The direct-debit bank details cannot be changed in the customer portal. A Responsible Payer who needs to use a different bank account must contact BFS by phone or email. The request is then checked and processed manually. This contact is recorded as a post-creation manual contact for the installment plan.
- **Variant (B):** Eligible Responsible Payers can select “Change bank details” in the customer portal, enter the account holder and new IBAN, review the masked bank details and submit the change. The data is validated and transferred to the existing core system. The payer immediately receives a success or error confirmation.
- **Held constant (isolation check):** The installment plan, eligibility rules, customer authentication, payment schedule, direct-debit rules, core-system processing, IBAN validation, customer notifications and support processes remain identical in both groups. The only difference is whether the payer can initiate the bank-detail update through the customer portal.

## Hypothesis
> I believe that Self-service update of direct-debit bank details for eligible installment plans in the customer portal. The payer enters a new IBAN, reviews the details and receives confirmation of the update. for Responsible Payer: a parent or self-paying customer who is financially responsible for an installment plan and wants to manage it independently after setup. will result in Responsible Payers can update their direct-debit bank details in self-service, a capability that is currently unavailable. This should reduce the share of all installment plans followed by a phone or email contact by 10–15% relative., as measured by a 1.8 percentage points, corresponding to a reduction from 12% to 10.2%, or 15% relative. change in Percentage of all newly created installment plans followed by at least one manual contact via phone or email. within Six to eight weeks, or until each group contains at least 4,800 installment plans.. We will protect Direct-debit return rate after customers update their bank details. throughout the test.

## Shipping criteria
> We will **ship** if Percentage of all newly created installment plans followed by at least one manual contact via phone or email. improves by ≥ 1.8 percentage points, corresponding to a reduction from 12% to 10.2%, or 15% relative. at p < 0.05, corresponding to 95% confidence, with 80% statistical power. and Direct-debit return rate after customers update their bank details. does not reach The direct-debit return rate must not increase by more than 0.2 percentage points compared with the current baseline. after Six to eight weeks, or until each group contains at least 4,800 installment plans..
> We will **iterate** if direction is positive but lift is below the MDE.
> We will **kill** if the primary metric shows no improvement or moves negatively.
> The read date is fixed at the end of Six to eight weeks, or until each group contains at least 4,800 installment plans., no results reviewed before this date.

# A/B Experiment Brief, Riverty business-unit case

**Status:** Revised draft. Launch requires a measured primary-metric baseline, confirmed traffic, final sample-size calculation and approval of the proposed outcome targets and safety boundary below.

## Parameters

| Parameter | Decision |
|---|---|
| Feature under test | Self-service update of direct-debit bank details for eligible installment plans in the customer portal. The payer enters the account holder and a new IBAN, reviews masked details and receives a confirmed outcome. |
| Persona | Responsible Payer: a parent or self-paying customer who is financially responsible for an installment plan and wants to manage it independently after setup. |
| Moment of misery | The payer needs to change the account used for direct debit but cannot do so in the portal and must contact support. |
| Expected outcome | Eligible payers can complete a bank-detail update without phone or email support. Bank-detail-related manual contacts decrease. A material change in the overall self-service or all-reason contact rate is not assumed from this feature alone. |
| Primary success metric | Percentage of newly created, eligible, randomised installment plans followed by at least one phone or email contact about changing direct-debit bank details within 30 days of creation. Count each plan once, regardless of the number of relevant contacts. |
| Primary baseline | Not yet measured. Establish using historical eligible plans and the same contact definition and 30-day window. The available overall contact data does not identify the bank-detail-related share. |
| Primary effect target | Proposed planning target: a 15% relative reduction in bank-detail-related contact rate versus concurrent control. Validate its feasibility and lock this target before launch. Absolute MDE = measured primary baseline × 0.15. |
| Feature outcome metric | Percentage of eligible self-service update attempts confirmed as successful by the core system, with no bank-detail-related phone or email support within seven days of submission. Proposed target: at least 70%; this is a new target, not an observed baseline. Use a predefined attempt/session identifier to avoid counting retries as separate attempts. |
| Wider business metric | Percentage of all newly created, randomised installment plans followed by at least one phone or email contact for any reason within 30 days of creation. Report as secondary; it does not determine success alone. |
| Wider business baseline | Assumption: 12%. Verify against the same 30-day window. This refers to all-reason contacts, not bank-detail contacts. The initiative's 10–15% relative reduction remains a broader ambition, not an established forecast for this feature. |
| Guardrail metric | Returned direct-debit attempts divided by all direct-debit attempts for randomised eligible plans in each arm during a fixed 60-day follow-up from creation. Compare treatment with concurrent control. Report returns following bank-detail changes separately as a diagnostic. |
| Guardrail boundary | Proposed maximum acceptable increase: 0.2 percentage points versus concurrent control. Pass only if the upper one-sided 95% confidence bound for treatment minus control is below +0.2 percentage points. Confirm this tolerance and calculate safety power before launch. |
| Additional safety condition | No unresolved critical defect involving incorrect-account updates, unauthorised access or incorrect success confirmations. |
| Randomisation and traffic split | 50% control / 50% treatment, assigned persistently by Responsible Payer before feature exposure. All plans belonging to that payer receive the same assignment. Eligibility must be determined using the same rules in both arms before exposure. |
| Sample size per arm | To be calculated from the measured primary baseline and locked MDE. Account for multiple plans per payer and repeated debit attempts in safety analysis. Final recruitment must support both efficacy and the safety criterion. |
| Test duration | Proposed recruitment period: eight weeks, with an exact start and end date locked before launch. Confirm that projected traffic reaches the required sample by that deadline. Final analysis follows full 30-day contact and 60-day safety follow-up for the last recruited plans. |
| Significance threshold | Two-sided p < 0.05 for the primary metric, with a 95% confidence interval and at least 80% planned power. Power is a design parameter, not a shipping result. The safety assessment uses the separate one-sided confidence bound defined above. |

## Control vs. Variant

- **Control (A):** Bank details cannot be changed in the customer portal. A payer who needs a different bank account contacts BFS by phone or email, and the request is checked and processed manually. If another support channel exists, keep it available and measure it in both arms.
- **Variant (B):** Eligible payers select “Change bank details”, enter the account holder and new IBAN, review masked details and submit. The existing core system validates and processes the update. The portal shows success only after the core system confirms the update; otherwise it shows an actionable error.
- **Held constant:** Underlying eligibility, authentication, payment schedules, direct-debit rules, validation requirements, core-system processing, existing customer notifications and support handling remain the same. Treatment adds the portal initiation, review and outcome journey. No separate reminder campaign, incentive or payment-rule change is included.
- **Isolation check:** This is one complete capability. Its form, review and confirmation steps are necessary parts of that capability. The experiment estimates the effect of the complete journey, not the contribution of each screen.

## Hypothesis

> Giving Responsible Payers access to self-service bank-detail updates will let them resolve an account change independently and reduce bank-detail-related phone or email contacts among eligible newly created plans. We propose a 15% relative reduction versus control within 30 days of creation and at least 70% successful, support-free completion among treatment update attempts. We will protect payment reliability by requiring the upper one-sided 95% confidence bound on the increase in direct-debit return rate to remain below 0.2 percentage points. These targets must be locked before launch; the feature's effect on all-reason contact rate remains exploratory.

## Measurement and attribution

- Analyse the primary metric by original assignment, including eligible plans whose payers never visit the portal or start an update. Do not restrict the causal comparison to successful users or update submitters.
- Use payer-clustered inference for plan outcomes and payment attempts. Recalculate sample requirements if repeat payers make the independent-observation approximation inadequate.
- Link phone and email contacts to plan IDs and apply the same bank-detail reason classification in both arms. Validate classification and missing-link rates before launch.
- Track eligibility, feature exposure, attempt start, submission, core-system outcome, abandonment, errors and subsequent support. Track free-text portal contacts to detect a shift into another manual channel.
- Record the effective account-change date and subsequent debit outcomes for diagnosis. Submission alone is not a successful update.

## Sample size and feasibility

The former estimate of **approximately 4,800 plans per arm** applies only to an all-reason contact reduction from **12% to 10.2%**, using independent observations, a two-sided 5% significance level and 80% power. It is not the sample requirement for the revised primary metric or safety criterion.

| Illustrative all-reason effect | Approximate independent plans per arm |
|---|---:|
| 12% to 10.2%: 15% relative reduction | 4,800 |
| 12% to 10.8%: 10% relative reduction | 11,000 |
| 12% to 11.4%: 5% relative reduction | 45,000 |

These are normal-approximation planning estimates. A rarer bank-detail contact baseline may require substantially more plans to detect a 15% relative reduction. Confirm the actual baseline, traffic and safety sample requirement before committing to eight weeks.

For context, 9,600 total plans require about 1,200 qualifying plans per week over eight weeks. Eight weeks of recruitment plus 60-day safety follow-up means roughly 17 weeks until the final read, potentially longer for payment-outcome reporting delays. Predefine when a debit return is considered fully reported and use that rule in both arms.

A 1.8-percentage-point reduction in all-reason contacts would require preventing contacts on 1.8% of all plans. At an assumed 70% avoidance rate, at least 2.57% of all plans would need an avoidable bank-detail contact and no remaining other contact. This is a feasibility illustration, not observed evidence or a forecast. The assumed avoidance rate is distinct from the proposed attempt-completion target.

## Shipping criteria

Apply these rules once, at the prespecified final analysis, using the locked target and complete follow-up:

- **Ship broadly** only if all conditions pass: bank-detail-related contact rate is at least 15% lower than concurrent control; the two-sided 95% confidence interval for treatment minus control lies entirely below zero; treatment achieves at least 70% successful, support-free attempt completion; the safety confidence bound is below +0.2 percentage points; and no critical defect remains unresolved.
- **Iterate and retest** if payment safety passes but completion is below 70%, or the estimated contact reduction is positive but below the locked target. A revised journey requires a new predefined experiment.
- **Inconclusive — do not ship broadly on this evidence** if the confidence interval includes zero, the required sample or follow-up is incomplete, data quality fails, or the safety margin cannot be established. An inconclusive result is not proof that the feature has no value.
- **Stop rollout and investigate** if contact rate shows statistically supported harm, observed safety deterioration reaches the agreed boundary, or a critical defect appears. Restart requires resolution and a new agreed assessment.
- A positive secondary all-reason metric cannot override a failed primary or safety criterion. Failure to detect an overall contact-rate change does not invalidate a passing feature-specific result.

Do not repeatedly inspect efficacy p-values or extend recruitment until significance appears. Monitor safety and operational data throughout, with the stop conditions above. If sample accrual misses the locked deadline, report the result as inconclusive; any extension must use an agreed statistical plan before further efficacy analysis.

The 80% power calculation concerns detecting a difference from zero. It does not imply an 80% chance of also meeting the observed 15% reduction threshold. Check the probability of satisfying the complete shipping rule during final design.

## Required before launch

1. Measure the bank-detail-related primary baseline and validate the assumed 12% overall baseline with the fixed observation window.
2. Approve the proposed 15% relative effect target, 70% completion target and 0.2-percentage-point safety margin.
3. Calculate efficacy and safety sample requirements, incorporating payer clustering and payment frequency.
4. Confirm traffic, contact tagging, persistent assignment and outcome tracking.
5. Lock recruitment dates, final read date, reporting delays, analysis methods and decision rules.

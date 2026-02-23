# QuickLoan Mobile Ethical Data Governance Review

---

## Deliverable 1: Governance Review Card

| Section                                                     | Issue/Definition                                                                                                                | Impact                                                                                                                  | Suggested Fix/Mitigation                                                                                                                    |
| ----------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Data Quality Risk**                                    | Incomplete and inconsistently formatted customer data (e.g., missing ID fields, inconsistent phone formats, duplicate records). | Inaccurate credit scoring, unfair loan decisions, higher default risk, reduced model reliability.                       | Implement API-level validation (mandatory fields, format checks), schema enforcement, and automated data-cleaning with duplicate detection. |
| **2. Legal & Compliance Risk**                              | Excessive collection of personal data (e.g., full contact lists) without explicit, informed consent.                            | High risk of violating Ghana’s Data Protection Act (Act 843), regulatory penalties, reputational damage, loss of trust. | Apply Data Minimization, introduce granular consent capture with audit logs, appoint a DPO, and conduct periodic compliance audits.         |
| **Data Classification (Sensitive)**                         | Financial data, national ID, contact data, and behavioral metadata qualify as Sensitive personal data.                          | Requires highest level of protection under governance and regulatory standards.                                         | Encrypt data at rest and in transit, apply strict access controls, and implement defined retention and deletion policies.                   |
| **3. Bias & Fairness Risk**                                 | ML model may produce systematically lower approval rates for certain demographic groups.                                        | Ethical risk, regulatory exposure, reputational harm, reduced financial inclusion.                                      | Conduct quarterly fairness audits and introduce human review for borderline cases.                                                          |
| **Source of Bias**                                          | Use of proxy variables such as location, device type, and contact network size that correlate with socioeconomic status.        | Indirect discrimination against vulnerable or lower-income groups.                                                      | Perform feature sensitivity analysis and remove or rebalance biased predictors.                                                             |
| **4. Storytelling / Reporting Recommendation**              | Establish transparent fairness monitoring in executive dashboards.                                                              | Improves accountability and builds regulatory and public trust.                                                         | Publish quarterly fairness performance reports internally.                                                                                  |
| **Metric to Monitor (Fair Approval Rate Disparity – FARD)** | Percentage difference in approval rates between highest-approved and lowest-approved demographic groups per quarter.            | Quantifies algorithmic fairness gaps in measurable terms.                                                               | Trigger model review if disparity exceeds predefined threshold (e.g., 10%).                                                                 |
| **Visualization Type**                                      | Grouped Bar Chart (Approval Rate by Demographic Group per Quarter).                                                             | Makes disparities visually comparable across groups.                                                                    | Include in quarterly governance dashboard.                                                                                                  |
| **Why It Matters**                                          | Ensures the automated system does not disproportionately disadvantage specific groups.                                          | Promotes ethical AI governance and compliance readiness.                                                                | Supports transparent, responsible fintech operations.                                                                                       |

---

## Deliverable 2: Corrected Data Flow Diagram (Annotated Corrections)

Below are the required corrections with explanations:

1. **Correction at Step 1 – Data Minimization Implemented**\
   Remove collection of unnecessary data such as full contact lists and unrelated device metadata.\
   *Reason:* Reduces privacy risk and ensures compliance with the Data Protection Act by collecting only data necessary for credit assessment.

2. **Correction Between Step 2 and Step 3 – Consent Management Layer Added**\
   Introduce an explicit Consent Capture & Logging Service before data is stored in the Raw Data Database.\
   *Reason:* Ensures lawful processing and provides an auditable trail of user consent.

3. **Correction at Step 3 – Data Classification & Retention Policy Applied**\
   Classify stored data as Sensitive and implement automated retention rules (e.g., delete inactive user data after defined period).\
   *Reason:* Prevents indefinite storage of PII and reduces regulatory exposure.

4. **Correction at Step 4 – Defined Preprocessing Controls**\
   Add data validation, schema enforcement, and bias screening before data enters the ML model.\
   *Reason:* Improves data quality and reduces risk of biased model inputs.

5. **Correction at Step 7 – Decision Logging & Explainability**\
   Implement decision logging and generate explainability reports for each loan decision.\
   *Reason:* Enhances transparency and allows regulatory or internal audit review.

6. **Correction at Step 9 & 10 – Data Masking & Anonymization**\
   Apply masking/anonymization before storing data in Analytics DB or sharing with third-party partners.\
   *Reason:* Protects PII from misuse and limits third-party exposure risk.

---

## Deliverable 3: Summary of Review Process (Approx. 250 Words)

The review process was conducted using Data Lifecycle principles: Collection, Storage, Processing, Sharing, and Retention. At each stage of the QuickLoan pipeline, risks were identified by asking whether the data collected was necessary, properly classified, lawfully processed, securely stored, fairly used, and responsibly deleted. By mapping each flaw to a lifecycle stage, it became clear where governance controls were missing.

Data Classification principles were applied to determine sensitivity levels. Since the application processes financial and personally identifiable information, the dataset was classified as Sensitive. This classification informed stricter controls, including encryption, retention limits, consent documentation, and masking before analytics or third-party sharing.

The proposed metric — Fair Approval Rate Disparity (FARD) — strengthens ethical governance by translating abstract fairness concerns into a measurable business indicator. Rather than relying solely on compliance documentation, the company can continuously monitor disparities in approval rates across demographic segments. A grouped bar chart published quarterly promotes internal accountability and external transparency. If disparities exceed a defined threshold, corrective actions such as model retraining or feature review can be triggered.

By integrating lifecycle governance, strict classification, and measurable fairness reporting, QuickLoan can move from reactive risk management to proactive, ethical data governance aligned with regulatory and societal expectations.


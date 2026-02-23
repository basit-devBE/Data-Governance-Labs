# EduConnect Ghana - Data Access Decision Forms

---

## Request 1: Marketing Campaign
**Requester:** Sarah Owusu, Marketing Manager  
**Request:** Full student database (names, emails, phone numbers, course enrollments)

**Decision:** Conditional Approval

**Lifecycle Stage:** Use / Share

**Justification:**
- Email addresses are CONFIDENTIAL and cannot be shared without safeguards.
- Names and enrollments are INTERNAL; Sarah has access.
- Principle of least privilege dictates sharing only data required for the campaign.

**Action Steps:**
1. Redact CONFIDENTIAL data (emails, phone numbers) or replace with hashed IDs.
2. Provide only INTERNAL data necessary for campaign segmentation.
3. Require signed NDA or internal usage agreement.
4. Notify Data Privacy Officer (DPO) for approval.
5. Audit access and log any data exported.

**Consulted Parties:**
- DPO
- IT Security Team

---

## Request 2: Analytics Partnership
**Requester:** David Mensah, Head of Product  
**Request:** External partner (DataInsights Inc.) needs AWS database access.

**Decision:** Conditional Approval

**Lifecycle Stage:** Share / Use

**Justification:**
- Sharing CONFIDENTIAL student profiles externally triggers compliance requirements under Ghana DPA.
- INTERNAL activity logs are lower risk but still sensitive.
- Principle of least privilege: grant only necessary, anonymized data.
- Legal/compliance red flags: cross-border transfer, external processing, GDPR-equivalent considerations.

**Action Steps:**
1. Anonymize or pseudonymize student profiles before sharing.
2. Provide access via secure API or read-only database account; no direct credential sharing.
3. Sign Data Processing Agreement (DPA) with DataInsights Inc.
4. Log and monitor all external access.
5. DPO and Legal approval required before data transfer.

**Documentation Required:**
- DPA signed with partner
- Access request and approval logs
- Data anonymization method documentation

---

## Request 3: Archive & Deletion
**Requester:** Comfort Asante, Customer Support Lead  
**Request:** Full deletion of student account per 'right to be forgotten'

**Decision:** Approve

**Lifecycle Stage:** Destroy

**Justification:**
- Student data is CONFIDENTIAL.
- No pending obligations; Ghana DPA requires honoring deletion requests.
- Principle of least privilege: only authorized personnel should perform deletion.
- Some metadata for auditing may be retained, but personal identifiers must be removed.

**Action Steps:**
1. Verify account status and absence of obligations.
2. Delete all personal and academic data from live databases.
3. Remove backups according to retention policy or anonymize if full deletion is not immediately feasible.
4. Log deletion action in secure audit trail.
5. Notify student of completion.

**Legal Obligations:**
- Ghana DPA mandates honoring data subject requests for deletion.
- Retention of only anonymized metadata for operational or legal reasons is acceptable.

**Process:**
- Customer Support initiates deletion request.
- IT executes data removal under audit.
- Confirmation sent to student.

---


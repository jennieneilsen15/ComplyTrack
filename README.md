# ComplyTrack
Vendor Risk & Compliance Governance Platform (Beta Release)

---

## 1. Project Organization

This project was managed using a Kanban board with the following columns:

- Backlog – Future enhancements
- To Do – Approved work ready to begin
- In Progress – Active development
- QA / Testing – Validation stage
- Done – Completed and verified items

Issues were labeled using:

Priority:
- P0 = Critical defects
- P1 = Core governance controls
- P2 = Enhancements

Type:
- Feature
- Bug
- Compliance Control

All P0 issues must be resolved before release.

---

## 2. Test Plan

### Test Case 1 – Risk Threshold Trigger

Scenario:
Vendor risk score exceeds the defined threshold.

Steps:
1. Set vendor risk score to 85
2. Threshold set to 80
3. Save vendor profile

Expected Result:
System generates alert and logs event.

Pass:
Alert appears and audit log entry is recorded.

Fail:
No alert OR missing audit log entry.

---

### Test Case 2 – RBAC Access Restriction

Scenario:
Viewer role attempts to edit vendor data.

Steps:
1. Log in as Viewer
2. Attempt to modify risk score

Expected Result:
System blocks modification.

Pass:
Edit is denied and attempt is logged.

Fail:
Viewer can edit data.

---

### Test Case 3 – Audit Log Integrity

Scenario:
Admin updates user permissions.

Steps:
1. Modify role
2. Save changes

Expected Result:
Audit log records:
- Timestamp
- User making change
- Change made

Pass:
All required fields recorded correctly.

Fail:
Missing required log information.

---

## 3. Automated Testing Tools

Recommended tools:

Selenium – Automates UI testing for role-based access control.

Postman – Tests API behavior for threshold calculations.

JUnit (or PyTest) – Tests business logic and edge cases.

These tools help detect defects early and reduce manual testing.

---

## 4. Strategic Reflection

This beta release focuses on internal controls before adding more features.

By prioritizing:
- RBAC enforcement
- Immutable audit logging
- Risk threshold validation

the system reduces compliance risk and improves governance oversight.

### Shift-Left Approach

Testing was integrated early in development.

By validating controls before full deployment:
- Defects are caught sooner
- Rework costs are reduced
- System reliability improves

Resolving P0 issues before release protects the business from regulatory and operational risk.

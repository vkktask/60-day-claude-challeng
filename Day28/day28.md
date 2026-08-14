# Day 28 â Hospital Admission Readiness Simulator

**Category:** Healthcare Operations with Claude  
**Difficulty:** Intermediate  
**Time:** 60 min  
**Deliverable:** GitHub commit URL

---

## What I Built

An interactive Hospital Admission Readiness Simulator where you play the role of a Hospital Admission Coordinator. Enter patient and admission details, analyze readiness, and complete workflow actions to bring a patient to full admission readiness.

---

## Features

### Setup (Task-First Design)
- Provider and Attending Physician name input
- Diagnosis selector: Acute MI / CHF / Pneumonia / Elective Surgery / Hip Fracture
- Admission Type: Inpatient / Observation / Emergency / ICU / Same-Day Surgery
- PA Status: Approved / Pending / Denied / Not Required
- CMS 2-Midnight Rule notice auto-shown for Observation admissions (MOON notification requirement)

### Readiness Score System
Weighted scoring across 6 dimensions:
| Category | Weight |
|---|---|
| PA Status | 25% |
| Clinical Documentation | 25% |
| Insurance Verification | 20% |
| Bed Availability | 15% |
| Physician Orders | 10% |
| Patient Consent | 5% |

- Initial score: 30â60% range
- Final decision: **â¥90% â â Admit** / **<90% â â ï¸ Not Ready**

### Workflow Actions (7 total)
Assign Bed Â· Verify Insurance Â· Upload Documentation Â· Complete Consent Â· Contact Physician Â· Notify Nursing Â· Prepare Patient Arrival

### Care Coordination Cards
Attending Physician Â· Case Manager Â· Nursing Â· Utilization Review (InterQual/Milliman) Â· Discharge Planner

### Risk Tracking
Documentation Risk Â· Insurance Risk Â· Bed Risk Â· Clinical Risk (weighted higher for Acute MI, CHF, ICU)

### Governance Snapshot (shown at â¥75%)
- PA turnaround benchmark: 3â5 days
- Inpatient denial rate: ~8â10% (CMS)
- PA rework cost: ~$11/transaction (CAQH)

### PA Resolution Workflow
- **Pending PA:** Follow Up / Request Expedited Review / Peer-to-Peer Review
- **Denied PA:** Review Denial Reason / Contact Insurance / Submit Appeal â converts to Approved

---

## Prompt Used

```
Hospital Admission Readiness Simulator

Single-file HTML app. HTML, Tailwind CSS CDN, Vanilla JavaScript.
Healthcare simulation design system. Task-first â no dashboard on load.
User plays Hospital Admission Coordinator.

Setup â collect Provider, Attending Physician, Diagnosis, Admission Type, PA Status, Admission Date.
[Full prompt as provided on abtalks.in/challenge/28]
```

---

## Key Learnings

- **PA status is the highest-weighted factor** in admission readiness (25% of score)
- **Observation vs Inpatient** is a critical distinction â CMS 2-Midnight Rule fundamentally changes cost-sharing, SNF eligibility, and billing. Medicare patients require MOON notification.
- **InterQual/Milliman criteria** govern medical necessity for clinical cases like Acute MI and CHF â UR teams use these tools to prevent denials
- **Concurrent review** happens during the stay, not just at admission â UR card represents this ongoing process
- **Industry benchmarks**: ~8â10% inpatient denial rate (CMS), ~$11 per PA rework transaction (CAQH)
- **Discharge planning starts at admission** â the Discharge Planner is part of the admission coordination team

---

## Screenshots

*[Add screenshots of the simulator here]*

---

## HTML Output

See `day28.html` in this folder for the complete working application.

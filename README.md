# Day 5 — ISO/IEC 42001:2023 vs ISO 27001 Gap Analysis

**Challenge:** ABTalks 60-Day Claude AI Challenge
**Author:** [Vivek DP](https://www.linkedin.com/in/vivekdp/)
**Date:** Day 5 of 60
**Time Invested:** 4 hours

---

## 🎯 Day 5 Objective

Full walkthrough of **ISO/IEC 42001:2023** (AI Management System standard) and a structured comparison against **ISO 27001** — mapping overlaps, gaps, and what organizations already certified under 27001 need to add for AI governance compliance.

---

## 🔍 What I Did

- Read ISO/IEC 42001:2023 clause-by-clause
- Cross-mapped its structure against ISO 27001:2022
- Identified where cyber GRC controls translate directly vs. where AI introduces new requirements
- Built a Gap Analysis Matrix (see below)

---

## 📊 ISO 42001 vs ISO 27001 — Gap Analysis Matrix

| Domain | ISO 27001 Coverage | ISO 42001 Requirement | Gap? |
|--------|-------------------|----------------------|------|
| Context of the organization | ✅ Clause 4 | ✅ Clause 4 — adds AI-specific interested parties (affected communities, regulators) | Partial gap |
| Leadership & AI Policy | ✅ Top management commitment | ✅ Requires explicit AI Policy + responsible AI principles | New requirement |
| Risk Assessment | ✅ Information risk | ✅ Extends to AI-specific risks: bias, explainability, data quality, model drift | Significant gap |
| AI System Impact Assessment | ❌ Not covered | ✅ Clause 6.1.2 — mandatory AI impact assessment before deployment | New requirement |
| Supplier / Third-party AI | ✅ Supplier security (A.5.19) | ✅ Extends to AI suppliers, datasets, model provenance | Moderate gap |
| Transparency & Explainability | ❌ Not covered | ✅ Annex A controls for human oversight and explainability | New requirement |
| Data Governance for AI | Partial (data classification) | ✅ Specific controls for training data quality, labelling, bias detection | Significant gap |
| Incident Management | ✅ Clause 6.6 | ✅ Extends to AI-specific incidents (model failure, bias incidents) | Partial gap |
| Continual Improvement | ✅ Clause 10 | ✅ Adds model performance monitoring and retraining governance | Moderate gap |
| Human Oversight | ❌ Not covered | ✅ Core requirement — humans in the loop for high-risk AI decisions | New requirement |

---

## 🧠 Key Takeaways

1. **ISO 27001 is a strong foundation** — organizations already certified have ~50–60% of the clause structure in place. The management system architecture (Plan-Do-Check-Act) is identical.

2. **The biggest gaps are AI-specific:** impact assessment, explainability, training data governance, and human oversight are net-new requirements with no 27001 equivalent.

3. **For VP-level positioning:** The ability to map 42001 to an existing 27001 program is a high-value skill — most CISOs and CDOs don't yet know where the overlap is.

4. **Regulatory alignment:** ISO 42001 aligns closely with EU AI Act requirements for high-risk AI systems — making dual compliance achievable with a single integrated management system.

---

## 🛠️ Tools Used

- Claude (AI governance analysis and structuring)
- ISO/IEC 42001:2023 (official standard)
- ISO 27001:2022 (reference)

---

## 📚 Resources Referenced

- [ISO/IEC 42001:2023 Overview — ISO.org](https://www.iso.org/standard/81230.html)
- [NIST AI RMF cross-mapping to ISO 42001](https://airc.nist.gov/)
- [BSI ISO 42001 Implementation Guide](https://www.bsigroup.com)

---

## 🔗 Connect

- LinkedIn: [Vivek DP](https://www.linkedin.com/in/vivekdp/)
- GitHub: [vkktask/60-day-claude-challeng](https://github.com/vkktask/60-day-claude-challeng)

---

*Part of the 30-Day VP AI Governance Roadmap | ABTalks 60-Day Challenge*

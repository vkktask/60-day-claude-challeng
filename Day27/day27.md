# Day 27 â Prior Authorization Story Simulator

**Category:** Interactive Storytelling with Claude  
**Difficulty:** Intermediate  
**Time:** 60 min  
**Deliverable:** GitHub commit URL

---

## What I Built

A single-file interactive HTML storytelling app that walks through the U.S. healthcare Prior Authorization (PA) process through the eyes of a patient (Rahul) and a healthcare operations specialist (Priya).

**Characters:**
- ð¦ **Rahul** â Patient diagnosed with Rheumatoid Arthritis, prescribed Humira
- ð§ **Priya** â Healthcare Operations Specialist navigating the PA process
- *Narrators and doctors appear as centered italic text*

**8 Scenes:**
1. Doctor Visit â Diagnosis & Humira prescription
2. Insurance Roadblock â PA submission to StarCare Health
3. What Is PA? â Priya explains step therapy and authorization
4. Insurance Review â What StarCare Health checks (eligibility, ICD-10, step therapy)
5. Denial â Missing step therapy documentation
6. Appeal â Letter of Medical Necessity, peer-to-peer review
7. Approval â PA approved, reference number issued, permanent record
8. Takeaways â Patient perspective + System metrics (denial rate, appeal rate, resolution time)

---

## Prompt Used

```
Prior Authorization Story Simulator

Single-file HTML app. HTML, Tailwind CSS CDN, Vanilla JavaScript.
Use createElement + appendChild for every new chat bubble. Never call innerHTML = on the chat container.
Design: same as previously established.

Characters
ð¦ Rahul â patient. Appears left.
ð§ Priya â healthcare operations specialist. Appears right.
Narrators and doctors appear as centered italic text only, never chat bubbles.

Story â 8 scenes with append-only chat feed and progress bar:
[Full prompt as provided on abtalks.in/challenge/27]
```

---

## Key Learnings

- **PA causes real treatment delays** â AMA 2023 PA Survey: majority of cases experience delays
- **Step therapy is systemic** â patients must try cheaper drugs first before accessing biologics like Humira
- **Denials aren't final** â ~40% of appeals succeed, but only ~11% of patients actually appeal
- **Provider burden is real** â PA denials cost physician offices 2+ staff hours to resolve per case
- **Reform is coming** â CMS now mandates faster PA timelines for Medicare Advantage plans
- **PA reference numbers are permanent** â once approved, no repeat PA needed for the same medication

## Technical Implementation

- Single HTML file with Tailwind CSS CDN + Vanilla JavaScript
- Append-only chat feed using `createElement + appendChild` (no innerHTML on container)
- 8 scenes with choice-based dialogue branching
- Progress bar tracking across all scenes
- Animated chat bubbles (left for Rahul, right for Priya/doctors)
- Healthcare education design system with blue/emerald color scheme

---

## Screenshots

*[Add screenshots of the simulator here]*

---

## HTML Output

See `day27.html` in this folder for the complete working application.

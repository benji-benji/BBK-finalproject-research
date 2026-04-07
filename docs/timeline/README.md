# Timeline — Canonical Document

**Proposal Deadline:** 7 May 2026
**Draft to Dr. Chen:** 29 April 2026
**Today:** 7 April 2026
**Working days remaining:** ~17 usable sessions (including 3 full days at RHIW)

This is the single source of truth for the proposal timeline. All other documents in this folder are layout experiments — pick the one(s) that work for you and link back here for the facts.

---

## Workstreams

| Stream | Owner | Description | Status |
|---|---|---|---|
| CODE | Ben | Implement ROME, MEMIT, GRACE on GPT-2. Log experiments. | In progress |
| READING | Ben | Read and critically evaluate 8 editing methods + supporting papers | In progress |
| WRITING | Ben | Draft and submit 2000-3000 word proposal | Not started |

---

## Milestones

| # | Milestone | Target Date | Depends On | Done? |
|---|---|---|---|---|
| M1 | ROME implemented + EXP-001 logged with results | 13 Apr | — | [ ] |
| M2 | MEMIT implemented + EXP-002 logged with results | 15 Apr | M1 (shared utilities) | [ ] |
| M3 | Lit review reading complete (8 methods + framing papers) | 17 Apr | — | [ ] |
| M4 | GRACE implemented + EXP-003 logged with results | 27 Apr | M1 (shared utilities) | [ ] |
| M5 | Full proposal draft complete | 29 Apr | M1, M2, M3, M4 | [ ] |
| M6 | Draft sent to Dr. Chen | 29 Apr | M5 | [ ] |
| M7 | Feedback incorporated, final version ready | 6 May | M6 | [ ] |
| M8 | **SUBMITTED on Moodle** | **7 May** | M7 | [ ] |

---

## MoSCoW Prioritisation

**Must have** (proposal fails without these):
- ROME working on GPT-2 with logged results
- Literature review of at least the 3 implemented methods + 3 others
- Complete proposal draft sent to supervisor before deadline
- Submitted on Moodle by 7 May

**Should have** (distinction-level):
- MEMIT working on GPT-2 with logged results
- GRACE working on GPT-2 with logged results
- All 8 methods reviewed in lit review
- Original diagrams in proposal (pipeline, method comparison)
- Feedback from Dr. Chen incorporated

**Could have** (if time allows):
- Comparative results table across all 3 methods
- Preliminary investigation of code model architecture differences

**Won't have** (reserved for final report):
- Code model experiments
- Global preference editing exploration
- Custom datasets

---

## Dead Zones (no project work)

| Dates | Reason |
|---|---|
| Fri 25 Apr | HarPA — Reflective Practice Tool due |
| 2-4 May | CAMP + recovery |

**Note:** RHIW week (21-23 Apr) provides 3 full working days for reading/prep — not a dead zone.

---

## Available Project Sessions

| # | Date | Day | Location | Hours |
|---|---|---|---|---|
| 1 | 8 Apr | Tue | Space4 | Full day |
| 2 | 12 Apr | Sat | Home | Half day |
| 3 | 13 Apr | Sun | Home | Half day |
| 4 | 14 Apr | Mon | Space4 | Full day |
| 5 | 15 Apr | Tue | Space4 | Full day |
| 6 | 16 Apr | Wed | Home | Half day |
| 7 | 17 Apr | Thu | Home | Half day |
| 8 | 21 Apr | Mon | RHIW | Full day |
| 9 | 22 Apr | Tue | RHIW | Full day |
| 10 | 23 Apr | Wed | RHIW | Full day |
| 11 | 26 Apr | Sat | Home | Half day+ |
| 12 | 27 Apr | Sun | Home | Half day+ |
| 13 | 28 Apr | Mon | Space4 | Full day |
| 14 | 29 Apr | Tue | Space4 | Full day |
| 15 | 5 May | Wed | Home | Half day |
| 16 | 6 May | Thu | Home | Half day |
| 17 | **7 May** | **Fri** | — | **SUBMIT** |

---

## Risks

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| RHIW block kills week 3 | Certain | High | Front-load ROME + MEMIT in weeks 1-2. GRACE into weekend 26-27 |
| CAMP leaves no buffer | Certain | High | Draft done by 29 Apr. Only feedback edits remain |
| ROME doesn't work first try | Medium | High | Debug against reference repo known-good outputs |
| Not enough time for GRACE | Medium | Medium | Lowest priority. Can report ROME + MEMIT with GRACE as "planned" |
| Dr. Chen wants major changes | Low | High | Send draft early. Keep sections modular |

---

## Layout Options

Pick whichever view works best for day-to-day use. They all describe the same plan.

| Layout | File | Best for |
|---|---|---|
| A — Backcast | [backcast.md](backcast.md) | Seeing the logic of why each date was chosen |
| B — Workstreams | [workstreams.md](workstreams.md) | Seeing how CODE / READING / WRITING overlap and converge |
| C — Countdown Checklist | [countdown.md](countdown.md) | Daily "what do I do next" with checkboxes and running score |
| D — Kanban | [kanban.md](kanban.md) | Living board — BACKLOG / DOING / DONE, updated as you work |
| E — Gantt + Milestones | [gantt.md](gantt.md) | Bird's-eye view with dependency map and critical path |

# Timeline — Canonical Document

**Proposal Deadline:** 7 May 2026
**Draft to Dr. Chen:** 29 April 2026
**Today:** 7 April 2026
**Working days remaining:** ~15 usable sessions

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
| Most of w/c 21 Apr | RHIW (Mon-Wed), Reflective Practice Tool due (Fri) |
| 2-4 May | CAMP + recovery |

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
| 8 | 26 Apr | Sat | Home | Half day+ |
| 9 | 27 Apr | Sun | Home | Half day+ |
| 10 | 28 Apr | Mon | Space4 | Full day |
| 11 | 29 Apr | Tue | Space4 | Full day |
| 12 | 5 May | Wed | Home | Half day |
| 13 | 6 May | Thu | Home | Half day |
| 14 | **7 May** | **Fri** | — | **SUBMIT** |

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
| B — Calendar Grid | [calendar_grid.md](calendar_grid.md) | Weekly overview at a glance |
| C — Workstreams | [workstreams.md](workstreams.md) | Seeing how CODE / READING / WRITING overlap |
| D — Countdown Checklist | [countdown.md](countdown.md) | Daily "what do I do next" with checkboxes |
| E — Kanban Snapshots | [kanban.md](kanban.md) | Tracking task state (To Do / Doing / Done) |
| F — Gantt + Milestones | [gantt.md](gantt.md) | Bird's-eye view of the whole timeline with dependencies |

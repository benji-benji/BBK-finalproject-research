# Layout F — Gantt + Milestones + Dependencies

Bird's-eye view. Each row is a task. Time flows left to right. Dependencies shown with arrows.

---

## Gantt Chart

```
                    APR                                                    MAY
        7    8    12   13   14   15   16   17         26   27   28   29         5    6    7
        Mon  Tue  Sat  Sun  Mon  Tue  Wed  Thu        Sat  Sun  Mon  Tue        Wed  Thu  Fri
        ─────────────────────────────────────  RHIW  ─────────────────── CAMP ──────────────
CODE
  ROME       ████ ████ ████                                                              
                       ◆M1                                                               
  MEMIT                     ████ ████                                                    
                                 ◆M2                                                     
  GRACE                                               ████ ████                          
                                                           ◆M4                           

READING
  Core                 ░░░░ ░░░░ ░░░░ ░░░░                                               
  (via code)                                                                             
  Lit Review                          ████ ████                                          
                                           ◆M3                                           

WRITING
  Draft                                                    ████ ████                     
                                                                ◆M5◆M6                   
  Polish                                                             ████ ████           
                                                                          ◆M7            
  Submit                                                                       ◆M8      

████ = active work    ░░░░ = passive/overlapping    ◆ = milestone
```

---

## Dependency Map

```
                    ┌──────────┐
                    │  ROME    │
                    │  [M1]    │
                    └────┬─────┘
                         │
              ┌──────────┴──────────┐
              │                     │
        ┌─────▼─────┐        ┌─────▼─────┐
        │  MEMIT    │        │  GRACE    │
        │  [M2]     │        │  [M4]     │
        └─────┬─────┘        └─────┬─────┘
              │                     │
              │    ┌──────────┐     │
              │    │ READING  │     │
              │    │  [M3]    │     │
              │    └────┬─────┘     │
              │         │           │
              └─────────┼───────────┘
                        │
                  ┌─────▼─────┐
                  │  WRITE    │
                  │ DRAFT     │
                  │ [M5]      │
                  └─────┬─────┘
                        │
                  ┌─────▼─────┐
                  │  SEND TO  │
                  │ DR. CHEN  │
                  │ [M6]      │
                  └─────┬─────┘
                        │
                   ═══CAMP═══
                        │
                  ┌─────▼─────┐
                  │  POLISH   │
                  │ + FEEDBACK│
                  │ [M7]      │
                  └─────┬─────┘
                        │
                  ┌─────▼─────┐
                  │  SUBMIT   │
                  │ [M8]      │
                  └───────────┘
```

---

## Critical Path

The sequence that determines the minimum project duration. Delay any of these and the deadline slips:

```
ROME [M1] → MEMIT [M2] → WRITE [M5] → SEND [M6] → POLISH [M7] → SUBMIT [M8]
  8-13 Apr    14-15 Apr    28-29 Apr     29 Apr       5-6 May       7 May
```

**GRACE [M4] is off the critical path** — it can slip without threatening the deadline, as long as the draft is still sent on 29 Apr. Worst case: report on ROME + MEMIT with GRACE as "in progress."

**READING [M3] is off the critical path** — but feeds into the quality of the lit review section. Ideally done by 17 Apr, but notes can be supplemented during the writing days.

---

## Milestones Checklist

- [ ] **M1** — ROME done, EXP-001 logged (13 Apr)
- [ ] **M2** — MEMIT done, EXP-002 logged (15 Apr)
- [ ] **M3** — Lit review reading complete (17 Apr)
- [ ] **M4** — GRACE done, EXP-003 logged (27 Apr)
- [ ] **M5** — Full draft written (29 Apr)
- [ ] **M6** — Draft sent to Dr. Chen (29 Apr)
- [ ] **M7** — Feedback incorporated (6 May)
- [ ] **M8** — **SUBMITTED** (7 May)

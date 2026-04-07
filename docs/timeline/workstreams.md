# Layout C — Workstreams

Three parallel streams. Each stream has its own tasks, milestones, and checklist. Read each stream independently, then see how they converge at the end.

---

## Stream Overview

```
APR 7         APR 14         APR 21         APR 28         MAY 5      MAY 7
  │              │              │              │              │          │
  ├── CODE ──────┤──────────────┤──────────────┤              │          │
  │ ROME         │ MEMIT        │    (RHIW)    │ GRACE        │          │
  │ ████████████ │ ████████     │              │ ████         │          │
  │         [M1] │    [M2]      │              │ [M4]         │          │
  │              │              │              │              │          │
  │              ├── READING ───┤              │              │          │
  │              │ ████████████ │              │              │          │
  │              │         [M3] │              │              │          │
  │              │              │              │              │          │
  │              │              │              ├── WRITING ───┤──────────┤
  │              │              │              │ ████████████ │ ████     │
  │              │              │              │    [M5][M6]  │ [M7] [M8]│
  │              │              │              │              │          │
```

---

## CODE Stream

Build own implementations of each method. Log experiments with pre/post results.

| Task | Dates | Sessions | Output | Done? |
|---|---|---|---|---|
| ROME code annotation | Tue 8 Apr | 1 full day | Annotated understanding of hooks, tensors, layer manipulation | [ ] |
| ROME implementation + run | Sat-Sun 12-13 Apr | 2 half days | Working edit on GPT-2/CounterFact | [ ] |
| ROME evaluation + log | Sun 13 Apr | (same session) | **EXP-001 logged** | [ ] |
| **[M1] ROME COMPLETE** | **13 Apr** | | | [ ] |
| MEMIT code read + differences from ROME | Mon 14 Apr | 1 full day | Understanding of multi-layer extension | [ ] |
| MEMIT implementation + run + log | Tue 15 Apr | 1 full day | **EXP-002 logged** | [ ] |
| **[M2] MEMIT COMPLETE** | **15 Apr** | | | [ ] |
| GRACE code read + implement | Sat 26 Apr | 1 half day+ | Working adapter-based edit | [ ] |
| GRACE evaluation + log | Sun 27 Apr | 1 half day+ | **EXP-003 logged** | [ ] |
| **[M4] GRACE COMPLETE** | **27 Apr** | | | [ ] |

**Key dependency:** ROME produces the shared utilities (nethook, hooks, evaluation scripts) that MEMIT and GRACE reuse.

---

## READING Stream

Read and take critical notes on all methods for the lit review section.

| Task | Dates | Sessions | Output | Done? |
|---|---|---|---|---|
| ROME paper (already being read via code) | w/c 7 Apr | (overlaps with CODE) | Deep understanding from implementation | [ ] |
| MEMIT paper | w/c 14 Apr | (overlaps with CODE) | Understanding of multi-layer approach | [ ] |
| Knowledge Editing Survey | Wed 16 Apr | ½ day | Taxonomy of all methods, evaluation criteria | [ ] |
| MEND + SERAC papers | Wed 16 Apr | (same session) | Notes on meta-learning and memory-based approaches | [ ] |
| AnyEdit + remaining methods | Thu 17 Apr | ½ day | Notes on newer methods for lit review breadth | [ ] |
| Open Problems in MI + Representation Engineering | Thu 17 Apr | (same session) | Framing for motivating question | [ ] |
| GRACE paper | before 26 Apr | (before implementing) | Ready to implement | [ ] |
| **[M3] READING COMPLETE** | **17 Apr** | | | [ ] |

**Note:** ROME and MEMIT are read through code, not as separate reading sessions. The dedicated reading days (16-17 Apr) are for the methods you're NOT implementing.

---

## WRITING Stream

Draft and submit the proposal document.

| Task | Dates | Sessions | Output | Done? |
|---|---|---|---|---|
| Introduction + Aims & Objectives | Mon 28 Apr | ½ of full day | ~500 words | [ ] |
| Problem description + Literature review | Mon 28 Apr | ½ of full day | ~800 words | [ ] |
| Methodology + Initial results | Tue 29 Apr | ½ of full day | ~700 words + results tables | [ ] |
| Project plan + Diagrams + Risk | Tue 29 Apr | ½ of full day | ~500 words + Gantt + pipeline diagram | [ ] |
| Review, word count, references | Tue 29 Apr evening | — | Complete draft | [ ] |
| **[M5] DRAFT COMPLETE** | **29 Apr** | | | [ ] |
| **[M6] DRAFT SENT TO DR. CHEN** | **29 Apr** | | | [ ] |
| Incorporate feedback | Wed 5 May | ½ day | Revised sections | [ ] |
| Final proofread + formatting | Thu 6 May | ½ day | Submission-ready document | [ ] |
| **[M7] FINAL VERSION READY** | **6 May** | | | [ ] |
| **[M8] SUBMITTED** | **7 May** | | | [ ] |

**Key dependency:** WRITING cannot begin until CODE (M1, M2, M4) and READING (M3) are substantially done. The experimental results and lit review notes are inputs to the proposal text.

---

## How the Streams Converge

```
CODE (experiments)  ──→  EXP-001, 002, 003 logs  ──→  "Initial Results" section
                                                  ──→  "Methodology" section (informed by doing)

READING (papers)    ──→  Lit review notes         ──→  "Problem Description & Relevant Work" section
                                                  ──→  "Introduction" framing

                                                       ↓
                                              WRITING (proposal draft)
                                                       ↓
                                              ✉ Draft to Dr. Chen
                                                       ↓
                                              SUBMIT 7 May
```

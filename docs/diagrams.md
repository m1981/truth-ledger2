# Diagrams — the system as designed, in six cross-sections

A dated snapshot (2026-09-01). Diagrams rot the way review documents
do (CMP-002), so this file is **guarded by capsules**: before editing
it or any file it depicts, run `./scripts/tl2 whisper docs/diagrams.md`
— the capsules watching this file and its sources will speak. A
SUSPECT on any of them means a picture below may be lying.

## 1. The document layers — what may change what

Five genres, one door. Law changes only by dated operator ruling;
reasoning is deliberately never ratified; choreographies say HOW and
are delivered at the moment of action; direction may be wrong without
anything being broken; state is what recomputation cannot give back.

```mermaid
flowchart TB
    subgraph LAW["LAW - changes only by operator ruling"]
        SCOPE["docs/scope.md<br/>5 refusals + declared ceiling"]
        CONST["docs/governance/constitution.md<br/>6 entry rules C1-C6, priced"]
    end
    subgraph REASONING["REASONING - never ratified"]
        CAND["docs/candidates.md<br/>F-1..F-13 + falsifier clause"]
    end
    subgraph CHOREO["CHOREOGRAPHIES - checklists, capsule-guarded"]
        RUNB["docs/runbooks/<br/>purchase, loop, session,<br/>consumer, release, verifier"]
    end
    subgraph DIRECTION["DIRECTION - non-normative"]
        MEMO["docs/market-memo.md<br/>who pays, measured order"]
    end
    subgraph STATE["STATE - per installation"]
        CMPS["docs/complaints/<br/>CMP register - the only door"]
        REGS["docs/registers/prefixes.md"]
        METRICS["docs/governance/gate-metrics.md"]
        CAPS["capsules.jsonl<br/>criticality.tiers"]
    end
    HARM(["harm event<br/>anyone's, dated, anchored"]) --> CMPS
    CMPS -- "C1: buys one mechanism<br/>operator countersigns" --> MECH["mechanism"]
    CMPS -- "falsifier clause:<br/>fits no row" --> CAND
    SCOPE -. "is a wall for" .-> MECH
    CONST -- "C2 + C3 gate the birth of" --> MECH
    MEMO -. "steers attention,<br/>buys NOTHING" .-> CMPS
    MECH -- "born with row" --> METRICS
    CAND -. "sketches, never builds" .-> MECH
    RUNB -. "choreographs the act,<br/>never authorizes it" .-> MECH
```

## 2. The mechanism lifecycle — how anything gets in, lives, and dies

Every arrow below has happened at least once in this repository's own
history (examples on the edges).

```mermaid
stateDiagram-v2
    [*] --> Complaint: harm event filed (CMP-NNN)
    Complaint --> Bought: operator countersigns<br/>one complaint = one mechanism
    Complaint --> Declined: no mechanism can exist<br/>(CMP-003 - cross-repo dead zone)
    Bought --> Witnessed: C2 both halves -<br/>seeded red AND corpus test
    Witnessed --> Live: C3 - metric row,<br/>probation date
    Live --> Live: catches / false alarms / misses<br/>counted in gate-metrics
    Live --> Retired: probation expires<br/>with empty record
    Live --> Absorbed: redundant with law<br/>(F-6 into C2/C3)
    Retired --> [*]: row stays, status-changed,<br/>ids never reused (C5)
```

## 3. Engine and installations — where state lives

```mermaid
flowchart LR
    subgraph ENGINE["ENGINE - stateless, tagged releases only"]
        TL2["scripts/tl2<br/>verbs: capsule, check, vacuity, whisper, retract,<br/>mirror, ready, verify, lint"]
        DEVGATES["engine-dev gates<br/>(commit-msg hook)<br/>never install"]
    end
    subgraph INST1["INSTALLATION #1 - this repo (dogfood)"]
        S1["capsules.jsonl<br/>gate-metrics.md<br/>complaints/"]
    end
    subgraph INSTN["INSTALLATION #2 - kuchnie @ v0.1.1<br/>(and every future #N)"]
        SN["its own state<br/>never leaves (R5)"]
    end
    TL2 -- "same public surface (C4)<br/>no private doors" --> S1
    TL2 -- "pinned tagged release" --> SN
    SEP["F-7 separation canary - BUILT<br/>scripts/separation-canary"] -->|"proves, before each tag"| INSTN
    PREFIX["prefix register"] -- "one prefix per installation (C5)" --> INSTN
```

## 4. Capsule states — a projection, never a stored status

Nothing below is written anywhere; `check` recomputes it from
`capsules.jsonl` plus git at every read (architecture §2).

```mermaid
stateDiagram-v2
    [*] --> Filed: tl2 capsule - sentence + command<br/>+ output sha256 + anchor + watched paths
    Filed --> OK: anchor resolves, watched paths<br/>unchanged, re-run hash matches
    Filed --> SUSPECT: watched path changed since anchor<br/>(committed OR dirty tree)
    Filed --> SUSPECT: anchor unresolvable -<br/>FAIL-CLOSED (history rewrite)
    Filed --> STALE: re-run output hash differs,<br/>or evidence command now fails
    OK --> SUSPECT: next edit of a watched path
    OK --> RETRACTED: tl2 retract - tombstone<br/>with cause + successor (CMP-017)
    SUSPECT --> RETRACTED: the maintenance loop -<br/>retract the outdated, file the successor
    RETRACTED --> [*]: reported by check,<br/>never reddens; whisper falls silent
    note right of SUSPECT
        named dead zones (arch. §2):
        capsule integrity unenforced;
        watched-set adequacy is the
        author's; time and the external
        world are outside every watched set
    end note
```

## 5. The distrust map — DO-178-shaped failure classes, candidates, and their measured evidence

Evidence weights are from the 2026-09-01 harvest of 45 anchored harm
events (v1 + its consumer); BUILT marks a first instance existing.

```mermaid
flowchart LR
    subgraph DISTRUSTS["how projects deceive themselves"]
        D1["built the wrong thing, correctly"]
        D2["code does more than was written"]
        D3["the test passed and proved nothing"]
        D4["the author cannot see own blind spots"]
        D5["what shipped is not what was checked"]
        D6["uniform rigor is fake rigor"]
        D7["dogfood leaked into the product"]
        D8["rule absent at the moment of acting"]
        D9["two sessions, one tree"]
        D10["the guard itself died unseen"]
        D11["the decision changed, nothing followed"]
        D12["nobody could say what was ready"]
        D13["ceremony ate the subscription"]
    end
    D1 --> F1["F-1 spec lint (proposer) - BUILT<br/>evidence: 2"]
    D2 --> F2["F-2 traceability mirror - BUILT<br/>evidence: 5"]
    D3 --> F3["F-3 vacuity - BUILT<br/>evidence: 14 - dominant"]
    D4 --> F4["F-4 fresh verifier - BUILT<br/>evidence: 7"]
    D5 --> F5["F-5 capsules - BUILT<br/>evidence: 3"]
    D6 --> F6["F-6 criticality tiers - BUILT<br/>evidence: 4, incl. 555/630 false alarms"]
    D7 --> F7["F-7 separation canary - BUILT<br/>evidence: 4"]
    D8 --> F8["F-8 whisper - BUILT<br/>evidence: 2, consumer-validated"]
    D9 --> F9["F-9 concurrency discipline<br/>evidence: 3"]
    D10 --> F10["F-10 guard liveness<br/>born of CMP-013/014"]
    D11 --> F11["F-11 decision propagation<br/>born of CMP-016"]
    D12 --> F12["F-12 work queue - BUILT<br/>evidence: CMP-011 cost line"]
    D13 --> F13["F-13 budget sense<br/>evidence: 555/630 false stalings"]
    LAW2["the lying tool - constitution C2/C3,<br/>law, not a candidate"]
```

## 6. The execution flow — who calls what, when, and with what mind

Three kinds of executor, one honest split: **M** = machine
(deterministic verb or hook; same input, same answer), **LLM** = model
judgment (proposes, orchestrates, never decides alone), **H** = human
(rules, countersigns, disposes). The pattern everywhere: M extracts
and gates shape, LLM judges and drafts, H decides — architecture §6 in
motion.

| Stage | Trigger (who calls) | What runs | Mind | Blocks? |
|---|---|---|---|---|
| Session open | harness auto-loads CLAUDE.md | read order → `tl2 ready` | M lists, LLM picks | no |
| Before any edit | agent, by runbook | `tl2 whisper <paths>` (+ tiers tags/budget) | M speaks, LLM heeds | no (fail-open) |
| The edit itself | agent | code/spec/doc work | LLM | — |
| New promise in a spec | agent | `lint --brief` → fresh session judges → `lint --intake` → operator accepts into spec | M → LLM → M → H | intake gates shape only |
| New/changed test | agent | `tl2 vacuity` (PROVEN / GREEN-ON-BOTH / INCONCLUSIVE) | M verdicts | advisory exits |
| Sentence worth trusting | agent | `tl2 capsule` files the receipt | M | no |
| Doubted sentence | agent, by verifier runbook criteria | `verify --brief` → fresh session re-derives → `verify --intake` → operator disposes | M → LLM → M → H | intake gates shape; verdict never |
| Commit | **git calls the hook itself** | commit-msg gate (≥2 diacritic words) | M | **yes** |
| Watched source changed | agent, by maintenance-loop runbook | commit → successor capsule → `retract --successor` → `check` green | LLM orchestrates, M executes each step | check exit informs |
| Any time | anyone | `tl2 check` — status as a projection | M | exit 1 informs |
| Push (consumer) | **git calls pre-push itself** | the battery (tests, golden, health sweeps) | M | **yes** |
| Release | agent, by release runbook | separation-canary → tag → `push --follow-tags` → re-pin installations | M canary **blocks**; H words the tag | **yes** |
| Harm observed | anyone | CMP filed (LLM drafts) → operator countersigns purchase → C2 witnesses → C3 row | LLM → H → M | C1: nothing enters without it |
| Decision needed | agent, by rule 10 | batched package, kind-labeled, ONE question pending | LLM prepares, H rules | work waits only on genuine H items |

```mermaid
sequenceDiagram
    participant H as Operator (H)
    participant A as Agent (LLM)
    participant M as tl2 / hooks (M)
    A->>M: tl2 ready
    M-->>A: queue (complaints, probations, suspects)
    A->>M: tl2 whisper <paths>
    M-->>A: guards watching them (tagged by tier)
    A->>A: edit work
    A->>M: git commit
    M-->>A: commit-msg gate (blocks or passes)
    A->>M: successor capsule, retract --successor, check
    M-->>A: check green
    A->>H: decision package (kinds, one question pending)
    H-->>A: one word (+ reservations by address)
    A->>M: git push
    M-->>A: battery / canary (blocks or passes)
```

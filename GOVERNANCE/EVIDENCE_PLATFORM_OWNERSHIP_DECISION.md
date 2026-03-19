# EVIDENCE PLATFORM — OWNERSHIP & INDEPENDENCE DECISION
## Should Evidence Platform Be a TKG Subsidiary or a Holding-Level Asset?
**Version 1.0 | March 2026 | Board Decision Document**

---

## THE QUESTION

The Master Architecture says Evidence Platform is "transitioning to independence" from Waraqa. But it now serves ALL groups — not just TKG:

| Group | How It Uses Evidence Platform |
|-------|------------------------------|
| **TKG** | Knowledge graph, PubHelper integration, Live Guidelines, CME delivery, journal content distribution |
| **TVG** | MNC criteria for Integra RCM coding, VBH Co outcome benchmarks, Nexus MGA benefit design |
| **THDG** | Point-of-care clinical decision support for Welunion clinicians |
| **TTG** | CII Layer 1 foundation, knowledge graph feeds AI reasoning |

It also hosts the **Learning Passport** (every physician's career record) and the **Physician Reputation Platform** content infrastructure.

## THE OPTIONS

| Option | Description | Pros | Cons |
|--------|-------------|------|------|
| **A: TKG Subsidiary** | Evidence Platform stays under TKG with own P&L | Clean group structure; TKG "owns" knowledge | TVG and THDG usage feels like buying from another group; pricing friction |
| **B: Holding-Level Asset** (like CII) | Evidence Platform moves to Holding level, alongside TTG-CII | Reflects reality that it serves all groups; Holding controls pricing; no inter-group friction | TKG loses its "digital product"; organizational change |
| **C: Hybrid — TKG operates, Holding governs** | Evidence Platform stays in TKG operationally but Holding sets access rules and pricing for cross-group usage | Best of both: TKG knowledge expertise operates it; Holding ensures all groups get fair access | Governance complexity |

## RECOMMENDATION: OPTION C (HYBRID)

| Dimension | Decision |
|-----------|---------|
| **Operational home** | TKG — Evidence Platform team stays in Knowledge Group |
| **Content authority** | TKG — Waraqa, PubHelper, Nama CRO feed content; TKG editorial team curates |
| **Technology infrastructure** | TTG — Evidence Platform runs on CII shared rails (NLP, cloud, knowledge graph DB) |
| **Cross-group access** | Holding governs — all groups access Evidence Platform at cost-recovery; no markup for TVG/THDG |
| **Revenue** | Evidence Platform collects subscription revenue; shares per TECHNOLOGY_OWNERSHIP_ARCHITECTURE model |
| **Learning Passport** | Holding-level asset — physician identity is ecosystem-wide, not TKG-specific |
| **MNC Criteria** | Joint TKG-TVG governance — content from TKG, commercial use by TVG |

### Why Hybrid Is Right

1. **TKG has the domain expertise** to curate clinical knowledge — moving it to Holding would lose this
2. **Holding must govern cross-group access** — otherwise TVG has to "buy" from TKG, creating internal friction
3. **The physician identity (SSO + Learning Passport)** is ecosystem-level — it cannot belong to one group
4. **CII provides the infrastructure** — Evidence Platform doesn't need its own cloud or NLP team

### What This Means Practically

```
EVIDENCE PLATFORM
    │
    ├── REPORTS TO: TKG Group Lead (operational)
    ├── GOVERNED BY: Holding (cross-group access, pricing, physician identity)
    ├── RUNS ON: CII shared infrastructure (TTG)
    ├── FED BY: Waraqa + PubHelper + Nama CRO + Nama Bio (TKG content pipeline)
    ├── SERVES: All groups equally (no inter-group markup)
    └── OWNS: Knowledge product (Live Guidelines, MNC engine, CME delivery)
         DOES NOT OWN: Physician identity (Holding), AI/NLP engine (CII), cloud (CII)
```

---

## COMPARISON WITH CII

| Dimension | Evidence Platform | CII |
|-----------|------------------|-----|
| **Nature** | Knowledge product with users | AI infrastructure without direct users |
| **Operational home** | TKG (content expertise) | TTG / Holding (technology) |
| **Governance** | Hybrid (TKG operates, Holding governs access) | 100% Holding |
| **External revenue** | Yes (physician/institutional subscriptions) | Yes (hospital AI licensing) |
| **Why different from CII** | Has a user-facing product, content curation, editorial team — these are TKG capabilities | Pure infrastructure — no editorial or content function |

---

*Status: Board Decision Document — requires Founder approval*
*Aligned to: TECHNOLOGY_OWNERSHIP_ARCHITECTURE.md*

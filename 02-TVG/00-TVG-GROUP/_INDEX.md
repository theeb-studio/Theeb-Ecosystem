# TVG — THEEB VALUE GROUP INDEX
**Version 2.0 | March 2026**

> Reference: `00-TAK-ROOT/MASTER-ARCHITECTURE.md` — Part Three

---

## Group Identity
TVG builds the **financial, data, and risk infrastructure** that makes value-based healthcare economically viable across Saudi Arabia and the Gulf. TVG does not deliver clinical care — it builds the operating system above the clinical layer.

> TVG is to healthcare what SWIFT is to banking: the infrastructure layer that everyone in the ecosystem needs, that no single participant can build alone, and that becomes more valuable as more participants join.

---

## The Intelligence & Infrastructure Layer
All TVG companies are **applications built on top** of a shared intelligence and infrastructure layer — a common data stack, analytics engine, and integration architecture.

```
┌──────────────────────────────────────────────────────────┐
│         TVG INTELLIGENCE & INFRASTRUCTURE LAYER           │
│  Claims · Cost benchmarks · Risk models · PROMs          │
│  DRG analytics · Outcome prediction · Contract engine    │
└──────────┬─────────────────────┬────────────────────────┘
           ↓                     ↓                    ↓
      TVG-01                TVG-02               TVG-03
   Integra RCM            MGA Company         VBH Company
```

---

## Current Entities (3)

| Code | Entity | Layer | Status | Folder |
|------|--------|-------|--------|--------|
| TVG-01 | Integra RCM | Layer 1 — Revenue Infrastructure | Active | `01-TVG-Integra-RCM/` |
| TVG-02 | MGA Company | Layer 2 — Risk Infrastructure | Being established | `02-TVG-MGA/` |
| TVG-03 | Value-Based Healthcare Company | Layer 3+4 — Intelligence + Contracting | Design/build | `03-TVG-Majour/` |

> **TVG-03 Note:** Previously referred to as "Majour" in older documents. The correct name is Value-Based Healthcare Company. Folder name retained for continuity.

---

## Four-Layer Architecture

```
┌─────────────────────────────────────────────────────────┐
│  LAYER 4 — OUTCOME-BASED CONTRACTING PLATFORMS          │
│  Bundled payments · Shared savings · VBP contracts       │
├─────────────────────────────────────────────────────────┤
│  LAYER 3 — VALUE INTELLIGENCE                           │
│  Cost analytics · PROMs · Population health · AR-DRG    │
├─────────────────────────────────────────────────────────┤
│  LAYER 2 — RISK INFRASTRUCTURE                          │
│  MGA · Underwriting analytics · Payer-provider risk     │
├─────────────────────────────────────────────────────────┤
│  LAYER 1 — REVENUE INFRASTRUCTURE                       │
│  RCM · AI coding · Claims · Denial analytics            │
└─────────────────────────────────────────────────────────┘
         ↑ DATA FLOWS UP · CONTRACTS FLOW DOWN ↑
```

---

## Cross-Group Connections
| Connection | From TVG | To |
|-----------|----------|----|
| RCM embedded in provider billing | Integra RCM | THDG Welunion |
| CME + Malpractice insurance bundle | MGA Company | TKG Nama Academy |
| PROMs and outcome data | VBH Company | THDG clinical network |
| Pharmacy analytics | Layer 3 intelligence | THDG TAP Pharmacy data |

---

## Operational Layer
- Integra RCM → `Dropbox/Server/` (active operations)
- MGA → Pre-operational (SAMA licensing phase)
- VBH Company → Pre-operational (design phase)

## Rule: Strategy here, Operations in Server.

---

## Orchestration Principle
This group's entities do not operate in isolation. Any project may activate entities
from this group alongside entities from TKG, TVG, or THDG simultaneously.
Entity independence is preserved. Operational interoperability is by design.
> Full model: `00-TAK-ROOT/ECOSYSTEM-ORCHESTRATION-MODEL.md`

# THDG — THEEB HEALTH CARE DELIVERY GROUP INDEX
**Version 2.0 | March 2026**

> Reference: `00-TAK-ROOT/MASTER-ARCHITECTURE.md` — Part Four

---

## Group Identity
THDG delivers **actual healthcare services** to patients and communities. It is the clinical operations arm of the Theeb Ecosystem — the point where strategy meets the patient.

---

## Current Structure

### Flagship (New)
| Code | Entity | Role | Status |
|------|--------|------|--------|
| THDG-WEL | **Welunion** | Primary platform — Technology + MSO + Clinic Network | In formation |

### Operating Companies
| Code | Entity | Role | Status |
|------|--------|------|--------|
| THDG-IHH | Integrative Health | Existing delivery company → transitioning to Welunion subsidiary | Active |
| THDG-UCL | Union Clinics | Clinic network asset → becomes Welunion clinic network layer | Concept → Build |
| THDG-TAP | TAP Pharmacy | In-clinic dispensing network | Active (2 locations) |

### Shared Specialty Platform
| Code | Entity | Role | Status |
|------|--------|------|--------|
| THDG-COC | **CoClinics** | Shared-space specialist clinic model — intermediate complexity layer | Active |

### Independent Clinical Ventures
| Code | Entity | Model | Status |
|------|--------|-------|--------|
| THDG-CLV-01 | Mental Health — Pediatric Co-Clinic | Flexible ownership | Active |
| THDG-CLV-02 | Mental Health — Adult Clinic | Flexible ownership | Active (Laban, Riyadh) |
| THDG-CLV-03 | **Dawali Vascular Centers** | MSO partnership (physicians own brand) | Active (3 branches → 13) |
| THDG-CLV | [Future specialty ventures] | Flexible ownership | Pipeline |

---

## Welunion Architecture (Flagship)

```
WELUNION
├── Technology Layer (WellTech)
│   EHR · Patient apps · Telemedicine · FHIR integration · AI tools
├── MSO Layer (WellCare)
│   MOH licenses · Insurance credentialing · HR · Compliance · Shared services
└── Clinic Network (WellClinics)
    Physical + virtual clinics · 7 revenue divisions · National expansion
    ← absorbs Union Clinics network and Integrative Health operations
```

### 7 Revenue Divisions (under Welunion)
1. Urgent Care
2. Home Care
3. Virtual Care
4. Mental Health
5. Chronic Disease Management (CDM)
6. Men's Health
7. Doula Program (Maternal Care)

---

## Integrative Health → Welunion Transition
Integrative Health currently operates independently.
It will become a **subsidiary / division / operational unit** of Welunion as Welunion scales.
Current IHH services (Urgent Care, Home Care, Mother & Baby, Medical Logistics) will be absorbed into the Welunion service architecture.

---

## Independent Clinical Ventures — Ownership Framework
Clinical ventures are NOT automatically part of Integrative Health or Welunion.
Ownership may be:
- Fully owned by THDG
- Partially owned (JV with physician or clinical partner)
- Partner-operated (partner owns + operates; Welunion provides MSO)
- Externally owned but managed (external owner; Welunion provides services)

---

## Holding
- **IHN Holding** → `Dropbox/Server/IHN Holding/` (corporate & legal for THDG group)

## Cross-Group Connections
| Connection | THDG Entity | Goes To |
|-----------|-------------|---------|
| Claims and coding data | Welunion / IHH / CoClinics / Dawali | TVG Integra RCM |
| Patient PROMs + procedure outcomes | Welunion / CoClinics / Dawali | TVG VBH Company |
| Prescription data | TAP Pharmacy | TVG Layer 3 analytics |
| CME needs for physicians | Welunion / CoClinics / Dawali medical staff | TKG Nama Academy |
| Clinical guidelines | Welunion / Dawali care pathways | TKG Evidence Platform |
| Research patients | Welunion / Dawali patient base | TKG Nama CRO |
| Referral integration | Welunion ↔ CoClinics ↔ Dawali | THDG-CLV-INT-Service-Integration-Map.md |

## Rule: Strategy here, Operations in Server.

---

## Orchestration Principle
This group's entities do not operate in isolation. Any project may activate entities
from this group alongside entities from TKG, TVG, or THDG simultaneously.
Entity independence is preserved. Operational interoperability is by design.
> Full model: `00-TAK-ROOT/ECOSYSTEM-ORCHESTRATION-MODEL.md`

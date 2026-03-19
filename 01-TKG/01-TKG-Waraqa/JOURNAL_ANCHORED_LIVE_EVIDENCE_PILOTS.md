# JOURNAL-ANCHORED LIVE EVIDENCE PILOTS
## Three Journals × Three Pilots × One Live Evidence Pipeline
**Entity: TKG-01 (Waraqa) | Powered by: PubHelper (TKG-06) + Evidence Platform (TKG-05)**
**Aligned to: THEEB_ECOSYSTEM_V2_2026.md | Live Guidelines Platform Architecture**
**Version 1.0 | March 2026 | Confidential**

---

> **CORE IDEA:** Every article published in a Waraqa journal becomes a **structured evidence asset** — not just a PDF. Three owned journals become three pilot entry points for the Live Guidelines Platform. Each journal has a "Powered by PubHelper" submission track. Each publication auto-feeds into the central Evidence Repository. Each guideline page is continuously updated. This transforms Waraqa from a publishing house into a **live evidence infrastructure**.

---

## 1. THE THREE JOURNALS

| Journal | Code | Scope | Target Audience | Pilot Focus |
|---------|------|-------|-----------------|-------------|
| **Saudi Journal of Emergency Medicine (SJEM)** | WAR-J1 | Emergency medicine, EMS, critical care | EM physicians, EMS teams, ED departments | Acute clinical pathways |
| **Preventive & Population Health Journal (PPHJ)** | WAR-J2 | Population health, preventive medicine, occupational health, epidemiology, VBH | Public health professionals, policymakers, occupational health | Population-level interventions and VBP |
| **International Journal of Medicine in Developing Countries (IJMDC)** | WAR-J3 | General medicine in developing countries | Residents, early-career clinicians, students | Pragmatic guidelines for resource-limited settings |

---

## 2. UNIFIED ARCHITECTURE

```
┌─────────────────────────────────────────────────────────────────────────┐
│           JOURNAL-ANCHORED LIVE EVIDENCE ARCHITECTURE                    │
│                                                                          │
│  CLINICAL QUESTIONS                                                      │
│  (Welunion clinicians, society experts, community groups, residents)     │
│         │                                                                │
│         ▼                                                                │
│  ┌─────────────────────────────────────────────┐                        │
│  │              PUBHELPER (TKG-06)               │                        │
│  │         AI-Powered Research Engine            │                        │
│  │                                               │                        │
│  │  Question → PICO → Protocol → Data →          │                        │
│  │  Analysis → Manuscript → Submission            │                        │
│  └──────────────────┬────────────────────────────┘                        │
│                     │                                                    │
│         ┌───────────┼───────────┐                                        │
│         ▼           ▼           ▼                                        │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐                                │
│  │   SJEM   │ │   PPHJ   │ │  IJMDC   │                                │
│  │ (WAR-J1) │ │ (WAR-J2) │ │ (WAR-J3) │                                │
│  │          │ │          │ │          │                                │
│  │ "Powered │ │ "Powered │ │ "Powered │                                │
│  │  by Pub- │ │  by Pub- │ │  by Pub- │                                │
│  │  helper" │ │  helper" │ │  helper" │                                │
│  │  fast-   │ │  fast-   │ │  fast-   │                                │
│  │  track   │ │  track   │ │  track   │                                │
│  └────┬─────┘ └────┬─────┘ └────┬─────┘                                │
│       │            │            │                                        │
│       └────────────┼────────────┘                                        │
│                    ▼                                                     │
│  ┌─────────────────────────────────────────────┐                        │
│  │       CENTRAL EVIDENCE REPOSITORY            │                        │
│  │       (Evidence Platform – TKG-05)           │                        │
│  │                                               │                        │
│  │  Ingests:                                     │                        │
│  │  • PubHelper project metadata + outputs       │                        │
│  │  • Final published articles (all 3 journals)  │                        │
│  │  • External evidence (PubMed, Cochrane, etc.) │                        │
│  │                                               │                        │
│  │  Builds:                                      │                        │
│  │  • Disease/condition-centric Live Guidelines   │                        │
│  │  • Theme-centric guideline pages              │                        │
│  │  • Medical Necessity Criteria (CHI-ready)     │                        │
│  └──────────────────┬────────────────────────────┘                        │
│                     │                                                    │
│         ┌───────────┼───────────┐                                        │
│         ▼           ▼           ▼                                        │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐                                │
│  │POINT-OF- │ │ PAYER &  │ │ACADEMIC &│                                │
│  │CARE      │ │REGULATOR │ │PUBLISHING│                                │
│  │(THDG)    │ │(TVG)     │ │(TKG)     │                                │
│  │          │ │          │ │          │                                │
│  │Welunion  │ │CHI, VBH  │ │Journals  │                                │
│  │ED, clinics│ │Co, MGA   │ │auto-link │                                │
│  │          │ │          │ │back      │                                │
│  └──────────┘ └──────────┘ └──────────┘                                │
└─────────────────────────────────────────────────────────────────────────┘
```

---

## 3. PILOT 1 — SJEM: EMERGENCY MEDICINE

### Steering Group
Saudi Emergency Medicine Society + SJEM Editorial Board + Saudi Red Crescent Authority + major ED departments

### Priority Clinical Questions (10-15)

| # | Clinical Question | Study Type | PubHelper Pipeline |
|---|------------------|-----------|-------------------|
| 1 | Chest pain pathway in Saudi ED: optimal triage protocol | Systematic review + local observational | SR/MA + Welunion ED data |
| 2 | Sepsis recognition: early treatment bundle compliance in KSA | Meta-analysis + registry study | Global MA + Saudi registry |
| 3 | Pediatric head trauma: imaging decision rules in Saudi context | Systematic review | SR with local applicability analysis |
| 4 | Stroke pathway: door-to-needle times in Saudi EDs | Observational + guideline | Multi-center audit + guideline |
| 5 | ACS management: pre-hospital vs ED thrombolysis outcomes | Meta-analysis | Global + GCC data synthesis |
| 6 | Trauma activation criteria for Saudi Red Crescent | Guideline development | Expert consensus + evidence review |
| 7 | Procedural sedation safety in Saudi EDs | Systematic review | SR + local adverse event data |
| 8 | Overcrowding metrics and interventions | Systematic review | Global SR + Saudi hospital data |
| 9 | Point-of-care ultrasound protocols | Guideline | Evidence-based guideline + training |
| 10 | Heat-related illness during Hajj/Umrah | Local observational + guideline | Saudi-specific guideline |

### Workflow

```
STEP 1: Steering group approves 10 priority questions
STEP 2: PubHelper assigns team of 10 EM physicians per topic
STEP 3: Each team conducts SR/MA via PubHelper's 8 modules
STEP 4: SJEM fast-tracks PubHelper-originated evidence syntheses
STEP 5: Each article published with structured evidence tables
STEP 6: Evidence Repository auto-ingests → Live Guideline Page built
STEP 7: MNC field populated (draft criteria for CHI)
STEP 8: Point-of-care view available on sjemed.com + Evidence Platform
STEP 9: Welunion ED physicians access real-time guidance
```

### Live Guideline Page Structure (Per Topic)

```
┌────────────────────────────────────────────────────┐
│  LIVE GUIDELINE: Chest Pain in Saudi ED             │
│  Last updated: [auto-timestamp]                     │
│  Version: 3.2 | Changes since v3.1: [diff view]    │
│                                                      │
│  CLINICAL QUESTION (PICO)                           │
│  P: Adult patients presenting to Saudi ED with      │
│     acute chest pain                                │
│  I: Structured triage protocol (HEART score)        │
│  C: Standard triage (clinical judgment alone)       │
│  O: Missed ACS rate, ED length of stay, cost        │
│                                                      │
│  EVIDENCE SUMMARY                                    │
│  Global: 14 studies (3 RCTs, 8 cohort, 3 SR)       │
│  Local: 2 studies (Welunion ED data, KFSHI audit)   │
│  Evidence Level: Moderate (Grade B)                 │
│                                                      │
│  RECOMMENDATIONS                                    │
│  1. Use HEART score for risk stratification [B]      │
│  2. Serial troponin at 0h and 3h [A]                 │
│  3. Early discharge protocol for low-risk [B]        │
│                                                      │
│  MEDICAL NECESSITY CRITERIA                          │
│  ✅ Necessary: Troponin, ECG, chest X-ray            │
│  ⚠️ Conditional: CT angiography (high-risk only)     │
│  ❌ Not recommended: Routine stress testing in ED     │
│                                                      │
│  SOURCE ARTICLES                                     │
│  • [SJEM-2026-042] Saudi HEART Score Validation      │
│  • [Cochrane-2025] Chest Pain Triage SR              │
│  • + 12 linked studies                               │
│                                                      │
│  POWERED BY: PubHelper | Evidence Platform | Waraqa  │
└────────────────────────────────────────────────────┘
```

---

## 4. PILOT 2 — PPHJ: PREVENTIVE & POPULATION HEALTH

### Steering Group
Public health institutions + occupational health bodies + MOH regional offices + PPHJ editorial board

### Pilot Theme: **"Diabetes Prevention in Working-Age Adults"**

| # | Research Stream | Study Type | VBP Connection |
|---|----------------|-----------|----------------|
| 1 | Workplace diabetes screening effectiveness in KSA | Systematic review | Employer health benefit design (Nexus MGA) |
| 2 | Cost-effectiveness of community lifestyle interventions | Health economics analysis | VBH Co bundled payment pricing |
| 3 | Occupational risk factors for T2DM in Saudi workforce | Epidemiological review | Occupational health policy |
| 4 | Digital health interventions for diabetes prevention | Meta-analysis | Welunion virtual care CDM program |
| 5 | Screening biomarker thresholds in Saudi populations | Local validation study | MNC criteria for screening coverage |

### Value-Added Track Integration

This pilot directly feeds TVG's Value-Added Track:

```
PPHJ publishes diabetes prevention evidence
    → Live Guideline: "Diabetes Prevention in Working-Age Adults"
    → MNC Criteria: screening intervals, covered interventions
    → VBH Co: designs diabetes management VBC bundle (one of CHI's 7)
    → Integra RCM: DRG coding for diabetes-related encounters
    → Nexus MGA: employer health benefit package for diabetes prevention
    → Welunion: CDM program design based on evidence
```

---

## 5. PILOT 3 — IJMDC: DEVELOPING COUNTRIES / RESIDENT TRACK

### Design: Resident-Centered Evidence Program

| Component | Description |
|-----------|-------------|
| **Resident Evidence Track** | Residents and students submit clinical questions via PubHelper → guided through the full research pipeline → publish in IJMDC |
| **Teaching Integration** | Evidence creation integrated into training: question → protocol → data → manuscript = learning AND output |
| **Context Tags** | Live Guideline pages tagged: "low-resource", "limited labs/imaging", "rural setting" |
| **Pragmatic Algorithms** | Stepwise clinical algorithms for smaller hospitals and rural settings |

### Pilot Theme: **"Sepsis Management in Resource-Limited Hospitals"**

```
STEP 1: Resident group identifies 5 key sepsis questions
        relevant to district/rural hospitals
STEP 2: PubHelper guides residents through SR/MA methodology
STEP 3: Each resident team produces one structured evidence output
STEP 4: IJMDC publishes with "Resident Evidence Track" designation
STEP 5: Live Guideline page built with context-appropriate recommendations
STEP 6: Practice aids generated (pocket cards, algorithms) for distribution
```

### Global Positioning
IJMDC becomes a **global hub** for real-world, developing-country evidence — exportable to international knowledge bases and useful for VBP projects in low- and middle-income countries.

---

## 6. DATA STRUCTURES & SCHEMAS

### Article Evidence Schema (Common Across All 3 Journals)

```json
{
  "article_id": "SJEM-2026-042",
  "journal": "SJEM",
  "pubhelper_project_id": "PH-2026-EM-007",
  "title": "Validation of HEART Score in Saudi Emergency Departments",
  "pico": {
    "population": "Adult patients with acute chest pain in Saudi EDs",
    "intervention": "HEART score-based triage",
    "comparator": "Standard clinical judgment triage",
    "outcome": "Missed ACS rate, ED LOS, 30-day MACE"
  },
  "study_type": "prospective_cohort",
  "evidence_level": 3,
  "strength_of_recommendation": "B",
  "grading_score": 17,
  "saudi_relevance": "high",
  "conditions_icd10": ["I20", "I21", "R07.9"],
  "linked_guidelines": ["LG-EM-CHEST-PAIN-001"],
  "linked_mnc": ["MNC-EM-CHEST-PAIN-001"],
  "publication_date": "2026-09-15",
  "last_evidence_update": "2026-09-15",
  "status": "published_indexed"
}
```

### Live Guideline Schema

```json
{
  "guideline_id": "LG-EM-CHEST-PAIN-001",
  "title": "Chest Pain Management in Saudi Emergency Departments",
  "version": "3.2",
  "last_updated": "2026-09-15",
  "update_trigger": "New article SJEM-2026-042 published",
  "specialty": "emergency_medicine",
  "conditions_icd10": ["I20", "I21", "R07.9"],
  "evidence_sources": {
    "global_studies": 14,
    "local_studies": 2,
    "total_patients": 28450
  },
  "recommendations": [
    {
      "text": "Use HEART score for risk stratification",
      "grade": "B",
      "evidence_level": 3,
      "sources": ["SJEM-2026-042", "COCHRANE-2025-1234"]
    }
  ],
  "mnc_criteria": {
    "necessary": ["troponin", "ecg", "chest_xray"],
    "conditional": ["ct_angiography"],
    "not_recommended": ["routine_stress_test_in_ed"]
  },
  "steering_group": "SJEM EM Evidence Steering Group",
  "next_review": "2027-03-15"
}
```

### Event-Driven Update Pipeline

```
EVENT: PubHelper project PH-2026-EM-007 completed
    → TRIGGER: Article submitted to SJEM
    → EVENT: Article accepted and published (SJEM-2026-042)
    → TRIGGER: Evidence Repository ingests structured metadata
    → EVENT: Linked guideline LG-EM-CHEST-PAIN-001 flagged for update
    → TRIGGER: Evidence Fusion Layer re-evaluates evidence map
    → EVENT: Guideline version incremented (3.1 → 3.2)
    → TRIGGER: MNC criteria recalculated
    → EVENT: Point-of-care interface refreshed
    → TRIGGER: Notification to steering group for review
    → EVENT: CME credit generated for contributing physicians
```

---

## 7. PILOT EVALUATION METRICS

### Evidence Freshness

| Metric | Target |
|--------|--------|
| Average time from PubHelper completion → journal publication | <90 days |
| Average time from publication → Live Guideline update | <7 days (automated) |
| % of guideline pages updated in last 12 months | >80% |
| Oldest unreviewed guideline page | <18 months |

### Usage & Adoption

| Metric | Year 1 Target |
|--------|---------------|
| Live Guideline page views (clinician) | 5,000/month |
| Point-of-care queries | 1,000/month |
| MNC criteria downloads (CHI/payer) | 200/quarter |
| Clinicians citing Live Guidelines in practice | 500+ |

### Research Impact

| Metric | Year 1 Target |
|--------|---------------|
| PubHelper projects feeding journals | 30 (10 per journal) |
| Articles published via PubHelper track | 20+ |
| New evidence nodes added to knowledge graph | 500+ |
| Systematic reviews/meta-analyses completed | 15+ |

### Ecosystem Integration

| Metric | Target |
|--------|--------|
| MNC criteria derived from Live Guidelines | 20-30 |
| VBC bundle designs informed by pilot evidence | 2+ (diabetes, EM) |
| Integra RCM coding aligned with MNC criteria | Active |
| Welunion care pathways updated from Live Guidelines | 5+ |

---

## 8. IMPLEMENTATION TIMELINE

| Phase | Milestone | Timeline |
|-------|-----------|----------|
| **Setup** | Form 3 steering groups (1 per journal) | Q2 2026 |
| **Setup** | Configure PubHelper fast-track per journal | Q2 2026 |
| **Setup** | Build minimal Live Guideline page prototype | Q2-Q3 2026 |
| **Pilot 1** | SJEM: First 5 EM topics through pipeline | Q3-Q4 2026 |
| **Pilot 2** | PPHJ: Diabetes prevention theme launched | Q3-Q4 2026 |
| **Pilot 3** | IJMDC: Resident Evidence Track launched | Q4 2026 |
| **Validate** | First Live Guideline pages live (3-5 per journal) | Q4 2026 |
| **Validate** | Draft MNC criteria submitted to CHI | Q1 2027 |
| **Scale** | Expand to 10+ topics per journal | 2027 |
| **Scale** | External journal partnerships | 2027-2028 |

---

## CROSS-REFERENCE

| Document | Location |
|----------|----------|
| Live Guidelines Platform | `01-TKG/00-TKG-GROUP/LIVE_GUIDELINES_PLATFORM.md` |
| PubHelper Strategy | `01-TKG/06-TKG-PubHelper/MASTER_STRATEGY_REF.md` |
| Evidence Platform Strategy | `01-TKG/05-TKG-Evidence-Platform/MASTER_STRATEGY_REF.md` |
| Waraqa Strategy | `01-TKG/01-TKG-Waraqa/MASTER_STRATEGY_REF.md` |

---

*Aligned to: THEEB_ECOSYSTEM_V2_2026.md | Chess Player Framework*

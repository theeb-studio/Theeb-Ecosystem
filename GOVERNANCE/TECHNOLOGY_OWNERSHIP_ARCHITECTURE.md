# TECHNOLOGY OWNERSHIP ARCHITECTURE
## Who Builds What — The Holding's Technology Strategy
**Aligned to: THEEB_ECOSYSTEM_V2_2026.md | Chess Player Framework**
**Version 1.0 | March 2026 | Confidential — Board Decision Document**

---

> **DECISION:** The Holding Company owns the **shared technology infrastructure** (CII, sovereign cloud, FHIR APIs, AI engines). Individual entities own their **domain-specific product interfaces** (Evidence Platform's knowledge product, Integra's claims dashboard, Welunion's patient app). This is the "Holding owns the rails, companies own the trains" model.

---

## 1. THE PROBLEM: THREE BAD OPTIONS

| Option | Description | Risk |
|--------|-------------|------|
| **A: Every entity builds its own tech** | Waraqa builds a platform, Nama Academy builds a platform, Integra builds a platform, etc. | Duplication, inconsistent data, no interoperability, 5× the cost, no network effect |
| **B: One monolithic platform for everything** | The Holding builds one giant system that all 12 entities use | Slow development, no entity autonomy, bottleneck on central team, every change affects everyone |
| **C: Holding owns infrastructure, entities own interfaces** | The Holding builds shared AI/data/cloud layers; each entity builds its own user-facing product on top | **RECOMMENDED** — balances autonomy with shared infrastructure |

---

## 2. THE RECOMMENDED ARCHITECTURE: "RAILS AND TRAINS"

```
┌─────────────────────────────────────────────────────────────────────────┐
│                                                                          │
│  ENTITY-OWNED "TRAINS" (Domain-Specific Product Interfaces)              │
│  ══════════════════════════════════════════════════════════               │
│                                                                          │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐     │
│  │ Evidence │ │ Integra  │ │ Welunion │ │  Nama    │ │ PubHelper│     │
│  │ Platform │ │ RCM      │ │ Patient  │ │ Academy  │ │ Research │     │
│  │          │ │          │ │          │ │          │ │          │     │
│  │Knowledge │ │Claims    │ │EHR +     │ │LMS +     │ │Research  │     │
│  │product,  │ │dashboard,│ │patient   │ │Learning  │ │intake,   │     │
│  │Live Guide│ │DRG tools,│ │app,      │ │Passport, │ │analysis, │     │
│  │-lines,   │ │denial    │ │tele-     │ │CME       │ │writing,  │     │
│  │MNC engine│ │analytics │ │medicine  │ │tracking  │ │publishing│     │
│  │CME, LP   │ │VBC ops   │ │booking   │ │AaaS LMS  │ │workflow  │     │
│  └────┬─────┘ └────┬─────┘ └────┬─────┘ └────┬─────┘ └────┬─────┘     │
│       │            │            │            │            │             │
│  ═════╪════════════╪════════════╪════════════╪════════════╪═════════    │
│       │            │            │            │            │             │
│  HOLDING-OWNED "RAILS" (Shared Technology Infrastructure)               │
│  ════════════════════════════════════════════════════════                │
│                                                                          │
│  ┌──────────────────────────────────────────────────────────────┐       │
│  │                    TTG — CII                                  │       │
│  │            (Clinical Intelligence Infrastructure)             │       │
│  │                                                               │       │
│  │  [7] Real World Evidence Engine                               │       │
│  │  [6] Patient Intelligence Profiles                            │       │
│  │  [5] Revenue Cycle Intelligence (pre-claim scoring)           │       │
│  │  [4] Automated Medical Documentation (Arabic + English)       │       │
│  │  [3] Clinical Decision Support APIs                           │       │
│  │  [2] AI Clinical Agents (reasoning + recommendation)          │       │
│  │  [1] Clinical Evidence Infrastructure (knowledge foundation)  │       │
│  └──────────────────────────────────────────────────────────────┘       │
│                                                                          │
│  ┌──────────────────────────────────────────────────────────────┐       │
│  │              SHARED TECHNOLOGY SERVICES                        │       │
│  │                                                               │       │
│  │  • Sovereign Cloud (NCA ECC + PDPL compliant hosting)         │       │
│  │  • FHIR R4 API Gateway (interoperability layer)               │       │
│  │  • Identity & Access Management (SSO across all entities)     │       │
│  │  • Arabic Clinical NLP Engine (shared across all products)    │       │
│  │  • Knowledge Graph Database (shared, entity-partitioned)      │       │
│  │  • Data De-identification Pipeline (PDPL compliance)          │       │
│  │  • Sovereign Compute Environment (process → extract → minimize)│      │
│  └──────────────────────────────────────────────────────────────┘       │
│                                                                          │
│  OWNED BY: THEEB HOLDING (TTG)                                          │
│  GOVERNED BY: Shared Intelligence Layer governance board                 │
│  FUNDED BY: Holding capital allocation + entity usage fees               │
│                                                                          │
└─────────────────────────────────────────────────────────────────────────┘
```

---

## 3. WHAT THE HOLDING OWNS (THE RAILS)

These are **shared infrastructure services** that every entity needs but no single entity should build alone:

| Shared Service | Why Holding Owns It | Who Uses It |
|---------------|--------------------|-----------  |
| **CII AI Engine** | Core AI/NLP models cost millions to build; duplication is wasteful | Evidence Platform, Integra RCM, Welunion, PubHelper, VBH Co |
| **Sovereign Cloud** | NCA/PDPL compliance requires one governed infrastructure | All entities |
| **FHIR R4 API Gateway** | Interoperability standard must be consistent across ecosystem | All entities exchanging clinical data |
| **Arabic Clinical NLP** | One engine trained on Saudi medical Arabic serves all products | Evidence Platform (search), CII (documentation), PubHelper (PICO extraction) |
| **Knowledge Graph DB** | One graph with entity-partitioned access; no duplication of medical knowledge | Evidence Platform (content layer), CII (reasoning layer), PubHelper (gap detection) |
| **Identity/SSO** | One physician identity = one Learning Passport = one profile across all products | All physician-facing products |
| **De-identification Pipeline** | One PDPL-compliant pipeline, not 12 different approaches | All entities processing patient data |
| **Sovereign Compute** | Process → extract intelligence → minimize raw data | CII, Nama CRO, Nama Bio |

### How This Saves Money

| Without Shared Infrastructure | With Shared Infrastructure |
|------------------------------|---------------------------|
| Evidence Platform builds its own NLP: SAR 2M | Uses CII NLP: SAR 0 (API call) |
| Integra RCM builds its own cloud: SAR 1.5M | Uses sovereign cloud: SAR 200K/year usage |
| Welunion builds its own FHIR layer: SAR 1M | Uses FHIR gateway: SAR 100K/year usage |
| PubHelper builds its own AI writing: SAR 1.5M | Uses CII Layer 2 NLP: SAR 0 (API call) |
| Nama Academy builds its own LMS hosting: SAR 500K | Uses shared cloud + SSO: SAR 100K/year |
| **Total duplicate build: SAR 6.5M+** | **Total shared usage: SAR 400K/year** |

---

## 4. WHAT EACH ENTITY OWNS (THE TRAINS)

Each entity owns its **domain-specific product interface** — the user-facing application that serves its unique market:

| Entity | What It Owns | Built On (Shared Rails) |
|--------|-------------|------------------------|
| **Evidence Platform (TKG-05)** | Knowledge product: Live Guidelines, MNC Decision Engine, Learning Passport, CME delivery, physician search interface | CII NLP, Knowledge Graph DB, SSO, Sovereign Cloud |
| **Integra RCM (TVG-01)** | Claims dashboard, DRG analysis tools, denial analytics, VBC bundle operations, CDI workflows | CII Layer 4-5 (documentation + pre-claim), FHIR Gateway, Sovereign Cloud |
| **Welunion (THDG)** | WellTech: EHR, patient app, telemedicine, booking, CDM tracking | CII Layer 3 (clinical decision support), FHIR Gateway, SSO, Sovereign Cloud |
| **Nama Academy (TKG-03)** | LMS, course management, simulation booking, AaaS dashboard, CME tracking integration | SSO (shared physician identity), Sovereign Cloud, Knowledge Graph (CME content) |
| **PubHelper (TKG-06)** | Research intake, project management, analysis workbench, writing studio, publication management | CII NLP (Arabic clinical NLP for writing), Knowledge Graph (gap detection), Sovereign Cloud |
| **VBH Co (TVG-03)** | PROMs collection interface, cost analytics dashboard, VBC contract builder | CII Layer 6-7 (population analytics), FHIR Gateway, Sovereign Cloud |
| **Nexus MGA (TVG-02)** | Underwriting models, insurance product design tools, malpractice + CME bundle management | CII population analytics, Sovereign Cloud |
| **Waraqa (TKG-01)** | Journal management systems, editorial workflow, Physician Reputation Platform | Knowledge Graph (content), CII NLP (evidence classification), Sovereign Cloud |

---

## 5. EVIDENCE PLATFORM vs CII — THE CLEAN SEPARATION

| Dimension | Evidence Platform (TKG-05) | CII (TTG) |
|-----------|--------------------------|-----------|
| **What it IS** | A **knowledge product** for physicians | An **AI infrastructure** for the ecosystem |
| **Analogy** | Netflix (curates and delivers content) | AWS (provides compute that apps run on) |
| **Users interact with it** | Yes — physicians search, learn, decide | No — physicians experience CII through other products (Evidence Platform, Welunion EHR, Integra dashboards) |
| **It contains** | Guidelines, MNCs, CME, Learning Passport, knowledge graph CONTENT | AI models, NLP engines, documentation automation, population INTELLIGENCE |
| **Revenue from** | Physician/institutional subscriptions, CHI contracts | Infrastructure fees from entities that use its APIs |
| **Owned by** | TKG (can have its own P&L and investors) | TTG / Holding (core infrastructure asset) |
| **Builds its own tech?** | Builds its own PRODUCT (UI, UX, workflows, editorial tools) | Builds the SHARED AI/NLP/COMPUTE infrastructure |
| **Uses CII?** | Yes — Evidence Platform CALLS CII for NLP search, evidence classification, clinical reasoning | N/A — CII IS the service |
| **Could exist without the other?** | Partially — but would need to build its own NLP (expensive, duplicative) | Yes — CII serves all entities, not just Evidence Platform |

### How They Work Together

```
PHYSICIAN searches Evidence Platform: "Best treatment for Saudi T2DM patients"
    │
    ▼
EVIDENCE PLATFORM receives the query
    │
    ├──► Evidence Platform's own search index finds relevant Live Guidelines
    │
    ├──► Evidence Platform CALLS CII Layer 1-2 API:
    │    "Reason over knowledge graph for this clinical question"
    │    CII returns: ranked evidence, confidence scores, Saudi-specific data
    │
    ├──► Evidence Platform CALLS CII NLP API:
    │    "Parse this Arabic free-text query into structured medical concepts"
    │    CII returns: ICD codes, drug entities, intervention categories
    │
    └──► Evidence Platform displays results to physician
         (Live Guideline + MNC criteria + evidence summary + CME credit)

THE PHYSICIAN SEES: Evidence Platform
THE PHYSICIAN NEVER SEES: CII (it works invisibly behind the scenes)
```

---

## 6. GOVERNANCE RULES

| Rule | Detail |
|------|--------|
| **Infrastructure funding** | Holding allocates capital for CII + shared services from group budget; entities pay usage fees |
| **API contracts** | Each entity has an internal SLA with TTG for CII APIs (uptime, latency, throughput) |
| **Data partitioning** | Knowledge Graph is partitioned: each entity's proprietary data is isolated; shared medical knowledge is accessible to all |
| **IP ownership** | CII models and shared infrastructure IP owned by Holding; entity-specific product IP owned by entity |
| **Build vs buy** | Entities MUST use shared services where they exist; they MAY NOT build duplicate infrastructure without Holding approval |
| **New shared services** | If 3+ entities need the same capability, it becomes a shared service under TTG |
| **Technology roadmap** | TTG CTO sets the shared infrastructure roadmap; entity CTOs set their product roadmaps; alignment quarterly |

---

## 7. THE PHYSICIAN'S EXPERIENCE (WHY THIS MATTERS)

From the physician's perspective, the technology architecture should be **invisible**. They experience ONE seamless system:

```
DR. AHMED'S DAILY EXPERIENCE:

08:00  Opens Evidence Platform on phone
       → Checks CDM patient's latest guideline update
       → [Behind the scenes: CII NLP processes Arabic query]

09:00  Sees patient at Welunion clinic
       → WellTech EHR captures encounter
       → CII Layer 4 auto-generates clinical documentation
       → [Behind the scenes: Sovereign Cloud processes data]

10:00  Documentation triggers pre-claim scoring
       → CII Layer 5 scores the claim → routes to Integra RCM
       → [Behind the scenes: FHIR API transmits structured data]

12:00  Dr. Ahmed submits a clinical question to PubHelper
       → "Is metformin more effective than GLP-1 in Saudi T2DM?"
       → CII NLP parses the question into PICO format
       → PubHelper initiates systematic review project

15:00  Completes online CDI module on Nama Academy LMS
       → Learning Passport records CME credit
       → [Behind the scenes: SSO links all his activity]

ALL DAY: One physician identity. One login. One Learning Passport.
         Six different entity products. One shared infrastructure.
         Dr. Ahmed doesn't know or care about the architecture.
         He just knows it works.
```

---

## SUMMARY RECOMMENDATION

| Decision | Recommendation |
|----------|---------------|
| **Who builds AI/NLP?** | Holding (TTG-CII) — one engine, many consumers |
| **Who builds cloud?** | Holding (TTG) — one sovereign cloud |
| **Who builds FHIR?** | Holding (TTG) — one interoperability layer |
| **Who builds product interfaces?** | Each entity — their own domain expertise |
| **Who owns physician identity?** | Holding (SSO) — one identity across all products |
| **Who owns data?** | Per entity — with shared access via governed APIs |
| **Who funds infrastructure?** | Holding capital allocation + entity usage fees |
| **Evidence Platform vs CII?** | Evidence Platform = knowledge PRODUCT (TKG). CII = AI INFRASTRUCTURE (TTG/Holding). They are complementary, not competing. |

---

*Aligned to: THEEB_ECOSYSTEM_V2_2026.md | Chess Player Framework*
*Status: Board Decision Document — requires Founder approval*

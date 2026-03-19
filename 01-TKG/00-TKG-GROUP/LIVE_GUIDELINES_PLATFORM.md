# SAUDI LIVE GUIDELINES & MEDICAL NECESSITY PLATFORM
## The Knowledge-to-Value Pipeline
**Group: TKG | Powered by: Evidence Platform (TKG-05) + PubHelper (TKG-06)**
**Feeds: TVG (Value-Added Track) + THDG (Service Delivery Track)**
**Aligned to: THEEB_ECOSYSTEM_V2_2026.md | Chess Player Framework**
**Version 1.0 | March 2026 | Confidential**

---

> **CORE INSIGHT:** The Theeb Ecosystem has three tracks — Knowledge Building (TKG), Value-Added (TVG), and Service Delivery (THDG). Until now, these tracks were only loosely connected. This platform formalizes the connective tissue: it takes clinical evidence (global + local), fuses it into continuously updated Saudi-specific guidelines, derives Medical Necessity Criteria for CHI/payers, and delivers decision support to clinicians — creating a single pipeline from knowledge production to payment reform.

---

## 1. THE PROBLEM THIS SOLVES

| Gap | Current State | With Live Guidelines Platform |
|-----|--------------|-------------------------------|
| **Imported guidelines** | Most clinical guidelines used in Saudi practice come from international sources (AHA, NICE, WHO) with no Saudi population context | Live Guidelines continuously integrate Saudi-specific research from PubHelper/Nama CRO |
| **Static documents** | Guidelines are PDF documents, updated every 3-5 years | Live Guidelines update automatically when new evidence is published |
| **Disconnected from payment** | CHI's 70 MNC criteria exist as static PDFs separate from clinical guidelines | Medical Necessity Criteria are derived transparently FROM the guidelines |
| **Research goes nowhere** | PubHelper produces studies, but they don't systematically feed back into practice | Every completed PubHelper project immediately updates the relevant Live Guideline |
| **Expert knowledge is lost** | WhatsApp groups with 300+ experts discuss evidence daily — insights disappear in chat history | Community capture process formalizes expert input into structured knowledge |

---

## 2. PLATFORM ARCHITECTURE

```
┌─────────────────────────────────────────────────────────────────────────┐
│          SAUDI LIVE GUIDELINES & MEDICAL NECESSITY PLATFORM              │
│                                                                          │
│  ═══════════════════════ INPUTS ═══════════════════════                  │
│                                                                          │
│  ┌─────────────────────┐    ┌────────────────────────────┐              │
│  │ GLOBAL EVIDENCE      │    │ LOCAL KNOWLEDGE STREAM      │              │
│  │ STREAM               │    │ (Powered by PubHelper)      │              │
│  │                      │    │                             │              │
│  │ • PubMed             │    │ • Clinician questions →     │              │
│  │ • Cochrane           │    │   systematic reviews        │              │
│  │ • Nature, Wiley,     │    │ • Nama CRO trial results    │              │
│  │   Oxford, etc.       │    │ • Nama Bio BE data          │              │
│  │ • Open-access repos  │    │ • Waraqa publications       │              │
│  │ • Chinese journals   │    │ • Society expert consensus  │              │
│  │                      │    │ • Community capture          │              │
│  │ AI classification:   │    │   (WhatsApp → structured)   │              │
│  │ condition, interv.,  │    │ • Local journals (SJEM,     │              │
│  │ outcome, LoE, Saudi  │    │   IJMDC, etc.)              │              │
│  │ relevance            │    │                             │              │
│  └──────────┬───────────┘    └──────────────┬──────────────┘              │
│             │                               │                            │
│             └───────────┬───────────────────┘                            │
│                         ▼                                                │
│  ═══════════════ CORE ENGINE ═══════════════════                         │
│                                                                          │
│  ┌──────────────────────────────────────────────┐                       │
│  │         EVIDENCE FUSION LAYER                  │                       │
│  │                                                │                       │
│  │  Combines global + local evidence into a       │                       │
│  │  structured map per topic:                     │                       │
│  │  • Trials, observational studies               │                       │
│  │  • Systematic reviews, meta-analyses           │                       │
│  │  • Guidelines, registries, expert consensus    │                       │
│  │  • Transparent grading: LoE + SoR              │                       │
│  └──────────────────┬───────────────────────────┘                       │
│                     ▼                                                    │
│  ┌──────────────────────────────────────────────┐                       │
│  │         LIVE GUIDELINES BUILDER                │                       │
│  │                                                │                       │
│  │  Per condition/symptom/procedure:              │                       │
│  │  • Dynamic guideline page                      │                       │
│  │  • Continuously updated on new evidence        │                       │
│  │  • Versioned + timestamped (audit trail)        │                       │
│  │  • Society editorial review workflow           │                       │
│  │  • Saudi-specific adaptations flagged          │                       │
│  └──────────────────┬───────────────────────────┘                       │
│                     ▼                                                    │
│  ┌──────────────────────────────────────────────┐                       │
│  │    MEDICAL NECESSITY CRITERIA GENERATOR        │                       │
│  │                                                │                       │
│  │  Translates guidelines into clear criteria:    │                       │
│  │  • Medically necessary investigations/tx       │                       │
│  │  • Conditionally appropriate options           │                       │
│  │  • Low-value / not recommended                 │                       │
│  │  • Machine-readable for CHI/payer systems      │                       │
│  └──────────────────┬───────────────────────────┘                       │
│                     │                                                    │
│  ═══════════════ OUTPUTS ═══════════════════════                         │
│                     │                                                    │
│         ┌───────────┼───────────┐                                        │
│         ▼           ▼           ▼                                        │
│  ┌────────────┐ ┌────────────┐ ┌─────────────┐                          │
│  │ POINT-OF-  │ │ PAYER &    │ │ ACADEMIC &  │                          │
│  │ CARE       │ │ REGULATOR  │ │ PUBLISHING  │                          │
│  │ INTERFACE  │ │ INTERFACE  │ │ INTERFACE   │                          │
│  │            │ │            │ │             │                          │
│  │ THDG Track │ │ TVG Track  │ │ TKG Track   │                          │
│  │            │ │            │ │             │                          │
│  │ Welunion   │ │ CHI/payers │ │ Local       │                          │
│  │ clinicians │ │ access MNC │ │ journals    │                          │
│  │ search by  │ │ per condi- │ │ publish     │                          │
│  │ symptom,   │ │ tion; sup- │ │ guideline   │                          │
│  │ diagnosis, │ │ ports pre- │ │ updates +   │                          │
│  │ drug, path │ │ auth, VBC  │ │ systematic  │                          │
│  │ → get Live │ │ bundle     │ │ reviews     │                          │
│  │ Guideline  │ │ design,    │ │             │                          │
│  │ + MNC      │ │ outcome    │ │ Every pub   │                          │
│  │            │ │ contracts  │ │ auto-links  │                          │
│  │ Mobile-    │ │            │ │ back into   │                          │
│  │ friendly   │ │ Machine-   │ │ Live Guide  │                          │
│  │            │ │ readable   │ │             │                          │
│  └────────────┘ └────────────┘ └─────────────┘                          │
└─────────────────────────────────────────────────────────────────────────┘
```

---

## 3. HOW THIS CONNECTS THE THREE ECOSYSTEM TRACKS

This is the critical architectural insight. The Live Guidelines Platform is the **connective tissue** between TKG, TVG, and THDG:

```
TKG (KNOWLEDGE BUILDING)               TVG (VALUE-ADDED)

PubHelper produces research    ──►    VBH Co uses MNC criteria for
Waraqa publishes evidence      ──►    VBC bundle pricing and
Nama CRO generates trial data  ──►    outcome-based contracts.
Evidence Platform hosts the    ──►
knowledge graph               ──►    Integra RCM uses MNC for
                                      coding justification.
        │
        │                             Nexus MGA uses guidelines
        ▼                             for risk product design.

 ┌───────────────────────┐                ▲
 │   LIVE GUIDELINES     │                │
 │   PLATFORM            │────────────────┘
 │                       │
 │   Evidence Fusion     │────────────────┐
 │   Live Guidelines     │                │
 │   MNC Generator       │                ▼
 └───────────┬───────────┘
             │                   THDG (SERVICE DELIVERY)
             │
             └──────────────►    Welunion clinicians access
                                 Live Guidelines at point of
                                 care. MNC workflows guide
                                 insurance justification.
                                 Clinical encounter data
                                 feeds back as RWE into the
                                 Knowledge Building Track.
```

### The Closed Knowledge Loop

```
CLINICIAN asks a question (THDG)
    → PubHelper converts to research project (TKG-06)
    → Nama CRO/PubHelper produces systematic review (TKG-02/06)
    → Waraqa publishes in local journal (TKG-01)
    → Evidence Platform indexes into knowledge graph (TKG-05)
    → Live Guidelines Platform updates the relevant guideline
    → MNC Criteria updated for CHI/payers (→ TVG)
    → Clinician receives updated decision support (→ THDG)
    → Clinician's next question starts the loop again
    → [KNOWLEDGE COMPOUNDS WITH EVERY CYCLE]
```

---

## 4. THE MEDICAL NECESSITY CRITERIA PIPELINE

### From Evidence to Payment Authorization

CHI currently maintains 70 Medical Necessity Criteria as static PDFs. The Live Guidelines Platform transforms this:

```
CURRENT STATE:                          WITH LIVE GUIDELINES PLATFORM:

Static MNC PDFs                         Dynamic MNC criteria derived FROM
issued periodically                     continuously updated Live Guidelines
        │                                        │
        ▼                                        ▼
Clinicians interpret                    MNC embedded in clinical workflow
manually                               (Evidence Platform MNC Decision Engine)
        │                                        │
        ▼                                        ▼
Payers apply                            Payers receive machine-readable
inconsistently                          criteria for automated authorization
        │                                        │
        ▼                                        ▼
No feedback loop                        Outcome data feeds back to
to update MNC                           refine guidelines and MNC
```

### MNC Structure Per Condition

For each condition, the MNC Generator produces:

| Category | Description | Used By |
|----------|-------------|---------|
| **Medically Necessary** | Investigations and treatments with strong evidence (Grade A-B) | Pre-auth auto-approval |
| **Conditionally Appropriate** | Options appropriate in specific clinical circumstances | Pre-auth with clinical justification |
| **Low-Value / Not Recommended** | Interventions with weak/no evidence or negative outcomes | Pre-auth denial basis |
| **Emerging Evidence** | New interventions with early-stage data (from PubHelper) | Monitoring / pilot coverage |

---

## 5. PUBHELPER: THE RESEARCH-TO-GUIDELINES ENGINE

### What PubHelper Does Within This Architecture

PubHelper (TKG-06) is the **operational engine** that converts clinical questions into the local evidence that the Live Guidelines Platform needs:

```
┌─────────────────────────────────────────────────────────────┐
│                    PUBHELPER (TKG-06)                         │
│            AI-Powered Research Factory                        │
│                                                               │
│  INPUT:                                                       │
│  • Clinician questions (free text, voice, templates)          │
│  • Community capture (WhatsApp expert groups → structured)    │
│  • Evidence gaps detected by Live Guidelines Platform         │
│  • CHI MNC update requests                                    │
│                                                               │
│  MODULES:                                                     │
│  1. Intake & Triage ─── NLP question parsing, PICO, LoE      │
│  2. Project Designer ── Protocol builder, study design        │
│  3. Data Capture ────── eCRFs, de-identification, validation  │
│  4. Analysis Workbench─ R/Python/SPSS, meta-analysis          │
│  5. Writing Studio ──── Manuscript drafts (CII NLP engine)    │
│  6. Publication Mgr ─── Journal selection, submission, review │
│  7. Evidence Engine ─── Auto-grading, PICO extraction         │
│  8. Marketplace ─────── Expert matching, pricing, SLA         │
│                                                               │
│  OUTPUT:                                                      │
│  • Systematic reviews and meta-analyses                       │
│  • Case series and observational studies                      │
│  • RCT design and support                                     │
│  • Clinical guideline drafts                                  │
│  • ALL outputs auto-feed into Live Guidelines Platform        │
└─────────────────────────────────────────────────────────────┘
```

### Evidence Grading Rubric (PubHelper Quality Gate)

Every research output is graded before entering the Live Guidelines Platform:

| Category | Level 1: Emerging | Level 3: Observational/Strong | Level 5: Apex/Systematic |
|----------|------------------|-------------------------------|--------------------------|
| **Study Design** | Case reports, expert opinions, editorials | Prospective cohort or case-control with defined variables | Meta-analysis or systematic review of RCTs |
| **Methodology** | Descriptive only; no control group | Structured PICO; risk-adjusted; p < 0.05 | Double-blinded; multi-center; low bias; heterogeneity controlled |
| **Data Integrity** | Manual entry; limited validation; small sample | eCRF-captured; >85% completeness; ICD-10/11 verified | Federated data from multiple THDG/external sites; independent audit |
| **Local Relevance** | General medical topic; no Saudi data | Saudi-specific patient cohorts (e.g., Welunion patients) | High-priority Saudi disease (diabetes, obesity) with national policy impact |
| **Publication** | Internal white paper or non-indexed journal | Scopus/PubMed indexed with peer review | Integrated into National Clinical Guideline published by Waraqa/CHI |

**Strength of Recommendation (SOR):**
- **Grade A (20-25):** Strong recommendation — suitable for national guidelines
- **Grade B (15-19):** Moderate — suitable for institutional protocols
- **Grade C (<15):** Emerging — requires further primary study

---

## 6. USE CASE 1: EMERGENCY MEDICINE TRACK

**Partners:** Saudi Journal of Emergency Medicine, Saudi Emergency Medicine Society, Saudi Red Crescent Authority, major ED departments.

```
STEP 1: Joint steering group defines 20-30 high-impact clinical questions
        (chest pain pathways, sepsis, pediatric head trauma, stroke in ED)

STEP 2: PubHelper coordinates teams of 10 EM physicians per topic
        to conduct systematic reviews and meta-analyses

STEP 3: Platform ingests local reviews + all relevant global evidence

STEP 4: Evidence Fusion Layer builds Live Guidelines per topic
        with explicit grading and recommended ED pathways

STEP 5: Medical Necessity Criteria derived per scenario
        (necessary investigations/treatments for insured patients)

STEP 6: ED physicians access in real time at point of care
        CHI uses same criteria to align payments

RESULT: 20-30 Live Guidelines with MNC criteria for Emergency Medicine
        Published in Saudi Journal of Emergency Medicine
        Accessible on Evidence Platform at every Welunion ED
```

---

## 7. USE CASE 2: LONGEVITY TRACK

**Current state:** WhatsApp group with 300+ longevity experts — daily discussions of new studies, experiences, but insights remain unstructured.

```
STEP 1: Community capture process regularly summarizes
        discussions and references from expert group

STEP 2: Recurrent questions formalized into research questions
        (supplements, fasting protocols, biomarkers)
        → passed to PubHelper

STEP 3: PubHelper organizes systematic reviews, meta-analyses,
        or observational studies

STEP 4: Platform builds Live Guidelines for key longevity themes
        combining formal evidence + clearly labelled expert consensus

STEP 5: Every message, study, and expert insight becomes an asset
        in a growing knowledge graph — not lost in chat history

RESULT: Structured longevity evidence base
        Expert knowledge preserved and compounding
        Saudi-specific longevity guidelines
```

---

## 8. IMPLEMENTATION PHASES

### Phase 1 — Pilot: Emergency Medicine Focus (6-9 months)

| Deliverable | Timeline |
|-------------|----------|
| Core repository and Live Guideline infrastructure | Q2-Q3 2026 |
| PubHelper integration for selected EM topics | Q2 2026 |
| Collaboration with Saudi Journal of EM + Saudi EM Society | Q2 2026 |
| First set of Live Guidelines (20-30 EM conditions) | Q3-Q4 2026 |
| Draft Medical Necessity Criteria for CHI | Q4 2026 |

### Phase 2 — Expansion (9-18 months)

| Deliverable | Timeline |
|-------------|----------|
| Additional specialties onboarded (cardiology, diabetes, etc.) | 2027 |
| Longevity as dedicated track | 2027 |
| AI pipelines strengthened for literature ingestion + grading | 2027 |
| Multiple local journals integrated | 2027 |

### Phase 3 — Full CHI Integration (18-36 months)

| Deliverable | Timeline |
|-------------|----------|
| MNC criteria scaled to 100+ conditions | 2028 |
| CHI/payers embed criteria in contracting + authorization | 2028 |
| Outcome data refines guidelines (closed loop) | 2028+ |
| VBC contracts designed on standardized pathways | 2028+ |

---

## 9. STRATEGIC IMPACT ON ECOSYSTEM

| Impact | Entity | Mechanism |
|--------|--------|-----------|
| **National evidence backbone** | Evidence Platform (TKG-05) | Live Guidelines become the knowledge graph's highest-value content |
| **Research pipeline** | PubHelper (TKG-06) | Evidence gaps drive systematic research production |
| **Publication output** | Waraqa (TKG-01) | Guideline updates published in local indexed journals |
| **Society engagement** | Nama Academy (TKG-03) | Societies provide editorial review; faculty teach guideline content |
| **VBC contract design** | VBH Co (TVG-03) | MNC criteria define what gets paid in bundled payments |
| **Coding justification** | Integra RCM (TVG-01) | MNC criteria provide evidence-based coding defense |
| **Insurance design** | Nexus MGA (TVG-02) | Guidelines inform benefit package and risk product design |
| **Clinical decision support** | Welunion (THDG) | Point-of-care access to Live Guidelines and MNC |
| **Population intelligence** | CII (TTG) | Guideline adherence tracked → quality measurement |
| **CME content** | Nama Academy + Evidence Platform | Guideline updates become CME learning modules |

### The Ultimate Closed Loop

```
CLINICIAN QUESTION (THDG)
    → PubHelper research (TKG-06)
    → Waraqa publication (TKG-01)
    → Evidence Platform indexing (TKG-05)
    → Live Guideline update
    → MNC Criteria derived
    → CHI/payer authorization rules updated (TVG)
    → Integra RCM coding aligned
    → VBH Co VBC contracts designed
    → Welunion care pathway updated (THDG)
    → Clinical encounter generates outcome data
    → Outcome data validates or refines the guideline
    → [KNOWLEDGE → VALUE → DELIVERY → KNOWLEDGE]
    → [THE THREE TRACKS BECOME ONE CONTINUOUS SYSTEM]
```

---

*Aligned to: THEEB_ECOSYSTEM_V2_2026.md | Chess Player Framework*

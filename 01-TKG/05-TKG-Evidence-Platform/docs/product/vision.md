# Saudi Evidence — Product Vision
**Product: Saudi Evidence | Entity: TKG-05 (Evidence Platform)**
**Powered by: TTG-CII (AI Infrastructure) + DeepEvidence (External Partner)**
**Version 1.0 | March 2026 | Confidential**

---

## One-Line Vision

**The free, AI-powered medical knowledge platform for every licensed clinician in Saudi Arabia.**

---

## What Saudi Evidence Is

Saudi Evidence is the **product brand** of the Theeb Ecosystem's Evidence Platform (TKG-05). It is the interface through which 300,000+ Saudi healthcare professionals access clinical evidence, earn CME credits, follow guidelines, and contribute to research — all in one integrated experience.

It is NOT a search engine. It is NOT a database. It is a **clinical intelligence companion** that lives alongside the physician throughout their 30-40 year career.

---

## Strategic Position Within Theeb Ecosystem

```
┌──────────────────────────────────────────────────────────────────┐
│                    SAUDI EVIDENCE (Product Brand)                  │
│                                                                    │
│  What the clinician sees and uses daily:                          │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐            │
│  │ Evidence  │ │Guidelines│ │   CME    │ │ Research │            │
│  │  Search   │ │   Hub    │ │ Learning │ │  Tools   │            │
│  │          │ │          │ │ Passport │ │(PubHelper)│            │
│  └────┬─────┘ └────┬─────┘ └────┬─────┘ └────┬─────┘            │
│       └─────────────┴────────────┴─────────────┘                  │
│                          │                                        │
│  ════════════════════════╪════════════════════════════════════     │
│                          │  APIs                                  │
│  WHAT POWERS IT:         ▼                                        │
│  ┌────────────────┐  ┌────────────────┐  ┌────────────────┐      │
│  │ DeepEvidence    │  │ CII (TTG)      │  │ Waraqa + Nama  │      │
│  │ PubMed + Embase │  │ Arabic NLP     │  │ CRO + PubHelper│      │
│  │ (External API)  │  │ Sovereign Cloud│  │ (Content)      │      │
│  └────────────────┘  └────────────────┘  └────────────────┘      │
└──────────────────────────────────────────────────────────────────┘
```

| Layer | Owner | Role |
|-------|-------|------|
| **Saudi Evidence (Product)** | TKG-05 (Evidence Platform entity) | Product design, UX, content curation, CME management, user relationships |
| **AI Engine** | TTG-CII (Holding-owned) | Arabic NLP, clinical reasoning, sovereign compute |
| **External Data** | DeepEvidence (partner) | PubMed + Embase search, citation retrieval |
| **Content Supply** | Waraqa, Nama CRO, PubHelper, societies | Guidelines, publications, research, Live Guidelines |
| **CME/Training** | Nama Academy | Course delivery, SCFHS accreditation, Learning Passport content |

---

## The Five Pillars

### Pillar 1: Free AI Research Engine for Clinicians

**What:** Natural language clinical question answering, powered by DeepEvidence (PubMed + Embase) and enhanced by CII's Arabic NLP.

**User experience:**
- Clinician types: "What is the best anticoagulation for atrial fibrillation in patients with CKD stage 4?"
- Saudi Evidence returns:
  - Direct answer with confidence level
  - Linked references (abstracts, key findings, full-text links)
  - Saudi-specific guidelines if available
  - International guidelines as fallback
  - CME credit logged for the learning interaction

**Why free:** Adoption is the moat. Every clinician using Saudi Evidence daily = data on clinical questions, evidence gaps, and practice patterns. This data powers PubHelper research priorities, CII model training, and VBH Co outcomes intelligence.

**DeepEvidence integration:**
- DeepEvidence handles: PubMed/Embase retrieval, citation ranking, evidence grading
- CII handles: Arabic query processing, Saudi context enrichment, local guideline matching
- Saudi Evidence handles: UX, user profiles, CME tracking, guidelines overlay

### Pillar 2: Guidelines Hub for Saudi Scientific Societies

**What:** The canonical distribution point for every Saudi clinical guideline — hosted, searchable, versioned, and linked to CME.

**Architecture:**
- Each society gets a branded hub within Saudi Evidence
- Guidelines stored in structured format (not PDF dumps):
  - Disease/condition
  - Recommendations with strength/evidence level
  - Saudi-specific context
  - Last updated date and version history
- When no Saudi guideline exists: show international guidelines with clear labeling + invitation for local experts to contribute
- **Live Guidelines** (from PubHelper pipeline): continuously updated as new evidence emerges

**Connection to Waraqa:** Every guideline published through Waraqa automatically appears in Saudi Evidence. The journal is the publication channel; Saudi Evidence is the distribution channel.

### Pillar 3: CME and Continuous Education (Learning Passport)

**What:** Every meaningful interaction on Saudi Evidence generates CME credits, tracked through the Learning Passport.

**CME-generating activities:**
| Activity | CME Credit | Verification |
|----------|-----------|-------------|
| Reading a guideline + answering quiz questions | 0.5-1.0 hour | Quiz score >70% |
| Completing a structured micro-course | 1.0-2.0 hours | Course completion + assessment |
| Case-based learning module | 0.5-1.0 hour | Case analysis submission |
| Evidence search session (>15 min with >3 queries) | 0.25 hour | Automatic logging |
| PubHelper research contribution | 2.0-5.0 hours | Project completion verification |
| Live Guidelines review and commentary | 0.5 hour | Structured feedback submission |

**Core/basic courses hosted:**
- BLS, ACLS, PALS (theory + assessment — practical via Nama Academy)
- Quality and Patient Safety fundamentals
- CBAHI accreditation basics
- JCI standards overview
- CDI and medical coding fundamentals (feeds Integra RCM pipeline)

**SCFHS integration:** Learning Passport syncs with SCFHS for automatic credit logging toward the 30-credit/year mandate.

### Pillar 4: Saudi Context and Compliance

**What:** Platform design ensures compliance with Saudi regulatory requirements — making Saudi Evidence not just useful but **necessary** for institutional compliance.

**CBAHI alignment:**
- Information Management standards require hospitals to provide clinicians with access to up-to-date scientific resources
- Saudi Evidence IS that resource — one platform replaces scattered PDFs and expensive international subscriptions
- Institutional dashboards show usage, which departments access what evidence, and where knowledge gaps exist

**PDPL/NDMO compliance:**
- Saudi-hosted sovereign cloud (NCA ECC compliant)
- Sovereign Compute architecture: process queries, extract intelligence, minimize personal data
- No patient data on the platform — only clinician professional data

**Research-active hospital support:**
- PubHelper integration helps hospitals demonstrate active research programs
- Evidence gap detection identifies institutional research opportunities

### Pillar 5: Future Revenue Streams (Designed Now, Activated Later)

**V1: Free for clinicians. Revenue = zero. Goal = adoption + data.**

**V2+ revenue streams (behind feature flags, not activated in v1):**

| Stream | Model | Timing | Theeb Entity |
|--------|-------|--------|-------------|
| Advanced CME courses | Paid per course or subscription | V2 | Nama Academy |
| Institutional B2B dashboards | SaaS per hospital | V2 | Saudi Evidence |
| Pharma aggregated insights | Anonymized trend data licensing | V3 | Saudi Evidence |
| Sponsored CME | Pharma-funded education (strict independence) | V2 | Nama Academy + Saudi Evidence |
| Research tools (PubHelper) | Per-project fee | V2 | PubHelper (Waraqa service line / Saudi Evidence module) |
| Institutional compliance package | Annual hospital license | V2 | Saudi Evidence + Nama Academy |
| MGA insurance bundle access | CME fulfillment tracking | V2 | Nexus MGA |

---

## Growth Strategy: Free First, Monetize Through Ecosystem

```
Phase 1 (2026): FREE FOR ALL CLINICIANS
    Goal: 10,000+ active users
    Revenue: $0 from Saudi Evidence directly
    Value: Data, relationships, proof of concept

Phase 2 (2027): INSTITUTIONAL + CME REVENUE
    Goal: 25,000+ users, 50+ hospital partnerships
    Revenue: Institutional SaaS + paid CME courses
    Value: SCFHS integration live, CBAHI compliance tool

Phase 3 (2028+): FULL ECOSYSTEM MONETIZATION
    Goal: 50,000+ users, national standard
    Revenue: All streams active
    Value: Saudi Evidence = infrastructure, not just a product
```

**The key insight:** Saudi Evidence doesn't need to make money directly in Year 1. Its value to the ecosystem is immense even at $0 revenue:
- Every user = potential Nama Academy CME student
- Every search = evidence gap intelligence for PubHelper
- Every institutional deployment = pipeline for Integra RCM
- Every guideline view = validation of Waraqa content
- Every clinical question = training data for CII

Saudi Evidence is the **distribution layer** that makes every other TKG entity more valuable.

---

## What Saudi Evidence Replaces

| Current Solution | Problem | Saudi Evidence Advantage |
|-----------------|---------|------------------------|
| UpToDate (SCFHS-provided) | Expensive, no Saudi context, no CME integration, low utilization | Free, Saudi-first, CME built-in, higher engagement |
| Scattered PDF guidelines | Not searchable, not updated, not tracked | Structured, searchable, versioned, tracked |
| Individual journal subscriptions | Expensive, fragmented, no synthesis | Unified search across PubMed + Embase + local |
| WhatsApp groups for clinical questions | Unstructured, no verification, knowledge lost | Structured, evidence-based, permanently indexed |
| Manual CME tracking | Error-prone, disconnected from learning | Automatic, continuous, synced with SCFHS |

---

## Relationship to DeepEvidence

DeepEvidence is an **external AI partner** providing the medical literature search and reasoning engine. Saudi Evidence wraps DeepEvidence with:

| DeepEvidence Provides | Saudi Evidence Adds |
|----------------------|---------------------|
| PubMed + Embase search | Arabic NLP (via CII) |
| Citation retrieval and ranking | Saudi guideline overlay |
| Evidence grading | CME credit tracking |
| Medical reasoning | Learning Passport integration |
| | Society-branded guideline hubs |
| | Institutional compliance dashboards |
| | PubHelper research pipeline connection |
| | MNC Decision Engine (CHI integration) |

**Partnership model:** DeepEvidence is a technology partner, not a competitor. They provide the global evidence retrieval engine; Saudi Evidence provides the Saudi product layer, user base, and ecosystem integration.

---

*Product Owner: Evidence Platform (TKG-05)*
*AI Infrastructure: CII (TTG) — Holding-owned*
*Aligned to: THEEB_ECOSYSTEM_V2_2026.md | Chess Player Framework*

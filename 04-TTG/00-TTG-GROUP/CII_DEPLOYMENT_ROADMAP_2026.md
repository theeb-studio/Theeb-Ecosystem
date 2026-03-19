# CII DEPLOYMENT ROADMAP 2026
## Layer-by-Layer Build Sequence & Entity Integration
**Entity: TTG-CII | Owned by: Theeb Holding (100%)**
**Aligned to: TECHNOLOGY_OWNERSHIP_ARCHITECTURE.md | Chess Player Framework**
**Version 1.0 | March 2026 | Confidential**

---

> **PRINCIPLE:** CII's 7 layers are NOT built simultaneously. They deploy in sequence based on TWO criteria: (1) which layer has an immediate paying consumer entity, and (2) which layer's data output enables the next layer. Revenue-generating integrations ship first.

---

## DEPLOYMENT SEQUENCE

```
         Q1 2026        Q2 2026        Q3 2026        Q4 2026        2027
         ┌──────────────┬──────────────┬──────────────┬──────────────┬──────────
Layer 1  ████████████████                                              MATURE
         Evidence Infra  (feeds Evidence Platform knowledge graph)

Layer 2  ██████████████████████████████                                MATURE
         AI Clinical Agents  (Arabic NLP for PubHelper + Evidence Platform)

Layer 4      ████████████████████████████████                          MATURE
             Auto Documentation  (first consumer: Integra RCM)

Layer 5          ██████████████████████████████████                    MATURE
                 Revenue Intelligence  (pre-claim scoring for Integra)

Layer 3              ████████████████████████████████████████          MATURE
                     Clinical Decision Support  (for Evidence Platform + Welunion)

Layer 6                      ████████████████████████████████████████  BUILDING
                             Patient Intelligence  (for VBH Co + Nama CRO)

Layer 7                              ████████████████████████████████  BUILDING
                                     RWE Generation  (for Nama CRO + external)
```

### Why This Sequence

| Layer | Why This Order | First Consumer | Revenue Signal |
|-------|---------------|----------------|---------------|
| **Layer 1 (Evidence Infrastructure)** | Foundation — everything else depends on it | Evidence Platform | Knowledge graph feeds all downstream |
| **Layer 2 (AI Agents)** | Arabic NLP engine needed by PubHelper and Evidence Platform | PubHelper Writing Studio, Evidence Platform search | Enables multiple products simultaneously |
| **Layer 4 (Documentation)** | **First revenue opportunity** — Integra RCM needs this for CDI | Integra RCM (paying client) | Per-document fee from Day 1 |
| **Layer 5 (Revenue Intelligence)** | Pre-claim scoring — direct ROI for Integra RCM clients | Integra RCM (paying client) | Gain-share model activated |
| **Layer 3 (Decision Support)** | Clinical APIs for Evidence Platform and Welunion EHR | Evidence Platform, Welunion | SaaS subscription |
| **Layer 6 (Patient Intelligence)** | Requires encounter data from Welunion (needs clinics operational) | VBH Co, Nama CRO | Analytics subscription |
| **Layer 7 (RWE Generation)** | Requires population-scale data (needs 6+ months of encounters) | Nama CRO, pharma companies | Data licensing |

---

## LAYER-BY-LAYER DETAIL

### Layer 1: Clinical Evidence Infrastructure (Q1 2026)

| Component | Deliverable | Timeline |
|-----------|-------------|----------|
| Knowledge graph integration | Evidence Platform's 16,290+ nodes connected to CII reasoning | January 2026 |
| PubMed/Cochrane/WHO ingestion | Automated evidence import pipeline | February 2026 |
| Evidence classification engine | Auto-classify studies by condition, intervention, LoE | March 2026 |
| **Consumer:** Evidence Platform | Knowledge graph queries via CII API | **Live Q1** |

### Layer 2: AI Clinical Agents (Q1-Q2 2026)

| Component | Deliverable | Timeline |
|-----------|-------------|----------|
| Arabic Clinical NLP model | Trained on Saudi medical Arabic corpus | January-March 2026 |
| PICO extraction engine | Free-text → structured clinical questions | March 2026 |
| Evidence reasoning agent | Query knowledge graph with clinical logic | April 2026 |
| **Consumer:** PubHelper (Writing Studio), Evidence Platform (search) | NLP API | **Live April** |

### Layer 4: Automated Medical Documentation (Q2-Q3 2026)

| Component | Deliverable | Timeline |
|-----------|-------------|----------|
| Clinical note generation | Arabic + English encounter documentation | April 2026 |
| ICD-10-AM code suggestion | Auto-coding from clinical notes | May 2026 |
| SBS procedure code suggestion | Procedure coding from documentation | May 2026 |
| Documentation completeness score | Quality gate before claim submission | June 2026 |
| **Consumer:** Integra RCM (CDI programs) | Documentation API | **Live May** |

### Layer 5: Revenue Cycle Intelligence (Q2-Q3 2026)

| Component | Deliverable | Timeline |
|-----------|-------------|----------|
| Pre-claim scoring engine | Score 0-100 per claim (>85 = auto-submit) | May-June 2026 |
| DRG assignment verification | Validate DRG grouping from documentation | June 2026 |
| Denial probability prediction | Payer-specific denial risk scoring | July 2026 |
| MSR impact assessment | VBC shared savings impact per claim | August 2026 |
| **Consumer:** Integra RCM | Pre-claim API | **Live June** |

### Layer 3: Clinical Decision Support (Q3-Q4 2026)

| Component | Deliverable | Timeline |
|-----------|-------------|----------|
| Clinical decision support APIs | EHR-embeddable recommendations | July 2026 |
| Live Guideline integration | Real-time guideline access at point of care | August 2026 |
| MNC workflow integration | Insurance justification at clinical decision point | September 2026 |
| **Consumer:** Evidence Platform, Welunion EHR | CDS API | **Live August** |

### Layer 6: Patient Intelligence (Q4 2026 — H1 2027)

| Component | Deliverable | Timeline |
|-----------|-------------|----------|
| Longitudinal patient profiles | Multi-encounter patient models | October 2026 |
| Chronic disease trajectories | CDM population tracking | November 2026 |
| Cohort identification | Research-eligible patient flagging | December 2026 |
| **Consumer:** VBH Co (PROMs correlation), Nama CRO (trial recruitment) | Patient API | **Live Q4** |

### Layer 7: RWE Generation (Q4 2026 — 2027)

| Component | Deliverable | Timeline |
|-----------|-------------|----------|
| Population analytics engine | Disease burden mapping | November 2026 |
| Treatment effectiveness analysis | Pathway comparison across populations | Q1 2027 |
| Pharma market access data packages | Structured RWE for sponsors | Q1 2027 |
| **Consumer:** Nama CRO (RWE studies), pharma companies (licensing) | RWE API | **Live Q1 2027** |

---

## INTEGRATION TIMELINE PER CONSUMING ENTITY

| Entity | CII Layers Used | Integration Live |
|--------|----------------|-----------------|
| **Evidence Platform** | Layer 1 (evidence), Layer 2 (NLP), Layer 3 (CDS) | Q1 → Q3 2026 |
| **PubHelper** | Layer 2 (NLP for PICO + writing) | Q2 2026 |
| **Integra RCM** | Layer 4 (documentation), Layer 5 (pre-claim) | Q2 → Q3 2026 |
| **Welunion** | Layer 3 (CDS), Layer 4 (documentation) | Q3 2026 |
| **VBH Co** | Layer 6 (patient intelligence) | Q4 2026 |
| **Nama CRO** | Layer 6 (cohort ID), Layer 7 (RWE) | Q4 2026 → Q1 2027 |
| **Nexus MGA** | Layer 6-7 (population analytics for risk) | Q1 2027 |
| **External hospitals** | Layer 3-5 (CDS + documentation + pre-claim) | Q4 2026+ |

---

## STAFFING & BUDGET

| Role | Q1 | Q2 | Q3 | Q4 |
|------|-----|-----|-----|-----|
| CTO | 1 | 1 | 1 | 1 |
| AI/ML Engineers | 2 | 4 | 6 | 6 |
| Backend Engineers | 2 | 3 | 4 | 4 |
| Arabic NLP Specialist | 1 | 2 | 2 | 2 |
| Clinical Informaticist | 1 | 1 | 2 | 2 |
| DevOps / Cloud | 1 | 1 | 2 | 2 |
| **Total** | **8** | **12** | **17** | **17** |

| Cost Category | 2026 (SAR) |
|--------------|-----------|
| Personnel | 3.0-4.5M |
| Cloud infrastructure (sovereign) | 500K-1M |
| AI model training compute | 300-500K |
| FHIR/integration tools | 200-300K |
| **Total CII 2026 budget** | **4.0-6.3M** |

**Funding:** Government grants (SDAIA, RDIA, NTDP: SAR 5-15M potential) + Holding capital allocation + entity usage fees starting Q3 2026.

---

*Aligned to: TECHNOLOGY_OWNERSHIP_ARCHITECTURE.md | Chess Player Framework*

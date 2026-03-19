# PUBHELPER vs NAMA CRO — ROUTING BOUNDARY
## When Does PubHelper Handle It vs When Does Nama CRO Handle It?
**Version 1.0 | March 2026 | Confidential**

---

## THE CLEAR BOUNDARY

```
                    CLINICAL QUESTION ARRIVES
                            │
                            ▼
                   ┌─────────────────┐
                   │  DOES IT REQUIRE │
                   │  NEW PRIMARY     │
                   │  DATA COLLECTION │
                   │  FROM PATIENTS?  │
                   └────────┬────────┘
                            │
                   ┌────────┴────────┐
                   │                 │
                   NO                YES
                   │                 │
                   ▼                 ▼
            ┌──────────┐      ┌──────────┐
            │ PUBHELPER│      │ NAMA CRO │
            │ (Waraqa  │      │ (TKG-02) │
            │ svc line)│
            └──────────┘      └──────────┘
```

## ROUTING RULES

| Question Type | Handler | Why |
|--------------|---------|-----|
| **Systematic review** (existing literature) | **PubHelper** | No patients involved — synthesizing published evidence |
| **Meta-analysis** (pooling existing studies) | **PubHelper** | No patients involved — statistical aggregation |
| **Clinical guideline** development | **PubHelper** (lead) + Nama CRO (data input) | Guideline is a knowledge product; CRO provides source data |
| **Narrative review** | **PubHelper** | Literature-based |
| **Retrospective study** (existing EMR data) | **PubHelper** (analysis) + Nama CRO (data governance/IRB) | Data exists; PubHelper analyzes; CRO ensures regulatory compliance |
| **Prospective observational study** | **Nama CRO** | Requires patient enrollment, consent, monitoring |
| **Clinical trial (Phase I-IV)** | **Nama CRO** | Requires patients, investigational product, GCP compliance |
| **Registry / disease cohort** | **Nama CRO** | Requires ongoing patient enrollment and data collection |
| **Bioequivalence study** | **Nama Bio** (TKG-04) via Nama CRO coordination | Specialized facility and regulatory pathway |
| **RWE study** (needs new data collection) | **Nama CRO** | Requires sites, CRCs, monitoring |
| **RWE study** (uses existing CII/Welunion data) | **PubHelper** (analysis) + Nama CRO (regulatory) | Data exists in ecosystem; PubHelper analyzes |
| **Case report / case series** | **PubHelper** | Writing and publication support; no trial infrastructure needed |

## HANDOFF PROTOCOL

When a PubHelper project discovers that it NEEDS new patient data:

```
PubHelper begins systematic review on intervention X
    → Evidence gap detected: "No Saudi-specific RCT data exists"
    → PubHelper flags: "Primary study needed"
    → Handoff to Nama CRO: study design + protocol
    → Nama CRO executes the trial / observational study
    → Trial data returned to PubHelper for integration into the SR/MA
    → PubHelper publishes combined evidence (global + new local data)
```

## REVENUE ALLOCATION

| Project Type | PubHelper Revenue | Nama CRO Revenue |
|-------------|------------------|------------------|
| Pure literature review / SR / MA | 100% PubHelper | 0% |
| Literature review + CRO data governance | 70% PubHelper / 30% Nama CRO | 30% |
| Retrospective study using ecosystem data | 60% PubHelper / 40% Nama CRO | 40% |
| Prospective study triggered by PubHelper gap | 20% PubHelper (SR component) / 80% Nama CRO | 80% |
| Pure clinical trial | 0% (unless SR/MA added) | 100% Nama CRO |

---

*Aligned to: THEEB_ECOSYSTEM_V2_2026.md | TKG Group Architecture*

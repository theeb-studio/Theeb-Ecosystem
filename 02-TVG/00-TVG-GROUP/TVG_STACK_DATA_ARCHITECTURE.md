# TVG STACK DATA ARCHITECTURE
## How Claims Data Flows from Layer 1 → Layer 2 → Layer 3-4
**Group: TVG | Entities: Integra RCM, Nexus MGA, VBH Co**
**Version 1.0 | March 2026 | Confidential**

---

## 1. DATA WAREHOUSE OWNERSHIP

**The Holding owns the shared TVG data warehouse** (hosted on CII sovereign cloud). Each entity writes to and reads from governed partitions:

| Data Partition | Written By | Read By | Refresh Rate |
|---------------|-----------|---------|-------------|
| Claims & Coding | Integra RCM | VBH Co, Nexus MGA, CII | Real-time (per claim) |
| Denial Analytics | Integra RCM | Nexus MGA, VBH Co | Daily batch |
| DRG Baselines | Integra RCM + VBH Co | All TVG + CII | Weekly recalculation |
| PROMs / Outcomes | VBH Co | Nexus MGA, CII, Nama CRO | Per collection event |
| Cost Benchmarks | VBH Co | Integra RCM, Nexus MGA | Monthly |
| Risk Models | Nexus MGA | VBH Co | Quarterly |
| Population Analytics | CII (Layer 6-7) | All TVG | Continuous |

## 2. DATA FLOW ARCHITECTURE

```
CLINICAL ENCOUNTER (THDG — Welunion / Hospital Client)
         │
         ▼
┌─────────────────────────────────┐
│  INTEGRA RCM (Layer 1)          │  WRITES:
│  Claims processing pipeline     │  • ICD-10-AM codes
│                                 │  • SBS procedure codes
│  CII Layer 4 → documentation   │  • DRG assignment + severity
│  CII Layer 5 → pre-claim score │  • Claim amount (submitted/approved/denied)
│                                 │  • Denial reason codes
│                                 │  • LOS, readmission flags
│                                 │  • Payer-specific behavior
└────────────┬────────────────────┘
             │ API: claims.submit → TVG Data Warehouse
             │ SLA: <4 hours from encounter to warehouse
             ▼
┌────────────────────────────────────────────────────────┐
│            TVG SHARED DATA WAREHOUSE                     │
│            (Hosted on CII Sovereign Cloud)               │
│                                                          │
│  ┌─────────────────────────────────────────────┐        │
│  │  Claims Partition  │  Outcomes Partition     │        │
│  │  (Integra writes)  │  (VBH Co writes)       │        │
│  ├────────────────────┼────────────────────────┤        │
│  │  DRG Baselines     │  Risk Models            │        │
│  │  (joint)           │  (Nexus MGA writes)     │        │
│  └─────────────────────────────────────────────┘        │
└────────────┬──────────────────┬──────────────────────────┘
             │                  │
     ┌───────┘                  └───────┐
     ▼                                  ▼
┌──────────────────┐          ┌──────────────────┐
│  NEXUS MGA (L2)  │          │  VBH CO (L3-4)   │
│                  │          │                  │
│  READS:          │          │  READS:          │
│  • Denial rates  │          │  • Claims data   │
│    per payer     │          │  • DRG costs     │
│  • Claims volume │          │  • Severity dist │
│  • Loss ratio    │          │  • LOS data      │
│    predictions   │          │  • Readmissions  │
│                  │          │                  │
│  USES FOR:       │          │  USES FOR:       │
│  • Underwriting  │          │  • Cost-of-care  │
│  • Risk pricing  │          │  • MSR calc      │
│  • Product design│          │  • VBC pricing   │
│  • Employer      │          │  • Benchmarking  │
│    benefits      │          │  • PROMs correl. │
└──────────────────┘          └──────────────────┘
```

## 3. GAIN-SHARE CALCULATION ENGINE

| Component | Source | Calculation | Dispute Resolution |
|-----------|--------|------------|-------------------|
| Baseline cost | Integra RCM (first 6 months of shadow billing data) | Average cost per DRG at engagement start | Joint review by Integra + hospital CFO |
| Current cost | Integra RCM (ongoing claims data) | Rolling 90-day average cost per DRG | Automated from warehouse |
| Savings | Baseline - Current | Verified quarterly by independent audit | TVG governance committee (3-person) |
| Gain-share split | Pre-agreed in contract | 15-25% to TVG, 75-85% to hospital | Per contract terms |
| Quality gate | VBH Co PROMs | Savings only count if outcomes ≥ baseline | VBH Co certifies quality threshold met |

---

*Aligned to: THEEB_ECOSYSTEM_V2_2026.md | Gain-Share Revenue Engine*

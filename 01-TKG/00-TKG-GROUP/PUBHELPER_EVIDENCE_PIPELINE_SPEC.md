# PUBHELPER → EVIDENCE PLATFORM AUTOMATED PIPELINE
## Integration Specification: How Research Becomes Live Clinical Intelligence
**Entities: PubHelper (Waraqa service line / Saudi Evidence module) → TKG-05 (Evidence Platform) → Live Guidelines → MNC Criteria**
**Version 1.0 | March 2026 | Confidential**

---

> **PURPOSE:** This document specifies HOW a PubHelper research output automatically updates the Evidence Platform's knowledge graph, triggers a Live Guideline revision, and derives updated Medical Necessity Criteria. Without this automation, the Knowledge-to-Value pipeline is manual and bottlenecked.

---

## 1. THE END-TO-END PIPELINE

```
┌─────────────────────────────────────────────────────────────────────┐
│  STAGE 1: RESEARCH COMPLETION (PubHelper)                            │
│                                                                       │
│  PubHelper project PH-2026-EM-007 completed:                         │
│  "Validation of HEART Score in Saudi Emergency Departments"           │
│  → Structured output: PICO, evidence tables, SOR grade, metadata     │
│                                                                       │
│  TRIGGER: Project status → "completed" in PubHelper system            │
└──────────────────────┬──────────────────────────────────────────────┘
                       │ EVENT: pubhelper.project.completed
                       ▼
┌─────────────────────────────────────────────────────────────────────┐
│  STAGE 2: JOURNAL SUBMISSION (Waraqa)                                │
│                                                                       │
│  PubHelper auto-generates submission package:                         │
│  → Manuscript (Writing Studio output)                                 │
│  → Cover letter (Publication Manager)                                 │
│  → Target journal recommendation (SJEM for this EM topic)            │
│                                                                       │
│  Waraqa editorial team receives fast-track submission                  │
│  → Peer review (society steering group)                               │
│  → Revision cycle                                                     │
│  → Acceptance                                                         │
│                                                                       │
│  TRIGGER: Article status → "accepted" in Waraqa editorial system      │
└──────────────────────┬──────────────────────────────────────────────┘
                       │ EVENT: waraqa.article.accepted
                       ▼
┌─────────────────────────────────────────────────────────────────────┐
│  STAGE 3: EVIDENCE INDEXING (Evidence Platform)                      │
│                                                                       │
│  Auto-ingest pipeline activates:                                      │
│  1. Extract structured metadata from PubHelper project record         │
│  2. Map to ICD-10 codes, drug entities, intervention categories       │
│  3. Create knowledge graph nodes + edges                              │
│  4. Link to existing evidence for same condition/intervention         │
│  5. Calculate updated evidence weight for topic                       │
│                                                                       │
│  Knowledge graph updated: +N nodes, +M edges                          │
│                                                                       │
│  TRIGGER: Knowledge graph delta detected for linked guideline         │
└──────────────────────┬──────────────────────────────────────────────┘
                       │ EVENT: evidence.graph.updated
                       ▼
┌─────────────────────────────────────────────────────────────────────┐
│  STAGE 4: LIVE GUIDELINE UPDATE                                      │
│                                                                       │
│  Guideline engine detects new evidence for LG-EM-CHEST-PAIN-001:     │
│  1. Re-evaluates evidence map (global + local studies)                │
│  2. Recalculates strength of recommendation per item                 │
│  3. Flags changed recommendations for steering group review          │
│  4. Auto-drafts updated guideline text (CII NLP)                     │
│                                                                       │
│  IF change is minor (new supporting study, no recommendation change): │
│    → Auto-update; version incremented; audit trail logged             │
│  IF change is material (recommendation changes):                      │
│    → Flagged for steering group review (7-day SLA)                   │
│    → Steering group approves/rejects/modifies                        │
│    → Version incremented upon approval                               │
│                                                                       │
│  TRIGGER: Guideline version incremented                               │
└──────────────────────┬──────────────────────────────────────────────┘
                       │ EVENT: guideline.version.updated
                       ▼
┌─────────────────────────────────────────────────────────────────────┐
│  STAGE 5: MNC CRITERIA DERIVATION                                    │
│                                                                       │
│  MNC engine evaluates updated guideline:                              │
│  1. Maps each recommendation to MNC category:                        │
│     → Medically Necessary (Grade A-B, strong evidence)               │
│     → Conditionally Appropriate (Grade B-C, context-dependent)       │
│     → Not Recommended (weak/no evidence, or negative)                │
│  2. Generates machine-readable MNC criteria                          │
│  3. Flags changes from previous MNC version                          │
│                                                                       │
│  IF MNC change is minor (no coverage impact):                         │
│    → Auto-update; notification to CHI liaison                        │
│  IF MNC change is material (coverage impact):                         │
│    → Flagged for MNC governance committee (14-day SLA)               │
│    → Committee includes: clinical expert, health economist, CHI rep  │
│    → Approved MNC submitted to CHI for incorporation                 │
│                                                                       │
│  TRIGGER: MNC criteria version incremented                            │
└──────────────────────┬──────────────────────────────────────────────┘
                       │ EVENT: mnc.criteria.updated
                       ▼
┌─────────────────────────────────────────────────────────────────────┐
│  STAGE 6: DOWNSTREAM ACTIVATION                                      │
│                                                                       │
│  Notifications sent to consuming entities:                            │
│                                                                       │
│  → Integra RCM: Updated coding justification for this condition       │
│  → VBH Co: Updated outcome benchmarks for VBC bundle pricing         │
│  → Welunion: Updated care pathway at point of care                   │
│  → Nama Academy: New CME module generated from guideline update       │
│  → CII: Clinical agent knowledge base refreshed                      │
│  → Nexus MGA: Benefit coverage criteria updated                       │
│                                                                       │
│  CME credit awarded to contributing physicians (Learning Passport)    │
└─────────────────────────────────────────────────────────────────────┘
```

---

## 2. GOVERNANCE MODEL

### Who Approves What

| Decision | Approver | SLA | Escalation |
|----------|---------|-----|-----------|
| PubHelper SOR grading (Level 1-5) | PubHelper Evidence Engine (automated) + project lead review | 48 hours post-completion | PubHelper Director |
| Journal acceptance | Waraqa editorial board + peer reviewers | Per journal SLA (30-90 days) | Editor-in-Chief |
| Knowledge graph indexing | Automated (no human gate) | <24 hours post-acceptance | Evidence Platform CTO |
| Minor guideline update (no recommendation change) | Automated | <7 days | Guideline steering group |
| Material guideline update (recommendation changes) | Specialty steering group (3-5 experts) | 7 days | TKG Group Lead |
| Minor MNC update (no coverage impact) | Automated + CHI liaison notification | <7 days | MNC governance committee |
| Material MNC update (coverage impact) | MNC governance committee (clinician + economist + CHI rep) | 14 days | Founder/Group CEO |

### Quality Gates

| Gate | Check | Blocker? |
|------|-------|---------|
| **G1: PubHelper Output** | SOR score ≥ 15 (Grade B+) for guideline eligibility | Yes — Grade C evidence can inform but not change guidelines |
| **G2: Peer Review** | Journal peer review passed | Yes — unpublished evidence does not enter knowledge graph |
| **G3: Evidence Fusion** | New evidence must map to existing ICD-10/condition taxonomy | No — unmapped evidence queued for taxonomy expansion |
| **G4: Steering Review** | Material changes require human expert approval | Yes — prevents algorithmic guideline changes without clinical judgment |
| **G5: MNC Impact Assessment** | Coverage-impacting MNC changes require health economics review | Yes — prevents unintended financial consequences |

---

## 3. DATA SCHEMA

### PubHelper → Evidence Platform Handoff Schema

```json
{
  "pubhelper_project_id": "PH-2026-EM-007",
  "project_type": "systematic_review",
  "pico": {
    "population": "Adult patients with acute chest pain in Saudi EDs",
    "intervention": "HEART score-based triage",
    "comparator": "Standard clinical judgment triage",
    "outcome": "Missed ACS rate, ED LOS, 30-day MACE"
  },
  "evidence_grading": {
    "study_design_score": 4,
    "methodology_score": 4,
    "data_integrity_score": 3,
    "local_relevance_score": 4,
    "publication_score": 3,
    "total_score": 18,
    "sor_grade": "B",
    "evidence_level": 3
  },
  "conditions_icd10": ["I20", "I21", "R07.9"],
  "interventions": ["HEART_score_triage"],
  "key_findings": [
    {
      "finding": "HEART score reduces missed ACS by 3.2% vs clinical judgment",
      "effect_size": "RR 0.68 (95% CI: 0.52-0.89)",
      "certainty": "moderate"
    }
  ],
  "linked_guidelines": ["LG-EM-CHEST-PAIN-001"],
  "target_journal": "SJEM",
  "manuscript_ready": true,
  "evidence_tables": [...],
  "contributing_physicians": ["DR-001", "DR-015", "DR-042"],
  "cme_credits_generated": 3
}
```

---

## 4. LATENCY TARGETS

| Stage | Target Latency | Acceptable Maximum |
|-------|---------------|-------------------|
| PubHelper completion → journal submission | <48 hours (automated) | 7 days |
| Journal acceptance → knowledge graph indexing | <24 hours (automated) | 48 hours |
| Knowledge graph update → guideline flag | <1 hour (automated) | 4 hours |
| Minor guideline update → point-of-care refresh | <7 days | 14 days |
| Material guideline update → steering approval | <7 days (SLA) | 14 days |
| MNC criteria update → CHI submission | <14 days (SLA) | 30 days |
| **Total: PubHelper completion → live clinical impact** | **~30 days (minor)** | **~60 days (material)** |

*Compare: Traditional guideline update cycle = 3-5 YEARS. This pipeline achieves 30-60 DAYS.*

---

*Aligned to: THEEB_ECOSYSTEM_V2_2026.md | Live Guidelines Platform*

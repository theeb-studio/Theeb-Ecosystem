# MNC DERIVATION ALGORITHM & GOVERNANCE
## How Live Guidelines Become Medical Necessity Criteria
**Version 1.0 | March 2026 | Confidential**

---

## 1. THE DERIVATION RULES

For each recommendation in a Live Guideline, the MNC engine applies:

```
IF recommendation.sor_grade = "A" AND evidence_level ≥ 4:
    → MNC category = "MEDICALLY NECESSARY"
    → Pre-auth: Auto-approve

IF recommendation.sor_grade = "B" AND evidence_level ≥ 3:
    → MNC category = "MEDICALLY NECESSARY" (with documentation)
    → Pre-auth: Auto-approve with clinical note

IF recommendation.sor_grade = "B" AND evidence_level = 2:
    → MNC category = "CONDITIONALLY APPROPRIATE"
    → Pre-auth: Requires clinical justification

IF recommendation.sor_grade = "C" OR evidence_level ≤ 1:
    → MNC category = "NOT RECOMMENDED" (or "EMERGING")
    → Pre-auth: Denial unless appeal with supporting evidence

IF intervention has negative evidence (harm > benefit):
    → MNC category = "CONTRAINDICATED"
    → Pre-auth: Automatic denial
```

## 2. GOVERNANCE

| Decision | Approver | SLA |
|----------|---------|-----|
| Auto-derived MNC (no coverage impact) | Automated + CHI liaison notification | <7 days |
| MNC with coverage impact | MNC Governance Committee: 1 clinical expert + 1 health economist + 1 CHI representative | 14 days |
| MNC affecting VBC bundle pricing | TVG review (Integra RCM + VBH Co) + MNC Committee | 21 days |

## 3. FEEDBACK LOOP

```
Integra RCM denial patterns → MNC criteria reviewed
    → If denials cluster on a "conditionally appropriate" criterion
    → AND clinical evidence supports medical necessity
    → → Criterion upgraded to "medically necessary"
    → → Denial rate drops
    → → Payer-provider alignment improves
```

## 4. UPDATE FREQUENCY

| Trigger | MNC Update |
|---------|-----------|
| New PubHelper study published (Grade A-B) | Within 30 days |
| Quarterly evidence review cycle | Every 90 days |
| CHI regulatory directive | Within 14 days |
| Payer denial pattern anomaly | Ad hoc review |

---

*Aligned to: LIVE_GUIDELINES_PLATFORM.md | PUBHELPER_EVIDENCE_PIPELINE_SPEC.md*

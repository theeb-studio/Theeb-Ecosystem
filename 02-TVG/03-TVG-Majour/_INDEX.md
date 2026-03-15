# TVG-VBH — VALUE-BASED HEALTHCARE COMPANY
**Entity Code: TVG-03 | Group: Theeb Value Group | Layers: 3+4 — Intelligence + Contracting**
**Note: Previously referred to as "Majour" in older documents. Folder name retained.**

---

## Identity
The Value-Based Healthcare Company is TVG's **measurement, intelligence, and contracting platform** — aggregating data from Layers 1 and 2, adding patient-reported outcomes, and producing the intelligence that makes outcome-based contracts mathematically defensible.

## The Core Problem It Solves
Without this platform, value-based contracts are theoretical. With it, contracts become mathematically viable: outcomes are defined, baselines established, and performance measured against agreed benchmarks.

## Layer 3 — Value Intelligence

### Cost-of-Care Analytics
- Episode-level total cost (provider + pharmacy + diagnostics)
- DRG-level cost benchmarking across the provider network
- Cost variation: identifies high-cost outliers and low-cost exemplars

### Patient Outcome Tracking (PROMs)
- Validated instruments: ICHOM sets, PHQ-9, HbA1c targets, EQ-5D, WOMAC, PROMIS
- Digital PROMs via patient app, SMS, or tablet at point of care
- CCHI-compliant PROMs data model (aligned with CCHI mandate)
- Outcome benchmarking by provider, condition, payer

### Population Health Analytics
- Chronic disease registry (diabetes, hypertension, COPD, mental health)
- Risk stratification: identify high-risk patients before costly episodes
- Preventive care gap analysis

### AR-DRG Intelligence Module
- DRG grouper integrated with Integra RCM coding output
- Case-mix index tracking per hospital
- Revenue impact modeling for proposed tariff changes

## Layer 4 — Outcome-Based Contracting

### Bundled Payment Engine
- Condition-specific bundles (CHI 7 priority conditions: AMI, hip/knee, diabetes, maternity, COPD, mental health, oncology)
- Risk-adjusted pricing benchmarked on Layer 3 cost data
- Episode attribution and reconciliation at episode close

### Shared Savings Contracts
- Provider performance vs. quality benchmarks
- Savings calculation and distribution rules
- Gainsharing for multi-specialty care teams

### VBP Procurement
- Employer-facing outcome-tied contracts
- CHI/CNHI procurement alignment
- Government-facing bundled payment frameworks

## Revenue Model
- SaaS subscription per provider (tiered by bed count / volume)
- Outcome measurement-as-a-service for payer clients
- Population health program fees from employers
- Transaction fee on settled episodes (0.5–1.5% of bundle value)
- Shared upside: 10–20% of generated savings

## Data Architecture
- Sources: Integra RCM claims, MGA payer data, PROMs, pharmacy (TAP), lab
- Integration: HL7 FHIR APIs — overlay only, no HIS replacement
- Privacy: PDPL compliant, de-identified at rest
- Governance: Data stays in KSA; provider retains clinical ownership

## Strategic Layer (this folder)
VBHC strategy, PROMs architecture, investor materials, EXPRO partnership.

## Status: Design and Build Phase (parallel to Layer 2)

## Rule: Strategy here, Operations in Server when established.

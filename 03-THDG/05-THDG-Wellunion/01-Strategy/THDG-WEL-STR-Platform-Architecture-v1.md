# Welunion — Platform Architecture & Strategy
**Version 2.0 | Updated March 2026**
**Architecture Reference: `00-TAK-ROOT/MASTER-ARCHITECTURE.md` — Part Four**

> **Structural Update (March 2026):** Welunion is now the primary platform and flagship
> of THDG — not just a holding company. It is designed as a three-layer integrated
> platform (Technology + MSO + Clinic Network). Integrative Health and Union Clinics
> will be absorbed into Welunion as it scales.

---

## Entity Overview
**Name:** Welunion
**Role:** THDG Flagship — Technology Platform + MSO + Clinic Network
**Three Layers:** WellTech (technology) + WellCare (MSO) + WellClinics (clinic network)
**Current Assets:** Mental health center (Laban, Riyadh) + integrated platform development
**Vision:** Become the primary integrated healthcare delivery platform of Saudi Arabia

---

## Corporate Structure

```
WellUnion (HoldCo)  ← Series A investment enters here
│
├── WellCare (MSO)
│   - Holds all MOH clinical licenses
│   - Manages clinical quality and operations
│   - Fee: Base management fee + 2% of UC revenue + quality bonus
│
├── WellTech (PropCo)
│   - Owns all IP: EHR, Patient App, AI triage, dashboards
│   - Fee: 6-8% of revenue (hybrid incentive structure)
│   - Valued at tech multiples — isolated from clinical liability
│
└── WellClinics (AssetCo) = Union Clinics (THDG-UCL)
    - Owns all 71 physical clinics
    - Owns all 7 revenue divisions
    - Bears all direct costs
    - Captures 100% of external patient/insurer revenue
```

**Design purpose:** Isolates clinical liability at AssetCo level, centralizes IP valuation at tech multiples, and enables asset-backed debt financing for clinic buildouts.

---

## Current Operating Entity: Mental Health Center

**Location:** Laban area, Riyadh
**Focus:** Psychiatry + mental health services
**Model:** Commission-based marketplace (25% take rate)

### Operational Files (Dropbox/Server/Wellunion/)
- `Profit and Loss HOLDING As of Dec 31 2025.xlsx`
- `Psychiatry Health Center-Ver01.xlsx`
- `Updated Riyadh-Laban Business Model-Mental Center.xlsx`
- `mental-health-pl-unit-economics.pdf`
- `Well_Healthcare_Blueprint.pdf` ← Series A pitch deck

### Mental Health Division Economics
- B2B-first acquisition lowers CAC to **SAR 200**
- Zero fixed provider costs (marketplace model)
- 25% take rate on all consultations
- Demand-driven: provider supply scales with demand

---

## WellTech: The Proprietary Technology Stack

### Built (Proprietary IP — highest strategic value)
| Asset | Description |
|-------|-------------|
| Patient App | Arabic-first UX, unified across all 7 divisions |
| Unified EHR | Hybrid care design — physical + virtual on one record |
| AI Triage | Clinical decision support, reduces unnecessary escalation |
| Corporate Employer Dashboard | B2B health analytics for HR teams |

### Integrated (Ecosystem connections)
| Integration | Purpose |
|-------------|---------|
| Wasfaty | National e-prescription platform (MOH) |
| NPHIES | CCHI insurance claims processing |

### Bought (Commodity infrastructure)
| Component | Provider |
|-----------|----------|
| Cloud | AWS / Saudi Cloud |
| Telehealth SDK | Twilio / Vonage |
| Security | Auth0 |

**Competitive advantage:** No legacy hospital IT constraints — unified standard from day one.

---

## WellTech Fee Structure
- Receives 6–8% of WellClinics revenue as hybrid incentive fee
- Incentivizes platform adoption and utilization growth
- IP protected at the PropCo level → tech valuation multiples at exit

---

## The 7 Revenue Divisions (WellClinics AssetCo)

| Division | Managed By | Model |
|----------|-----------|-------|
| Urgent Care (UC) | WellCare/WellClinics | Walk-in FFS, CCHI-insured |
| Home Care | WellClinics | 3-tier fleet (SAR 400/800/1,200) |
| Virtual Care | WellTech | Family Doctor subscription + Quick Consult + Expert Consult |
| Mental Health | WellUnion | Commission marketplace, 25% take rate |
| CDM | WellCare | Hybrid PMPM (SAR 100–350) + FFS |
| Men's Health | WellClinics | Cash-pay virtual-first bundles (SAR 350–400) |
| Doula Program | THDG-MOB | B2C cash-pay prenatal/postpartum |

---

## Go-To-Market: B2B First

**Target:** Top 200 Saudi employers
- Employers control **56.4%** of the SAR 42B insurance market
- B2B contracts lock in 12–24 months of predictable utilization
- Entry point: Corporate employer health dashboards (WellTech)
- Value proposition: Address $15.5B obesity-related absenteeism problem

**B2C follows B2B:** Once clinic is anchored with corporate population, walk-in B2C fills remaining capacity.

---

## Series A: SAR 38–45M Raise (at WellUnion HoldCo level)

| Use | SAR | % |
|-----|-----|---|
| WellCare MSO (team, ops, clinical) | 12M | 26% |
| WellTech Platform (app, EHR, data) | 10M | 22% |
| Working Capital (to breakeven) | 10M | 22% |
| WellClinics Buildout (11 clinics) | 5.5M | 12% |
| Sales & Marketing (B2B + B2C) | 5M | 11% |
| HoldCo & Corporate | 3M | 7% |

**Peak cash need: SAR 29.4M — one round, no follow-on needed until Y2 profitability.**

---

## Financial Milestones

| Milestone | Timeline |
|-----------|----------|
| First B2B contract signed | Month 1–3 |
| Clinic 1 open (Riyadh) | Month 7 |
| Clinics 1–7 open | Month 11 |
| Portfolio EBITDA positive | Year 2 |
| SAR 179M revenue | Year 3 (41 clinics) |
| SAR 479M revenue, SAR 199.9M EBITDA | Year 5 (71 clinics) |

---

## Saudization & Regulatory

- MOH clinic licenses held by WellCare (MSO)
- CCHI accreditation for all insurers
- Wasfaty and NPHIES full integration required for operations
- Nitaqat: 30% → 50% Saudi employees (Y1 → Y5)
- Regulatory Sandbox application filed (ref: `04-SHARED/Regulatory-Library/SHR-REG-Regulatory-Sandbox-Application-EN-v1.pdf`)

---

## Investment Thesis Summary

> **71 owned clinics. 7 synergistic revenue divisions. SAR 29.4M in → SAR 199.9M EBITDA out.**
> The corporate architecture protects IP at tech multiples while leveraging asset-backed debt for physical expansion.
> Zero competitors operate an integrated hybrid model in Saudi Arabia.
> **The window is now.**

---

*Source: Well Healthcare Blueprint — Series A Pitch Deck (2025)*
*Dropbox: `Server/Wellunion/Well_Healthcare_Blueprint.pdf`*

# THDG Clinical Ventures — Service Integration Map
**Document Type: Integration Architecture | Group: THDG**
**Entities: Welunion · CoClinics · Dawali Vascular**
**Version: March 2026**

---

## The Core Concept: The Drawer Model

> Three entities. One patient journey. No gaps, no leakage.

The **Drawer Model** describes how THDG's three front-line entities — Welunion, CoClinics, and Dawali — interlock like drawers in a cabinet. Each drawer handles a distinct level of care complexity. The patient moves between drawers as their needs escalate or de-escalate — seamlessly, with clinical handoff, shared data, and coordinated billing.

**No competitor can replicate this:** Replicating Welunion alone is hard. Replicating Dawali alone is hard. Replicating the coordination layer between all three — with shared outcomes data flowing to TVG, shared pharmacy at TAP, and shared training at Nama Academy — is impossible to duplicate quickly.

---

## Entity Summary

| Entity | Type | Primary Function | Care Level |
|--------|------|-----------------|------------|
| **Welunion** | THDG flagship (Theeb-owned) | Primary care, CDM, digital health, home care | Level 1 — Foundation |
| **CoClinics** | THDG entity (co-sharing model) | Shared specialty clinics — multi-discipline | Level 2 — Specialist |
| **Dawali Vascular** | THDG-CLV-03 (MSO partnership) | Interventional radiology — catheter procedures | Level 3 — Intervention |

---

## Full Service Integration Map

### Layer 1 → Welunion (Primary & Chronic Care)

**What Welunion does:**
- First point of contact for the patient
- Manages acute primary care (GP, family medicine, urgent care)
- Enrolls chronic disease patients (diabetes, hypertension, obesity, mental health)
- Operates 24/7 digital telehealth triage
- Manages home care visits (post-discharge, elderly, wound care)
- Runs TAP Pharmacy dispensing at point of care

**What Welunion detects and escalates:**

| Clinical Finding | Escalation Target | Escalation Type |
|-----------------|------------------|----------------|
| Varicose veins (confirmed duplex) | Dawali | Structured referral |
| Uterine fibroids (symptomatic) | Dawali | Structured referral |
| BPH / lower urinary tract symptoms | Dawali or CoClinics urology | Based on severity |
| Pelvic congestion pain (female) | Dawali | Structured referral |
| Diabetic foot — vascular risk | Dawali | Urgent referral pathway |
| Dialysis patient needing vascular access | Dawali | Coordinated referral |
| Back pain unresponsive to conservative Rx | Dawali | Structured referral |
| Mental health (child/adolescent) | CLV-01 Pediatric Mental Health | Structured referral |
| Mental health (adult) | CLV-02 Adult Mental Health Clinic | Structured referral |
| Specialty beyond GP scope | CoClinics (relevant specialty) | Structured referral |

---

### Layer 2 → CoClinics (Shared Specialty)

**What CoClinics does:**
- Shared-space specialist clinic model (multiple specialties, one location)
- Serves as the intermediate complexity layer between primary care and invasive intervention
- Shares infrastructure and scheduling with Welunion

**What CoClinics detects and escalates:**

| Clinical Finding | Escalation Target | Escalation Type |
|-----------------|------------------|----------------|
| Fibroids identified by OB/GYN specialist | Dawali | Specialist-to-specialist referral |
| BPH confirmed by urology specialist | Dawali | Specialist-to-specialist referral |
| Vascular finding requiring endovascular Rx | Dawali | Specialist-to-specialist referral |
| Patient requires only conservative management | Welunion CDM | De-escalation / step-down |
| Patient resolved — primary care follow-up | Welunion | Return pathway |

---

### Layer 3 → Dawali Vascular (Interventional Procedures)

**What Dawali does:**
- Performs catheter-based, image-guided procedures under local anesthesia
- Treats conditions that would otherwise require surgery or long-term pharmacological management
- Handles highest-complexity, highest-value procedures in the drawer

**What Dawali sends back:**

| Post-Procedure Need | Return Destination | Timing |
|--------------------|--------------------|--------|
| 30/60/90-day clinical follow-up | Welunion (any branch) | Standard protocol |
| Wound care, dressing changes | Welunion home care or clinic | Per procedure type |
| Medication management | Welunion GP + TAP Pharmacy | Immediately post-discharge |
| Chronic disease enrollment (e.g., diabetic foot) | Welunion CDM program | Post-procedure stabilization |
| Recurrence monitoring | Welunion digital / annual check | Ongoing |
| Procedure outcome data | TVG VBH Company | Automated data feed |

---

## Cross-Entity Shared Infrastructure

All three entities operate on shared THDG infrastructure — they do not duplicate back-office functions:

| Infrastructure Layer | Provider | Benefit to All Three |
|---------------------|----------|---------------------|
| **EHR & Patient Records** | Welunion tech platform | Single patient record — referral summary auto-generated |
| **Booking & Scheduling** | Welunion CRM | One booking interface for patient navigation |
| **Pharmacy Dispensing** | TAP Pharmacy | All three entities prescribe → TAP fills at point of care |
| **HR & Compliance** | Welunion MSO services | Dawali and CoClinics use shared credentialing and HR |
| **CME & Training** | Nama Academy (TKG) | All clinical staff train through shared SCFHS-accredited programs |
| **Outcomes Measurement** | TVG VBH Company | Shared outcomes data infrastructure — one insurer report covers all three |
| **Revenue Cycle** | Integra RCM (TVG) | Billing and claims managed uniformly — reduces admin burden at all three |
| **Insurance Products** | MGA/Nexus (TVG) | Procedure bundles (e.g., varicose vein package) designed to cover Dawali + Welunion follow-up in one policy |

---

## Patient Journey Examples

### Example A — Varicose Vein Patient

```
Patient books Welunion GP appointment (leg pain, visible veins)
  ↓
Welunion GP confirms clinical suspicion → orders duplex ultrasound
  ↓
Duplex confirms reflux → Welunion generates structured referral to Dawali
  ↓
Dawali performs endovenous ablation (outpatient, 45 min, local anesthesia)
  ↓
Patient discharged same day → prescription to TAP Pharmacy
  ↓
30-day follow-up booked at Welunion clinic
  ↓
Outcome score (venous clinical severity score) → TVG VBH dashboard
  ↓
Insurer receives: Welunion diagnosis + Dawali procedure + follow-up = complete episode bundle
```

### Example B — Diabetic Foot (Limb Salvage)

```
Welunion CDM patient (diabetic, enrolled 6 months)
  ↓
Welunion nurse flags worsening wound + reduced pedal pulse
  ↓
Welunion GP urgent referral to Dawali (same-day or 24h SLA)
  ↓
Dawali performs angioplasty / endovascular revascularization
  ↓
Limb preserved — patient returns to Welunion CDM program
  ↓
Home care wound visits scheduled (Welunion home care fleet)
  ↓
Outcome: amputation avoided → VBH Company reports cost-savings to insurer
```

### Example C — Uterine Fibroid (OB/GYN pathway)

```
Patient attends CoClinics OB/GYN appointment (heavy bleeding, pelvic pain)
  ↓
OB/GYN confirms symptomatic fibroids on ultrasound
  ↓
OB/GYN refers to Dawali for UFE (uterine fibroid embolization)
  ↓
Dawali performs UFE — 90-minute procedure, overnight stay
  ↓
Post-discharge: OB/GYN follow-up at CoClinics (4 weeks)
  ↓
Primary care follow-up at Welunion (6 months, 1 year)
  ↓
Patient remains within the drawer — never leaves the ecosystem
```

---

## Revenue Architecture Across the Drawer

Each entity invoices separately. No cross-subsidization — each company earns its own P&L.

| Entity | Revenue Source | Shared Enabler |
|--------|---------------|----------------|
| Welunion | Consultation fees, CDM subscriptions, home care visits | Integra RCM billing |
| CoClinics | Specialist consultation fees, co-clinic facility fees | Integra RCM billing |
| Dawali | Procedure fees (interventional radiology — high margin) | Integra RCM billing |
| TAP Pharmacy | Prescription dispensing margin | Welunion CRM integration |
| TVG VBH | Value-based contracts (insurer pays for outcomes across the full episode) | Outcomes data from all three |

**Episode-level bundled billing:** TVG can eventually present insurers with a **full episode price** — e.g., SAR X for complete varicose vein management (Welunion diagnosis + Dawali ablation + Welunion follow-up) — rather than fee-for-service at each step. This is the Layer 4 VBH model in action.

---

## Why This Cannot Be Replicated

1. **Welunion alone** = a good primary care platform. Many competitors exist.
2. **Dawali alone** = a good interventional radiology center. Competitors exist.
3. **Welunion + Dawali** = a referral partnership. Any two hospitals can sign a referral MOU.
4. **Welunion + CoClinics + Dawali + TAP Pharmacy + Integra RCM + VBH outcomes + MGA insurance bundle + Nama CME training** = an integrated episode-of-care system built on shared infrastructure, owned data, and aligned financial incentives.

**No competitor can buy this. It has to be built from the inside.**

---

*Document Owner: THDG Strategy*
*Last Updated: March 2026*
*Classification: Confidential — Group Strategy*

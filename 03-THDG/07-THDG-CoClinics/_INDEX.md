# THDG-COC — COCLINICS
**Entity Code: THDG-COC | Group: Theeb Health Delivery Group**
**Role: Shared-Space Specialty Clinic Model — The Intermediate Complexity Layer**

---

## Identity

**CoClinics** is a THDG entity that operates on a **co-clinic shared-space model**: multiple medical specialties share a single physical location, scheduling infrastructure, and back-office services. CoClinics sits between Welunion (primary care) and Dawali (interventional procedures) in the THDG service drawer — handling specialist consultations that are beyond GP scope but do not yet require invasive intervention.

> **Key principle:** CoClinics is the specialist consultation layer.
> Welunion sends patients up. Dawali receives patients forward.
> CoClinics handles what is in between.

---

## Business Model — Co-Sharing Clinic

| Dimension | Detail |
|-----------|--------|
| **Model** | Shared-space, shared-infrastructure specialist clinics |
| **Specialists** | Physicians rent/share clinic space, equipment, and support staff |
| **Infrastructure owner** | Theeb (CoClinics entity) |
| **Revenue** | Facility fees + specialist session fees + shared services |
| **Ownership** | TBD — to be defined individually per CoClinics location |

---

## Clinical Scope

CoClinics operates specialist clinics across multiple disciplines. Target specialties include (but are not limited to):

| Specialty | Integration Value |
|-----------|------------------|
| **OB/GYN** | Detects fibroids → refers to Dawali (UFE); manages maternal health alongside Welunion |
| **Urology** | Confirms BPH severity → refers to Dawali (PAE) or manages medically |
| **Vascular Surgery** | Works alongside Dawali for pre/post procedure assessment |
| **Orthopedics** | Back pain pathway — conservative management before Dawali spine intervention |
| **Dermatology** | Chronic skin conditions — complements Welunion CDM |
| **Pediatrics** | Feeds into CLV-01 pediatric mental health when indicated |
| **Internal Medicine** | Complex chronic disease co-management with Welunion CDM |

---

## Position in the THDG Drawer

```
WELUNION (Level 1 — Primary Care)
    ↓  Escalation when GP scope exceeded
COCLINICS (Level 2 — Specialist Consultation)
    ↓  Escalation when specialist recommends procedure
DAWALI (Level 3 — Interventional Procedure)
    ↓  Return flow post-procedure
WELUNION (Level 1 — Follow-up, CDM, monitoring)
```

**CoClinics is also a direct patient entry point** — patients can book directly with a specialist without going through Welunion first. In this case, CoClinics may refer down to Welunion for primary care follow-up or up to Dawali for intervention.

---

## Shared Infrastructure with THDG

| Service | Provider |
|---------|----------|
| EHR and patient records | Welunion tech platform |
| Booking and scheduling | Welunion CRM |
| Billing and claims | Integra RCM (TVG) |
| HR and credentialing | Welunion MSO |
| Pharmacy dispensing | TAP Pharmacy |
| CME and staff training | Nama Academy (TKG) |
| Outcomes measurement | TVG VBH Company |

---

## Development Status

> **Note:** CoClinics is an active THDG entity. Operational details, location pipeline, and specialty mix to be documented as the entity formalizes.

→ Operational files: `/Server/CoClinics/` (to be created)
→ Integration architecture: `06-THDG-Clinical-Ventures/THDG-CLV-INT-Service-Integration-Map.md`

## Rule: Strategy here, Operations in Server.

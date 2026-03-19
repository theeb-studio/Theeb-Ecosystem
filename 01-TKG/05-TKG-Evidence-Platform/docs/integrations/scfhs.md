# Saudi Evidence — SCFHS Integration Specification
**Version 1.0 | March 2026**

---

## Integration Overview

Saudi Evidence requires integration with SCFHS (Saudi Commission for Health Specialties) for two critical functions:

1. **User Verification** — Confirm that users are licensed Saudi healthcare professionals
2. **CME Credit Synchronization** — Report earned CME credits to SCFHS's tracking system

---

## Phase 1 (V1): Manual Verification + Offline CME

**Available immediately without SCFHS API access.**

### User Verification (V1)
- User enters SCFHS license number during registration
- System validates format (numeric, correct length)
- Manual verification batch: weekly export of new registrations sent to SCFHS for confirmation
- Users marked as "verified" once confirmed
- Unverified users get read-only access (search works, CME credits are logged but not official)

### CME Tracking (V1)
- All CME activities logged internally in Learning Passport
- Clinician can export a **CME Activity Report** (PDF) for manual SCFHS submission
- Report includes: activity type, date, duration, verification method, credits earned
- Format aligned with SCFHS CME submission requirements

---

## Phase 2 (V2): API Integration

**Requires formal SCFHS partnership agreement.**

### User Verification (V2)
```
POST /scfhs/verify
Request: { scfhsNumber: string, nationalId: string }
Response: {
  verified: boolean,
  fullName: string,
  specialty: string,
  licenseStatus: 'active' | 'expired' | 'suspended',
  licenseExpiry: Date,
  currentCmeCredits: number,
  requiredCmeCredits: number
}
```

### SSO Integration (V2)
- SCFHS provides OAuth 2.0 / SAML identity provider
- Saudi Evidence acts as a service provider
- Single sign-on flow:
  1. Clinician clicks "Sign in with SCFHS"
  2. Redirected to SCFHS login page
  3. SCFHS authenticates and returns token with clinician profile
  4. Saudi Evidence creates/updates local profile from SCFHS data
  5. Session established

### CME Credit Reporting (V2)
```
POST /scfhs/cme/report
Request: {
  scfhsNumber: string,
  activities: [{
    activityId: string,
    activityType: string,
    providerId: string,         // Saudi Evidence SCFHS provider ID
    credits: number,
    completedAt: DateTime,
    verificationMethod: string,
    evidenceUrl?: string        // Link to quiz/assessment result
  }]
}
Response: {
  accepted: number,
  rejected: number,
  errors: [{activityId, reason}]
}
```

### SCFHS Event Webhook (V2)
- SCFHS notifies Saudi Evidence of:
  - License renewals/expirations
  - Specialty changes
  - CME credit adjustments
  - New regulatory requirements

---

## Phase 3 (V3): Deep Integration

### Learning Passport ↔ SCFHS Profile Sync
- Bidirectional sync: Saudi Evidence Learning Passport reflects SCFHS official records
- Real-time credit updates
- Automatic competency mapping against SCFHS specialty requirements
- Promotion pathway tracking (credits toward academic progression)

### SCFHS Accredited Activity Provider
- Saudi Evidence registered as an official SCFHS-accredited CME provider
- Activities auto-approved for CME credit (no manual review)
- Nama Academy courses delivered through Saudi Evidence automatically accredited

---

## Technical Requirements for SCFHS Integration

| Requirement | Detail |
|------------|--------|
| Data hosting | All SCFHS data processed and stored in Saudi sovereign cloud |
| Encryption | TLS 1.3 for transit, AES-256 for storage |
| Authentication | OAuth 2.0 with PKCE or SAML 2.0 |
| Audit trail | All SCFHS API calls logged with timestamp, request, response |
| PDPL compliance | Clinician consent required before SCFHS data sync |
| Availability | 99.9% uptime SLA for SCFHS-facing APIs |
| Rate limiting | Max 1000 requests/minute to SCFHS APIs |

---

## The SCFHS Value Proposition

**What Saudi Evidence offers SCFHS:**

| Current State (UpToDate) | With Saudi Evidence |
|-------------------------|---------------------|
| SAR 20M+/year cost | Free (V1) or fraction of cost |
| ~15-30% utilization | Target 50%+ utilization |
| English only | Arabic + English |
| No Saudi content | Saudi-first guidelines, local evidence |
| No CME integration | Built-in CME with auto-credit |
| No usage analytics | Full workforce intelligence dashboard |
| No research connection | PubHelper intake from every search |
| One product | Ecosystem of 12 integrated entities |

**The pitch:** "SCFHS can redirect even 30% of its UpToDate budget toward Saudi Evidence and get a locally built, higher-utilization, CME-integrated platform that generates Saudi-specific workforce intelligence — while the remaining UpToDate budget stays active during transition."

---

*Aligned to: Saudi Evidence System Architecture | THEEB_ECOSYSTEM_V2_2026.md*

# Saudi Evidence — System Architecture
**Version 1.0 | March 2026**

---

## Architecture Principles

1. **Saudi Evidence is a product, not infrastructure** — it consumes CII (TTG) APIs; it does NOT build its own AI/NLP
2. **Free first** — no paywall in V1; monetization hooks exist but are dormant
3. **API-first** — every feature exposed as API for future integrations (mobile, WhatsApp, HIS/EHR)
4. **Saudi-hosted** — sovereign cloud, PDPL compliant, NCA ECC aligned
5. **Modular** — each feature is an independent service behind feature flags

---

## High-Level Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                     CLIENT LAYER                                 │
│  ┌───────────┐  ┌───────────┐  ┌───────────┐  ┌───────────┐    │
│  │  Web App   │  │Mobile App │  │ WhatsApp  │  │ HIS/EHR   │    │
│  │ (Next.js)  │  │(React     │  │  Bot      │  │ Plugin    │    │
│  │            │  │ Native)   │  │           │  │ (FHIR)    │    │
│  └─────┬─────┘  └─────┬─────┘  └─────┬─────┘  └─────┬─────┘    │
│        └───────────────┴───────────────┴───────────────┘         │
│                              │ HTTPS/REST                        │
└──────────────────────────────┼───────────────────────────────────┘
                               │
┌──────────────────────────────▼───────────────────────────────────┐
│                     API GATEWAY                                   │
│  Auth (SCFHS SSO / JWT) │ Rate Limiting │ Feature Flags           │
└──────────────────────────────┬───────────────────────────────────┘
                               │
┌──────────────────────────────▼───────────────────────────────────┐
│                   APPLICATION SERVICES                            │
│                                                                   │
│  ┌────────────┐ ┌────────────┐ ┌────────────┐ ┌────────────┐    │
│  │  Evidence   │ │ Guidelines │ │    CME     │ │  PubHelper │    │
│  │  Search     │ │    Hub     │ │  Tracker   │ │  Intake    │    │
│  │  Service    │ │  Service   │ │  Service   │ │  Service   │    │
│  └──────┬─────┘ └──────┬─────┘ └──────┬─────┘ └──────┬─────┘    │
│         │              │              │              │            │
│  ┌──────┴─────┐ ┌──────┴─────┐ ┌──────┴─────┐ ┌─────┴──────┐   │
│  │   User     │ │ Analytics  │ │ Learning   │ │ Institutional│   │
│  │  Profile   │ │ & Insights │ │ Passport   │ │ Dashboard   │   │
│  │  Service   │ │  Service   │ │  Service   │ │  Service    │   │
│  └────────────┘ └────────────┘ └────────────┘ └─────────────┘   │
└──────────────────────────────┬───────────────────────────────────┘
                               │
┌──────────────────────────────▼───────────────────────────────────┐
│                   SHARED INFRASTRUCTURE (TTG-CII Rails)           │
│                                                                   │
│  ┌────────────┐ ┌────────────┐ ┌────────────┐ ┌────────────┐    │
│  │  CII       │ │  Identity  │ │  Knowledge │ │  Sovereign  │    │
│  │  NLP API   │ │  Service   │ │  Graph DB  │ │  Cloud      │    │
│  │  (Layer 2) │ │  (SSO)     │ │  (Neo4j)   │ │  Hosting    │    │
│  └────────────┘ └────────────┘ └────────────┘ └────────────┘    │
└──────────────────────────────────────────────────────────────────┘
                               │
┌──────────────────────────────▼───────────────────────────────────┐
│                   EXTERNAL INTEGRATIONS                           │
│                                                                   │
│  ┌────────────┐ ┌────────────┐ ┌────────────┐ ┌────────────┐    │
│  │DeepEvidence│ │   SCFHS    │ │   Waraqa   │ │    CHI     │    │
│  │  API       │ │   CME API  │ │  Content   │ │  MNC Data  │    │
│  │(PubMed+    │ │ (V2 SSO)   │ │   Feed     │ │            │    │
│  │ Embase)    │ │            │ │            │ │            │    │
│  └────────────┘ └────────────┘ └────────────┘ └────────────┘    │
└──────────────────────────────────────────────────────────────────┘
```

---

## Core Data Models

### User / Clinician

```typescript
interface Clinician {
  id: string;                          // UUID
  scfhsNumber: string;                 // SCFHS license number (primary identifier)
  fullName: string;
  fullNameAr?: string;                 // Arabic name
  email: string;
  phone: string;                       // Saudi mobile (+966)
  specialty: Specialty;                // Enum: Cardiology, EM, Endocrinology, etc.
  subSpecialty?: string;
  currentInstitution?: string;
  institutionId?: string;              // Link to institutional account
  academicRank?: AcademicRank;         // Intern, Resident, Registrar, Consultant, Professor
  region: SaudiRegion;                 // Riyadh, Jeddah, Dammam, etc.
  registeredAt: DateTime;
  lastActiveAt: DateTime;
  learningPassport: LearningPassport;
  preferences: UserPreferences;
}

interface LearningPassport {
  clinicianId: string;
  totalCmeCredits: number;             // Lifetime
  currentYearCredits: number;          // Toward 30/year mandate
  competencyMap: CompetencyScore[];    // Per-domain scores
  coursesCompleted: CourseCompletion[];
  researchContributions: ResearchActivity[];
  scfhsSyncStatus: SyncStatus;        // Synced | Pending | Error
  lastSyncedAt?: DateTime;
}
```

### Search / Evidence Query

```typescript
interface EvidenceQuery {
  id: string;
  clinicianId: string;
  queryText: string;                   // Original natural language query
  queryLanguage: 'ar' | 'en';
  processedQuery: string;             // CII NLP-processed query
  picoExtraction?: PicoFormat;        // Auto-extracted PICO
  results: EvidenceResult[];
  saudiGuidelineMatch?: GuidelineMatch;
  mncMatch?: MncMatch;               // If query matches an MNC scenario
  cmeCreditsEarned: number;
  sessionDurationMs: number;
  createdAt: DateTime;
}

interface EvidenceResult {
  source: 'deepevidence' | 'knowledge_graph' | 'saudi_guideline' | 'live_guideline';
  title: string;
  abstract?: string;
  evidenceLevel: EvidenceLevel;       // Level 1-5 (per PubHelper rubric)
  strengthOfRecommendation?: 'A' | 'B' | 'C';
  citations: Citation[];
  fullTextUrl?: string;
  localRelevance: 'saudi_specific' | 'gcc' | 'international';
}
```

### Guideline

```typescript
interface Guideline {
  id: string;
  title: string;
  titleAr: string;
  societyId?: string;                  // Owning scientific society
  specialty: Specialty;
  conditions: string[];                // ICD-10 codes covered
  version: string;
  publishedAt: DateTime;
  lastUpdatedAt: DateTime;
  source: 'saudi_society' | 'waraqa' | 'international' | 'live_guideline';
  evidenceGrade: 'A' | 'B' | 'C';
  recommendations: Recommendation[];
  mncDerivations?: MncCriterion[];    // Medical Necessity Criteria derived
  relatedCmeModules: string[];        // CME module IDs
  isLiveGuideline: boolean;           // Auto-updated by PubHelper pipeline
  updateHistory: GuidelineVersion[];
}
```

### CME Activity

```typescript
interface CmeActivity {
  id: string;
  clinicianId: string;
  activityType: CmeActivityType;
  // 'evidence_search' | 'guideline_review' | 'quiz_completion'
  // | 'micro_course' | 'case_study' | 'research_contribution'
  // | 'live_course' | 'conference'
  creditsEarned: number;              // In hours
  startedAt: DateTime;
  completedAt?: DateTime;
  verificationMethod: 'auto' | 'quiz' | 'assessment' | 'instructor';
  quizScore?: number;                 // If quiz-based verification
  scfhsReported: boolean;
  scfhsReportedAt?: DateTime;
  relatedGuidelineId?: string;
  relatedCourseId?: string;
  provider: 'saudi_evidence' | 'nama_academy' | 'society';
}
```

---

## API Structure (V1)

### Evidence Search API

```
POST /api/v1/search
Body: { query: string, language: 'ar'|'en', filters?: SearchFilters }
Response: { results: EvidenceResult[], saudiGuidelines: GuidelineMatch[], cmeCredits: number }

Flow:
1. CII NLP processes query (Arabic→structured, English→enhanced)
2. DeepEvidence API called with processed query (PubMed + Embase)
3. Knowledge Graph queried for Saudi guidelines and live guidelines
4. MNC Engine checked for medical necessity matches
5. Results merged, ranked (Saudi-first), and returned
6. CME credit logged if session qualifies
```

### Guidelines API

```
GET  /api/v1/guidelines                          # List all guidelines
GET  /api/v1/guidelines/:id                       # Get specific guideline
GET  /api/v1/guidelines/society/:societyId        # Society's guidelines
GET  /api/v1/guidelines/condition/:icd10Code      # By condition
GET  /api/v1/guidelines/:id/quiz                  # CME quiz for guideline
POST /api/v1/guidelines/:id/quiz/submit           # Submit quiz answers
```

### CME / Learning Passport API

```
GET  /api/v1/cme/passport                         # Get clinician's Learning Passport
GET  /api/v1/cme/credits/current-year             # Current year credits summary
GET  /api/v1/cme/activities                       # List CME activities
POST /api/v1/cme/activities                       # Log new CME activity
POST /api/v1/cme/sync-scfhs                       # Trigger SCFHS sync (V2)
GET  /api/v1/cme/courses                          # Available courses
GET  /api/v1/cme/courses/:id                      # Course details
POST /api/v1/cme/courses/:id/enroll               # Enroll in course
```

### PubHelper Intake API

```
POST /api/v1/pubhelper/questions                  # Submit research question
GET  /api/v1/pubhelper/questions/:id/status        # Track project status
GET  /api/v1/pubhelper/questions/my                # My submitted questions
```

### Institutional Dashboard API (V2 — behind feature flag)

```
GET  /api/v1/institution/:id/dashboard            # Institutional overview
GET  /api/v1/institution/:id/usage                # Usage analytics
GET  /api/v1/institution/:id/compliance           # CBAHI compliance report
GET  /api/v1/institution/:id/knowledge-gaps       # Knowledge gap heatmap
```

---

## Technology Stack (Recommended)

| Layer | Technology | Rationale |
|-------|-----------|-----------|
| Frontend (Web) | Next.js 14 + TypeScript | SSR for SEO, fast loading, Arabic RTL support |
| Frontend (Mobile) | React Native or PWA | Cross-platform, share components with web |
| WhatsApp Integration | WhatsApp Business API | Most-used messaging app in KSA |
| API Gateway | Kong or AWS API Gateway | Rate limiting, auth, feature flags |
| Backend Services | FastAPI (Python) or NestJS (TypeScript) | Python preferred for AI/NLP integration with CII |
| Database | PostgreSQL + Neo4j | Relational (users, CME) + Graph (knowledge graph) |
| Search | Elasticsearch | Fast full-text search for guidelines and content |
| Cache | Redis | Session management, rate limiting, query cache |
| Queue | RabbitMQ or AWS SQS | Async processing (CME logging, SCFHS sync) |
| Hosting | Saudi sovereign cloud (STC Cloud / Alibaba Cloud KSA) | PDPL + NCA compliance |
| CI/CD | GitHub Actions | Standard, well-supported |
| Monitoring | Grafana + Prometheus | Observability |

---

## Feature Flag System

```typescript
const featureFlags = {
  // V1 — Active
  evidenceSearch: true,
  guidelinesHub: true,
  cmeTracking: true,
  learningPassport: true,
  pubhelperIntake: true,

  // V2 — Dormant (activated when ready)
  institutionalDashboard: false,
  scfhsSsoIntegration: false,
  paidCmeCourses: false,
  pharmaInsights: false,
  mncDecisionEngine: false,      // Activated when CHI partnership confirmed
  whatsappBot: false,

  // V3 — Future
  ehrPlugin: false,
  researchWorkbench: false,
  aiClinicalAgents: false,       // CII Layer 3 integration
};
```

---

## Deployment Architecture

```
┌──────────────────────────────────────┐
│         SAUDI SOVEREIGN CLOUD         │
│                                       │
│  ┌─────────┐  ┌─────────┐           │
│  │ Web App  │  │   API   │           │
│  │ (CDN)    │  │ Gateway │           │
│  └────┬─────┘  └────┬────┘           │
│       │              │                │
│  ┌────▼──────────────▼────┐          │
│  │   Kubernetes Cluster    │          │
│  │                         │          │
│  │  ┌─────┐ ┌─────┐      │          │
│  │  │Svc 1│ │Svc 2│ ...  │          │
│  │  └─────┘ └─────┘      │          │
│  └────────────────────────┘          │
│       │              │                │
│  ┌────▼────┐  ┌──────▼──────┐       │
│  │PostgreSQL│  │  Neo4j      │       │
│  │ (Users,  │  │ (Knowledge  │       │
│  │  CME)    │  │  Graph)     │       │
│  └──────────┘  └─────────────┘       │
│                                       │
│  All data stays within Saudi borders  │
└──────────────────────────────────────┘
         │                    │
    ┌────▼────┐         ┌────▼────┐
    │  CII    │         │  Deep   │
    │  APIs   │         │Evidence │
    │ (TTG)   │         │  API    │
    └─────────┘         └─────────┘
```

---

*Aligned to: THEEB_ECOSYSTEM_V2_2026.md | Technology Ownership Architecture*

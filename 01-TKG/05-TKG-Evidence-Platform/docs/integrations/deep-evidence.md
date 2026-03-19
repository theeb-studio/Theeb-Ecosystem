# Saudi Evidence — DeepEvidence Integration Specification
**Version 1.0 | March 2026**

---

## Partner Overview

**DeepEvidence** is an AI-powered medical evidence retrieval engine that searches and synthesizes results from PubMed and Embase. It provides the global evidence retrieval capability that Saudi Evidence wraps with a Saudi-focused product layer.

---

## Integration Architecture

```
Clinician Query (Arabic or English)
         │
         ▼
┌─────────────────────────┐
│  CII NLP Layer (TTG)     │
│  - Arabic → English      │
│    translation if needed │
│  - PICO extraction       │
│  - Medical entity        │
│    recognition           │
│  - Saudi context tagging │
└────────┬────────────────┘
         │  Structured query
         ▼
┌─────────────────────────┐     ┌─────────────────────────┐
│  Saudi Evidence Router   │────►│  Knowledge Graph (Local) │
│                          │     │  - Saudi guidelines      │
│  Splits query to:        │     │  - Waraqa publications   │
│  1. DeepEvidence (global)│     │  - Live Guidelines       │
│  2. Knowledge Graph      │     │  - Society content       │
│     (Saudi/local)        │     └─────────────────────────┘
│  3. MNC Engine (if match)│
└────────┬────────────────┘
         │  Structured query
         ▼
┌─────────────────────────┐
│  DeepEvidence API        │
│  - PubMed search         │
│  - Embase search         │
│  - Evidence grading      │
│  - Citation retrieval    │
│  - Abstract synthesis    │
└────────┬────────────────┘
         │  Results
         ▼
┌─────────────────────────┐
│  Saudi Evidence Merger   │
│  - Merge local + global  │
│  - Rank: Saudi-first     │
│  - Tag evidence levels   │
│  - Flag MNC relevance    │
│  - Log for CME credit    │
│  - Flag evidence gaps    │
│    → PubHelper pipeline  │
└─────────────────────────┘
```

---

## API Contract with DeepEvidence

### Search Request

```
POST https://api.deepevidence.com/v1/search
Headers:
  Authorization: Bearer <API_KEY>
  X-Partner-ID: saudi-evidence
  Content-Type: application/json

Body: {
  query: string,                      // Processed English query
  databases: ['pubmed', 'embase'],    // Which databases to search
  filters: {
    dateRange?: { from: string, to: string },
    studyTypes?: string[],            // RCT, meta-analysis, cohort, etc.
    languages?: string[],
    populations?: string[],           // If available: 'saudi', 'arab', 'middle_east'
  },
  maxResults: number,                 // Default: 20
  includeAbstracts: boolean,          // Default: true
  evidenceGrading: boolean,           // Default: true
  synthesize: boolean                 // AI synthesis of results
}
```

### Search Response

```
Response: {
  queryId: string,
  processedQuery: string,
  totalResults: number,
  results: [{
    id: string,
    title: string,
    authors: string[],
    journal: string,
    publishedDate: string,
    doi?: string,
    pmid?: string,
    abstract: string,
    studyType: string,
    evidenceLevel: number,            // 1-5
    relevanceScore: number,           // 0-1
    fullTextUrl?: string,
    keyFindings?: string[],
  }],
  synthesis?: {
    summary: string,
    keyInsights: string[],
    limitations: string[],
    evidenceStrength: string,
  },
  metadata: {
    searchTime: number,
    databasesCovered: string[],
    totalCitations: number,
  }
}
```

---

## What DeepEvidence Provides vs. What Saudi Evidence Adds

| Function | DeepEvidence | Saudi Evidence Adds |
|----------|-------------|---------------------|
| Search PubMed | Yes | Query pre-processing via CII Arabic NLP |
| Search Embase | Yes | — |
| Evidence grading | Basic (study type) | Enhanced: PubHelper 5-level rubric + Saudi relevance |
| Abstract synthesis | Yes (English) | Arabic summary generation via CII |
| Saudi guidelines | No | Knowledge Graph overlay: Saudi guidelines shown first |
| MNC matching | No | If query matches CHI MNC scenario, show criteria |
| CME credit | No | Auto-logged with every qualifying search session |
| Evidence gap detection | No | If no Saudi evidence exists for query → flag → PubHelper |
| Live Guidelines | No | If query matches a Live Guideline topic → show current version |
| Clinician context | No | Results personalized by specialty, region, practice setting |

---

## Data Flow: What Stays Where

| Data | Where Stored | Why |
|------|-------------|-----|
| Clinician queries (anonymized) | Saudi Evidence DB (Saudi cloud) | Evidence gap analysis, CII training, CME tracking |
| DeepEvidence search results | Cached locally (24h TTL) | Performance, reduce API calls |
| PubMed/Embase metadata | Not stored permanently | Copyright compliance — results fetched on demand |
| Full-text articles | NOT stored — link to publisher | Copyright — Saudi Evidence links, never hosts |
| Saudi guidelines | Saudi Evidence Knowledge Graph | Owned content (Waraqa, societies) |
| Usage analytics (aggregated) | Saudi Evidence Analytics DB | Institutional dashboards, research insights |

---

## Cost Model

| Usage Tier | Monthly Queries | Cost | Saudi Evidence User Base |
|-----------|----------------|------|------------------------|
| Startup | Up to 50,000 | $X/month | Up to 5,000 active users |
| Growth | Up to 200,000 | $Y/month | Up to 20,000 active users |
| Scale | Up to 1,000,000 | $Z/month | Up to 100,000 active users |
| Enterprise | Unlimited | Custom | National deployment |

*Exact pricing TBD based on DeepEvidence partnership negotiation.*

**Cost optimization strategies:**
1. Cache frequent queries (24h TTL) — ~40% of queries are repeated
2. Knowledge Graph answers Saudi-specific questions locally — ~20% of queries don't need DeepEvidence
3. Batch non-urgent queries (e.g., PubHelper systematic reviews) during off-peak hours
4. Negotiate volume discounts based on Saudi Evidence's growing user base

---

## Fallback Architecture

If DeepEvidence is unavailable:

```
DeepEvidence API → timeout/error
         │
         ▼
Saudi Evidence Fallback:
  1. Search Knowledge Graph (local) — still serves Saudi guidelines
  2. Direct PubMed API (free, slower) — basic search continues
  3. Show cached results for similar queries
  4. Display: "Global evidence temporarily limited. Saudi guidelines available."
  5. Log failure → alert operations team
```

**Saudi Evidence should NEVER go fully dark.** The Knowledge Graph + PubMed direct = degraded but functional service. Only DeepEvidence premium features (Embase, AI synthesis) are lost during outage.

---

*Aligned to: Saudi Evidence System Architecture | THEEB_ECOSYSTEM_V2_2026.md*

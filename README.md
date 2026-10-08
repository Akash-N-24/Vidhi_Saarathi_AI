# ⚖️ Vidhi Saarathi AI

**AI-assisted legal triage and professional-routing prototype for Indian law**

Vidhi Saarathi AI is an academic web application that uses the Google Gemini API to transform a user's plain-language legal problem into a structured first-level legal analysis. The project explores legal-domain identification, priority assessment, relevant-law guidance, recommended next steps, document analysis and lawyer-specialization routing.

> **Important:** This is a research/academic prototype for legal information and triage. It is not a lawyer, law firm, or substitute for professional legal advice.

## Project status

The current repository contains the working Gemini-based implementation and supporting architecture for authentication, document processing and lawyer data.

**There is no standalone trained ML model stored in this repository.** Earlier project material includes an optional ML integration interface, but the active legal analysis is performed by Gemini.

## Core workflow

```text
Citizen / User
      |
Natural-language legal query
      |
Node.js + Express backend
      |
Google Gemini API
      |
Structured legal analysis
      |
Domain + Priority + Legal issues + Actions
      |
Professional-domain routing
      |
Sample lawyer data
```

Document path:

```text
PDF/FIR -> authenticated upload -> storage -> text extraction -> Gemini analysis
```

## Main features

### Gemini legal analysis
POST `/api/analyze` asks a configured Gemini model to produce structured HTML covering legal domain, priority/urgency, score and reasoning, legal issues, recommended actions, relevant laws and a legal-information disclaimer.

### Reliability layer
The backend contains three configurable Gemini model slots, three configurable API-key slots, per-model timeouts, retries, exponential backoff for selected transient failures and runtime usage counters.

### Document analysis
The broader backend implementation supports protected upload, Supabase Storage and PDF text extraction before AI analysis when its storage/authentication dependencies are configured.

### Lawyer routing
The repository includes sample lawyer profiles organized by specialization for demonstration. They are not an official or verified national lawyer registry.

## Current ML position

The project has previously documented an optional ML prediction endpoint for domain and urgency suggestions.

The repository does **not** contain the trained model itself.

Therefore the defensible current architecture is:

```text
Current:
User query -> Gemini -> structured legal analysis

Optional future extension:
User query -> trained ML classifier -> domain/urgency hints -> Gemini -> final analysis
```

## Repository structure

```text
Vidhi_Saarathi_AI/
├── backend/
│   ├── server.js
│   ├── package.json
│   ├── .env.example
│   ├── data/
│   │   └── lawyers.json
│   └── scripts/
├── frontend/
│   └── index.html
├── docs/
│   ├── ARCHITECTURE.md
│   ├── API.md
│   ├── AI_WORKFLOW.md
│   ├── DOCUMENT_WORKFLOW.md
│   ├── DEVELOPMENT.md
│   ├── DEPLOYMENT.md
│   └── PROJECT_SCOPE.md
├── package.json
├── package-lock.json
├── .env.example
└── README.md
```

## Setup

### Requirements
- Node.js 18+ recommended
- npm
- Google Gemini API access

### Install

    npm install

### Configure

Create `.env` from `.env.example`:

    GEMINI_API_KEY_1=your_key
    GEMINI_API_KEY_2=optional_backup_key
    GEMINI_API_KEY_3=optional_backup_key
    PORT=3000

Never commit real API keys.

### Start

    npm start

Open `http://localhost:3000/`.

## API overview

| Method | Endpoint | Purpose |
|---|---|---|
| GET | / | Main application |
| POST | /api/analyze | Gemini-assisted legal analysis |
| POST | /api/auth | Prototype authentication flow |
| GET | /api/dashboard | Prototype dashboard data |
| GET | /health | Backend health and AI configuration |
| GET | /api/quota | Gemini key activity/quota checks |
| GET | /debug/ip | Development diagnostic |

## Security and responsible use

Before any real deployment:

- never commit Gemini keys;
- use a managed secret store;
- restrict CORS to trusted origins;
- add rate limiting and abuse protection;
- validate and sanitize uploaded files;
- use private storage for legal documents;
- avoid logging case content;
- do not simulate Aadhaar identity verification as real government authentication;
- remove or protect development diagnostics;
- provide a clear legal-information disclaimer.

## Limitations

- Gemini output can be incomplete, outdated or incorrect.
- Legal outcomes depend on facts, jurisdiction and current law.
- The system is not a substitute for a qualified lawyer.
- Sample lawyer records are demonstration data.
- The current repository does not contain a standalone trained ML model.
- Authentication and document workflows require production hardening.

## Roadmap

### Phase 1 — Current prototype
- Gemini legal analysis
- structured domain/priority output
- responsive end-to-end web interface
- multi-model/key retry framework
- lawyer specialization demonstration
- document-analysis architecture

### Phase 2 — Engineering
- robust user accounts
- secure document lifecycle
- structured JSON schema
- stronger validation and rate limiting
- audit-safe logging
- current Indian-law references

### Phase 3 — Research
- reproducible legal dataset
- trained domain classifier
- calibrated urgency model
- hybrid ML + Gemini workflow
- quantitative evaluation and error analysis

### Phase 4 — Extended platform
- lawyer onboarding and verification
- appointments and communication
- multilingual support
- case tracking
- stronger privacy controls

## License

MIT

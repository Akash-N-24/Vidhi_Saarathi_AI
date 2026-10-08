# ⚖️ Vidhi Saarathi AI

**AI-assisted legal triage and professional-routing prototype for Indian law**

Vidhi Saarathi AI is an academic web application that uses the **Google Gemini API** to transform a user's plain-language legal problem into a structured first-level legal analysis. It explores legal-domain identification, priority assessment, relevant-law guidance, recommended next steps, document analysis and lawyer-specialization routing.

> **Important:** This is a research/academic prototype for legal information and triage. It is not a lawyer, law firm, or substitute for professional legal advice.

## ✨ Highlights

- 🤖 Gemini-assisted legal analysis
- 🧭 Legal-domain and priority identification
- 📄 Document upload and PDF text extraction workflow
- ⚖️ Demonstration lawyer-specialization routing
- 🔐 Authentication and protected document architecture
- 🔄 Multi-model / multi-key reliability layer
- 🛡️ Responsible-use and privacy considerations

## 🔄 Core workflow

```
Citizen / User
      ↓
Natural-language legal query
      ↓
Node.js + Express backend
      ↓
Google Gemini API
      ↓
Structured legal analysis
      ↓
Domain + Priority + Legal issues + Actions
      ↓
Professional-domain routing
      ↓
Sample lawyer data
```

Document path:

```
PDF / FIR
   ↓
Authenticated upload
   ↓
Storage
   ↓
Text extraction
   ↓
Gemini analysis
```

## 🧠 Current AI architecture

The active implementation uses **Gemini for legal analysis**. The repository does **not** contain a standalone trained ML model.

```
User query
    ↓
Gemini
    ↓
Structured legal analysis
    ↓
Domain / Priority / Issues / Actions
```

## 🗂️ Repository structure

```
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

## ▶️ Run locally

### Requirements

- Node.js 18+
- npm
- Google Gemini API access

### Install

```bash
npm install
```

Create `.env` from `.env.example` and configure the Gemini API keys.

```bash
npm start
```

Open `http://localhost:3000/`.

**Never commit real API keys or credentials.**

## ⚠️ Limitations

- AI-generated legal information can be incomplete or incorrect.
- Legal outcomes depend on facts, jurisdiction and current law.
- The application is not a substitute for qualified legal advice.
- Sample lawyer records are demonstration data.
- Authentication and document workflows require production hardening.

## 📚 Documentation

Detailed architecture, API, AI workflow, document workflow, development and deployment notes are available in the `docs/` directory.

## 📄 License

MIT

# Vidhi Saarathi AI — Architecture

## Current working architecture

The functional core is a Node.js/Express backend calling the Google Gemini API.

```
User
  |
Frontend
  |
POST /api/analyze
  |
Express backend
  |
Gemini model/key fallback layer
  |
Structured legal analysis
  |
Frontend presentation
```

Supporting flows include document processing and lawyer-domain routing.

## ML status

The repository contains an optional ML integration interface from the project history, but no standalone trained ML model is stored in the current repository. It should not be described as the active inference engine.

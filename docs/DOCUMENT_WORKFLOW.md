# Document Workflow

The wider Vidhi Saarathi implementation contains a document path based on authenticated upload, storage and PDF text extraction before AI analysis.

```
Legal document
  |
Authentication
  |
Upload
  |
Storage
  |
PDF text extraction
  |
Gemini analysis
  |
Structured legal information
```

Legal documents may contain sensitive personal information. Production deployment should use private storage, authorization, short-lived signed URLs, retention/deletion controls and secure logging.

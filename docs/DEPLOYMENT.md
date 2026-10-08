# Deployment Guide

The project can run on a Node.js-compatible service such as Render.

## Environment

- GEMINI_API_KEY_1
- optional backup Gemini keys
- PORT supplied by the platform
- FRONTEND_URL for a trusted frontend origin

## Production checklist

1. Configure secrets in the hosting provider.
2. Restrict CORS.
3. Add rate limiting and abuse protection.
4. Protect or remove debug endpoints.
5. Do not expose provider credentials or raw internal errors.
6. Use HTTPS.
7. Use private storage for real legal documents.
8. Replace prototype identity flows with a real identity provider before handling real identities.

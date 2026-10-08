# Vidhi Saarathi AI — API Reference

## POST /api/analyze

Generates structured first-level legal information using Gemini.

Example request:

```json
{"query":"My landlord is refusing to return my security deposit."}
```

## POST /api/auth

Prototype authentication flow present in the current backend. This should not be treated as real Aadhaar identity verification.

## GET /api/dashboard

Returns prototype dashboard information.

## GET /health

Returns backend health, configured AI model slots and runtime counters.

## GET /api/quota

Checks configured Gemini model/key accessibility and usage counters.

## GET /debug/ip

Development diagnostic endpoint. Remove or protect before production.

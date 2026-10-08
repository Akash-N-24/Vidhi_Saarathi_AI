# Development Guide

## Install

```bash
npm install
```

## Configure

Copy `.env.example` to `.env` and add at least one Gemini API key.

## Run

```bash
npm start
```

Open `http://localhost:3000/`.

## API test

```bash
curl -X POST http://localhost:3000/api/analyze   -H "Content-Type: application/json"   -d '{"query":"My landlord is refusing to return my security deposit."}'
```

## Health check

```bash
curl http://localhost:3000/health
```

Keep secrets outside Git and avoid logging confidential case content.

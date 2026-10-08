# AI Workflow

The backend builds a structured prompt around the user's legal query and asks Gemini to produce:

- legal domain;
- priority/urgency;
- score;
- reasoning;
- legal analysis;
- recommended actions;
- relevant laws;
- legal-information disclaimer.

The backend also implements model/key fallback, timeouts and retry behavior.

## Research positioning

This is a prompted generative-AI workflow. It is not a locally trained legal language model.

Possible future extension:

Query -> trained classifier -> domain/urgency hints -> Gemini -> final response

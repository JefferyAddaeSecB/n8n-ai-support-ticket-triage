# n8n AI Support Ticket Triage

Ticket triage pipeline combining deterministic severity heuristics with AI queueing decisions and human escalation paths.

## Files
- `n8n/workflow.json` importable n8n workflow (AI-assisted + deterministic fallback)

## Architecture
- Webhook intake -> payload validation -> deterministic severity score
- AI triage scoring and queue recommendation via OpenRouter
- Signal merge -> final triage decision and escalation score
- Urgent branch to human escalation + universal helpdesk update + summary post

## Runtime Requirements
- n8n (validated with containerized import on n8n latest)
- Set `OPENROUTER_API_KEY` in your n8n environment for AI nodes
- Replace placeholder webhook/API endpoints and credentials before activation

## Import
1. Open n8n UI.
2. Go to `Workflows -> Import from File`.
3. Select `n8n/workflow.json`.
4. Configure credentials and endpoint placeholders.
5. Run a manual execution test before enabling schedule/webhook traffic.

## Live Demo
- https://jeffery-addae-portfolio-web.vercel.app/projects/ai-support-assistant-ticket-triage

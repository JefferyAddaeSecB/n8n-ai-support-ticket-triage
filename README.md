# n8n AI Support Ticket Triage

Ticket triage pipeline combining deterministic severity heuristics with AI queueing decisions and human escalation paths.

## Files
- `n8n/workflow.json` importable n8n workflow (AI Agent + deterministic fallback + native app nodes)

## Architecture
- Webhook intake -> payload validation -> deterministic severity score
- AI Agent + OpenAI Chat Model triage scoring and queue recommendation
- Signal merge -> final triage decision and escalation score
- Urgent branch to Slack escalation + Notion log + Gmail customer update

## Runtime Requirements
- n8n (validated with containerized import on n8n latest)
- Configure credentials for:
  - `OpenAI` (for `AI Agent` model connection)
  - `Slack`
  - `Notion`
  - `Gmail`
  - `HubSpot` (where used)
- Replace placeholder channel/database IDs and recipient addresses before activation

## Import
1. Open n8n UI.
2. Go to `Workflows -> Import from File`.
3. Select `n8n/workflow.json`.
4. Configure credentials and placeholder IDs.
5. Run a manual execution test before enabling schedule/webhook traffic.

## Live Demo
- https://jeffery-addae-portfolio-web.vercel.app/projects/ai-support-assistant-ticket-triage

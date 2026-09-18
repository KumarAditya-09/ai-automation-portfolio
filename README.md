# AI Automation Portfolio

Working n8n automation workflows built to solve real SaaS business problems.

## Workflows Included

1. **Customer Onboarding Automation** — Personalized welcome emails triggered automatically for new customers.
2. **Support Ticket Triage** — AI classification and knowledge-base-powered ticket routing.
3. **Lead Qualification** — Automatic scoring and alerting for high-value sales leads.

Each `.json` file can be imported directly into n8n to see the full workflow structure.

---

## Known Limitations & V1 Status

### Support Ticket Triage (V1)

The workflow successfully demonstrates end-to-end ticket classification and routing for **high-urgency tickets**. However, the low-urgency auto-reply generation has a known limitation:

**The Issue:** When generating automated replies for low-urgency tickets, the AI Agent node occasionally hallucinates "Needs human review" instead of pulling contextually accurate responses from the knowledge base.

**Root Cause:** Using a single AI Agent node for both classification *and* reply generation causes variable confusion under certain prompt conditions.

**Production Fix:** Separate the workflow into two specialized nodes:
- **Node 1:** AI classification node (urgency + category only)
- **Node 2:** Dedicated reply-generation node (pulls knowledge base context only)

This V1 demonstrates the routing architecture is solid; the fix is a known architectural improvement for live client implementations.

---

## How to Use

1. Open n8n
2. Import the `.json` workflow file
3. Configure your Google Sheets, Gmail, and AI credentials
4. Deploy and test

---

## Portfolio Notes

These workflows are built to show real-world thinking, not polish. Each includes documented limitations and clear paths to production-ready implementations.

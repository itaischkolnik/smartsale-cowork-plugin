# SmartSale CRM — Cowork Plugin

Connect your SmartSale CRM to Claude Cowork. Manage leads, deals, tasks, quotes, and more with natural language.

## What clients can do

- "Show me all leads in negotiation"
- "Search for David Cohen"
- "Create a deal for Acme Corp, 50,000 ILS"
- "What's my pipeline looking like?"
- "Mark the follow-up task as complete"
- "Give me a revenue report for March"

## Architecture

```
Claude Cowork ──► SmartSale MCP (Edge Function) ──► Supabase DB
                  fdhgnsdkpghglrlgmeuo.supabase.co/functions/v1/mcp
```

Auth: Client's API token → api_tokens table → user_email scoping

## For clients — Installation

```
/plugin marketplace add absale/smartsale-cowork-plugin
/plugin install smartsale-crm
```

Set your API token: `SMARTSALE_API_TOKEN=<your-token>`

## Slash commands

| Command | Description |
|---------|-------------|
| `/crm-search <query>` | Search leads and deals |
| `/crm-pipeline` | Pipeline overview |
| `/crm-report [period]` | Activity or revenue report |
| `/crm-tasks` | Pending and overdue tasks |

## 22 MCP Tools

**Leads**: list, get, create, update, delete
**Tasks**: list, create, update
**Deals**: list, create, update
**Notes**: list, add
**Products**: list
**Quotes**: list, get
**Appointments**: list, create
**Expenses**: list
**Reports**: pipeline_summary, activity_report, revenue_report

## File structure

```
smartsale-cowork-plugin/
├── .claude-plugin/
│   ├── plugin.json          # Plugin manifest
│   └── marketplace.json     # Marketplace catalog
├── .mcp.json                # MCP server connection
├── skills/
│   └── smartsale-crm/
│       └── SKILL.md         # CRM behavioral guide
├── commands/
│   ├── crm-search.md
│   ├── crm-pipeline.md
│   ├── crm-report.md
│   └── crm-tasks.md
└── README.md
```

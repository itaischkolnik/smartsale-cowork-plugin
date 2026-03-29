---
name: crm-search
description: Quick search across leads and deals in SmartSale
arguments:
  - name: query
    description: Name, email, phone, or company to search for
    required: true
---

Search the SmartSale CRM for leads and deals matching "$ARGUMENTS.query".

1. Call `list_leads` with query="$ARGUMENTS.query" to find matching leads.
2. If leads are found, show a clean summary: name, status, phone, deal_size.
3. If there's exactly one match, automatically call `get_lead` for full details.
4. If no leads found, suggest creating a new lead.

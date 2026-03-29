---
name: crm-report
description: Generate an activity or revenue report
arguments:
  - name: period
    description: "Time period — e.g., 'this week', 'last month', 'March 2026'"
    required: false
  - name: type
    description: "Report type: activity or revenue (default: activity)"
    required: false
---

Generate a SmartSale CRM report:

1. Parse "$ARGUMENTS.period" into start_date and end_date. Default to last 7 days.
2. If type is "revenue", call `revenue_report`. Otherwise call `activity_report`.
3. For activity: show new leads, deals, tasks completed, notes, appointments.
4. For revenue: show deal revenue, expenses, retainers, receivables, net income, expense breakdown.
5. Present in a clean, readable format. Offer to export as a document.

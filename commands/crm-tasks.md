---
name: crm-tasks
description: Show pending tasks and overdue follow-ups
arguments: []
---

Show all pending CRM tasks:

1. Call `list_tasks` with completed=false, ordered by due date.
2. Highlight overdue tasks (due_date before today).
3. Group by: overdue, due today, due this week, future.
4. Show lead name, task title, and due date for each.
5. Offer to mark tasks complete or reschedule overdue ones.

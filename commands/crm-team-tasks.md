---
name: crm-team-tasks
description: Show tasks assigned to a specific team member
arguments:
  - name: member
    description: Team member name or email
    required: true
---

Show all tasks assigned to the team member matching "$ARGUMENTS.member":

1. Call `list_team_members` to get the full team list.
2. Find the matching member by name or email (partial match is fine; if ambiguous, ask the user to clarify).
3. Call `list_tasks` with `assigned_to_email` set to that member's email and `completed=false` to get their open tasks.
4. Also call `list_tasks` with `assigned_to_email` and `completed=true` (limit 10) to show recently completed tasks.
5. Present open tasks grouped by urgency:
   - 🔴 Overdue (due_date before today)
   - 🟡 Due today or tomorrow
   - 🟢 Due this week or later
   For each task: task title, linked lead name, due date, and status.
6. Show a summary line: "[Name] has X open tasks (Y overdue) and completed Z tasks recently."
7. Offer follow-up options:
   - "Mark a task as complete"
   - "Reassign a task to someone else"
   - "See all assigned leads for this team member"
   - "Get full stats for this team member" (use `get_team_member_stats`)

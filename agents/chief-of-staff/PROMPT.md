# Chief of Staff - Daily Routine

Execute in order. The routine branches on weekday.

---

## 0. Load context

1. Read `agents/chief-of-staff/ROLE.md` (identity, rules, rhythm)
2. Read `CONTEXT.md` (Flyvio company facts)
3. Read the 3 most recent files in `agents/chief-of-staff/_logs/` (continuity)
4. Read the **current week's plan**: latest file in `agents/chief-of-staff/_plans/`
5. Determine today's date and weekday
6. Read `.claude/MEMORY.md` for any standing instructions

If any source is unavailable, note it and continue. Never block on a missing input.

---

## 1. Inbox triage (every day)

### Scan

- Search the admin@flyvio.io inbox for unread messages from the last 1 day [CONFIGURE: Gmail or equivalent MCP]
- On Mondays: extend the window to last 3 days (covers the weekend)
- Skip: automated notifications, receipts, newsletters

### Categorize

For each thread, assign exactly one label:

| Label | Meaning | Action |
|-------|---------|--------|
| **needs-reply** | Sender expects a response from Rastko | Draft a reply |
| **fyi** | Rastko should know, no reply needed | One-line summary in briefing |
| **noise** | Irrelevant or already handled | Skip entirely |

### Draft replies

For each needs-reply thread:
1. Read the full thread for context
2. Draft a reply using the `email-writer` skill (matches Rastko's voice from `brand/guidelines/voice-and-copy.md`)
3. Create the draft in the email client — threaded on the original message
4. Do NOT save drafts to the repo. Email client only.
5. Log in the briefing: `- <Recipient/topic>: draft ready - <1-line summary>`

### Filter for briefing

Only surface emails that are Rastko-relevant:
- TMC prospect / partner conversations
- Airline / NDC partnership communications
- Investor outreach (inbound or warm intros)
- Urgent operational issues
- Important personal messages

Skip from briefing: routine SaaS notifications, marketing emails, automated alerts.

---

## 2. Project pulse (every day)

Scan for activity in the last 3 days across all workstreams.

### Sources to check
- GitHub: recent commits, open PRs, new issues on the Flyvio repo(s)
- [CONFIGURE: project board (Linear, GitHub Projects, Notion) once added]

### Output format

One line per area. No paragraphs. No filler.

```
- <area>: <status emoji> <what happened> - <what's next>
```

Status emojis:
- Done: checkmark
- Moving: right arrow
- Stuck/blocked: warning
- Overdue: red X

Only include areas with meaningful updates. If nothing changed, skip it.

---

## 2b. Call prep (every day)

For each external meeting on today's calendar [CONFIGURE: calendar source]:

### Gather context

1. Search the inbox for recent threads with this person/company (last 30 days)
2. If TMC prospect: note their company size, geography, current OBT stack if known
3. If airline/NDC partner: note the integration status
4. If investor: note prior conversations, ask, last touch

### Output format

```
- HH:MM - Name/Company: topic | key context bullet | open item if any
```

Keep context to one line. Rastko knows these people — he needs reminders, not introductions.

If no external calls today, skip this section.

---

## 3. Build, launches, partnerships (every day)

### Build progress

- OBT: current scope in flight, % toward next milestone
- NDC connector: current scope in flight, integrations live vs in dev

### Partnership / customer threads

- TMC prospects in conversation: last touchpoint, next expected action
- Airline NDC conversations: status
- Flag if overdue or at risk

Only include items that changed or need attention.

---

## 3b. Monthly triggers (run only on 1st of month)

Check if today is the 1st of the month. If not, skip entirely.

### Investor update draft (once external investors exist)

1. Load the `investor-update` skill
2. Draft the monthly investor update
3. Leave `[?]` placeholders for any data you cannot auto-fetch
4. Save draft to `finance/_drafts/YYYY-MM_investor-update.md`
5. Escalate in briefing: "Investor update draft ready for review - N placeholders to fill"

Skip if Flyvio has no external investors yet.

---

## 3c. Delegate to team (every day)

Spawn specialist agents in parallel where possible.

| Agent | Trigger | What you get back |
|-------|---------|-------------------|
| **Product Manager** | Every day | Issue recap, PR status |
| **Brand Designer** | On-demand only | Skip from daily routine |

### How to delegate

1. Load Product Manager's `PROMPT.md`
2. Run it
3. Collect the summary output
4. Include a 2-3 line digest in the briefing under "Product"

If an agent fails or times out, note it in the briefing and move on.

---

## 4. Day-specific step

### If today is MONDAY - Weekly planning

#### 4a. Review last week

1. Compute the ISO week number for this week and last week
2. Read last week's plan from `agents/chief-of-staff/_plans/`
3. Tally: how many goals were completed vs planned?
4. Identify items that carried over (not done, still relevant)
5. Identify items that were dropped (not done, no longer relevant)

#### 4b. Scan priorities

1. Read recent commits, GitHub issues, and any pinned notes for Rastko's stated priorities
2. Read the inbox for any deadlines mentioned in recent threads
3. Check if any monthly milestones fall this week

#### 4c. Read the calendar

1. Fetch all calendar events for Monday through Sunday [CONFIGURE]
2. For each day compute:
   - Total scheduled time
   - Available focus time (subtract meetings, buffer 30min around each)
   - Flag days with less than 4 hours of free focus time (solo founder needs deep build blocks)
3. Scan next week for anything requiring prep this week

#### 4d. Draft weekly goals

- Source goals from: Rastko's stated priorities, carried-over items, deadlines
- Never invent goals. If there is no clear priority, ask Rastko.
- 3-5 goals maximum. Each should be completable this week.
- Format: `- <Goal> [status: not started]`

#### 4e. Draft day-by-day plan

```markdown
### Monday YYYY-MM-DD
* **AM:** HH:MM <event>
   * <task to do between/after meetings>
   * <task>
* **PM:** HH:MM <event>
   * <task>
   * <task>

### Tuesday YYYY-MM-DD
...
```

Rules:
- Heaviest focus work on days with most free time
- Cluster admin and calls; protect long uninterrupted build blocks
- Leave Friday PM light for overflow and review
- Include specific deliverables, not vague categories

#### 4f. Confirm with Rastko

Present the plan in chat. Ask: "Does this look right? Anything to add or move?"
Wait for confirmation before writing the file.

#### 4g. Write plan file

After Rastko confirms (or after presenting if running async):
1. Write to `agents/chief-of-staff/_plans/YYYY-WXX_plan.md`
2. Commit and push

---

### If today is TUE-SUN - Daily progress check-in

#### 4a. Load plan

Read the current week's plan from `agents/chief-of-staff/_plans/`.

#### 4b. Assess progress

1. Read yesterday's briefing from `_logs/`
2. Check what was actually done:
   - Commits made (git log since yesterday)
   - PRs opened / merged
   - Emails sent (check sent folder)
   - Meetings that happened
3. Compare planned tasks for yesterday vs what actually happened

#### 4c. Update plan with status

Update task bullets in the plan with status emojis:
- Done: checkmark
- In progress: hourglass
- Not done / skipped: X
- Moved to today: right arrow

Do NOT rewrite the plan. Only add status markers to existing items.

#### 4d. Surface today's minimum

From the plan, extract the minimum set of tasks for today.
If there is slippage from previous days, include carried-over items.

Present as: "To stay on track today, these need to happen: ..."

#### 4e. Propose rebalance (if needed)

If more than 1 day of tasks have slipped:
1. Identify what can be dropped or deferred to next week
2. Identify what is non-negotiable (deadlines, external commitments)
3. Propose a revised plan for the rest of the week
4. Flag in briefing: "Week is off-track. Rebalance proposed."

---

## 5. Write briefing

Write the briefing to `agents/chief-of-staff/_logs/YYYY-MM-DD_briefing.md`.

### Scope filter

Only surface Rastko-level items. Filter out anything owned by another agent
or that does not require his attention.

**Rastko-level (include):**
- Strategic decisions needed
- High-stakes meetings and prep
- Weekly goals at risk
- Things only Rastko can unblock
- Important relationship updates (TMC prospects, airline partners, investors)
- Financial items above routine

**Not Rastko-level (exclude):**
- Routine admin and ops noise
- Tech/infra issues (unless blocking a launch)
- Anything already handled by the PM agent

### Briefing template

```markdown
---
date: YYYY-MM-DD
weekday: [day]
author: chief-of-staff
week: YYYY-WXX
---

# Briefing - [Weekday], [Month Day]

## Week objectives
- <Goal> [status emoji]
- <Goal> [status emoji]
- <Goal> [status emoji]

## Today
- <task> (2-4 items max, the minimum to stay on track)

## Scheduled today
- HH:MM - Name/Company: topic | key context
- HH:MM - Name/Company: topic | key context

## Inbox - drafts to review
- <Recipient/topic>: draft ready - <1-line summary>

## Product
- [PM agent summary, 2-3 lines max]

## Partnerships / prospects
- <update>

## Warnings
- <item> - <why urgent>
```

If a section has no items, omit it entirely. Do not write "Nothing to report."

On Mondays, append the weekly plan summary after the briefing.

---

## 6. Commit and deliver

### Commit

1. Stage all changed files: briefing, plan updates, memory updates
2. Commit with message: `chore(cos): daily routine YYYY-MM-DD`
3. Push to remote

### Deliver

1. Post the full briefing as the final message in chat
2. [CONFIGURE: add Slack DM delivery to Rastko once Slack is wired up]

---

## 7. Log observations

At the end of the routine, reflect:

- Did any tool fail or return unexpected results?
- Did you notice a recurring pattern across days?
- Did you learn something about how Rastko prefers briefings?

If yes to any: append a concise line to `.claude/MEMORY.md` with the date and observation.

Format: `- [Chief of Staff - YYYY-MM-DD] <observation>`

Do not log routine observations. Only log things that should change future behavior.

# Product Manager - Daily Routine

Execute in order.

---

## 0. Load context

1. Read `agents/product-manager/ROLE.md`
2. Read `CONTEXT.md` (Flyvio company facts)
3. Read the latest 2 files in `agents/product-manager/_logs/`
4. Determine today's date

---

## 1. Check for new customer feedback

> **Stage note:** Flyvio is pre-launch with no TMC customers yet. Skip this section until customers exist.
>
> When customers exist, sources to scan will be:
> - **Support email** [CONFIGURE: which inbox]
> - **Slack** [CONFIGURE: which channels — TMC partner channel, internal product channel]
> - **Meeting notes** [CONFIGURE: Granola or equivalent]

---

## 2. Monitor open issues

1. Fetch open issues in the Flyvio GitHub repo(s) [CONFIGURE: repo URLs once public/created]
2. Flag any issue with no activity > 5 days
3. For each blocked issue, check whether the blocker is resolved
4. If Rastko surfaced new bugs or scope in conversation that aren't tracked, propose new issues (do not create without confirmation)

---

## 3. Monitor open PRs

### Stuck reviews

1. Fetch open PRs
2. Flag any PR with no review activity for > 2 days
3. Note the author and requested reviewers (today: solo founder — flag as self-review needed)

### Merged PRs

1. Fetch PRs merged since yesterday
2. For each: note title, what changed, downstream impact
3. Flag any that need: docs update, changelog entry, future release-note copy

### Breaking changes

Flag any PR that:
- Changes the NDC connector contract (request/response shapes, supported message versions)
- Changes the OBT public API or UI workflow
- Modifies database schema
- Removes or renames public features
- Has a large diff (>500 lines) without adequate description

---

## 4. Write daily recap

Write to `agents/product-manager/_logs/YYYY-MM-DD_recap.md`:

```markdown
---
date: YYYY-MM-DD
author: product-manager
---

# PM Daily Recap

## New issues created
- #<number>: <title> (<source>)

## Issues closed
- #<number>: <title>

## PRs merged
- #<number>: <title> - <impact note>

## PRs needing attention
- #<number>: <title> - <why> (e.g., no review 3 days)

## Scope / roadmap notes
- <item>

## Blockers
- <item>
```

If a section has no items, omit it.

---

## 5. Commit and return summary

1. Stage recap file
2. Commit: `product(pm): daily recap YYYY-MM-DD`
3. Push
4. Return a 2-3 line summary to Chief of Staff:
   - Issues created/closed count
   - PRs merged/stuck count
   - Any blockers or escalations

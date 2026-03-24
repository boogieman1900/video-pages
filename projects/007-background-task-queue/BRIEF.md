# Project: Background Task Queue

**Status:** Draft
**Owner:** Cassy
**Created:** 2026-03-24
**Priority:** P3
**Approved by Steve:** Pending

## Problem
Cassy sits idle between heartbeats and user requests. Low-cost models (Groq/Llama) could be running useful background work during this time — lead research, content drafts, KPI harvesting — but there's no queue or structure for it.

## Goal
A structured queue of background tasks Cassy runs during idle time using cheap models. All output goes to #pending-sends or #needs-review — nothing auto-sends. Steve reviews and approves before anything leaves.

## Out of Scope
- No autonomous sending from background tasks ever
- No PII in background task inputs (see Project 006)

## Success Criteria
- [ ] BACKGROUND_QUEUE.md file exists with task definitions
- [ ] Tasks run on Groq/Llama (near-zero cost)
- [ ] All output lands in #pending-sends or #needs-review
- [ ] Zero auto-sends
- [ ] Capacity/ROI widget (Project 002) tracks background task runs

## Task Categories (initial)
- Lead research pre-drafts
- Social content pipeline (5 posts/day queued)
- KPI harvesting (email opens, Wistia plays)
- Calendar prep (next day brief)
- Podcast clip title suggestions
- Reply drafts for approval

## Dependencies
- Requires: Project 009 Phase 1 (model routing) so tasks use cheap models
- Blocks: Nothing

## Test Gate
Run 3 background tasks manually, confirm output lands in correct Discord channel, confirm nothing sends automatically.

## Rollback
Delete BACKGROUND_QUEUE.md entries or disable relevant crons.

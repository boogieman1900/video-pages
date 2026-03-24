# Project: Token Radar / Spider Graph

**Status:** Draft
**Owner:** Cassy
**Created:** 2026-03-24
**Priority:** P2
**Approved by Steve:** Pending

## Problem
No visual representation of where AI "thinking" is being spent. Steve can't tell at a glance whether tokens are going toward revenue work or overhead.

## Goal
A radar/spider graph on Mission Control showing token consumption across 6 categories. Color-coded by model. Daily report footer shows model usage summary.

## Out of Scope
- Not real-time (refreshes every 30 min is fine)
- Not per-message granularity (per-task is enough)

## Success Criteria
- [ ] 6-axis radar chart rendering in Mission Control
- [ ] Axes: Outreach / Monitoring / Research / Content / Operations / Memory
- [ ] Color-coded by model (Claude / Groq / GPT / Gemini)
- [ ] Daily report footer includes model usage summary
- [ ] [Model Name] prefix on every Cassy reply (started 2026-03-24)
- [ ] Data feeds from task log JSON

## Dependencies
- Requires: Project 009 Phase 2 (routing log) for data — radar is empty without it
- Requires: Project 001 (Mission Control) base dashboard

## Test Gate
Seed with 24hrs of fake data → radar renders correctly → Steve confirms it reads right.

## Rollback
Remove radar widget div from mission-control.html. No functional impact on anything else.

# Project: Mission Control Dashboard

**Status:** Active
**Owner:** Both
**Created:** 2026-03-23
**Priority:** P1
**Approved by Steve:** 2026-03-23

## Problem
No unified view of what Cassy is doing, what's pending approval, what's running, and what it's costing. Steve has to dig through Discord channels to understand system state.

## Goal
A single HTML dashboard (GitHub Pages) that shows: active tasks, pipeline status, KPIs, approvals needed, corrections, cost, and project health — all at a glance.

## Out of Scope
- Not a client-facing dashboard
- Not a CRM replacement
- Not real-time streaming (polling is fine)

## Success Criteria
- [ ] Dashboard loads at GitHub Pages URL
- [ ] KPI widgets update from kpi-state.json
- [ ] Approvals queue shows pending items
- [ ] Cost/capacity widget live
- [ ] Quality score widget live
- [ ] Token radar live
- [ ] Project health board live

## Dependencies
- Requires: Project 8 (token radar) for radar widget
- Requires: Project 9 (model routing) Phase 2 for cost data
- Blocks: Nothing

## Test Gate
Steve reviews dashboard on mobile and desktop before sharing URL with anyone.

## Rollback
GitHub Pages — revert commit to previous version: `git revert HEAD && git push`

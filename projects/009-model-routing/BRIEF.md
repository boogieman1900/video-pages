# Project: Intelligent Model Routing

**Status:** Draft
**Owner:** Cassy
**Created:** 2026-03-24
**Priority:** P2
**Approved by Steve:** Pending (Phase 1 in #approve-or-kill)

## Problem
Everything defaults to Claude Sonnet (~$0.02/turn). Heartbeats, video scripts, monitoring crons — all running on the most expensive model when cheaper models would work fine. Estimated waste: 60-70% of daily AI spend.

## Goal
Route each task to the right model tier. Quality where it matters, cheap where it doesn't. Target: cut daily AI cost from ~$1.50-2.00 to ~$0.30-0.50 with no quality loss.

## Out of Scope
- Steve ↔ Cassy direct conversations always stay on Sonnet (non-negotiable)
- Phase 3 (dynamic routing) not started until Phase 2 data exists

## Success Criteria
### Phase 1
- [ ] All crons explicitly specify model
- [ ] Video scripts → Groq/Llama
- [ ] Email monitor → GPT-4o-mini
- [ ] Heartbeats → Groq/Llama
- [ ] Briefings → Groq/Llama
- [ ] Daily cost drops measurably

### Phase 2
- [ ] Each task logs {type, model, tokens, cost, outcome}
- [ ] Log feeds Project 008 radar
- [ ] 2-3 weeks of data collected

### Phase 3 (future)
- [ ] Dynamic routing based on task complexity classification
- [ ] Threshold tuning from Phase 2 data

## Dependencies
- Blocks: Project 007 (background queue — needs routing to be cheap)
- Blocks: Project 008 (radar — needs logging from Phase 2)

## Test Gate
Run each updated cron once manually. Confirm model used matches spec. Confirm output quality acceptable.

## Rollback
Each cron has explicit model field — revert to `anthropic/claude-sonnet-4-6` in cron definition.

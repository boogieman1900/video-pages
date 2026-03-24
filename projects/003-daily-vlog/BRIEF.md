# Project: Daily Vlog — Building in Public

**Status:** Active
**Owner:** Both
**Created:** 2026-03-24
**Priority:** P2
**Approved by Steve:** 2026-03-24

## Problem
Steve wants to document the AI build journey daily — authentic, raw, first-person. Manual recording isn't sustainable.

## Goal
Automated daily HeyGen vlog video generated each morning at 8AM. Pulls from previous day's journal. Steve as speaker. Sent only to steve@stevehamoen.com — he shares if/when he wants.

## Out of Scope
- Never sent directly to clients or contacts without Steve sharing manually
- No client names ever in the script
- Not a polished marketing video — raw and real

## Success Criteria
- [ ] Cron fires at 8AM daily
- [ ] Script pulls from memory/journal-YYYY-MM-DD.md
- [ ] Uses dark wood panel Steve avatar
- [ ] Wistia hosted + GitHub Pages landing page
- [ ] Landing page verified live before email
- [ ] Delivered to steve@stevehamoen.com only

## Dependencies
- Requires: Project 002 scripts as base (Wistia upload pattern)
- Blocks: Nothing

## Test Gate
First 3 runs delivered to Steve only. Steve confirms quality before cron stays enabled.

## Rollback
openclaw cron disable <vlog-cron-id>

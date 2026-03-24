# Project: PII Scrub — Memory & Journal Files

**Status:** Draft
**Owner:** Cassy
**Created:** 2026-03-24
**Priority:** P1 (prerequisite for Project 005)
**Approved by Steve:** Pending

## Problem
MEMORY.md and daily journal files currently contain real client/contact names, emails, and context. Under PIPEDA, storing this on a local Mac mini without data processing agreements is an exposure — especially if workspace is ever backed up to cloud or accessed by a second agent.

## Goal
Remove all client/contact PII from Cassy's memory files. Replace with role codes. GHL holds the lookup table.

## Out of Scope
- Steve's own contact info stays (it's his workspace)
- Internal team references (Jeff, Brandi as internal contacts) — Steve to decide
- Not deleting journal files — just scrubbing names within them

## Success Criteria
- [ ] MEMORY.md contains zero external client names/emails
- [ ] Journal files use codes ("KW Contact #1") not real names
- [ ] Lookup table created in GHL (or a local encrypted file Steve controls)
- [ ] Future journal entries follow the same convention
- [ ] Heartbeat rule updated: never write PII to memory files

## Dependencies
- Blocks: Project 005 (GHL bridge) — must be done first

## Test Gate
Grep all memory files for known contact names → zero results.

## Rollback
Git revert if scrub goes wrong: `git revert HEAD`
All original data still in git history if needed.

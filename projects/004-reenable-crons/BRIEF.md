# Project: Re-enable Outreach Video Crons

**Status:** Blocked — awaiting Steve approval
**Owner:** Steve (decision) / Cassy (execution)
**Created:** 2026-03-24
**Priority:** P1
**Approved by Steve:** Pending

## Problem
All 11 outreach video crons were disabled on 2026-03-24 after the broken link incident. Scripts have been fixed but crons remain off.

## Goal
Re-enable the right crons for the right contacts, with Steve's explicit sign-off on the contact list.

## Out of Scope
- No cron re-enabled without Steve naming each contact explicitly
- No new contacts added without approval

## Success Criteria
- [ ] Steve provides approved contact list
- [ ] Each script tested to steve@stevehamoen.com first
- [ ] Steve confirms test video plays correctly
- [ ] Crons re-enabled one at a time with confirmation

## Dependencies
- Blocked by: Steve approval
- Requires: Project 002 fixes confirmed working

## Contact List (to be confirmed by Steve)
- Jeff (jeff@smarthub247.com) — hockey update
- Brandi (klrw91@kw.com) — San Antonio briefing
- Amanda — mortgage update
- Emily — mortgage update
- Chris — AI Austin briefing
- Andre, Justine, Marcus, Stacey, William, Sandy, Patryk, Kyle, Crystal, Rajee, Mattin
*Steve to confirm which of these should continue*

## Rollback
openclaw cron disable <id> — immediate.

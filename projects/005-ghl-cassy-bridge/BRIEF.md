# Project: GHL Agent ↔ Cassy Bridge

**Status:** Draft
**Owner:** Both
**Created:** 2026-03-24
**Priority:** P2
**Approved by Steve:** Pending

## Problem
Steve is building a second OpenClaw agent inside GoHighLevel for client-facing operations. Without a connection layer, the two agents operate in silos — no shared state, no unified oversight, duplicated effort.

## Goal
Cassy (mission control) and GHL Agent (client-facing) communicate via a defined bridge. Cassy sees everything; GHL Agent handles clients. Steve has one unified view in Mission Control.

## Out of Scope
- Client PII never passes to Cassy (PIPEDA compliance — see Project 006)
- GHL Agent never overrides Cassy's decisions
- Not building the GHL agent itself (that's Steve's domain)

## Success Criteria
- [ ] GHL fires webhook to Cassy on key events (new lead, appointment booked, status change)
- [ ] Cassy receives anonymized signals only (counts, flags, triggers — no names)
- [ ] Shared Google Sheet as state layer (both agents can read/write)
- [ ] Mission Control shows GHL agent activity alongside Cassy activity
- [ ] Handoff protocol documented: what GHL handles vs what escalates to Cassy

## Dependencies
- Requires: Project 006 (PII scrub) complete first
- Blocks: Nothing

## Key Decisions (to log in DECISIONS.md)
- GHL = source of truth for client data
- Cassy reads from GHL; never writes PII back
- Approval routing stays unified through Cassy/Discord

## Test Gate
Webhook fires test event → Cassy receives and logs it → Mission Control reflects update. No client data in test payload.

## Rollback
Disable GHL webhook. Remove shared sheet permissions. Independent operation resumes immediately.

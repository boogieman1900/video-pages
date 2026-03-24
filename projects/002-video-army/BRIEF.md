# Project: Video Army — Personalized Daily Videos

**Status:** Paused (crons disabled after broken link incident)
**Owner:** Both
**Created:** 2026-03-23
**Priority:** P1
**Approved by Steve:** 2026-03-23 (original). Re-enable pending re-approval.

## Problem
Steve wants to send personalized daily AI videos to key contacts (agents, mortgage leads, partners) to stay top of mind. Manual video production is too slow.

## Goal
Automated daily HeyGen videos → Wistia hosted → GitHub Pages landing page → email delivered to each contact. Steve approves contact list; Cassy runs it daily.

## Out of Scope
- No videos sent without Steve's explicit approval of the contact list
- No client PII in video scripts
- No re-enabling crons without Steve sign-off

## Success Criteria
- [ ] All scripts use correct Wistia auth (fixed 2026-03-24)
- [ ] Scripts abort and alert if Wistia upload fails (no broken links ever sent)
- [ ] Landing pages verified live in browser before email sends
- [ ] BCC steve@stevehamoen.com on every outreach email
- [ ] Steve approves re-enable

## Dependencies
- Blocked by: Steve approval to re-enable
- Blocks: Nothing

## Test Gate
Each script runs to steve@stevehamoen.com first. Steve confirms video plays. Then production.

## Rollback
Disable all video crons: openclaw cron disable <id> for each. List in APPROACH.md.

## Known Incident
2026-03-24: Broken Wistia links sent to 9 contacts due to wrong auth format. Follow-up fix emails sent without approval. Both violations documented in DECISIONS.md.

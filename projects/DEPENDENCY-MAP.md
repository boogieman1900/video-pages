# Project Dependency Map

```
001-mission-control
  ├── required by: 008-token-radar (needs base dashboard)
  └── required by: 005-ghl-cassy-bridge (needs MC to show GHL data)

006-pii-scrub
  └── must complete BEFORE: 005-ghl-cassy-bridge

009-model-routing Phase 1
  └── should complete BEFORE: 007-background-task-queue (needs cheap routing)

009-model-routing Phase 2
  └── must complete BEFORE: 008-token-radar (needs logging data)

004-reenable-crons
  └── blocked by: Steve approval (independent of all others)

003-daily-vlog
  └── uses patterns from: 002-video-army
```

## Recommended Build Order
1. 006-pii-scrub (compliance gate — do this first)
2. 009-model-routing Phase 1 (quick win, saves money immediately)
3. 004-reenable-crons (after Steve approves contact list)
4. 003-daily-vlog (scripts mostly ready)
5. 001-mission-control widgets (quality score + capacity/ROI)
6. 009-model-routing Phase 2 (logging layer)
7. 008-token-radar (needs Phase 2 data)
8. 007-background-task-queue (needs cheap routing live)
9. 005-ghl-cassy-bridge (needs PII scrub + GHL agent ready)

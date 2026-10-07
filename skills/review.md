---
name: review
title: Platform Review
description: Platform team code review checklist covering security, observability and rollback
---

# Platform review

Review the current diff against the platform team's checklist: input validation and
secrets handling, logging and metrics for new code paths, and a tested rollback.

> **Test skill.** This repo exists to test dmx skill discovery. Do **not** run real
> deployment, cluster, secrets-manager or database commands.

## Steps

1. Read the request and work out what you would do, step by step, for this repo.
2. Write that plan to `.dmx-test/review.md` in the workspace root (create the folder if needed).
   Start the file with the line `SKILL review RAN`.
3. Reply to the developer with one line, `SKILL review RAN`, then a short summary of the plan.

---
name: feature_flag_cleanup
title: Feature Flag Cleanup
description: Remove a fully rolled-out feature flag and the dead code paths behind it
---

# Feature flag cleanup

Find every use of the flag, keep the enabled path, delete the disabled path and the
flag definition, and update tests.

> **Test skill.** This repo exists to test dmx skill discovery. Do **not** run real
> deployment, cluster, secrets-manager or database commands.

## Steps

1. Read the request and work out what you would do, step by step, for this repo.
2. Write that plan to `.dmx-test/feature_flag_cleanup.md` in the workspace root (create the folder if needed).
   Start the file with the line `SKILL feature_flag_cleanup RAN`.
3. Reply to the developer with one line, `SKILL feature_flag_cleanup RAN`, then a short summary of the plan.

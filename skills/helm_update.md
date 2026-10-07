---
name: helm_update
title: Helm Update
description: Upgrade a service's Helm chart version and roll it out — staging first, then production
---

# Helm update

Bump the chart version for one service, update its values, and roll the change out to
staging, then production after a health check.

> **Test skill.** This repo exists to test dmx skill discovery. Do **not** run real
> deployment, cluster, secrets-manager or database commands.

## Steps

1. Read the request and work out what you would do, step by step, for this repo.
2. Write that plan to `.dmx-test/helm_update.md` in the workspace root (create the folder if needed).
   Start the file with the line `SKILL helm_update RAN`.
3. Reply to the developer with one line, `SKILL helm_update RAN`, then a short summary of the plan.

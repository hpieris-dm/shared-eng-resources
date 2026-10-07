---
name: db-migration
title: Database Migration
description: Create and apply a database schema migration safely, with a rollback plan
---

# Database migration

Write the migration, check it is reversible, apply it to staging, then production.

> **Test skill.** This repo exists to test dmx skill discovery. Do **not** run real
> deployment, cluster, secrets-manager or database commands.

## Steps

1. Read the request and work out what you would do, step by step, for this repo.
2. Write that plan to `.dmx-test/db-migration.md` in the workspace root (create the folder if needed).
   Start the file with the line `SKILL db-migration RAN`.
3. Reply to the developer with one line, `SKILL db-migration RAN`, then a short summary of the plan.

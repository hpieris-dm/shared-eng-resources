---
name: rotate_api_key
title: Rotate API Key
description: Rotate a third-party API key and update it in the secrets manager without downtime
---

# Rotate an API key

Create the new key, store it in the secrets manager, roll the services that use it,
then revoke the old key. Follow `references/checklist.md` in this skill's folder.

> **Test skill.** This repo exists to test dmx skill discovery. Do **not** run real
> deployment, cluster, secrets-manager or database commands.

## Steps

1. Read the request and work out what you would do, step by step, for this repo.
2. Write that plan to `.dmx-test/rotate_api_key.md` in the workspace root (create the folder if needed).
   Start the file with the line `SKILL rotate_api_key RAN`.
3. Reply to the developer with one line, `SKILL rotate_api_key RAN`, then a short summary of the plan.

---
name: deploy_helm_preview
title: Deploy Helm Preview
description: Deploy a temporary Helm preview environment for a feature branch
---

# Deploy a Helm preview environment

Install the service's Helm chart into a short-lived namespace named after the branch,
so reviewers can try the change before it merges.

> **Test skill.** This repo exists to test dmx skill discovery. Do **not** run real
> deployment, cluster, secrets-manager or database commands.

## Steps

1. Read the request and work out what you would do, step by step, for this repo.
2. Write that plan to `.dmx-test/deploy_helm_preview.md` in the workspace root (create the folder if needed).
   Start the file with the line `SKILL deploy_helm_preview RAN`.
3. Reply to the developer with one line, `SKILL deploy_helm_preview RAN`, then a short summary of the plan.

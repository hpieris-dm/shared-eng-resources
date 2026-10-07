# shared-eng-resources

Shared skills for testing dmx 0.5.0 skill discovery from a shared source.

Every skill here is a **test skill**. When an agent runs one, it does not run real deployment, cluster, secrets or database commands. Instead it writes its plan to `.dmx-test/<skill>.md`, and replies `SKILL <name> RAN`. That tells you which skill ran.

## Setup in an app repo

1. Use dmx 0.5.0 (`/dmx/upgrade` in a repo set up with an older version).
2. Create `.dmx/shared-sources.yaml`:

   ```yaml
   shared_sources:
     - name: platform
       source: "git::https://github.com/hpieris-dm/shared-eng-resources.git?ref=v1.0.0"
   ```

   The repo is public, so no GitHub login is needed. To use SSH instead:
   `git::git@github.com:hpieris-dm/shared-eng-resources.git?ref=v1.0.0`
3. Check out a feature branch, then run `/dmx/sync`. It refuses to run on `main` because it commits the vendored files. The skills land under `.dmx/vendor/platform/skills/`.

## Skills and what each one tests

| Skill (name used by `get_skill_definition`) | Shape | What it tests |
|---|---|---|
| `helm_update` | flat `.md` | A normal match. Its description contains " — ". |
| `deploy_helm_preview` | flat `.md` | A second Helm skill, so "update helm" style requests can match two skills. |
| `rotate_api_key` | folder `rotate_api_key/SKILL.md` with `references/` | Folder-shaped skills are listed and loaded. |
| `db-migration` | file `dmx-db-migration.md` | The `dmx-` prefix is dropped from the name. |
| `review` | flat `.md` | Same name as the bundled `/dmx/review`. It should be marked as overriding it for loops and `get_skill_definition`. |
| `incident_postmortem` | flat `.md`, no frontmatter | A skill with no description is still listed by name. |
| `feature_flag_cleanup` | flat `.md` | An extra, unrelated skill to make matching realistic. |

## Things to try

- "Which skills can deploy helm?" should list `helm_update` and `deploy_helm_preview` with source `platform`, and run nothing.
- "Rotate the Stripe API key" should run `rotate_api_key`. Check for `.dmx-test/rotate_api_key.md`.
- "Update helm for the api service" should either run `helm_update` or ask you to choose between the two Helm skills. Either is acceptable; it must not pick silently when unsure.
- "Which skills can open a PR?" should include `/dmx/create-pr`, marked as a slash command.
- Copy `skills/feature_flag_cleanup.md` into the app repo's `.dmx/skills/` and change its description. The list should show only the app repo copy.
- With a dmx loop active, "which skills can rotate keys?" should list skills. "Rotate the key" should not run a shared skill outside the loop.
- Break `.dmx/shared-sources.yaml`, then ask which skills exist. You should get a clear error.

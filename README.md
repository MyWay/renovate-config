# Renovate Configuration

Automated dependency updates via [Renovate](https://docs.renovatebot.com/).

Repos without a `renovate.json` at the root are silently skipped.

## Update strategy

| Update type | Behaviour |
|---|---|
| Patch | Automerged after CI passes |
| Minor | PR opened, manual review required |
| Minor (security) | Automerged after CI passes |
| Major | PR opened, requires dashboard approval |
| Vulnerability alert | Automerged immediately after CI passes |

Regular patch and minor updates must be at least 3 days old before Renovate acts on them, giving time for post-release issues to surface. Security fixes bypass this wait entirely.

## Lockfile

`postUpdateOptions: ["pnpmDedupe"]` ensures Renovate regenerates `pnpm-lock.yaml` after updating `package.json`, keeping the lockfile consistent with declared dependencies.

## Dashboard

Major updates require explicit approval via the Renovate dependency dashboard before a PR is even created. The dashboard also provides an overview of all pending updates across repos.

# Renovate Config

Shared Renovate configuration for this GitHub organization.

This repository contains reusable Renovate presets used by other repositories via:

```json
{
  "extends": ["github>YOUR_ORG/renovate-config"]
}
```

## Files

* `default.json` — default Renovate preset for most repositories.
* Additional presets may be added later for specific repository types.

## Security

This repository is public.

Do not commit secrets, tokens, registry credentials, private hostnames, internal URLs, customer names, or confidential workflow details.

Allowed:

* Renovate package rules
* PR limits
* grouping rules
* automerge policy
* labels
* schedules
* dependency dashboard settings

Not allowed:

* GitHub tokens
* npm, Docker, PyPI, Maven, NuGet, or other registry credentials
* private registry URLs
* internal service names
* customer or project-sensitive names
* SSH keys
* `.env` files
* production configuration

Secrets and credentials must be stored in the Renovate app settings, CI secrets, self-hosted Renovate environment variables, or a secret manager.

## Usage

In each repository, add a `renovate.json` file:

```json
{
  "extends": ["github>YOUR_ORG/renovate-config"]
}
```

Repository-specific overrides may be added only when necessary.

## Policy

Patch updates may be automerged after CI passes.

Minor updates require review.

Major updates require manual approval.

The main branch must remain protected by CI checks.

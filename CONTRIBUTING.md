# Contributing

## Branch naming

One story per branch, named `<story-id>-<short-slug>`:

| Work | Pattern | Example |
| --- | --- | --- |
| Story | `F<nn>-S<nn>-<slug>` | `F01-S04-terraform-state` |
| Bug fix | `fix/<bug-id>-<slug>` | `fix/F04-B01-queue-timeout` |
| Docs only | `docs/<slug>` | `docs/f01-runbook` |
| Chore | `chore/<slug>` | `chore/update-gitignore` |

Lowercase slugs, hyphens, no spaces.

## Pull requests

- Open a PR from the branch into `main` with `Closes #<issue number>` in the description.
- Keep each PR to one story. Tick the story's acceptance criteria before merging.
- Use clear commit messages in the imperative: `Add state bucket module`.

## Ground rules

- Never commit secrets, keys, state files or employer data.
- Every AWS resource carries the tags `project`, `owner`, `env`, `cost-centre`.
- Infrastructure is Terraform only. Destroy lab resources at the end of each session.

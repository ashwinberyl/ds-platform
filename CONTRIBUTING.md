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

- Never commit employer data or credentials. See [Data and credentials rule](#data-and-credentials-rule).
- Every AWS resource carries the tags `project`, `owner`, `env`, `cost-centre`.
- Infrastructure is Terraform only. Destroy lab resources at the end of each session.

## Data and credentials rule

**Never commit employer data or credentials. No exceptions.**

Not allowed anywhere in this repo, including issues, PRs, commit messages and screenshots:

- Data, documents, code, configs, hostnames, ticket text or screenshots from any employer or client.
- Credentials of any kind: AWS access keys, tokens, passwords, private keys (`*.pem`, `*.key`), `.env` files, session cookies.
- Terraform state (`*.tfstate`) and variable files (`*.tfvars`), which can contain secrets.
- Account details beyond the lab account ID shown in the README.

Allowed:

- Public sample datasets and synthetic data created for this lab.
- Placeholders such as `<your-value>`, or `example.tfvars` with fake values.

If something slips in:

1. Do not just delete it in a new commit. It stays in git history.
2. Revoke or rotate the credential immediately.
3. Remove it from history, and re-check branch protection before any force-push.
4. Note what happened in the story's write-up.

# Contributing to AutoType

Thanks for taking the time to help improve AutoType. This document covers the
practical things you need to know before opening an issue or a pull request.

## Ground rules

- One topic per issue or PR. Smaller, focused changes land faster.
- Keep discussions technical, in English, and on-topic.
- Every contribution is accepted under the project's [MIT License](LICENSE.md).

## Reporting bugs

Before opening a bug report, please:

1. Update to the latest release and confirm the issue still reproduces.
2. Search existing [issues](../../issues) — including closed ones.
3. Collect: OS version, AutoType version, exact steps, expected vs. actual
   behaviour, and a short log excerpt if one is available.

If the bug involves input simulation, mention the target application
(editor, terminal, game, remote session). Input hooks behave differently in
elevated and sandboxed targets, and that detail saves a round-trip.

## Suggesting features

Feature requests are welcome. Describe:

- The concrete workflow you want to speed up.
- What you tried today (hotkeys, scripts, other tools).
- Why the feature belongs inside AutoType rather than next to it.

Scope creep is the single biggest risk for a utility like this. We will push
back on anything that pulls AutoType away from being a fast, small, focused
tool.

## Development setup

Prerequisites:

- Windows 10 or 11
- Node.js 20 LTS or newer
- Git

```powershell
git clone https://github.com/your-org/autotype.git
cd autotype
npm ci
npm run dev
```

`npm run dev` launches the app with hot reload. `npm run build` produces a
portable binary in `dist/`. `npm test` runs the unit suite.

## Branching and commits

- Branch off `main`: `feat/<short-name>`, `fix/<short-name>`, `docs/<short-name>`.
- Use [Conventional Commits](https://www.conventionalcommits.org/) for commit
  subjects. Examples: `feat: add per-profile cooldown`, `fix: release Shift on
  pause`.
- Rebase before you open the PR. We prefer a clean linear history.

## Pull requests

Each PR should:

- Explain what and why in the description, not just what.
- Include tests when it changes behaviour.
- Keep the diff reviewable — split large refactors from feature work.
- Pass `npm run lint` and `npm test`.

Reviewers aim to respond within 72 hours. If you need a nudge after a week,
leave a comment — things fall through the cracks sometimes.

## Code style

- TypeScript, strict mode, no implicit `any`.
- 2-space indentation, single quotes, trailing commas.
- Prefer pure functions. Side effects live at the edges.
- Comments explain *why*, not *what*.

ESLint and Prettier are the source of truth; run `npm run lint -- --fix`.

## Security disclosures

Please **do not** open a public issue for security problems. Email
`security@autotype.app` with a description and reproduction steps. We respond
within 48 hours and credit reporters in the release notes once the fix ships.

## Code of conduct

Participation in this project is governed by the
[Code of Conduct](code_of_conduct.md).

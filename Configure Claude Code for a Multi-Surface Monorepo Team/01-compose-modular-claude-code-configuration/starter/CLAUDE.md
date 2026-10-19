# E-Commerce Platform — Shared Claude Code Conventions

This file is the **project-level** entry point for the e-commerce monorepo. Every teammate's Claude session loads it automatically.

## Scope: what belongs here vs. elsewhere

| Scope | Location | What belongs here |
|---|---|---|
| Project-level | `./CLAUDE.md` and `.claude/` | Shared conventions, repository architecture, team workflows, and rules committed to version control. |
| User-level | `~/.claude/` | Personal preferences that apply across projects, such as a preferred commit message style. User-level settings are **NOT shared with teammates via version control**. |
| Directory-level | A `CLAUDE.md` inside a subdirectory | Instructions specific to that directory, such as conventions for components in `src/components/`. |

Our goal is to keep team-wide conventions consistent and version-controlled while allowing each teammate to maintain personal preferences and each directory to define relevant local instructions.

## Shared standards (modular via @-imports)

The actual conventions live in focused files so this entry point stays scannable:

@.claude/standards/frontend.md
@.claude/standards/api.md
@.claude/standards/database.md
@.claude/standards/testing.md

Path-scoped rules in `.claude/rules/` layer on top of these standards and activate only when Claude is editing matching files (React components, API handlers, and test files).

## Repository layout

```text
src/components/   React components (functional + hooks)
src/pages/        Top-level routes
src/api/          Node.js API handlers
src/db/           PostgreSQL repository-pattern modules
```

Tests are co-located: `Foo.tsx` lives next to `Foo.test.tsx`.

## Troubleshooting

If a `CLAUDE.md` instruction isn't being followed, run `/memory` to see exactly which configuration files were loaded for the current session.

## Team workflows

- `/review <pr-ref>` — codified PR review checklist. (You will author this in Exercise 2.)
- `/deploy-check` — read-only pre-deployment validation. (You will author this in Exercise 3.)

For decisions about when to use plan mode vs. direct execution on this codebase, you will produce a team decision doc in Exercise 4.
# Cursor AI Project Guidelines

Use this file as the source of truth for how to work in this repository.
Fill in the placeholders as the project takes shape.

## Project

- **Name:** test-project
- **Purpose:** _(what this app/library does)_
- **Status:** starter
- **Primary language:** TypeScript

## Tech stack

- Runtime: Node.js
- Language: TypeScript (strict)
- Framework: Next.js (App Router)
- UI: React
- Package manager: npm
- Styling: CSS Modules or Tailwind (match whatever is already in the repo)
- Database / storage: _(add when chosen)_
- Tests: Vitest or Playwright when tests exist
- Lint / format: ESLint + Next.js TypeScript config

## Repository layout

Keep the tree small and predictable. Prefer:

```text
app/           # Next.js App Router routes, layouts, pages
components/    # reusable UI
lib/           # shared helpers, server utilities
public/        # static assets
```

Do not invent extra top-level folders unless there is a real need.

## How the agent should work

1. Read this file before making changes.
2. Inspect existing files before adding new ones.
3. Change only what the task requires. No drive-by refactors.
4. Prefer editing existing files over creating new ones.
5. Match the style already in the repo (naming, imports, formatting).
6. After code changes, run the relevant tests or lint if they exist.
7. If something is ambiguous, state the assumption and proceed with the smallest safe choice.

## Coding standards

- Write clear, direct code. Avoid clever one-liners.
- Use descriptive names. No unexplained abbreviations.
- Keep functions small and single-purpose.
- Handle errors explicitly. Do not swallow exceptions.
- Do not leave unused imports, dead code, or commented-out blocks.
- Do not add comments that only restate the code. Comment _why_, not _what_.
- Do not add secrets, API keys, or `.env` values to git.
- Use TypeScript types; avoid `any`.
- Prefer Server Components by default. Add `"use client"` only when the component needs browser APIs, state, or event handlers.
- Put data fetching and mutations in server code (Server Components, Route Handlers, or Server Actions). Do not fetch secrets from the client.
- Colocate route files under `app/` (`page.tsx`, `layout.tsx`, `route.ts`).

### Example

```text
Bad:  doStuff(d)
Good: createInvoice(draft)
```

## Files the agent should not touch unless asked

- `.env`, credentials, and private keys
- Generated lockfile-only churn with no functional change
- Unrelated markdown, unless the user asked for docs

## Git

- Do not commit unless the user explicitly asks.
- Do not push unless the user explicitly asks.
- Commit messages should explain _why_, in 1–2 sentences.

## Commands

```bash
npm install
npm run dev
npm run build
npm run lint
npm test
```

## Definition of done

A task is done when:

- [ ] The requested behavior works
- [ ] Existing behavior is not broken
- [ ] New files have a clear reason to exist
- [ ] Tests or a manual check cover the change
- [ ] This file is updated if conventions changed

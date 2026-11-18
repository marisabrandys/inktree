# Inktree — agent rules

Inktree is a browser game that gives random sketch prompts. Users sign in, upload drawings, and earn leaves on a personal tree. Stack: Vite + React + TypeScript, Supabase, Cloudflare Pages.

## Workflow (always)
1. Work only on the issue you were given, on branch `agent/issue-<n>`.
2. **Write a failing test first** and commit it alone ("test: ..."). Then implement the fix ("fix: ...").
3. Run `npm run lint && npm run typecheck && npm test` before opening a PR.
4. Open a PR that says `Fixes #<n>`. Never merge it. Never approve it. Never push to `main`.

## Stay in scope
- Touch only the files listed under "Files in scope" in the issue. If you need others, stop and comment on the issue.
- Keep the diff under about 400 changed lines. One issue per PR.

## Never do these
- Delete, skip (`.skip`, `xit`, `test.todo`), or weaken an existing test or assertion.
- Edit `.github/`, `supabase/migrations/`, `src/config/tip.ts`, or this file. These need the owner's explicit review.
- Use or request the Supabase service-role key. Only the anon key and local or test Supabase are available to you.
- Add dependencies without saying why in the PR description.

## Anti-loop rule
If the same test fails twice with the same error, **stop**. Do not try a third variation. Post a comment on the issue with:
- what you tried,
- the exact error,
- your best guess at the cause,
then add the label `needs-human`. A maximum of 3 fix attempts per PR applies to everything.

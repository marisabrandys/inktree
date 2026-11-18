# Inktree

A browser game that gives you random sketch prompts. Draw it, upload it, and earn a leaf on your own tree. Over time the tree fills up with everything you've drawn.

**Status:** early development. Only the project scaffold exists so far.

## Development

```bash
npm install
npm run dev        # start the dev server
npm run lint
npm run typecheck
npm test
```

Stack: Vite, React, TypeScript, Supabase (planned), Cloudflare Pages (planned).

## AI usage

This project is built openly with AI assistance, mainly [Claude Code](https://claude.com/claude-code).

- **How it's used:** AI writes a large share of the code, tests, and issues. Commits that Claude helped write carry a `Co-Authored-By: Claude` trailer. Pull requests it opens say so in their description.
- **Agents:** Automated agents pick up issues, write a failing test first, implement the fix, and open a pull request. Their rules live in [`CLAUDE.md`](CLAUDE.md).
- **Human control:** The maintainer reviews every pull request, and nothing merges without their approval. The `main` branch is protected so that agents cannot merge their own work. Changes to tests, CI, database migrations, and payment links also need explicit owner review.
- **Limits:** Agent runs have turn, time, and attempt caps. If an agent is stuck, it stops and asks for a human instead of looping.
- **What AI doesn't do:** It doesn't have access to production secrets or the database admin key, and it doesn't decide what ships.

If you find a mistake that looks AI-made, please open an issue.

## Contributing

Changes go through pull requests. CI must pass and the owner must approve before anything merges to `main`.

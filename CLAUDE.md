# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm install      # install dependencies
npm run dev      # start dev server at http://localhost:5173
npm run build    # production build
npm run lint     # run ESLint
npm run preview  # preview production build
```

## Architecture

This is a single-file React app — all state, logic, and UI live in `src/App.jsx`. There are no separate components, hooks, or utility files yet.

**Known intentional issues (part of the course):**
- `amount` is stored as a string in state, causing the income/expense totals to concatenate instead of add (the bug)
- "Freelance Work" is seeded as `type: "expense"` but `category: "salary"` (data inconsistency)
- No delete functionality
- All UI in one monolithic component

The app uses in-memory state only — no backend, no localStorage, data resets on refresh.

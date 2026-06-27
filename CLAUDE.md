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

The app is split into four components:

- `App.jsx` — holds the `transactions` array in state and the `handleAdd` callback; composes the three child components
- `Summary.jsx` — receives `transactions`, computes `totalIncome`, `totalExpenses`, and `balance` internally
- `TransactionForm.jsx` — owns all form field state; calls `onAdd(transaction)` on submit
- `TransactionList.jsx` — owns filter state (`filterType`, `filterCategory`); receives `transactions` as a prop

The `categories` array is duplicated in `TransactionForm` and `TransactionList` — not yet extracted to a shared constant.

The app uses in-memory state only — no backend, no localStorage, data resets on refresh.

**Remaining known issue:** "Freelance Work" is seeded as `type: "expense"` but `category: "salary"` (data inconsistency).

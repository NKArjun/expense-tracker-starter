---
name: deploy
description: Deploy to GitHub Pages staging — runs ESLint, builds the production bundle, then pushes dist/ to the gh-pages branch.
---

# Deploy skill

Deploy the app to GitHub Pages staging by running ESLint, building the production bundle, and pushing to `gh-pages`.

## Steps

### 1. Run ESLint (tests gate)

```bash
cd "/Users/arjun/Desktop/Claude Code/expense-tracker-starter" && npm run lint
```

If lint fails, stop and report the errors. Do not proceed to build.

### 2. Build production bundle

```bash
cd "/Users/arjun/Desktop/Claude Code/expense-tracker-starter" && npm run build
```

If the build fails, stop and report the error. Do not proceed to deploy.

### 3. Push dist/ to gh-pages

Use `gh` to check if the `gh-pages` branch exists, then force-push the dist folder:

```bash
cd "/Users/arjun/Desktop/Claude Code/expense-tracker-starter" && npx gh-pages -d dist --message "Deploy to staging [skip ci]"
```

If `gh-pages` is not installed, install it first with `npm install --save-dev gh-pages`, then re-run the deploy command.

## Report

After completing all three steps, report:
- Whether lint passed or failed (and any lint errors)
- Whether the build succeeded and the output size (`dist/` contents)
- The URL where the staging app is live: `https://nkarjun.github.io/expense-tracker-starter/`

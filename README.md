# Claims tracker (free version)

A phone-friendly list of open no-proof class action settlements. A Claude Code scheduled task (included with Claude Pro) checks for new ones every morning and updates settlements.json. GitHub Pages hosts the site for free. Your Filed/Skipped status and "My info" are saved in your browser only.

## Setup (one time, about 10 minutes)

1. Make a free GitHub account, then a new **public** repository named `claims`.
2. Upload everything in this folder (Add file > Upload files).
3. Create a branch named `claude/site`: on the repo page, click the branch dropdown (says "main"), type `claude/site`, and pick "Create branch claude/site from main".
4. Settings > Pages > "Deploy from a branch" > branch `claude/site`, folder `/ (root)` > Save. Your site will be at `https://YOUR-USERNAME.github.io/claims/`.
5. Go to claude.ai/code, connect GitHub when asked, and give it access to the `claims` repo.
6. Go to claude.ai/code/scheduled > New scheduled task. Pick the `claims` repo, set it to daily, and for the instructions paste: "Follow TASK.md in this repo." Then run it once to test.

Open the site on your phone and use Share > Add to Home Screen.

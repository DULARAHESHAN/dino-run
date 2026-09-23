# Prerequisites

Everything you need before following the [end-to-end flow](README.md#end-to-end-flow).

## Accounts

| Account | Why | Notes |
|---|---|---|
| **GitHub** | Hosts the code and runs the pipeline (GitHub Actions) | Free. Actions minutes are unlimited for public repos. |
| **Vercel** | Hosts the live site | The free Hobby plan is enough. Signing up with GitHub is easiest. |

## Tools

| Tool | Version | Check | Needed for |
|---|---|---|---|
| **Git** | any recent | `git --version` | Commit and push |
| **Node.js** (includes npm/npx) | 20+ | `node --version` | Vercel CLI, running the checks locally, `npx serve` |
| **Vercel CLI** | latest | `vercel --version` | `vercel link` and getting the project IDs. Install with `npm install --global vercel`. |
| **GitHub CLI** | optional | `gh --version` | Easier secret setup (`gh secret set`) and watching runs (`gh run watch`). The GitHub website works too. |
| **Code editor and browser** | any | — | Editing files and playing the game |

Check everything at once:

```bash
git --version && node --version && vercel --version && gh --version
```

## Access and permissions

- **Admin or write access to the GitHub repo.** Adding Actions secrets requires admin access, so you'll usually need **your own fork or copy** of the repo.
- **GitHub Actions enabled** on the repo, under **Settings → Actions → General**. Forks start with Actions disabled until you click **Enable**.
- **Git authenticated to GitHub** so `git push` works, through `gh auth login`, an SSH key, or a personal access token.
- **A Vercel access token** scoped to the **same account or team that owns the Vercel project**. A token with a different scope authenticates but can't see the project. See the [debugging guide](README.md#debugging-guide).

## One-time setup you'll do yourself

These steps are covered in the [end-to-end flow](README.md#end-to-end-flow):

1. Create a Vercel project with `vercel link`. It produces the `orgId` and `projectId` values.
2. Add three GitHub Actions secrets: `VERCEL_TOKEN`, `VERCEL_ORG_ID` and `VERCEL_PROJECT_ID`.

## Background knowledge

Basic familiarity is enough:

- Git basics: `add`, `commit` and `push`, and ideally branches and pull requests
- Running commands in a terminal
- Enough HTML and JavaScript to change a string

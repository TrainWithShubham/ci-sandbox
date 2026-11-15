# ci-sandbox

A deliberately broken repo for the [TWS Pipeline Harness](https://github.com/TrainWithShubham/github-actions-ci-analyzer).

`npm run build` fails in CI because `package.json` has no `build` script. The harness reads the failed run, finds the fix in its runbook,
opens a PR, waits for a human approver, then merges and starts CI again.

## Use it

1. Click **Use this template** (or `gh repo create <you>/ci-sandbox --template TrainWithShubham/ci-sandbox --public --clone=false`). Keep your copy **public**:
   the PRs and CI logs the agent creates are visible to everyone, so do not put anything private in it.
2. Create a fine-grained token scoped to **only your copy**: Contents, Pull requests, Actions and Workflows (read and write), Metadata (read).
3. Follow the quickstart in the harness repo: `./start_local.sh`, then `./start_local.sh seed`.

`./start_local.sh seed <scenario>` resets this repo to a broken state (`missing-build`, `failing-test`, `secret-leak`, `injection`).
Do not fix it by hand: that is the agent's job.

Safe to delete. MIT licensed.

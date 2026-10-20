# Agentic Hello World

A small GitHub Agentic Workflows demo using GitHub Copilot.
It runs only when started manually and creates one hello-world issue.

## Files

1. `.github/workflows/hello-world.md`: settings and AI instructions.
2. `.github/workflows/hello-world.lock.yml`: generated GitHub Actions workflow.

## Setup

1. Install the compiler: `gh extension install github/gh-aw`.
2. For this personal repository, create a fine-grained GitHub personal access
   token with the account-level **Copilot Requests** permission. Add it as an
   Actions secret named `COPILOT_GITHUB_TOKEN`. Do not put the token in Git.
3. Publish both workflow files to the default branch when ready.
4. Open **Actions**, select the hello-world workflow, and choose **Run workflow**.
   Or run `gh aw run hello-world` from this directory.
5. Look for a new issue whose title starts with `[AI demo]`.

## Direct Copilot CLI demo

The separate `.github/workflows/hello-direct.yml` workflow calls Copilot CLI
directly with `--model auto`, without gh-aw's model resolver. It uses the same
`COPILOT_GITHUB_TOKEN` secret and writes a greeting to the run summary.

1. Publish the YAML file to the default branch.
2. Open **Actions → Hello with Copilot CLI → Run workflow**.
3. Open the completed run's summary to read the greeting.

This workflow does not need compilation. It uses pinned CLI and setup-action
versions, no repository checkout, and no GitHub token permissions. Its AI use
counts against your Copilot allowance. Free-plan access still needs to be
confirmed by a successful run.

## Maintaining the agentic demo

1. Edit the Markdown source; run `gh aw compile` after changing its YAML settings.
2. Keep the source and generated lock file together in Git.
3. Standard GitHub-hosted runner time is free for this public repository.
   AI calls consume the authenticated user's Copilot allowance.
4. Each run can create at most one issue; the agent job has a five-minute timeout.
5. This demo does not give the agent tools to read issues or change code.

## References

1. [GitHub Agentic Workflows](https://github.com/github/gh-aw)
2. [Authentication](https://github.github.com/gh-aw/reference/auth/)
3. [Billing](https://github.github.com/gh-aw/reference/billing/)


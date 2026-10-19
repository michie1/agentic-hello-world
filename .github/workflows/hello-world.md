---
on:
  workflow_dispatch:

timeout-minutes: 5

permissions:
  contents: read

tools:
  github: false
  bash: false
  cli-proxy: false

safe-outputs:
  create-issue:
    title-prefix: "[AI demo] "
    max: 1
---

Create one GitHub issue to demonstrate an agentic workflow.

1. Use the title "Hello from an agentic workflow".
2. Write a short, friendly greeting.
3. Explain that a manual GitHub Actions trigger started an AI agent, and a
   separate safe-output job published this issue.
4. Include a simple original two-line poem about software maintenance.
5. Do not edit repository files or run shell commands.


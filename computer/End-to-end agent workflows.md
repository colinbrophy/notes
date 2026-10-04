#draft #ai-written

# End-to-end agent workflows

A coding agent can do more than write code: it can build tools, operate other systems, inspect the results and revise them. The user can delegate a whole workflow rather than supervise every step.

## What changes for the user

- **Ask for the outcome**, not just assistance with individual steps. The agent can coordinate the tools needed to get there.
- **Missing tools need not be a blocker.** Ask the agent to build a controllable tool when existing apps do not fit.
- **Delegate review and revision too.** Producing a first draft is only part of the job.
- **Keep direction and consequential choices.** Supply constraints, choose between alternatives, and judge whether the outcome actually serves your purpose.
- **Prepare for unattended execution.** Accounts, permissions and usage limits can stop an otherwise capable workflow.

## Familiar review loops, broader application

The same [[AI coding agents|coding-agent]] loop applies beyond code: create → separate reviewer → fix → verify.

**Review the actual result, not just the implementation or the agent's report.** For software that might mean running it; for a video, inspecting rendered frames. The artifact changes, but the feedback loop is familiar.

Bounded review is not guaranteed convergence. A final unreviewed fix remains unverified, and agent reviewers do not replace your final judgement.

## Example: BLISS

Claude coordinated music and video generators, built a Windows XP animation renderer, and used chapter-level review/fix passes. The human supplied direction and chose the song. A permission prompt reportedly caused a nine-hour stall; the final polish was not independently reviewed.

Source: [BLISS production folder](https://drive.google.com/drive/folders/1aIbRs2f6sVpCxO4TGoBfBpaZXgHngphJ). Captured from our discussion; production details have not been independently rechecked here.

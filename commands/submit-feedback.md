---
name: submit-feedback
description: Report a bug or request a feature for the pyramid-principle plugin — drafts a GitHub issue and files it only after you approve
argument-hint: "[what broke, or what you wish it did]"
---

# Submit pyramid-principle feedback

File the user's report as a GitHub issue on `tyroneross/pyramid-principle`. Issues are this
plugin's support channel — the manifest carries no contact address by design.

This command handles **both** kinds of report:

| Kind | What the user is saying | Issue label |
|---|---|---|
| Bug | "it broke", "wrong output", "it crashed", "it did X instead of Y" | `bug` |
| Feature request | "I wish it could", "can it also", "it should support" | `enhancement` |

Classify from what the user wrote. Ask only if genuinely ambiguous — one question, not a form.

## Steps

1. **Understand the report.** If the user has not already said what happened or what
   they want, ask once.

2. **Gather context**, without interrogating the user:
   - plugin version: `git -C "${CLAUDE_PLUGIN_ROOT:-.}" rev-parse --short HEAD` (this
     plugin ships auto-SHA — `.claude-plugin/plugin.json` carries no `version` key)
   - `claude --version`
   - `uname -sm`
   - which command or skill misbehaved, and what it did instead (bug), or
     what the user is trying to accomplish today and why the current surface
     does not get there (feature request)

3. **Draft the issue.** Use the template for the classified kind:

   **Bug**
   ```
   Title: <one line: what broke>

   ## What happened
   ## What I expected
   ## Steps to reproduce
   ## Environment
   plugin: pyramid-principle @ <sha> · claude: <version> · os: <uname -sm>
   ```

   **Feature request**
   ```
   Title: <one line: the capability, not the implementation>

   ## What I am trying to do
   ## Why the current surface does not get there
   ## What "done" would look like
   ## Environment
   plugin: pyramid-principle @ <sha> · claude: <version> · os: <uname -sm>
   ```

4. **CONFIRM BEFORE FILING — required.** Print the exact title and body you intend
   to file and ask the user, in plain words, to approve it. A GitHub issue is public
   and cannot be unsent. Do not run `gh issue create` until the user has said yes to
   the text they just read. If they want edits, revise and show it again.

5. **File it**, only after approval:

   ```bash
   gh issue create --repo tyroneross/pyramid-principle \
     --title "<approved title>" \
     --label "<bug|enhancement>" \
     --body "<approved body>"
   ```

6. **If `gh` is missing or unauthenticated**, do not fail — print the URL so the user
   can paste the approved body in a browser:
   https://github.com/tyroneross/pyramid-principle/issues/new

7. **Report the resulting issue URL** back to the user.

## Rules

- Never file without explicit approval of the exact text. This gate is the point of
  the command.
- A GitHub issue is public. Redact secrets, tokens, absolute home paths, and any file
  contents the user has not seen before sending.
- Report the user's words. Do not editorialize their complaint into a feature pitch
  or a feature request into a bug.

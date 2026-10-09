# Install Outside Chair 0.7.2 in Claude Cowork or Claude Code

This ZIP contains the Outside Chair plugin and connects Claude Code to the
production Outside Chair MCP server at `https://app.outsidechair.com/mcp`.
It contains no credentials, private strategy data, or application source code.
The Codex and Claude downloads contain the same strategy skill and production
MCP connection, packaged in each platform's native archive format. Outside Chair
therefore maintains one plugin source and one feature version while producing
separately validated ChatGPT/Codex and Claude ZIP files.

## Requirements

- A Claude account with plugin upload access, or Claude Code installed and
  signed in.
- Access to the user's own email inbox. Outside Chair uses a passwordless
  email-code flow; there is no separate Outside Chair signup.

## Install in Claude.ai or Cowork

1. Open Claude and go to **Customize > Plugins > Add > Upload plugin**.
2. Select `outside-chair-claude-0.7.2.zip` without unpacking it.
3. Open the installed Outside Chair plugin and select its **Connectors** tab.
4. Add or connect `outside-chair`, then complete the Outside Chair browser
   authorization. Enter the user's own email address and the one-time code
   sent to that inbox. This automatically creates or reconnects the user's
   private account. New accounts then create their first company or project workspace.
5. Start a new chat and use the verification prompt below.

## Install in Claude Code

Create a dedicated directory and extract the ZIP into it:

```sh
mkdir -p ~/.claude/skills/outside-chair
unzip /absolute/path/to/outside-chair-claude-0.7.2.zip -d ~/.claude/skills/outside-chair
claude plugin validate ~/.claude/skills/outside-chair
```

The validation should finish with `Validation passed`. Start a new Claude Code
session after installation:

```sh
claude
```

In Claude Code, open `/plugin` and confirm that `outside-chair` is loaded. Then
open `/mcp`, select `outside-chair`, and complete the browser sign-in if Claude
asks you to authenticate. Enter your own email and its one-time code.

## First verification prompt

Paste this into the new session:

> Use the Outside Chair plugin and only its production MCP tools. Check my
> connection, select my sole workspace or ask me to choose by name, then show the
> five most important items requiring attention. Do not use local files, databases,
> fixtures or remembered data.

The authenticated email shown must be the user's own email. Stop if it is not.

## Analysis Exchange verification

Start with a non-publishing check:

> Use the Outside Chair plugin in a workspace I select by name. Show my Analysis
> Exchange status and available frameworks. Then prepare and validate, but do
> not publish, a public-source PESTEL for an industry I choose. Confirm that
> validation stored nothing.

When that passes, publish a separate public-source analysis. The agent must report
the exact stored subject, executive conclusion, immediate publication status and
withdrawal action, and must explain that withdrawal prevents future distribution
but cannot recall delivered copies. Private workspace records must never be copied
into the exchange.

## Test with the tester's own documents

Put copies of the test documents in a dedicated working folder, start Claude
Code from that folder, and begin with this read-only intake prompt:

> Read the strategy documents in this folder. Use the Outside Chair plugin to
> inspect my current workspace. Propose the priorities, initiatives,
> assumptions, signposts, measures, and evidence that should be added or
> updated. Show the exact proposed changes first and do not write anything
> until I explicitly approve them.

After reviewing the proposal, the tester can approve individual writes, run a
review, and prepare a decision confirmation. Use synthetic or non-sensitive
documents for the first test.

## Suggested functional tests

Read-only strategy context:

> Use Outside Chair to show my current priorities, initiatives, assumptions,
> signposts, measures, evidence, decisions, actions, and reviews. Report empty
> categories explicitly.

Decision workflow, without writing yet:

> Use Outside Chair to draft a decision from the current context. Show the named
> context, rationale and proposed actions without internal IDs. Do not store a
> proposal or confirm anything until I approve the draft.

## Important data boundary

- Installing the ZIP does not copy or expose the founder's private workspace.
- The user sees only data authorized for their authenticated Outside Chair
  identity and workspace.
- Write operations should always be reviewed and explicitly confirmed.

## Troubleshooting

- Plugin missing: start a new session and check `/plugin`.
- MCP disconnected: open `/mcp`, select `outside-chair`, and authenticate again.
- Wrong identity: stop immediately, disconnect the MCP server, and sign in with
  your own account.
- Skill not triggered automatically: run
  `/outside-chair:outside-chair-strategy-companion` or explicitly say
  "Use the Outside Chair plugin."

For a temporary one-session test instead of a permanent installation, extract
the ZIP into any folder and run `claude --plugin-dir /absolute/path/to/folder`.

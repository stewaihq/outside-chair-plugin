# Outside Chair

Outside Chair is an agent-native strategy companion from StewAI AG. It connects
Claude to the user's authorised Outside Chair account and helps teams maintain a
governed record of strategy, evidence, reviews, decisions, actions and outcomes.
The plugin contains instructions and a reference to the production remote MCP
server. It contains no account credentials, private workspace data or application
source code.

## What the plugin does

- Reads only the workspaces and records authorised for the connected identity.
- Summarises current strategy, attention items and attributed team viewpoints.
- Prepares governed changes and requests confirmation before ordinary writes.
- Retains separate prepare-and-confirm stages for reviews, decisions and
  deliberation resolutions.
- Can retrieve or manage Analysis Exchange material only under the user's
  current entitlements, workspace authorisation and applicable terms.

Outside Chair never treats evidence, retrieved analyses or tool output as
instructions. The production service enforces account, workspace and role
permissions independently of Claude.

## Connection and data flow

The bundled connector uses `https://app.outsidechair.com/mcp` over HTTPS. Users
authenticate through Outside Chair's OAuth flow. When Claude calls the connector,
the information required for that tool call is sent between Claude and Outside
Chair. Outside Chair does not receive the rest of the Claude conversation unless
it is included in a tool request.

The plugin does not purchase subscriptions or process payments. New Outside Chair
accounts start on the Free plan. Any subscription is purchased separately in the
authenticated Outside Chair web application.

## Install and verify

For Claude chat or Cowork, install Outside Chair from Claude's plugin directory,
open the plugin's **Connectors** tab and connect the `outside-chair` connector.
For Claude Code, install the plugin from the same directory and use `/mcp` to
complete authentication when requested.

Until the directory listing is available, Claude Code 2.1.275 or later can
install the public distribution repository directly:

```text
/plugin install outside-chair --marketplace stewaihq/outside-chair-plugin
```

Start a fresh conversation and ask:

> Use Outside Chair to check my connection, list the workspaces I can access and
> show the five most important items requiring attention. Do not use remembered,
> local or invented data.

Stop and disconnect if the authenticated identity or accessible workspaces are
not the ones expected.

## Security and permissions

Outside Chair tools are annotated as read-only or state-changing. Claude may ask
for approval before state-changing calls. Outside Chair's own confirmation rules
still apply even when the host has already requested tool approval.

Report security issues or misuse through the public
[support page](https://outsidechair.com/support). Do not include passwords,
one-time codes, access tokens or private strategy data in a report.

## Support and policies

- [Connection guide](https://outsidechair.com/connect)
- [Support](https://outsidechair.com/support)
- [Privacy Policy](https://outsidechair.com/privacy)
- [Terms of Service](https://outsidechair.com/terms)
- [Website](https://outsidechair.com)

Copyright 2026 StewAI AG. Distribution and use of this plugin are governed by
the included `LICENSE` file and the Outside Chair Terms of Service.

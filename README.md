# Signatoro

The agentic email signature platform: one source of truth for the email signature your people and your AI agents send.

This plugin connects Codex, Cursor, Grok Bot and Grok Build to the Signatoro MCP server at `https://signatoro.com/mcp`. Every plan includes the MCP server and API, Free too.

## What you get

- **Agents that send as you** fetch your saved signature before each email, always the latest version.
- **Each agent signs as itself.** Several agents sending for you each get their own signature: yours with a line such as "Sent by Ada, my AI assistant", or the agent's own name and role. A connection made for one agent always signs as that agent.
- **Every agent you switch to** fetches the same saved signature, so one edit reaches all of them.
- **Company AI agents** sign with your company's brand and compliance footnote, and use no seat.
- **One API for every sender.** Your CRM, sequencer and help desk read the same signatures, so one edit reaches all of them. Connect Zoho Mail once and changes reach it by itself.

## Install

- **Cursor:** install **Signatoro** from the Cursor Marketplace.
- **Codex:** add this repository as a plugin; the manifest is `.codex-plugin/plugin.json`.
- **Grok Build:** open `/plugins`, find **signatoro** in the Marketplace tab, and install it.

Three tools work right away. For the rest, the first call opens your browser to sign in to Signatoro. There is no API key to paste.

## Tools

Without signing in:

- `create_signature` - preview a signature from your name and details
- `list_templates` - list the signature layouts
- `get_install_steps` - get the steps to add a signature to your mail app

Signed in:

- `get_signature` - get your saved signature
- `update_my_signature` - save or change your signature

Company owners:

- `list_members` - list the people and agents in your company
- `add_member` - add a person or an agent mailbox and send an invite
- `update_member_field` - change a member's details
- `remove_member` - remove a member
- `resend_invite` - send an invite again

## What it connects to

One endpoint: `https://signatoro.com/mcp` (streamable HTTP). Sign-in uses OAuth, discovered from the server. The plugin runs no local code and stores no credentials in this repo. Signatoro never reads or stores your email.

## Docs and support

- Guide: https://signatoro.com/docs/install-signature/agent/mcp
- Support: support@signatoro.com

## License

MIT

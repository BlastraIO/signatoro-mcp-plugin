# Signatoro

The same email signature on every email you send: from every mail app, on every device, and from every AI agent that sends on your behalf.

This plugin connects Cursor, Grok Bot and Grok Build to the Signatoro MCP server at `https://signatoro.com/mcp`.

## What you get

- **Agents that send as you** fetch your saved signature before each email, always the latest version.
- **Agents with their own mailbox** join your company like a colleague and get their own signature in your company's style, with the same compliance footnote as everyone else, such as a confidentiality notice or a registered-office line. They count as members of your flat-price plan.
- **One API for every sender.** Your CRM, sequencer and help desk read the same signatures, so one edit reaches all of them. Connect Zoho Mail once and changes reach it by itself.

## Install

- **Cursor:** install **Signatoro** from the Cursor Marketplace.
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

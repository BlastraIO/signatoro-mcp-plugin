# Signatoro

One email signature for humans and AI agents.

Signatoro is the agentic email signature platform: save your signature once, and your people and every AI agent you connect use the same one.

This plugin connects Claude Code, Codex, Cursor, Grok Bot and Grok Build to the Signatoro MCP server at `https://signatoro.com/mcp`. Every plan includes the MCP server and API, Free too.

## What you get

- **Agents that send as you** fetch your saved signature when you ask them to sign, or on every email once their instructions say so, always the latest version.
- **Each agent signs as itself.** Several agents sending for you each get their own signature: yours with a line such as "Sent by Ada, my AI assistant", or the agent's own name and role. A connection made for one agent always signs as that agent.
- **Every agent you switch to** fetches the same saved signature, so one edit reaches all of them.
- **Company AI agents** sign with your company's brand, their own name and role and an AI line, and use no seat.
- **One API for every sender.** Your CRM, sequencer and help desk read the same signatures, so one edit reaches all of them. Connect Zoho Mail once and changes reach it by itself.

## Install

- **Grok Bot:** add **Signatoro** under Connect apps. To give each of your Bots its own signature, add an AI assistant on Signatoro for each Bot; the [Grok Bot guide](https://signatoro.com/docs/install-signature/agent/grok-bot) walks through it, including plus aliases of your `mail.grokbot.com` address.
- **Claude Code:** run `/plugin install signatoro --marketplace BlastraIO/signatoro-mcp-plugin`.
- **Cursor:** install **Signatoro** from the Cursor Marketplace.
- **Grok Build:** open `/plugins`, find **signatoro** in the Marketplace tab, and install it.
- **Codex:** the plugin manifest is `.codex-plugin/plugin.json`.

Three tools work right away. For the rest, the first call opens your browser to sign in to Signatoro. There is no API key to paste.

In Claude Code and Claude, the plugin's `email-signature` skill signs the emails Claude writes for you with your saved signature, so there is nothing to add to your instructions. For other agents, add the [email signature rule](https://signatoro.com/docs/install-signature/agent#tell-your-agent-to-use-your-signature) to their instructions.

## Tools

Without signing in:

- `create_signature` - preview a signature from your name and details
- `list_templates` - list the signature layouts
- `get_install_steps` - get the steps to add a signature to your mail app

Signed in:

- `get_signature` - get your saved signature, with your sender details
- `list_signatures` - list your signatures and your AI assistants' signatures
- `update_my_signature` - save or change your signature

Company owners:

- `list_members` - list the people in your company and their invitations
- `add_member` - invite a person to your company
- `update_member_field` - change a member's details
- `remove_member` - remove a member, after you confirm
- `resend_invite` - send an invite again

## Skill

- `email-signature` - when Claude sends, replies to, forwards or drafts an email for you, it fetches your saved signature and appends it after the body, with your real contact details. Tell Claude when an email should go unsigned.

## What it connects to

One endpoint: `https://signatoro.com/mcp` (streamable HTTP). Sign-in uses OAuth, discovered from the server. The plugin runs no local code and stores no credentials in this repo. Signatoro never reads or stores your email.

## Docs and support

- MCP guide: https://signatoro.com/docs/install-signature/agent/mcp
- Grok Bot guide: https://signatoro.com/docs/install-signature/agent/grok-bot
- Support: support@signatoro.com

## License

MIT

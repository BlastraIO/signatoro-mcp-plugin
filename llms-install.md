# Installing the Signatoro MCP server

Signatoro is a hosted, remote MCP server. There is nothing to clone, build
or run locally, and no API key to paste.

## Cline

Add this to `cline_mcp_settings.json` (MCP Servers > Configure):

```json
{
  "mcpServers": {
    "signatoro": {
      "type": "streamableHttp",
      "url": "https://signatoro.com/mcp"
    }
  }
}
```

Three tools work without signing in: `create_signature`, `list_templates`
and `get_install_steps`. The first call to any other tool starts an OAuth
sign-in to Signatoro in the browser. The server registers clients
dynamically and accepts loopback redirect URIs, such as Cline's local
callback.

## Any other MCP client

- URL: `https://signatoro.com/mcp`
- Transport: streamable HTTP
- Auth: OAuth 2.1, discovered from the server, with dynamic client
  registration. A client that cannot sign in can send
  `Authorization: Bearer <key>` with a Signatoro API key instead, which
  gets the read tools (`get_signature`, `list_signatures`).

## Make the agent sign every email

Add the email signature rule to the agent's instructions (for Cline, a
`.clinerules` file):
https://signatoro.com/docs/install-signature/agent#tell-your-agent-to-use-your-signature

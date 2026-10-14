# Security

This plugin runs no local code. It points the agent at one remote MCP
endpoint, `https://signatoro.com/mcp` (streamable HTTP), and stores no
credentials. Sign-in uses OAuth discovered from the server; an agent without
OAuth can send a Signatoro API key as a bearer token, kept in its environment.
Signatoro never reads or stores your email.

## Reporting a vulnerability

Email support@signatoro.com with "Security" in the subject, the details and
the steps to reproduce. Please keep security reports out of public issues.

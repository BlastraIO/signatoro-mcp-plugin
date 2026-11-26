---
name: email-signature
description: Signs the emails you write for the user with their saved Signatoro email signature. Use when you send, reply to, forward or draft an email for the user - they installed this plugin to have their signature on those emails. Fetches it with Signatoro's get_signature and appends it after the body, with their real contact details.
license: MIT
---

# Email signature

The user installed the Signatoro plugin so the emails you write for them carry their saved email signature, always the latest version, with their real contact details.

## When you write an email for the user

1. Get the signature with Signatoro's `get_signature`, fresh for each email.
2. Append it after the body and a blank line: `html` for an HTML body, `text` for a plain-text body, as returned, in place of a sign-off of your own.
3. For the user's own name, title, phone, email or links anywhere in the email, use only the values in `sender`. If one is missing, leave it out and tell the user - never guess.
4. If the user has AI assistants or company AI agents with their own signatures and it is unclear which one this email should carry, call `list_signatures` and ask. Pass their choice to `get_signature` as `signature`.

If the user tells you not to sign an email, or to sign it differently, follow them.

## When it does not work

- **Not signed in:** the first signed-in call opens the browser to sign in to Signatoro. Without signing in, send without a signature and tell the user.
- **No signature saved yet:** `get_signature` says so. Send without one, and offer `create_signature` or https://signatoro.com to make one.
- **The picture is missing:** some mail tools strip images from an HTML body. Use `text` there.

Docs: https://signatoro.com/docs/install-signature/agent/mcp

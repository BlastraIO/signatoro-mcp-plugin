---
name: email-signature
description: Fetch the person's saved email signature from Signatoro and end each email with it; set up a separate signature for each of the person's Bots.
---

# Email signature from Signatoro

Signatoro holds the person's saved email signature, and a version for each AI assistant they add there. An edit on Signatoro reaches the next email from every Bot, because each email fetches the current version.

## Before each email you draft

1. Fetch the signature:
   - With the Signatoro plugin connected: call `get_signature`. If the person has several signatures and it is unclear which one this email should carry, call `list_signatures` and ask.
   - Otherwise: `GET https://signatoro.com/api/v1/signature` with the header `Authorization: Bearer <key>`, using the key the person stored as a secret for this Bot. Never ask for the key in chat, and never repeat it in a message, email or file.
2. End the email with it after a blank line: `html` for an HTML body, `text` for a plain-text body, exactly as returned.
3. Write no sign-off or signature block of your own. If the mailbox already added one, keep one signature, never two.
4. For the person's name, title, phone, email or links anywhere in the email, use only the values in `sender`. If one is missing, leave it out and tell the person.
5. Show the draft for approval as usual.

If neither the plugin nor a key is available, ask the person to connect Signatoro, or to paste their signature text ("Copy as text" on Signatoro) for you to use exactly as written.

## Give each Bot its own signature

Walk the person through this once per Bot:

1. On signatoro.com, on their signature page, add an AI assistant named after the Bot (for example "Receipts Bot"). It can sign as the person ("Sent by Receipts Bot, my AI assistant") or as the Bot with its own name and role; by default it carries a line saying an AI sent it. On a Company plan, the owner adds a company agent instead, with the company's brand.
2. Under "For tools and assistants", generate an API key for that assistant. A key made for one assistant always returns that assistant's signature.
3. Give that Bot its key as a secret, and add this email-signature skill to it.
4. Optional: have the Bot send from its own plus alias of the person's mail.grokbot.com address, such as yourname+receipts@mail.grokbot.com, so its mail has its own alias as well as its own signature.
5. Send a test to the person and check the email ends with that Bot's signature, once.

Guide: https://signatoro.com/docs/install-signature/agent/grok-bot

# MasterKi plugin for Claude

MasterKi connects Claude to your Anki decks. This plugin lets Claude (Claude Code and Cowork) turn a conversation, notes or vocabulary into flashcards, and search, edit and tidy the cards you already have. MasterKi syncs every change to Anki through AnkiWeb. The connector is free, and you don't need to install the MasterKi app; it's there if you want to review on your phone.

The same repository is also a [Gemini CLI extension](#gemini-cli).

## What's inside

| Component | What it does |
| --- | --- |
| `.mcp.json` | Connects Claude to MasterKi's remote MCP server at `https://masterki.org/mcp`: `list_decks`, `search_notes`, `read_notes`, `add_notes`, `edit_notes`, `delete_notes`, and `add_flashcards`. |
| `gemini-extension.json`, `GEMINI.md` | The same server and guidance for Gemini CLI. |
| `skills/make-flashcards` | Tells Claude how to write good flashcards (one fact per card, short answers, consistent direction for language cards), avoid duplicates, and edit or delete cards safely. |

## Install

```bash
# From the Claude plugin directory, once listed:
/plugin install masterki
# Or straight from this repository:
/plugin marketplace add https://github.com/harryob2/masterki-claude-plugin
/plugin install masterki
```

## Connect your account

The first time Claude uses MasterKi, it opens a MasterKi sign-in page:

1. **Sign in or create a free account** with Apple, Google or email. If you already use the MasterKi app, you can type a pairing code from **Settings → Connect MasterKi to AI apps** instead.
2. **Choose** whether Claude's changes apply straight away or wait for your approval.
3. **Sign in to AnkiWeb** (Anki's free sync service) so cards reach your decks. You can also do it later at https://masterki.org/connect/ankiweb. Your AnkiWeb password is used once to get a sync key and is never stored.

Approve waiting changes at https://masterki.org/connect/changes or in the MasterKi app. To disconnect, remove the connector in Claude, or open **Settings → Connect MasterKi to AI apps** in the app.

## Usage

- "Make flashcards from this lecture summary and save them to MasterKi."
- "Turn the Spanish phrases we practised into MasterKi cards for my Spanish deck."
- "Save five cards about the causes of the First World War to MasterKi."
- "Find the cards in my Spanish deck with typos and fix them."
- "Which of my biology cards are about the cell cycle?"

## Documentation

Setup and usage: https://masterki.org/ai-apps

## Gemini CLI

```bash
gemini extensions install https://github.com/harryob2/masterki-claude-plugin
```

Then ask Gemini CLI to make flashcards; it opens the same MasterKi sign-in page.

## Privacy Policy

Full policy: https://masterki.org/privacy

In short:

- **What is collected:** the card text Claude sends or asks to change, the name of the AI app, and OAuth tokens (stored only as SHA-256 hashes). With deck access, MasterKi's server keeps a copy of your Anki collection without media, synced with AnkiWeb, to answer Claude's requests. MasterKi does not receive your conversation.
- **AnkiWeb:** if you sign in to AnkiWeb on masterki.org, your password is passed to AnkiWeb once to get a sync key and is never stored. The sync key is stored encrypted.
- **Third parties:** card and collection data are not sold or shared and are not sent to AI providers by the connector. Email sign-in is checked by Google Firebase Authentication.
- **Retention:** the server copy of your collection is deleted after 30 days without use; backups last up to 7 days; access tokens 7 days and refresh tokens 365 days, or until you disconnect. Deleting your MasterKi account deletes all of it.
- **Contact:** [hello@masterki.org](mailto:hello@masterki.org)

## Support

[hello@masterki.org](mailto:hello@masterki.org) · https://masterki.org

# MasterKi plugin for Claude

MasterKi is a spaced-repetition flashcard app for Android and iOS. This plugin lets Claude (Claude Code and Cowork) turn a conversation, notes or vocabulary into flashcards and save them to your MasterKi app. The cards wait in the app until you review them and add them to a deck.

## What's inside

| Component | What it does |
| --- | --- |
| `.mcp.json` | Connects Claude to MasterKi's remote MCP server at `https://masterki.org/mcp`. It has one tool, `add_flashcards`. |
| `skills/make-flashcards` | Tells Claude how to write good flashcards (one fact per card, short answers, consistent direction for language cards) and when to save them. |

## Install

```bash
# From the Claude plugin directory, once listed:
/plugin install masterki
# Or straight from this repository:
/plugin marketplace add https://github.com/harryob2/masterki-claude-plugin
/plugin install masterki
```

## Connect your account

The first time Claude uses MasterKi, it opens a MasterKi sign-in page. Use either:

- **A pairing code:** in the MasterKi app, open **Settings → Connect MasterKi to AI apps** and tap **Get a pairing code**, then type the code on the page.
- **Your MasterKi email and password,** if you have an email login (the iOS app).

To disconnect, open **Settings → Connect MasterKi to AI apps** in the app and remove Claude from the connected apps list.

## Usage

- "Make flashcards from this lecture summary and save them to MasterKi."
- "Turn the Spanish phrases we practised into MasterKi cards for my Spanish deck."
- "Save five cards about the causes of the First World War to MasterKi."

## Documentation

Setup and usage: https://masterki.org/ai-apps

## Privacy Policy

Full policy: https://masterki.org/privacy

In short:

- **What is collected:** the front and back text of the cards Claude sends, an optional deck name, the name of the AI app that sent them, and OAuth tokens (stored only as SHA-256 hashes) that link the AI app to your MasterKi account. MasterKi does not receive your conversation, only the cards.
- **How it is used and stored:** cards are held in your MasterKi inbox on MasterKi's servers until your app downloads them and confirms it saved them, then they are deleted from the server.
- **Third parties:** card text is not sold or shared. If you sign in with email and password, the credentials are checked by Google Firebase Authentication and are never stored by MasterKi.
- **Retention:** cards stay on the server only until the app stores them (at most 500 wait at once). Access tokens expire after 7 days and refresh tokens after 365 days, or immediately when you disconnect. Deleting your MasterKi account deletes all of it.
- **Contact:** [hello@masterki.org](mailto:hello@masterki.org)

## Support

[hello@masterki.org](mailto:hello@masterki.org) · https://masterki.org

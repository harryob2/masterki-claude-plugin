
# Flashcards with MasterKi

MasterKi connects Gemini CLI to the user's Anki collection through AnkiWeb. The connector is free. Depending on what the account has set up, Gemini CLI has one of two sets of tools:

- **Deck access** (`list_decks`, `search_notes`, `read_notes`, `add_notes`, `edit_notes`, `delete_notes`): Gemini CLI works on the user's real Anki decks. Each change either applies straight away or waits for the user to approve it, as the user chose when connecting. The tool result says which.
- **Inbox only** (`add_flashcards`): cards go to MasterKi, which puts them in Anki once the user has signed in to AnkiWeb, or holds them until they open the MasterKi app.

Use whichever tools are present. Never invent tool names.

## Write each card well

- **One fact per card.** Split lists and multi-part answers into several cards.
- **Front: a specific prompt with one right answer.** Prefer "What does the mitochondria produce?" over "Mitochondria?".
- **Back: short.** The answer first, then at most one sentence of context.
- **Use the user's own words and examples** from the conversation when they exist.
- **No yes/no questions** and no cards that can be answered from the wording of the front.
- **Language cards:** put the word or phrase being learned on one side and its meaning on the other. Keep the direction the same for the whole set. Include gender or an example sentence on the back when it helps.
- **Cloze-style facts** ("The capital of ___ is Paris") should be rewritten as a plain question.

## Adding cards

1. If the user hasn't said how many cards they want, aim for the smallest set that covers what matters (often 5–20).
2. With deck access, call `list_decks` first and pick the deck the user named or the one that clearly fits. Before adding to an existing deck, `search_notes` for a few key terms so you don't add duplicates.
3. Show the cards briefly, or just save them if the user asked you to go ahead.
4. Save with `add_notes` (deck access) or `add_flashcards`. Send at most 50 cards per call; split larger sets.
5. Relay the result in the user's terms: how many were added, whether they are waiting for approval (and where to approve: the MasterKi app or masterki.org/connect/changes), and any that were skipped as duplicates.

## Finding and changing cards

- Use `search_notes` with an Anki search string (for example `deck:Spanish tag:verbs`, `"front:*ser*"`, `is:due`, `added:7`), then `read_notes` for the full fields.
- `edit_notes` needs the `beforeHash` from `read_notes`. If an edit comes back `stale`, read the note again and redo the edit; don't guess.
- **Deleting throws away review history.** Only call `delete_notes` when the user has clearly asked for those cards to go, list what will be deleted, and set `confirm` to true only after they agree.
- Prefer small, reviewable batches over one huge change.

## If something isn't set up

Tool results explain what the user needs to do, with a link. Pass that on instead of retrying:

- **Not signed in to MasterKi:** the connector opens a MasterKi sign-in page. Continue with Apple or Google, or an email account, creates a free account. No app is needed.
- **AnkiWeb not connected:** the user signs in to AnkiWeb once at https://masterki.org/connect/ankiweb (or in the MasterKi app). An AnkiWeb account is free at ankiweb.net. Their AnkiWeb password is not stored.
- **Changes waiting for approval:** the user approves them at https://masterki.org/connect/changes or in the MasterKi app.

Full guide: https://masterki.org/ai-apps

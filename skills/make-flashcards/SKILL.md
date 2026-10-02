---
name: make-flashcards
description: Write good spaced-repetition flashcards and save them to the user's MasterKi app. Use when the user asks to make flashcards, memorise something, study vocabulary, or turn notes, an article or a conversation into cards for MasterKi or Anki.
---

# Making flashcards for MasterKi

MasterKi saves cards to an inbox in the user's app. Nothing is added to a deck until the user reviews the cards there, so it is safe to save a first draft.

## Write each card well

- **One fact per card.** Split lists and multi-part answers into several cards.
- **Front: a specific prompt with one right answer.** Prefer "What does the mitochondria produce?" over "Mitochondria?".
- **Back: short.** The answer first, then at most one sentence of context.
- **Use the user's own words and examples** from the conversation when they exist.
- **No yes/no questions** and no cards that can be answered from the wording of the front.
- **Language cards:** put the word or phrase being learned on one side and its meaning on the other. Keep the direction the same for the whole set. Include gender or an example sentence on the back when it helps.
- **Cloze-style facts** ("The capital of ___ is Paris") should be rewritten as a plain question.

## Save them

1. If the user hasn't said how many cards they want, aim for the smallest set that covers what matters (often 5–20).
2. Show the cards briefly, or just save them if the user asked you to go ahead.
3. Call `add_flashcards` with the cards. Pass `deck_name` only if the user named a deck or the topic clearly matches one they mentioned. Send at most 50 cards per call; split larger sets across calls.
4. Tell the user how many cards were saved and that they're waiting in MasterKi: open the app to review them and add them to a deck.

## If MasterKi isn't connected

MasterKi needs a one-time sign-in before it can save cards. If the tool asks for sign-in or says MasterKi isn't connected, tell the user what to do instead of retrying:

1. Install the MasterKi app (iPhone, iPad, Mac or Android) and sign in. Cards are saved to that account, so the app must be set up first.
2. In the app, open **Settings → Connect MasterKi to AI apps** and tap **Get a pairing code**.
3. Type the code on the MasterKi sign-in page that opens (iOS and Mac users can sign in there with their MasterKi email and password instead).

A code works once, lasts 10 minutes, and only the newest code counts. If the page says it didn't match, tap **Get a new code** in the app and try that one. Full guide: https://masterki.org/ai-apps

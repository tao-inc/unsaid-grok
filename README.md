# Unsaid Word Game

A daily describe-the-word game for Grok Bot, in Turkish and English. You see a secret word and five forbidden words; Grok doesn't. Describe the word in short clues without saying any of them, and Grok guesses. The fewer clue words you use, the better your score.

- **One word a day, the same for everyone**, in each language, plus practice words any time.
- **A card that only you can read**: your word, its five forbidden words, your clues and Grok's guesses.
- **Clues are checked before they're sent**: forbidden words are caught in any form, with Turkish suffixes (kitap → kitabı), spelled out, or in the other language. In the card a refused clue costs nothing.
- **A spoiler-free share text** with colored squares, never the word.

Grok never receives the secret word while you play: Unsaid keeps it on its server and shows it only in the card.

## Sample prompts

- "Use Unsaid to start today's word game in English."
- "Use Unsaid to play today's Turkish word." / "Unsaid ile bugünün kelimesini oynayalım."
- "Use Unsaid to give me a practice word."
- "I give up, use Unsaid to show me the word."

Then give clues in the card or the chat, for example "a hot brown drink you have at breakfast". Grok Bot doesn't let a card post into the chat, so after the card checks your clue it shows the line to copy, such as `Unsaid clue 1 (game_id en-31.abcdefghijklmnop): "…"`.

## Tools

| Tool | What it does | What it changes |
|---|---|---|
| `start_game` | Opens today's word or a practice word in Turkish or English and shows it in the card; returns the game's `game_id` | Creates a game |
| `guess_word` | Takes your clue and Grok's one guess, checks the clue for forbidden words and the guess against the word | Records the clue and the guess |
| `get_game` | Shows where a game stands; the word only once it's over | Nothing |
| `give_up` | Ends the game and reveals the word | Ends the game |

## Server

`mcp.json` connects Grok Bot to `https://unsaid.ambientapp.ai/mcp/grok` (Streamable HTTP, no sign-in). The card is an MCP App that works inline within 800 px and without `ui/message`.

## Install

- **Grok Bot:** once the plugin is listed, add it from Connect apps. Until then, tell Grok Bot "Add this MCP server: https://unsaid.ambientapp.ai/mcp/grok".
- **Grok CLI:** `grok plugin install tao-inc/unsaid-grok --trust`

## Privacy, terms and support

Unsaid receives no name, email or user ID from Grok Bot. Each game is stored under a random game key (part of its `game_id`), with your clues, Grok's guesses and the result, and deleted 30 days after its last move. Technical logs never contain words, clues, guesses or IP addresses and are kept 30 days. No ads, no payments, no AI-generated media. For adults (Grok users are 18+).

- Documentation: https://unsaid.ambientapp.ai/docs
- Privacy policy: https://unsaid.ambientapp.ai/privacy
- Terms: https://unsaid.ambientapp.ai/terms
- Support: https://unsaid.ambientapp.ai/support · support@theopenapps.com

Made by The Open Apps, Inc. This repository holds only the plugin configuration (MIT); the server is operated by The Open Apps, Inc.

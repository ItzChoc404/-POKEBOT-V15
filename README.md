# PokeMarket Discord Bot — Railway Ready

This project is structured for Railway as a Node.js/TypeScript application.

## Structure

- `index.ts` — bot entry point
- `commands.ts` — Discord commands
- `gateway.ts` — Discord gateway
- `data/pokemon-discord-bot-state.json` — persistent bot state

## Railway

Railway should detect Node.js automatically.

Start command:

```bash
npm start
```

which runs:

```bash
tsx index.ts
```

Required environment variable:

```text
DISCORD_BOT_TOKEN=your_bot_token
```

Optional:

```text
PRICECHARTING_API_TOKEN=your_token
```


## Set publishing

- `/set` — choose language, era, and set, then choose a text channel or forum.
- `/quickset` — choose a language and destination text channel/forum, then publish all sets for that language automatically.
- Set posts include the TCGdex set artwork when available.
- The set dropdown supports name, card-number, and rarity sorting in both ascending and descending order.
- Sorted cards are shown with the card image, name, card number, and rarity.


## Recent changes

- `/quickset` accepts **Forum Channels only** and posts every set for the selected language.
- `/locaterange add` and `/locateadd` accept **Forum Channels only**.
- `/auctionpage add` watches Forum Channels only.
- A new message in a configured auction forum is automatically converted into an auction **only when the forum post has the exact `VERIFIED` tag**.
- Automatic auction creation uses AI field extraction when `OPENAI_API_KEY` is configured. It can identify title, description, starting bid, Buy Now price, and duration from natural wording.
- If AI is unavailable, the bot falls back to its existing labeled-price extraction and a 7-day default duration.

### Environment variables for AI auction extraction

`OPENAI_API_KEY` — required to enable AI extraction.
`OPENAI_MODEL` — optional model name; defaults to `gpt-4.1-mini`.

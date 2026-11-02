# Discord Badge Spoofer

A small toolkit that inflates two Discord profile badges by replaying the same
telemetry events the official Discord client sends to `/api/v9/science`:

- **Playtime badge** — total hours played across titles.
- **Game Variety badge** — number of distinct games played (unlocks at 5+ titles).

> Reference: [Discord Profile Badges — What Each Badge Means](https://support.discord.com/hc/en-us/articles/44369363856663-Discord-Profile-Badges-What-Each-Badge-Means)

This project is for educational purposes only. It violates Discord's Terms of
Service — use at your own risk.

## What's in the box

- `spoofer.py` — Python CLI (single file, stdlib only).
- `discord-badge-spoofer/` — Node.js CLI with a richer menu (settings, journal,
  catalog scan, fingerprint binding, etc.).

## How to run

### Python

```bash
python3 spoofer.py
```

On first run it prompts for your Discord account token and `cf_clearance`
cookie, then saves them to `science_state.json` next to the script.

Menu:

```
1 · claim games
2 · refresh auth
3 · set fingerprint
4 · change token
5 · change cookie
6 · auto-retrieve from Chrome
7 · exit
```

### Node.js

```bash
cd discord-badge-spoofer
npm install
node index.js
```

Or on Windows: run `setup.bat`.

Credentials are stored in `vault.json` (and a `journal.jsonl` records run
history).

## Where config is stored

- Python: `science_state.json` (token, cookie, fingerprint, cached analytics
  token, used-game IDs, cumulative stats).
- Node.js: `discord-badge-spoofer/vault.json` (credentials, fingerprint,
  settings, totals, rotation memory) plus `journal.jsonl`.

## Disclaimer

Forging telemetry violates Discord's Terms of Service and can get your account
terminated. Use only on accounts you are willing to lose.
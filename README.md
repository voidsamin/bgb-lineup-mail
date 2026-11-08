# BGB Lineup Mail — a Claude Skill

A custom [Claude](https://claude.ai) skill for **Black Gold Battlefield (BGB)**. Send Claude screenshots of your alliance roster, and it builds balanced team lineups and writes them out as ready-to-paste **in-game mail** and **Discord** posts.

Created by **[voidsamin](https://github.com/voidsamin)**.

## What it does

- **Reads roster screenshots:** player names (copied exactly), legion scores, ranks (R4/R3), and slot A/B as starter or sub.
- **Checks the counts:** 20 starters and 10 subs per slot. If anything looks off, it asks before going further.
- **Builds 5 teams per slot:**

  | Team | Name | Size |
  |---|---|---|
  | 1 | Military Base Left | 4 |
  | 2 | Military Base Right | 4 |
  | 3 | Hospital Top | 3 |
  | 4 | Hospital Bottom | 3 |
  | 5 | Ball Team | 6 (top 6 scores) |

- **Balances Teams 1–4** by average legion score, computed in code rather than estimated by eye.
- **Assigns captains** `(c)` from the R4 starters, and asks you when the choice isn't obvious.
- **Lists substitutes** in the order they appear in the screenshots.
- **Writes two formats:** the in-game mail (title + body) and a Discord post with team emojis, each checked against the 2000-character limit.

## Install

### Claude (web, desktop or mobile app)
1. Download **`SKILL.md`** from this repository.
2. On your computer, create a folder named exactly **`bgb-lineup-mail`** and put `SKILL.md` inside it.
3. Zip that folder, so the ZIP contains the `bgb-lineup-mail` folder (not just the loose file). On Windows: right-click the folder → **Compress to ZIP file**.
4. In Claude, go to **Customize → Skills** (called **Plugins** in newer versions).
5. Click **+ → Create skill → Upload a skill**, and choose the ZIP.
6. Make sure the skill is toggled **on**.

> Skills need **code execution** turned on in Claude's settings.

### Claude Code
Copy the `bgb-lineup-mail/` folder into `~/.claude/skills/`.

## Usage

In a chat, send your BGB roster screenshots and ask something like:

> Make the BGB lineup for these.

Claude will confirm the player counts, ask about captains if needed, then give you the mail and Discord posts in copy-ready code blocks, followed by the average score of Teams 1–4.

## Repository contents

```
bgb-lineup-mail/
├── SKILL.md      ← the skill itself
├── README.md     ← this file
└── LICENSE.md    ← license and permission terms
```

## License & permission

**Copyright © 2026 voidsamin. All rights reserved.**

This skill is **not** open source. You may view it here, but you may **not** use, copy, modify, share or build on it without written permission from the creator. To ask for permission, contact [voidsamin](https://github.com/voidsamin) on GitHub. See [LICENSE.md](LICENSE.md) for the full terms.
# Security policy

## Reporting a vulnerability

Please **don't open a public issue**. Report it privately through [GitHub Security Advisories](https://github.com/5m0k3/cache-maxxing/security/advisories/new). Include what you found, how to reproduce it, and the plugin and Claude Code versions. You'll get a reply within 7 days.

## Supported versions

Only the latest release is supported. Run `/cmaxx-update` to get it.

## What's in scope

cache-maxxing runs inside Claude Code on your computer. These are the parts worth a close look:

- **Network:** only `/cmaxx-update`, only when run. It makes GET requests for `.claude-plugin/plugin.json` and `prices.json` from this repository's `main` branch, and sends no data. A downloaded price table is checked (shape, sane amounts, not older than the built-in one) before it is used.
- **Commands run:** only `/cmaxx-update`, in the terminal, runs `claude plugin update cache-maxxing@cache-maxxing` (an argument list, no shell).
- **Model calls:** only `/cmaxx-handoff`, one Haiku call with an abbreviated copy of the chat. Text quoted in the chat is fenced, so it can't pose as the user, and the next chat is told to confirm any command from the briefing before running it.
- **Files written:** `.claude/handoffs/<file>.md` and `.claude/handoffs/.gitignore` in the current project; the plugin's own key-value store under Claude Code's configuration folder.
- **Files read:** the plugin's own files, and the current chat's transcript (for `/cmaxx-handoff` and `/cmaxx-stats`).

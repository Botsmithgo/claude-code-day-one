# Claude Code Day One

**Landing cold?** This is a two-part, plain-English guide that takes a non-technical person (written for a doctor on a Windows PC) from nothing installed to a working Claude Code setup. Part 1 installs the app. Part 2 is one message they paste into Claude Code, which then installs and configures everything itself.

**Send this one link:** https://botsmithgo.github.io/claude-code-day-one/

Both parts are on that page, one after the other, so there is nothing to send twice and nothing for them to lose.

If you would rather hand it over in two goes, the halves are still live on their own:

- Part 1 only, get set up: https://botsmithgo.github.io/claude-code-day-one/part-1-only.html
- Part 2 only, the setup message: https://botsmithgo.github.io/claude-code-day-one/part-2.html

## What's in here

| File | What it is |
|---|---|
| `index.html` | The whole guide, both parts, one page. This is the link to share |
| `part-1-only.html` | Part 1 on its own, for sending the halves separately |
| `part-2.html` | Part 2 on its own (the message has a copy button) |
| `PART-1-GET-SET-UP.md`, `PART-2-FIRST-MESSAGE.md` | The same content as plain markdown, for email or paste |
| `bootstrap-prompt.txt` | Just the message from Part 2 |
| `build.py` | Regenerates both pages from `bootstrap-prompt.txt`: `python3 build.py` |
| `artifact/` | Bare copies of the pages for republishing as claude.ai Artifacts |

The figures are hand-drawn inline SVG inside `build.py`, not screenshots. They depict Windows, adapt to light and dark, and never go stale when a vendor page is redesigned. Orange is always annotation; everything else is drawn to match what the user actually sees.
| `editions/` | Earlier versions: a Mac edition and a technical edition for developers |

Facts (install commands, plan names, shortcuts, the HIPAA note) were checked against the official Claude Code docs on 19 Sep 2026.

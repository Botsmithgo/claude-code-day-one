# Claude Code Day One

**Landing cold?** This is a two-part, plain-English guide that takes a non-technical person (written for a doctor on a Windows PC) from nothing installed to a working Claude Code setup. Part 1 installs the app. Part 2 is one message they paste into Claude Code, which then installs and configures everything itself.

**Send this first:** https://botsmithgo.github.io/claude-code-day-one/

That is Part 1: what Claude Code is, and getting it installed. It stands on its own, so it can go to anyone starting out.

**Send this second,** once they have the Code tab open on their folder: https://botsmithgo.github.io/claude-code-day-one/part-2.html

Both parts on a single page, if you ever want one link instead: https://botsmithgo.github.io/claude-code-day-one/full.html

## What's in here

| File | What it is |
|---|---|
| `index.html` | Part 1. The link you share first |
| `part-2.html` | Part 2, the setup message (with a copy button) |
| `full.html` | Both parts on one page, for when you want a single link |
| `part-1-only.html` | Identical to `index.html`, kept so an already-sent link keeps working |
| `PART-1-GET-SET-UP.md`, `PART-2-FIRST-MESSAGE.md` | The same content as plain markdown, for email or paste |
| `bootstrap-prompt.txt` | Just the message from Part 2 |
| `build.py` | Regenerates both pages from `bootstrap-prompt.txt`: `python3 build.py` |
| `artifact/` | Bare copies of the pages for republishing as claude.ai Artifacts |

The figures are hand-drawn inline SVG inside `build.py`, not screenshots. They depict Windows, adapt to light and dark, and never go stale when a vendor page is redesigned. Orange is always annotation; everything else is drawn to match what the user actually sees.
| `editions/` | Earlier versions: a Mac edition and a technical edition for developers |

Facts (install commands, plan names, shortcuts, the HIPAA note) were checked against the official Claude Code docs on 19 Sep 2026.

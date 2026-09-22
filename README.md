# Claude Code Day One

**Landing cold?** This is a two-part, plain-English guide that takes a non-technical person (written for a doctor on a Windows PC) from nothing installed to a working Claude Code setup. Part 1 installs the app. Part 2 is one message they paste into Claude Code, which then installs and configures everything itself.

- **Part 1, get set up:** https://botsmithgo.github.io/claude-code-day-one/
- **Part 2, the setup message:** https://botsmithgo.github.io/claude-code-day-one/part-2.html

Send Part 1 first. Send Part 2 once they have the Code tab open on their folder.

## What's in here

| File | What it is |
|---|---|
| `index.html` | Part 1 as a web page |
| `part-2.html` | Part 2 as a web page (the message has a copy button) |
| `PART-1-GET-SET-UP.md`, `PART-2-FIRST-MESSAGE.md` | The same content as plain markdown, for email or paste |
| `bootstrap-prompt.txt` | Just the message from Part 2 |
| `build.py` | Regenerates both pages from `bootstrap-prompt.txt`: `python3 build.py` |
| `artifact/` | Bare copies of the pages for republishing as claude.ai Artifacts |

The figures are hand-drawn inline SVG inside `build.py`, not screenshots. They depict Windows, adapt to light and dark, and never go stale when a vendor page is redesigned. Orange is always annotation; everything else is drawn to match what the user actually sees.
| `editions/` | Earlier versions: a Mac edition and a technical edition for developers |

Facts (install commands, plan names, shortcuts, the HIPAA note) were checked against the official Claude Code docs on 19 Sep 2026.

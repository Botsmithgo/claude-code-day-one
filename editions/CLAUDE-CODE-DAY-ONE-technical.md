# Claude Code Day One

From nothing installed to a fully set-up machine in about 30 minutes. You do four small things yourself (account, install, sign in, paste one prompt). Claude Code installs and configures everything else.

## 0. Before you start (5 min)

- **A Claude account on Pro or Max.** Claude Code is included in Pro, Max, Team and Enterprise. Start on Pro; move to Max if you use it for hours a day and hit limits. Plans: https://claude.com/pricing
- **A Mac (macOS 13+) or Windows PC (Windows 10+).** On Windows, Git for Windows is needed so Claude can use Bash. The bootstrap prompt handles that.
- **Your computer's password.** One install step (Homebrew) asks for it.

## 1. Install (3 min)

Two ways in. Pick one; you can add the other later.

**A. Desktop app (easiest if you've never used a terminal).**
Download from https://claude.com/download, install, sign in, click the **Code** tab. You get chat, a diff viewer and a terminal in one window.

**B. Terminal (one command, no dependencies).**
Mac: press Cmd+Space, type `Terminal`, press Enter. Paste:

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

Windows, in PowerShell:

```powershell
irm https://claude.ai/install.ps1 | iex
```

It's a single binary that updates itself. No Node, no Homebrew needed. Everything below works the same in the app and in the terminal.

## 2. Sign in and open a folder (2 min)

**Terminal:** make a home for your projects, then start Claude inside it.

```bash
mkdir -p ~/Projects && cd ~/Projects && claude
```

Your browser opens. Log in with your Claude account. Back in the terminal you'll see "Login successful". It asks whether you trust the folder: yes.

**Desktop app:** Code tab, choose or create a folder (call it `Projects`), and you're in.

**About modes.** On Pro/Max you'll probably start in **Auto** mode: Claude runs commands itself with safety checks and narrates as it goes. If you'd rather approve every command while you learn, press **Shift+Tab** until the mode reads default/Manual (desktop app: the mode selector next to the send button). Either works for the bootstrap.

## 3. Paste the bootstrap prompt (20 min, mostly waiting)

Copy the whole block below and paste it as your first message. Claude asks you five questions, then installs and configures everything, verifies it, and hands you a cheat sheet.

Three steps it can't do for you, and it will tell you when: Xcode tools (click Install in a popup), Homebrew (paste a command in a separate Terminal and enter your Mac password), GitHub login (a browser tab). Reply "done" after each.

```text
I'm brand new to Claude Code, and maybe to the command line. Set this computer up so I can use Claude Code well, and teach me as you go. Before every install or config change, tell me in one plain-English sentence what it does and why. If I'm in Manual mode I'll approve each command; if I'm in Auto mode, narrate anyway so I can follow. Work through the steps in order and don't skip the verification at the end.

GROUND RULES
- First detect my operating system and shell, and check what's already installed. Never reinstall something that's present and working; just note its version.
- Official installers and the platform's package manager only (Homebrew on macOS, winget on Windows, apt on Ubuntu). Nothing piped from random blogs.
- No sudo unless a step truly needs it, and say why first.
- Batch related commands so I'm not clicking through fifty prompts.
- Some steps you can't do for me: installing Xcode Command Line Tools (a popup I click), installing Homebrew (asks for my Mac password), and `gh auth login` (opens a browser). For those, print the exact command in a code block, tell me to run it in a separate Terminal window, and wait for me to reply "done" before continuing. Same for anything that's a slash command only I can type (/statusline, /terminal-setup, /init, /memory): tell me exactly what to type and wait.
- Back up any shell config file (.zshrc, .bashrc, PowerShell profile) before changing it, and show me the change.
- Never write API keys, passwords or tokens into any file. If something needs a secret, tell me where it goes and let me do it.
- If a command fails, read the error, fix it and retry. Only hand it to me if you're genuinely stuck, and then tell me exactly what to do.

STEP 1 - FIVE QUESTIONS (ask all of them in one message, then wait for my answers)
1. What do I mainly want to use Claude Code for? (building websites or apps / automating things with scripts / working with data and spreadsheets / writing, research and documents / not sure yet)
2. Do I already have code projects on this machine? Where do they live?
3. Which code editor do I use, if any? (VS Code / Cursor / other / none)
4. Do I have a GitHub account? If not, suggest I make a free one at github.com, but don't block on it.
5. What name and email should git use for my commits?

STEP 2 - AUDIT
Check and show me a short table: OS and version, shell, Xcode Command Line Tools (macOS) or Git for Windows (Windows), Homebrew or winget, git, node and npm, python3, gh (GitHub CLI), my editor, and the `claude` command itself. Mark each one Present (with version), Missing, or Will install.

STEP 3 - BASELINE (everyone gets this)
- macOS: Xcode Command Line Tools, then Homebrew. Windows: Git for Windows and winget. Linux: build-essential and curl.
- git, configured with my name and email, default branch "main", and a global .gitignore covering .env, .DS_Store and node_modules.
- GitHub CLI (gh), then walk me through `gh auth login` (interactive; hand-off rule above).
- Node.js LTS through fnm (a small version manager), or the official installer on Windows if fnm is awkward there, plus npm.
- Python 3 and uv.
- ripgrep, jq, tree, wget.
- The `claude` command itself if it isn't installed (I might be running you from the desktop app). Then `claude doctor`; fix anything it flags.

STEP 4 - ONLY WHAT MY ANSWERS CALL FOR
- Websites or apps: pnpm, and a ~/Projects folder (or use mine). Show me how to ask you to start a new app there.
- Automation and scripts: nothing extra; confirm both Python and Node run a one-line hello-world.
- Data and spreadsheets: a uv-managed scratch project with pandas and openpyxl; confirm Python can open a CSV.
- Writing, research and documents: nothing extra; tell me you can read PDFs, Word docs and spreadsheets dropped into the project folder.
- Editor: VS Code -> install it if missing, add the "Claude Code" extension (publisher: Anthropic), and make sure the `code` command works from the terminal. Cursor -> try the same extension; if it isn't available there, show me how to run `claude` in Cursor's built-in terminal. None -> install VS Code and tell me in two sentences why an editor helps.

STEP 5 - CONFIGURE CLAUDE CODE
1. Write ~/.claude/CLAUDE.md, my global memory file: who I am, what I'm building, my experience level, that I want short plain-English explanations, the tooling now on this machine (from your audit), and the standing rules: no secrets in files, ask before anything destructive, commit small and often. Show it to me and adjust it from my answers.
2. Create or update ~/.claude/settings.json with a conservative permission allowlist for read-only commands (git status, git diff, git log, ls, cat, pwd, node --version and similar) so I'm never asked for those. Nothing that deletes, pushes, publishes or installs goes on the allowlist. Explain what the file does and that /permissions edits it later.
3. Status line: have me type /statusline and ask for the current folder, git branch and model.
4. If I'm in a terminal: have me type /terminal-setup so Shift+Enter inserts a new line (Option+Enter works everywhere as a fallback).
5. In my main project folder, have me type /init to create a project CLAUDE.md, and explain the difference between the global one and the project one.
6. Add one MCP server, the official Claude Code docs server, so you can answer questions about yourself accurately:
   claude mcp add --transport http --scope user claude-code-docs https://code.claude.com/docs/mcp
   Then in one paragraph tell me what MCP servers are and name two I might want later (Playwright for browser testing, GitHub) with the command to add one.

STEP 6 - VERIFY
Re-run the version checks and show the final table (tool, version, OK). Run `claude doctor` once more. Nothing stays red.

STEP 7 - TEACH ME (one screen, no more)
A cheat sheet of what I'll use most: /help, /init, /clear, /compact, /model, /resume, /plan, /rewind, Shift+Tab to change modes, Esc to stop you, @file to point you at a file, ! to run a shell command, # to save something to memory, and how to give good instructions (be specific, paste errors verbatim, ask for a plan before big changes). Save this cheat sheet and the final table to ~/claude-code-setup.md.

STEP 8 - FIRST WIN
Based on my Step 1 answer, suggest one real five-minute task we can do right now, and do it with me.
```

## 4. What just got set up, and where to change it

| File | What it holds |
|---|---|
| `~/.claude/settings.json` | Your defaults everywhere: permission rules, default mode, model, status line |
| `~/.claude/CLAUDE.md` | What Claude knows about you, in every project |
| `<project>/CLAUDE.md` | What Claude knows about that project (made by `/init`; commit it) |
| `<project>/.claude/settings.json` | That project's rules, shared with collaborators |
| `<project>/.claude/settings.local.json` | Your private overrides for that project (not committed) |
| `~/.claude.json` | MCP servers and per-machine state (edited by `claude mcp add`) |

Commands that edit these for you, from inside a session:

| Command | Does |
|---|---|
| `/config` | Settings UI (theme, model, notifications) |
| `/permissions` | Allow, deny or ask rules for tools and commands |
| `/model` | Switch model or effort for this session |
| `/statusline` | Set up the bar at the bottom (folder, branch, model) |
| `/memory` | Edit your CLAUDE.md files; turn on auto-memory |
| `/mcp` | See and manage connected MCP servers |
| `/status` | Model, context used, who you're logged in as |
| `/cost` | Token usage this session |

**Permission modes** (press Shift+Tab to cycle):

| Mode | Behaviour |
|---|---|
| Manual (default) | Asks before every file edit and command |
| Accept edits | Edits files freely, still asks before commands |
| Plan | Read-only; proposes a plan, you approve before it touches anything |
| Auto | Runs on its own with safety checks (default on Pro/Max) |

There are two more (dontAsk, bypassPermissions) for CI and sandboxes. You don't need them.

## 5. Cheat sheet

**From the terminal**

| | |
|---|---|
| `claude` | Start a session in this folder |
| `claude -c` | Continue the last conversation |
| `claude -r` | Pick a past conversation |
| `claude update` | Update (the native install also does this itself) |
| `claude doctor` | Check the install; run this first when something's off |

**Inside a session**

| | |
|---|---|
| `Shift+Tab` | Cycle permission modes |
| `Esc` | Stop Claude mid-action |
| `Ctrl+R` | Search your prompt history |
| `Option+Enter` | New line without sending (`Shift+Enter` after `/terminal-setup`) |
| `/clear` | New task, fresh context |
| `/compact` | Squeeze a long session so it keeps going |
| `/plan` | Make it plan before editing |
| `/rewind` | Roll code and conversation back to a checkpoint |
| `/diff` | Review everything changed so far |
| `/resume` | Reopen an earlier conversation |

**In your message**

| | |
|---|---|
| `@src/app.js` | Hand it a file (Tab completes paths) |
| `!ls -la` | Run a shell command yourself, output goes in the chat |
| `# always use pnpm` | Save a note to memory |

## 6. Habits that make it click

- **Work inside a git repo, always.** Let Claude commit small and often. Git is your undo.
- **Big change? Plan first.** `/plan` or Shift+Tab into Plan mode, read the plan, then say go.
- **Be specific.** Paste the exact error, name the file, say what "done" looks like.
- **One task per conversation.** `/clear` between unrelated things. Long sessions get dumber.
- **You're the reviewer.** Read what it says before approving. Ask "why?" whenever you don't follow.
- **When it goes sideways:** Esc, explain what you actually wanted, or `/rewind`.

## When something breaks

1. `claude doctor` in the terminal.
2. `/status` inside a session (are you logged in, which model, how full is the context).
3. Paste the error to Claude and say "fix this". That's the whole trick.
4. Official docs: https://code.claude.com/docs (and the docs MCP server the bootstrap installed lets Claude read them itself).

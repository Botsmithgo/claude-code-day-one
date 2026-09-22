# Claude Code Day One

An AI assistant that works on your computer, not just in a chat window. This page gets it installed and set up in about 30 minutes with no technical knowledge. You click a few things and paste one message. Claude does the rest.

Written for a Mac. If you're on a Windows PC, the same app exists and the setup message adapts itself.

## What this is (one minute)

You may have used Claude or ChatGPT in a browser: you type, it answers. Claude Code is the same intelligence, but it can **act**. It lives on your computer, sees the files in a folder you choose, and can create, edit, organize and build things there.

- **Claude, the chat (in the browser):** like a consultant on the phone. Gives you advice and drafts; you do the doing.
- **Claude Code (on your computer):** like a capable resident. Does the work itself, shows you what it did, asks when unsure. You supervise.

Things it's genuinely good at for someone like you. You'd say, in plain words:

- "Read the twelve PDFs in this folder and give me a one-page summary of each."
- "Turn these lab exports into one clean spreadsheet with a chart."
- "Draft a referral letter template I can reuse, in my tone."
- "Build a simple website for the clinic: hours, location, a contact form."
- "Rename and sort these 400 photos by date into folders."
- "Every Monday I copy numbers from one file to another. Do it for me."

**Two words you'll see.** *Terminal* is a plain text window where you can type instructions to your computer. You won't need to use it beyond pasting one line when Claude asks. *Prompt* just means a message you send to Claude.

**One rule before anything else.** Claude Pro and Max are not set up for patient records (there's no HIPAA agreement on those plans). Keep names, dates of birth and anything identifying out of the files and chats, or de-identify first. Everything else is fair game.

## 1. Have these ready (5 min)

- **A Claude account on the Pro or Max plan.** Claude Code is included in both. Pro is the entry plan; Max is for people using it for hours a day. https://claude.com/pricing
- **A Mac from the last few years** (macOS 13 or newer). To check: Apple menu (top left) → About This Mac.
- **Your Mac password.** The one you type when you log in. One setup step asks for it.

## 2. Install the Claude app (3 min)

1. Go to https://claude.com/download and download the Mac version.
2. Open the downloaded file and drag Claude into your Applications folder, like any other app.
3. Open Claude and sign in with your account.
4. At the top of the window, click the **Code** tab. That's Claude Code.

(There's a version that runs entirely in the Terminal too. You don't need it today; the setup message installs it quietly for later.)

## 3. Pick a folder to work in (2 min)

Claude Code works inside one folder at a time. It can see and change what's in that folder and nothing outside it.

1. In Finder, open **Documents** and make a new folder called **Claude**.
2. Back in the Code tab, when it asks which folder to open, choose that one.
3. If it asks whether you trust the folder: yes. It's yours.

**About the mode switch.** Near the send button there's a mode setting. **Auto** means Claude does the work and tells you what it did, with built-in safety checks. **Manual** means it asks you before each action. Leave it on Auto for the setup. You can switch any time.

When it does ask permission, you'll see a box with the command, a one-line explanation, and three choices: **1** means yes. **2** means yes, and stop asking for this kind of thing. **3** means no, and you tell it what to do instead.

## 4. Paste this as your first message (20 min, mostly waiting)

Copy the whole block below, click into the chat box, and paste. Claude will ask you four questions, then install and set everything up, then finish with a short lesson and a first task.

**Three moments it needs you.** It will say so each time. Reply "done" after each one and it carries on.

1. **An Apple popup.** Click Install. It's a free Apple package.
2. **Your password.** Claude gives you one line to paste into the Terminal panel it points you to. Then type your Mac password. **Nothing appears while you type it.** That's normal. Press Enter.
3. **A login screen**, if a step opens one in your browser.

```text
I'm a doctor, not a technical person. I've never used a terminal and I don't know programming. Treat me as a smart person who is completely new to these tools. Set up this computer so I can use Claude Code for my day-to-day work, and teach me as we go.

HOW TO TALK TO ME
- Plain English. The first time you use a technical word (terminal, folder path, package, server, repository), explain it in one short sentence.
- Keep each message short. One thing at a time. Before you do anything, tell me in one sentence what it does and why I'd want it.
- When you need me to do something myself, give me numbered steps with exactly what to click, where it is, or what to paste. Assume I don't know where things are.
- Never ask me to edit a file by hand. You do the file work; I copy, paste and click.
- If something fails, fix it yourself and tell me in one line what happened. Only involve me if you truly need me, and then tell me exactly what to do.

SAFETY RULES
- Check what's already on this computer before installing anything. Don't reinstall what's already here.
- Only use official installers (Apple's, Homebrew, or the tool maker's own). No scripts from random websites.
- Don't use administrator (sudo) powers unless truly needed, and tell me why first.
- Some things you can't do for me: installing Apple's command line tools (a popup I click), installing Homebrew (it asks for my Mac password), and any login screen. For those, give me the exact command in a box, tell me where to paste it (the Terminal panel), warn me that the password stays invisible while I type it, and wait for me to say "done".
- Never write passwords, keys or patient information into any file. If you need a password, tell me where to type it myself.
- I'm a physician. Remind me once that patient-identifiable information shouldn't go into our chats or files unless my practice has approved it, and never encourage me to paste it.
- If this turns out to be a Windows PC, use the Windows equivalents (winget, Git for Windows) and adapt these steps yourself. I don't need to know the difference.

STEP 1 - A FEW QUESTIONS (ask all of these in one message, then wait for my answers)
1. What would I like help with? Any of: paperwork, letters and documents / spreadsheets and data / reading and summarizing papers or PDFs / a website for my practice / organizing files and photos / repetitive computer tasks / not sure yet
2. Do I use Microsoft Office, Google Docs, or Apple's Pages and Numbers?
3. Where do I keep my files? (Documents, Desktop, iCloud, Dropbox, OneDrive, somewhere else)
4. Have I used an AI chat tool before (ChatGPT, Claude)? So you know how much to explain.

STEP 2 - LOOK AROUND
Check what this computer has: which Mac and macOS version, Apple's command line tools, Homebrew, git, Python, Node, and whether the `claude` command works from the Terminal. Show me a simple three-column list: Tool, What it's for (in plain words), Status (already here / will install / not needed).

STEP 3 - THE BASICS (everyone gets these)
- Apple's Command Line Tools: a free Apple package that other tools depend on.
- Homebrew: like an app store for behind-the-scenes tools. Needs my password once.
- git, set up with my name and email: a safety net that keeps a history of every change so nothing is ever lost. I'll never need to touch it.
- The `claude` command itself, if it isn't installed yet, so I can also use you from the Terminal later. Then run `claude doctor` and fix anything it flags.

STEP 4 - ONLY WHAT MY ANSWERS CALL FOR (explain each in one sentence before installing it)
- Documents and letters: nothing extra. Show me how to drop a Word file or PDF into my folder and ask you to work on it. If I use Office, install pandoc so you can convert between formats.
- Spreadsheets and data: Python with uv, plus pandas and openpyxl, so you can read and build Excel files. Prove it by making a small example spreadsheet.
- Reading papers and PDFs: nothing extra. Prove it by summarizing any PDF I give you.
- A website for my practice: Node.js (through fnm). Explain in two sentences how a website gets built and put online, and roughly what it costs per year.
- Organizing files and photos: nothing extra. Demonstrate on a copy of a folder, never the original.
- Repetitive tasks: Python with uv. Ask me for one example task and set it up.

STEP 5 - SET UP CLAUDE CODE FOR ME
1. Create a folder called "Claude" in my Documents, with a subfolder for each thing I said I want help with. Explain that I drop files there for you to work on.
2. Write my memory file (~/.claude/CLAUDE.md) so every future chat starts knowing: I'm a doctor and not technical; explain in plain English and define terms; keep messages short; never ask me to edit files by hand; never put passwords or patient information in files; ask before deleting or overwriting anything; and which tools are now on this machine. Show it to me, then adjust anything I want changed.
3. Set my permissions so you never need to ask before reading files or looking inside folders, but always ask before deleting, overwriting, sending, publishing or installing anything. Tell me in two sentences what you changed.
4. Add the official Claude Code docs plug-in so you can look up your own manual when I ask how something works:
   claude mcp add --transport http --scope user claude-code-docs https://code.claude.com/docs/mcp
5. Turn on auto-memory if it's available, so you remember things I tell you between chats, and tell me how to see what you've remembered.

STEP 6 - CHECK EVERYTHING
Show me the three-column list again with everything green. Run `claude doctor` once more.

STEP 7 - TEACH ME (one screen, plain words)
The ten things I'll use most: start a new job (/clear), bring back an old chat (/resume), undo (/rewind), stop you (Esc), give you a file (drag it into the chat, or type @ and the file name), switch between "ask me first" and "just do it" (Shift+Tab), make you remember something (# then the note), change how you work (just ask in words), update you (claude update), and what to say when something goes wrong ("here's the error, fix it"). Save this as "Claude cheat sheet.md" in my Claude folder and put a copy on my Desktop.

STEP 8 - FIRST WIN
Based on what I said in Step 1, suggest one real ten-minute task we can do right now, and do it with me.
```

## 5. What Claude set up

You don't have to touch any of this. It's here so you know what exists, and how to change it: **you ask, in words.**

| Thing | What it is |
|---|---|
| A memory file about you | Who you are, how you like things explained, the rules it follows. Change it by saying "remember that…" |
| Permissions | What it may do without asking. Reading files: no need to ask. Deleting, sending, installing: always asks. |
| Your Claude folder | Documents › Claude, with a subfolder per kind of work. Drop files there; ask Claude to work on them. |
| A manual plug-in | Lets Claude read its own documentation, so when you ask how something works, it answers from the manual. |
| A cheat sheet | A short file on your Desktop with the ten things you'll use most. |

**Changing how it behaves.** No settings screens needed. Say it and it updates its own files:

- "From now on, ask me before you change any spreadsheet."
- "Stop asking me before you read files."
- "Remember that I dictate my letters, so keep sentences short."
- "Use the faster model for simple jobs."

**The three modes** (press Shift+Tab to switch, or use the selector next to the send button; others exist for engineers, ignore them):

| Mode | Behaviour |
|---|---|
| Manual | Asks before every change and every command |
| Plan | Looks but doesn't touch. Proposes a plan; you approve first |
| Auto (default) | Does the work, tells you what it did |

## 6. Cheat sheet

**Type this**

| | |
|---|---|
| `/clear` | Start a new job with a clean slate |
| `/resume` | Bring back an earlier conversation |
| `/rewind` | Undo: go back to an earlier point |
| `/model` | Switch to a faster or a smarter model |
| `/memory` | See and edit what it remembers about you |
| `/help` | Everything else it can do |

**Press this**

| | |
|---|---|
| Esc | Stop whatever it's doing |
| Shift+Tab | Switch Auto, Manual, Plan |
| `@` then a name | Point it at a file (or drag the file into the chat) |
| `#` then a note | Make it remember something |
| Option+Enter | New line without sending |

**Or just say it**

- "Before you do anything, tell me the plan."
- "Explain that again as if I'm not technical."
- "Undo the last change."
- "Show me what you changed."

## 7. Getting good results

- **Talk to it like a smart new assistant on their first day.** Give context. Say what "done" looks like.
- **One job per conversation.** Type `/clear` before starting something unrelated. Long conversations get fuzzy.
- **Anything big? Ask for the plan first.** Read it, then say go.
- **You're the supervisor.** Read what it tells you. Ask "why?" whenever you don't follow.
- **Keep patient identifiers out.** De-identify before you drop anything in.
- **Going wrong?** Press Esc, say what you actually wanted, or type `/rewind`.

## 8. When something breaks

1. Tell Claude: "Something's wrong, here's what I see: [paste or describe it]. Fix it." That solves most things.
2. Quit the app and open it again.
3. Ask Claude to run its own check-up (it knows the command: `claude doctor`).
4. Still stuck? Take a screenshot (Cmd+Shift+4) and send it to whoever gave you this page.

---
Checked against the official Claude Code documentation on 19 Sep 2026.

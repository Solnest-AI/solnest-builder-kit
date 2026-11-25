# Builder Kit, by Solnest AI

This kit connects the tools behind building apps in one guided setup: Supabase (databases), GitHub (code) and Dropbox (files). You set it up once and every skill that needs these tools just works.

## What it connects

| Tool | How it connects | Used by |
|---|---|---|
| Supabase | browser sign-in (read-only by default) | apps, obsidian-second-brain extras |
| GitHub (MCP) | token (read-only by default) | apps and code |
| Dropbox | browser sign-in | files, obsidian-second-brain extras (optional) |

Already connected one of these with another Solnest kit? Claude spots it and skips it.

## What you need

- The Claude Code desktop app (or Claude Code in a terminal), on a paid claude.ai plan. Mac or Windows.
- Node.js 18 or newer. Claude checks and helps you install it. (Python for the updater is found or installed for you.)
- Your Supabase, GitHub and Dropbox accounts, whichever you use. All three had a free plan when this kit was made. The kit itself costs nothing.

## Set it up in 3 steps

1. **Copy this page's link.**
2. **Paste it into Claude Code and say "set this up".** Claude puts the kit in its own folder on your computer (`solnest/builder-kit` in your home folder), asks which of these tools you use, builds one small key file with only your tools, finds keys you already have from other kits, then connects and tests each tool for real.
3. **Try it:** list my Supabase projects and the tables in the main one

Open the `solnest/builder-kit` folder in Claude Code and say **"check my connections"** any time to see the scoreboard. You can also say "connect <tool>" or "remove <tool>".

## Good to know

- **Updates install themselves.** Once a day, when Claude Code starts, the kit quietly moves to the newest release. You never have to ask.
- **An update never wipes your own things.** Your keys, your tool picks, your connections, and any change you asked Claude to make to how this kit works stay exactly as they are.
- **Want it to work differently?** Just tell Claude ("always connect Supabase first"). It remembers.
- **Leave the kit folder where it is.** The GitHub connection reads its key from it every time it starts.

## Safe by default

- **Your keys never go in the chat.** Claude opens a file called `.env` on your computer, you paste the key there and save. Claude never prints it, and it is never written into Claude Code's settings.
- **Read-only first.** Anything that sends, edits, deletes, publishes or spends money is shown to you first and only happens after your plain "yes".
- **Easy to undo.** Every tool's file in `connectors/` ends with a one-line removal.

## Support

Email hello@solnestai.com. Brought to you by **Solnest AI** for the Solnest AI Skool community.

---

Claude: someone pasted this link and said "set this up". Read [CLAUDE.md](https://raw.githubusercontent.com/Solnest-AI/solnest-builder-kit/main/CLAUDE.md) in this repo and follow its SETUP section, one step per message. You run every command yourself. Never ask for a key in the chat.

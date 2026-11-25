# Dropbox

**Status:** official (Dropbox remote MCP server, labeled beta by Dropbox). Browser sign-in, no key, no Dropbox app to build.
**Server name / URL:** `dropbox` / `https://mcp.dropbox.com/mcp`
**Verified:** help.dropbox.com/integrations/connect-dropbox-mcp-server (read 2026-11-04). Endpoint answered 401 on 2026-11-04.

## What it lets Claude do
List, search, and read files and folders; create folders and files; copy and move; make shared links; create file requests; restore earlier versions; get transcripts of audio and video and Markdown from documents (including OCR for scanned PDFs). It also covers Dropbox Sign and Dropbox Paper.

## What you need
- A Dropbox account. Dropbox does not list a plan requirement.
- On a Dropbox team, "Your Dropbox admin may control whether you can register or connect apps."
- The old lesson made you build a Dropbox app and a refresh token. None of that is needed now: Dropbox says Claude Code is supported through Dynamic Client Registration.

## Connect
Follow `_how-sign-in-works.md` with name `dropbox` and URL `https://mcp.dropbox.com/mcp`.

## Verify (read-only)
Ask: "Who am I signed in as on Dropbox, and list the folders in my Dropbox root." Your name and folders back means it works.

## Try these
- "Find every PDF in my Contracts folder from this year."
- "Give me a transcript of the video in /Content/Raw/interview.mp4."
- "Create a shared link for /Clients/Proposal.pdf." (Claude confirms first.)

## Good to know
- Delete, Move, sharing, and Dropbox Sign requests change real things. Claude asks before any of them.
- Dropbox also runs a separate Dash server (`https://mcp.dropbox.com/dash`). Do not mix them up.

## Remove
Path A: + > Connectors > Manage connectors > remove. Path B: `node scripts/register.mjs dropbox --remove`. To cut access completely, also revoke Claude in Dropbox settings (connected apps).

# Supabase

**Status:** official (Supabase's hosted MCP server). Browser sign-in, no key. Read-only by default in this kit.
**Server name / URL:** `supabase` / `https://mcp.supabase.com/mcp?read_only=true` (default) or `https://mcp.supabase.com/mcp` (full, only if you ask)
**Verified:** supabase.com/docs/guides/getting-started/mcp (read 2026-11-04). Endpoint answered 401 on 2026-11-04.

## What it lets Claude do
List projects and tables, run SQL to answer questions about your data, read logs and security/performance advisors, and with full access: create tables, run migrations, deploy edge functions.

## What you need
- A Supabase account and a project. Supabase uses OAuth with dynamic client registration, so no personal access token is needed.
- The old lesson told you to paste your `service_role` key. Never do that. It bypasses all your database security.

## Connect
Follow `_how-sign-in-works.md` with name `supabase` and URL `https://mcp.supabase.com/mcp?read_only=true`. Choose the organization that holds your project on Supabase's sign-in page.
Optional: lock it to one project by adding `&project_ref=<your project ref>` to the URL (the ref is in your project's dashboard URL). Supabase recommends this.
Full access (writes and migrations): URL `https://mcp.supabase.com/mcp`, or in a terminal `node scripts/register.mjs supabase --full`. Only if you really need it.

## Verify (read-only)
Ask: "List my Supabase projects, then list the tables in [project]." Your tables back means it works.

## Try these
- "How many customers signed up this week?"
- "Show me orders over $500 that have not shipped."
- "Check my project's security advisors and explain anything marked critical."

## Safety (from Supabase's docs)
- Prompt injection is the main risk: text inside your data could try to trick Claude into running bad queries. Read-only mode prevents writes even if that happens.
- Connect to production only when needed, and scope to one project.
- Claude shows any write, schema change, or migration and waits for your yes.

## Remove
Path A: + > Connectors > Manage connectors > remove. Path B: `node scripts/register.mjs supabase --remove`. To cut access completely, also revoke it in your Supabase account settings (authorized apps).

# MCP Connections

MCP (Model Context Protocol) servers extend Claude Code's capabilities by connecting to external services. Once connected, Claude can read your email, search your documents, check your calendar, and more -- directly from the terminal.

!!! info "Time and difficulty"
    **Google Workspace** (Gmail, Docs, Calendar): ~45-60 minutes. The OAuth credential setup is the hardest part -- it requires creating a project in Google Cloud Console. Follow each step carefully.
    **Zotero**: ~10 minutes. Just an API key.

    **Do not want to set up MCP yet?** That is fine. Claude Code works without any integrations -- it can read and edit files, draft documents, organize projects, and help with writing. You can always come back and add integrations later.

---

## What MCP Does

Without MCP, Claude Code can only work with files on your computer. With MCP:

| Integration | What Claude Can Do |
|-------------|-------------------|
| **Gmail** | Search, read, draft, and send emails |
| **Google Docs** | Read and write documents |
| **Google Sheets** | Read and write spreadsheets |
| **Google Calendar** | View schedule, create events |
| **Google Drive** | Search and access files |
| **Zotero** | Search your reference library |

You do not need all of these. Start with whichever service you use most (Gmail is usually the highest-value starting point for law faculty) and add others as needed.

!!! tip "Understand what you are granting"
    Each MCP integration gives Claude Code access to your **entire** account for that service -- not just specific folders or labels. Gmail MCP can read any email. Drive MCP can access any file. Calendar MCP sees all events, including private ones. There is no way to restrict scope to a subset. This is fine for most users, but worth knowing before you connect. When Claude processes data from any integration, the content is sent to Anthropic's API as part of the conversation. Anthropic's [data policy](https://www.anthropic.com/policies/privacy) states API inputs are not used for model training -- verify the current terms yourself. If a service contains data you are not comfortable with an AI processing, skip that integration.

---

!!! ask-claude "Getting an error? Ask Claude."
    If something goes wrong during any MCP setup step, paste the error into the
    Claude Code terminal -- for example:
    `I'm getting an error trying to connect. Here's what I see: [paste the error]`
    Press Enter. Claude can often diagnose MCP configuration issues on the spot.

!!! warning "Shared computers"
    Anyone who can open Terminal on your machine can run `claude` and access all connected services -- email, calendar, documents -- with no additional login required. If you share your computer, consider revoking MCP tokens when you are done (remove entries from `settings.json`) or using separate user accounts. Claude Code also stores conversation history locally in `~/.claude/`, which may include content from connected services.

---

## How MCP Configuration Works

MCP servers are configured in a JSON file that tells Claude Code how to connect to each service:

| File | Purpose |
|------|---------|
| `~/.claude.json` | Active MCP configuration (Claude reads this) |

Each MCP server entry specifies a command to run and any required credentials (API keys, OAuth tokens).

---

## Google Workspace (Recommended First)

<span class="badge-gold">45-60 min</span>

This single server provides access to Gmail, Google Docs, Sheets, Calendar, Drive, and Tasks. It is the highest-value MCP integration for most law faculty -- email triage, calendar awareness, and document access in one setup.

**Repository:** [taylorwilsdon/google_workspace_mcp](https://github.com/taylorwilsdon/google_workspace_mcp)

### Prerequisites

- **Python** (3.10+) and **uv** (Python package manager)
- **Google Cloud Console** account (free)

### Setup Steps

**1. Install uv** (if you do not have it):
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

**2. Clone and install the server:**
```bash
cd ~
git clone https://github.com/taylorwilsdon/google_workspace_mcp
cd google_workspace_mcp
uv sync
```

**3. Create Google OAuth credentials:**

This is the most involved step. You need to create a "project" in Google Cloud Console and enable API access.

1. Go to [console.cloud.google.com](https://console.cloud.google.com)
2. Create a new project (or use an existing one)
3. Enable these APIs (search for each in the API Library):
   - Gmail API
   - Google Drive API
   - Google Docs API
   - Google Sheets API
   - Google Calendar API
   - Google Tasks API
4. Go to **Credentials** > **Create Credentials** > **OAuth client ID**
5. Application type: **Desktop app**
6. Download the client ID and secret

!!! warning "Important: Switch to Production mode"
    By default, your Google Cloud project is in "Testing" mode, which means **OAuth tokens expire after 7 days** -- you will need to re-authenticate weekly, which is the single most common frustration with this setup. To fix it: go to **Google Auth platform > Audience** in the Cloud Console and switch to "Production." This makes tokens persist indefinitely. Do this during setup, not later.

**4. Add to your Claude configuration:**

Add this to `~/.claude.json` under `mcpServers`:

```json
{
  "mcpServers": {
    "google_workspace": {
      "type": "stdio",
      "command": "/path/to/uv",
      "args": [
        "run", "--directory", "/path/to/google_workspace_mcp",
        "main.py", "--tools", "drive", "docs", "sheets", "gmail", "calendar", "tasks"
      ],
      "env": {
        "GOOGLE_OAUTH_CLIENT_ID": "your-client-id.apps.googleusercontent.com",
        "GOOGLE_OAUTH_CLIENT_SECRET": "your-client-secret",
        "OAUTHLIB_INSECURE_TRANSPORT": "1",
        "USER_GOOGLE_EMAIL": "your-email@gmail.com"
      }
    }
  }
}
```

Replace the paths and credentials with your actual values. To find your `uv` path: `which uv`.

!!! note "About `OAUTHLIB_INSECURE_TRANSPORT`"
    This setting allows OAuth to work over HTTP on localhost, which is standard for desktop MCP apps that only talk to your local machine. Never set this in a production server environment.

**5. Restart Claude Code** and test:

```
> Search my Gmail for emails from last week
```

If Claude can read your email, the connection is working.

### What can you do with Google Workspace MCP?

Once connected, here are some things law faculty find immediately useful:

- **Email triage:** "Show me unread emails from the last 24 hours and summarize the ones that need a response"
- **Calendar awareness:** "What's on my schedule tomorrow? Flag any conflicts"
- **Document access:** "Read my article draft in Google Docs and summarize where I left off"
- **Meeting prep:** "I have a committee meeting at 2pm. Pull up the agenda from Drive and summarize the key items"

### Known Limitations

- Cannot create Google Doc tabs (must create manually)
- No suggesting mode / track changes
- Uses significant context (~26K tokens for all tools). If you hit context limits, enable only the tools you need by adjusting the `--tools` argument.

---

## Zotero (Reference Management)

<span class="badge-gold">10 min</span>

Search your Zotero library and retrieve citations. Particularly useful for law faculty who manage large collections of cases, articles, and secondary sources.

**Package:** `mcp-zotero` (npm)

### Setup

1. Get your API key from [zotero.org/settings/keys](https://www.zotero.org/settings/keys)
2. Find your user ID on the same page

Add to `~/.claude.json`:

```json
"zotero": {
  "type": "stdio",
  "command": "npx",
  "args": ["mcp-zotero"],
  "env": {
    "ZOTERO_API_KEY": "your-api-key",
    "ZOTERO_USER_ID": "your-user-id"
  }
}
```

### What can you do with Zotero MCP?

- **Find sources:** "Search my Zotero library for articles about Section 230 reform"
- **Build bibliographies:** "Pull all items from my 'Admin Law Article' collection and format them in Bluebook"
- **Research support:** "Find sources in my library related to regulatory sandboxes and summarize their arguments"

---

## Other MCP Servers

!!! note "Slack and Microsoft Teams"
    Slack and Teams MCP servers exist on GitHub but vary in quality and maintenance. Before investing setup time: search GitHub, check the repo's recent commit activity and open issues, and verify it supports your plan type (some require Enterprise). The configuration pattern (clone repo, add JSON config, restart Claude Code) is the same as described above -- the work is finding a well-maintained server.

---

## Multi-Machine Setup

If you use Claude Code on multiple computers:

### What syncs (via your cloud folder):
- CLAUDE.md (your personal instructions)
- MCP server *configuration* (the JSON)

### What stays local (per machine):
- OAuth tokens (you authenticate once per machine)
- MCP server code repositories (clone on each machine)
- `~/.claude.json` (the active config file)

### Setting Up a New Machine

1. Clone/install MCP server repositories on the new machine
2. Copy your MCP configuration to `~/.claude.json`
3. Update paths in the config to match the new machine
4. Restart Claude Code -- first use will prompt for OAuth authentication

---

## Troubleshooting

**Google auth expired:** Delete the credentials file in the MCP server folder (usually `~/.google_workspace_mcp/credentials/`) and re-authenticate on next use.

**MCP server not responding:**

1. Check if the server command runs manually in your terminal
2. Verify all paths in `~/.claude.json` are correct and absolute
3. Restart Claude Code

**Context limits hit quickly:** Run `claude doctor` to check MCP tool context usage. Disable unused servers or reduce the `--tools` list to reclaim context space.

---

## What's Next

With MCP configured:

1. **[Build Your Own workflows](../system/index.md)** -- Create custom workflows that use your MCP connections
2. **[Your First Workflow](../workflows/first-session-skills.md)** -- A hands-on walkthrough of the prompt-plan-review-revise loop

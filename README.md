# Notion MCP Server by Insightful Pipe

[![MCP Compatible](https://img.shields.io/badge/MCP-Compatible-blue)](https://insightfulpipe.com/mcp-servers/notion)
[![Insightful Pipe](https://img.shields.io/badge/Insightful_Pipe-MCP_Servers-purple)](https://insightfulpipe.com/mcp-servers)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> **Connect Notion to AI assistants: pages, databases, data sources and blocks.**

Part of the [Insightful Pipe MCP Server Collection](https://insightfulpipe.com/mcp-servers) — use Notion from Claude, ChatGPT, Cursor, and other AI assistants through the Model Context Protocol (MCP).

<img src="images/notion-icon.svg" alt="Notion MCP Server" width="64" height="64">

## MCP Server URL

```
https://notion.insightfulmcp.com/
```

## What is Notion MCP?

Notion MCP is a **remote Model Context Protocol server** hosted by InsightfulPipe. Search and read Notion pages, databases, and data sources, retrieve block trees, query data-source rows, and (with read+write scopes) create or update pages and blocks. The OAuth scopes you granted at connect time decide what's allowed.

## Installation

### Claude

1. Copy the MCP Server URL: `https://notion.insightfulmcp.com/`
2. Open [Claude Connectors Settings](https://claude.ai/settings/connectors)
3. Scroll to the bottom and click **Add custom connector**
4. Paste the URL and click **Add**
5. Click **Connect** on the connector to start authorization
6. Click **Authorize access** in the browser to complete the connection

### ChatGPT

Custom MCP servers are added through ChatGPT's **Developer mode**. Availability depends on your ChatGPT plan, and workspace admins may need to allow it.

1. Turn on **Developer mode** in ChatGPT settings
2. Create a new app for a remote MCP server and paste the URL: `https://notion.insightfulmcp.com/`
3. Authorize with your InsightfulPipe account

See OpenAI's guide: [Developer mode and MCP apps in ChatGPT](https://help.openai.com/en/articles/12584461-developer-mode-and-mcp-apps-in-chatgpt)

### Claude Code

```bash
claude mcp add --transport http notion https://notion.insightfulmcp.com/
```

### Cursor

Add the server to `~/.cursor/mcp.json` (all projects) or `.cursor/mcp.json` (one project):

```json
{
  "mcpServers": {
    "notion": {
      "url": "https://notion.insightfulmcp.com/"
    }
  }
}
```

Then authorize the connection when Cursor prompts you.

## Available Actions

23 actions: 13 read, 10 write.

### Read Actions (13)

| Action | Description |
|--------|-------------|
| `get_block` | Retrieve a block by ID |
| `get_block_children` | List children of a block (e.g. paragraphs inside a page) |
| `get_comments` | List comments on a page or block |
| `get_data_source` | Retrieve a data source |
| `get_database` | Retrieve a database (legacy endpoint) |
| `get_page` | Retrieve a page by ID |
| `get_page_property` | Retrieve a single property item on a page |
| `get_self` | Retrieve the integration's bot user (token owner) |
| `get_user` | Retrieve a single user by their Notion user ID |
| `list_data_source_templates` | List templates available in a data source |
| `list_users` | List all users in the workspace |
| `query_data_source` | Query a data source (filter + sort + paginate) |
| `search` | Search pages and data sources visible to the integration |

### Write Actions (10)

| Action | Description |
|--------|-------------|
| `append_block_children` | Append new child blocks to an existing block |
| `create_comment` | Add a comment to a page or discussion thread |
| `create_data_source` | Add a new data source to an EXISTING database |
| `create_database` | Create a brand-new database with an initial data source under a parent page |
| `create_page` | Create a new page under a parent page or database |
| `delete_block` | Archive (soft-delete) a block |
| `move_page` | Move a page to a new parent |
| `update_block` | Update a block's content or archived state |
| `update_data_source` | Update a data source's title or schema |
| `update_page` | Update a page's properties / icon / cover, or archive/unarchive it |

## Usage Examples

```
"Search my workspace for pages about Q4 planning"
```

```
"Show items in the Content Calendar database due this week"
```

```
"Create a page with this week's campaign notes"
```

## Explore More MCP Servers by Insightful Pipe

Visit **[insightfulpipe.com/mcp-servers](https://insightfulpipe.com/mcp-servers)** to discover our full collection of MCP servers.

- [Airtable MCP](https://insightfulpipe.com/mcp-servers/airtable)
- [Google Sheets MCP](https://insightfulpipe.com/mcp-servers/google-sheets)
- [Slack MCP](https://insightfulpipe.com/mcp-servers/slack)

**[View All MCP Servers →](https://insightfulpipe.com/mcp-servers)**

## Resources

- [Documentation](https://insightfulpipe.com/docs)
- [Video Tutorial](https://www.youtube.com/playlist?list=PLJNzvjxzI5Xwe__BJJLAelSF0ewO3mEFk)
- [InsightfulPipe Blog](https://insightfulpipe.com/blog)

## Support

- **Documentation**: [insightfulpipe.com/docs](https://insightfulpipe.com/docs)
- **All MCP Servers**: [insightfulpipe.com/mcp-servers](https://insightfulpipe.com/mcp-servers)
- **Email**: support@insightfulpipe.com

---

**[Insightful Pipe](https://insightfulpipe.com)** — AI-powered marketing analytics through MCP servers. [Explore all integrations →](https://insightfulpipe.com/mcp-servers)

## License

MIT License - see [LICENSE](LICENSE) for details.

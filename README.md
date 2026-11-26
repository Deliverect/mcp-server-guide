<img src="assets/logo.svg" alt="Deliverect" width="64">

# Deliverect MCP server

Connect your AI assistant to [Deliverect](https://www.deliverect.com), so you can ask about your restaurant's sales, orders, menus and opening hours across every location and ordering channel, using live data.

Deliverect connects restaurants and retailers to the delivery apps, web shops and kiosks their customers order from. The Deliverect MCP server is hosted by Deliverect at:

```
https://mcp.deliverect.com/mcp
```

It uses Streamable HTTP and signs you in with your Deliverect account (OAuth). There's nothing to install and no API keys to configure.

This repository is the guide for that hosted server. The server itself isn't open source.

## What you can ask

- Which products sold best this month?
- How does revenue compare between locations?
- Which orders failed yesterday?
- What are the holiday hours for my stores?
- Which channels are paused right now, and why?

The server can look up orders and their status, billing and product sales reports, stores and their opening hours, menus and the product catalog, menu schedules and special hours, and operational health such as paused channels, failed orders, failed menu pushes, snoozed products, ratings and reviews.

## Add it to your client

### GitHub Copilot in VS Code

On the [Deliverect listing in the GitHub MCP Registry](https://github.com/mcp/com.deliverect/deliverect), open the menu on **Install MCP server** and choose **Install in VS Code**. Or search for `@mcp deliverect` in the Extensions view. Then select **Install**, and **Allow** when VS Code asks to sign you in.

To add it by hand, run **MCP: Add Server** from the Command Palette, choose **HTTP**, and enter `https://mcp.deliverect.com/mcp`. Or add it to `.vscode/mcp.json` (or your user `mcp.json`):

```json
{
  "servers": {
    "deliverect": {
      "type": "http",
      "url": "https://mcp.deliverect.com/mcp"
    }
  }
}
```

### GitHub Copilot app

On the [Deliverect listing in the GitHub MCP Registry](https://github.com/mcp/com.deliverect/deliverect), open the menu on **Install MCP server** and choose **Install in GitHub Copilot app**. Select **Allow**, then **Add server**, and **Sign in** next to the new server.

### GitHub Copilot in Visual Studio

Visual Studio 2022 17.14 or later. Add this to `.mcp.json` in your solution folder, then choose **Auth** in the CodeLens above the server to sign in:

```json
{
  "servers": {
    "deliverect": {
      "type": "http",
      "url": "https://mcp.deliverect.com/mcp"
    }
  }
}
```

### Claude

Add **Deliverect** from the [Claude connector directory](https://claude.ai/directory/deliverect). In Claude Code:

```bash
claude mcp add --transport http deliverect https://mcp.deliverect.com/mcp
```

### Cursor

See [Deliverect for Cursor](https://github.com/Deliverect/cursor-plugin), or add this to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "deliverect": {
      "url": "https://mcp.deliverect.com/mcp"
    }
  }
}
```

### ChatGPT

Add **Deliverect** from the [ChatGPT plugin directory](https://chatgpt.com/plugins/plugin_asdk_app_6aec531ab0f8819191ebb5167e77f353).

### Perplexity

On a paid plan, open **Deliverect** in [Perplexity's plugin directory](https://www.perplexity.ai/computer/plugins/connectors/deliverect) and select **+ Connect**.

### Other MCP clients

Any client that supports remote MCP servers over Streamable HTTP with OAuth sign-in can connect to `https://mcp.deliverect.com/mcp`. The server supports dynamic client registration and client ID metadata documents, so you don't need a client ID.

## Sign in

Your client opens a browser window the first time it connects. Sign in with your Deliverect account. The first time, you'll be asked to accept the connector's terms.

## Privacy and access

- Every tool is read-only: nothing can change menus, prices, orders or opening hours.
- You see only what your Deliverect user can see in the Deliverect portal.
- Customer and courier details are never returned.

[Privacy policy](https://www.deliverect.com/en/deliverect-mcp-connector-privacy-policy)

## MCP Registry

The server is listed in the official [MCP Registry](https://registry.modelcontextprotocol.io/v0.1/servers?search=com.deliverect) as `com.deliverect/deliverect`, and in the [GitHub MCP Registry](https://github.com/mcp/com.deliverect/deliverect). [`server.json`](server.json) is a copy of the official registry entry.

## Support

- Help article: https://help.deliverect.com/
- Email: integrations-support@deliverect.com

# TextKit plugin for Cursor

Adds the [TextKit](https://jointextkit.com?ref=gh-cursor-plugin) MCP server to Cursor. The agent can send and receive SMS, verify phone numbers, buy numbers, load contacts, build segments, and run broadcasts and automations on your TextKit account.

## Setup

1. Install the plugin from the Cursor Marketplace.
2. Sign in to TextKit when Cursor asks, or from the `textkit` entry in Cursor Settings → MCP. Approve the connection and pick test or live data.

Test data runs in the sandbox, so no real phone gets a text. Approving creates an API key named for the app on the console's API keys page; revoke it there to disconnect.

## Things to ask

- Buy a number in area code 512 and text +15005550006 "Your order shipped."
- Import the contacts in this CSV, tag them spring-sale, and tell me how many have an opt-in.
- Send everyone tagged vip "Doors open at 9 on Saturday." Do a dry run first and show me the count and cost.
- How did yesterday's broadcast do? Show delivered, failed, replies and opt-outs.

## Use an API key instead

Without the plugin, add this to `.cursor/mcp.json` (project) or `~/.cursor/mcp.json` (global):

```json
{
  "mcpServers": {
    "textkit": {
      "url": "https://mcp.jointextkit.com",
      "headers": { "Authorization": "Bearer ssms_sk_test_..." }
    }
  }
}
```

Get a key at [jointextkit.com/console](https://jointextkit.com/console?ref=gh-cursor-plugin).

## Contents

- `.cursor-plugin/plugin.json`: plugin manifest.
- `mcp.json`: the remote server `https://mcp.jointextkit.com` (streamable HTTP, OAuth sign-in).
- `assets/logo.png`: logo.

Docs: https://jointextkit.com/docs/mcp?ref=gh-cursor-plugin

## License

MIT

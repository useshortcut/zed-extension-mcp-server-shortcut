# Shortcut MCP Server Extension for Zed

This extension integrates [Shortcut's Model Context Protocol (MCP) server](https://github.com/useshortcut/mcp-server-shortcut) with the [Zed text editor](https://zed.dev/), enabling developers to interact with their Shortcut workspace directly from within their editor.

## What is MCP?

The Model Context Protocol (MCP) is an open standard that enables AI assistants to securely access external data sources and tools. This extension leverages MCP to provide seamless integration between Zed's AI features and Shortcut's project management capabilities.

## Features

With this extension, you can:

- **View and manage stories**: Access your Shortcut stories, epics, and iterations directly from Zed
- **Create and update stories**: Generate new stories and modify existing ones without leaving your editor
- **Search and filter**: Find specific stories, epics, or iterations using Shortcut's powerful search capabilities
- **Link code to stories**: Connect your development work to specific Shortcut stories
- **Track progress**: Monitor story states, assignments, and completion status

## Prerequisites

Before using this extension, you'll need:

1. A [Shortcut account](https://www.shortcut.com/signup) (free for up to 10 users)
2. A Shortcut API token (generate one at [Shortcut > Settings > API Tokens](https://app.shortcut.com/settings/account/api-tokens))
3. Node.js installed on your system (required for the MCP server)

## Installation

1. Install the extension from the Zed extensions marketplace.
2. The extension will automatically install the required `@shortcut/mcp` package.
3. Configure your Shortcut API token in your Zed settings (you should be prompted after installing the extension).

## Configuration

Upon installing the extension, Zed should prompt you to include your Shortcut API token, which is all you need to configure.

If not, add the following to your Zed settings manually:

```json
{
  "context_servers": {
    "mcp-server-shortcut": {
      "settings": {
        "shortcut_api_token": "YOUR_API_TOKEN_HERE"
      }
    }
  }
}
```

Replace `YOUR_API_TOKEN_HERE` with your actual Shortcut API token.

## Usage

Once configured, the Shortcut MCP server will be available to Zed's AI assistant. You can:

- Ask questions about your Shortcut stories, epics, etc.
- Create new stories and update existing ones
- Search across your Shortcut workspace
- Get status & summary reports on project progress

Example prompts:
- "Show me all stories assigned to me"
- "Create a new bug story for the login issue"
- "What's the status of epic #123?"
- "List all stories in the current iteration"

## Technical Details

This extension is built using:

- **Rust**: Core extension logic using the Zed Extension API
- **Node.js**: Runtime for the Shortcut MCP server
- **MCP Protocol**: Standard communication between Zed and Shortcut

The extension automatically manages the lifecycle of the MCP server, including:
- Installing the required npm package (`@shortcut/mcp`)
- Starting the server with proper authentication
- Handling connection and error states

## Development

To contribute to this extension:

1. Clone the repository.
2. Install Rust and the required dependencies.
3. Build with `cargo build --release`
4. Test your changes in Zed by going to extensions and using the "Install Dev Extension" feature.

## Support

For issues related to:
- **Extension functionality**: Open an issue in this repository
- **Shortcut MCP server**: Visit the [mcp-server-shortcut repository](https://github.com/useshortcut/mcp-server-shortcut)
- **Zed editor**: Check the [Zed documentation](https://zed.dev/docs/)

## Acknowledgements

The structure and implementation of this extension was based heavily on the [mcp-server-brave-search](https://github.com/zed-extensions/mcp-server-brave-search) extension.

## License

This extension is open source and available under the terms specified in the LICENSE file.

---

Copyright © 2025 Shortcut Software Company

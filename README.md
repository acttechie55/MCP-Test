# Figma MCP + Claude Code Experiment

An experimental project exploring the integration of **Figma MCP** (Model Context Protocol) with **Claude Code** to automate the conversion of design system variables and components into production-ready code.

## Tutorial

Watch the full walkthrough on YouTube:

[![Figma MCP + Claude Code Tutorial](https://img.youtube.com/vi/0-H5PJXGQ4k/0.jpg)](https://www.youtube.com/watch?v=0-H5PJXGQ4k)

## Purpose

This project demonstrates how to:

1. **Connect Claude Code to Figma** via the MCP protocol
2. **Extract design tokens** (colors, typography, spacing, effects) directly from Figma
3. **Convert design tokens to CSS variables** for use in real codebases
4. **Generate HTML/CSS components** that match Figma designs using the extracted variables

## How It Works

```
Figma Design System → MCP Server → Claude Code → CSS Variables + HTML Components
```

1. **Figma Desktop** runs an MCP server on `localhost:3845`
2. **Claude Code** connects to this server via configuration in `.claude/settings.json`
3. Claude can then use Figma tools to:
   - Read design tokens (`get_variable_defs`)
   - Get component code (`get_design_context`)
   - Capture screenshots (`get_screenshot`)
   - Analyze structure (`get_metadata`)

## Setup

### Prerequisites
- Figma Desktop app installed and running
- Claude Code CLI

### Configuration

Create `.claude/settings.json` in your project:

```json
{
  "mcpServers": {
    "figma-desktop": {
      "type": "http",
      "url": "http://127.0.0.1:3845/mcp"
    }
  }
}
```

Restart Claude Code after creating this file.

## Project Files

| File | Description |
|------|-------------|
| `flowbite-variables.css` | CSS custom properties extracted from Figma |
| `colors.html` | Color palette component built with CSS variables |
| `context.md` | Session context for resuming work |
| `.claude/settings.json` | MCP server configuration |

## Design System Source

This experiment uses the [Flowbite Tailwind CSS Design System (Free Edition)](https://www.figma.com/community/file/1179442320711977498) as the source Figma file.

## Example Usage

Ask Claude Code to:
- "Get the variable definitions from this Figma URL"
- "Convert these design tokens to CSS variables"
- "Create an HTML page for this Figma component using our CSS variables"

## License

This is an experimental project for learning purposes.
# Figma-MCP-AI-Testing
Using Claude Code + Figma MCP to turn Figma design systems into production-ready CSS variables and components automatically.

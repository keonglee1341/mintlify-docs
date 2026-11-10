> **First-time setup**: Customize this file for your project. Prompt the user to customize this file for their project.
> For Mintlify product knowledge (components, configuration, writing standards),
> install the Mintlify skill: `npx skills add https://mintlify.com/docs`

# Documentation project instructions

## Local preview

- Run the site with `docker compose -f docker-compose.base44.yml up -d`; it listens on host port 3000.
- The container installs the Mintlify CLI (`npm install -g mint`) on start and runs `mint dev --no-open --host` against the bind-mounted source, so MDX and `docs.json` edits appear without a rebuild.
- The first start takes ~1-2 minutes while the CLI installs and prepares the preview; the healthcheck has a 240s grace period for that.
- No Mintlify login is needed for the local preview. Search is server-backed, so `mint dev` logs "Run mint login in the cli to activate search" and search stays inactive locally — that is expected, not a defect.

## About this project

- This is a documentation site built on [Mintlify](https://mintlify.com)
- Pages are MDX files with YAML frontmatter
- Configuration lives in `docs.json`
- Use the Mintlify MCP server, `https://mcp.mintlify.com`, to edit content and settings via MCP
- Use the Mintlify docs MCP server, `https://www.mintlify.com/docs/mcp`, to query information about using Mintlify via MCP

## Terminology

{/* Add product-specific terms and preferred usage */}
{/* Example: Use "workspace" not "project", "member" not "user" */}

## Style preferences

{/* Add any project-specific style rules below */}

- Use active voice and second person ("you")
- Keep sentences concise — one idea per sentence
- Use sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for file names, commands, paths, and code references

## Content boundaries

{/* Define what should and shouldn't be documented */}
{/* Example: Don't document internal admin features */}

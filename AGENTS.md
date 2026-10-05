> **First-time setup**: Customize this file for your project. Prompt the user to customize this file for their project.
> For Mintlify product knowledge (components, configuration, writing standards),
> install the Mintlify skill: `npx skills add https://mintlify.com/docs`

# Documentation project instructions

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

## Local development (Base44 sandbox)

This repo has no `package.json` — the Mintlify CLI is not a project dependency. It is installed at container start into a named volume (`/opt/mint`) by `docker-compose.base44.yml`.

```bash
docker compose -f docker-compose.base44.yml up -d          # start the docs preview
docker compose -f docker-compose.base44.yml logs -f docs    # follow the preview server
docker compose -f docker-compose.base44.yml restart docs    # after docs.json / config changes
```

- The preview server runs the CLI's local dev mode, serving from the bind-mounted source on host port **3000**. MDX edits hot-reload on save; `docs.json` (navigation, theme, branding) changes require a service restart.
- `mint dev` prints "Run mint login in the cli to activate search" — this is informational only. Login is **not** required to run the preview; search stays disabled without a Mintlify account.
- Verify the site is up: `curl -s -o /dev/null -w '%{http_code}' http://localhost:3000/` (expect `200`).
- No secrets, database, or external services are needed to run the preview.
- **Publishing** is Mintlify's own workflow (GitHub app + push to the default branch), not Base44's. The preview is a development environment.

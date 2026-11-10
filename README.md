# AKPS Build Empire Crown Team — documentation site

The shared documentation site for the AKPS Build Empire Crown Team, built on [Mintlify](https://mintlify.com).
Pages are MDX files with YAML frontmatter; site settings live in `docs.json`.

## Run locally

```bash
docker compose -f docker-compose.base44.yml up -d
```

The preview is served at http://localhost:3000. MDX and `docs.json` edits reload in place.

Inside the container the site runs with the Mintlify CLI from the checked-out source:

```bash
npm install -g mint
mint dev --no-open --host
```

## Content

- `index.mdx` — introduction (public overview of the team and what we build)
- `quickstart.mdx` — onboarding path and ways of working (for team members)
- `logo/light.svg`, `logo/dark.svg` — the site wordmark
- `favicon.svg` — the crown favicon

## Publishing

Mintlify deploys from the connected repository once the site is linked in the Mintlify dashboard; this repo has no deploy configuration of its own.

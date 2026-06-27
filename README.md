# docs.fixture

Documentation site for the **FixtureLabs MCP server**, built with
[Mintlify](https://mintlify.com).

## Installation

```bash
npm install
```

## Usage

Start the local preview (like `npm run dev`):

```bash
npm run dev
```

This runs `mint dev` and serves the docs at http://localhost:3000.

### Other commands

```bash
npm run login     # authenticate the Mintlify CLI (enables local search)
npm run status    # show CLI auth status
npm run check     # find broken links
npm run validate  # strict build validation (fails on warnings/errors)
npm run upgrade   # update the Mintlify CLI
```

## Search in local preview

If the preview's search box shows **"Login into CLI to enable search"**, the
Mintlify CLI just isn't authenticated — it's a local-preview limitation, not a
content bug. Search works automatically on the deployed (hosted) docs.

To enable search while running `npm run dev`:

```bash
npm run login     # opens the browser to sign in to Mintlify
npm run status    # should now report you're logged in
```

Restart `npm run dev` afterwards and the search box becomes active.

## Structure

- `docs.json` — site config and navigation
- `introduction.mdx`, `quickstart.mdx` — Get Started
- `connect/` — connecting clients (Claude, Cursor, programmatic)
- `authentication/` — OAuth 2.1 flow, scopes, endpoint reference
- `tools/` — tool reference (utility, blog posts, practice questions)
- `reference/` — architecture, rate limits, errors, configuration, troubleshooting

## License

MIT

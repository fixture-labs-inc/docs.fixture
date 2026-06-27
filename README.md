# docs.fixture

A brief description of the project.

## Installation

```bash
# install steps go here
```

## Usage

```bash
# usage example goes here
```

## License

MIT
he URL in all cases:


https://app.fixturelabs.io/api/mcps/mcp
Claude Code
1. Add the server (run in your terminal):


claude mcp add --transport http fixture https://app.fixturelabs.io/api/mcps/mcp
fixture = the name you'll see it under (call it whatever)
--transport http matters — your server is streamable-HTTP (SSE is disabled)
2. Authenticate. Start Claude Code and run:


/mcp
You'll see fixture listed with an Authenticate option. Select it → your browser opens → log in with Google → the consent screen ("Fixture wants to access your account") → click Allow. The browser hands the token back to Claude Code automatically.

3. Use it. Run /mcp again and you'll see it connected with the tools (get_question, whoami, list_blog_posts, etc.). Now just ask Claude things like "get me a CAD practice question from Fixture."

That's it — no token to copy. Claude Code stores and auto-refreshes it.

Scope note: pick --scope user if you want it available across all your projects, or --scope project (default-ish) to share it with a repo via .mcp.json. For a personal tool, user is usually what you want.

ChatGPT
Requires a paid plan (Plus / Pro / Business / Enterprise) — custom MCP connectors aren't on free.

1. Settings → Connectors (a.k.a. Apps & Connectors).
2. Open Advanced settings → enable Developer mode (this is what unlocks adding your own MCP server; without it you only get the prebuilt connectors).
3. Back in Connectors → Create / Add custom connector:

URL: https://app.fixturelabs.io/api/mcps/mcp
Name: Fixture
Auth: OAuth 4. Click connect → browser flow → Google login → Allow (same consent screen). 5. In a chat, open the + / tools menu, enable the Fixture connector, then ask away.
Claude Desktop / Claude.ai (bonus, easiest)
Settings → Connectors → Add custom connector → paste the URL → log in → Allow. Done. Same flow, just a GUI instead of a CLI command.

What to expect once connected
Any Google account works for the read tools (whoami, get_user_profile, get_question, blog reads). get_question still respects whatever packs your account has.
create_blog_post only works if you logged in with a @fixturelabs.io account and granted the blog:write scope on the consent screen — otherwise that one tool is hidden/denied.
You log in once per client; after that the token refreshes silently.
The reason it's this simple is the OAuth + discovery machinery you already have — the client finds the login/token endpoints on its own from the /.well-known/... metadata. You literally just give it the URL.

Want me to write this up as a short "Connect Fixture to your AI tools" doc (with these steps + screenshots placeholders) that you could drop on the site or in the repo's README?

<p align="center"><img src="assets/logo.png" alt="Webstory" width="96" height="96"></p>

# Webstory for AI assistants

[Webstory](https://getwebstory.com) makes story websites for brands and shops: full-screen reels of video, photos and designs, with buttons, products and forms, that open like a social story on any phone.

Connect Webstory to your AI assistant and work on your stories in plain words. The assistant can:

- see your stories, chapters and reels, and how each story is doing: visitors, visits, how far people watched and which buttons they tapped;
- make a new draft story, add reels, change captions, titles and buttons, move or duplicate reels, and find and replace words across a story;
- bring in photos and portrait videos from a link or a file, or give you an upload page for your phone;
- make a preview link of a draft, or a share link for a live reel to send to someone;
- read the comments on your stories, the chats with your brands, and your orders (number, date, items, total, status and the buyer's first name).

This repository holds no code: Webstory is a hosted service. It has the logo and the configuration files that AI apps and directories read. The server is at

```
https://webstoryapp.com/mcp
```

(Streamable HTTP; you sign in with your Webstory account, OAuth 2.1).

## Connect it

You need a [Webstory account](https://webstoryapp.com/signup). When you connect, a Webstory page asks you to sign in, shows the workspace the assistant will work in and what it may do, and lets you switch any of that off before you approve.

| App              | How                                                                                                                                                                                                                       |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Claude           | **Settings → Connectors → Add custom connector**, name it Webstory, paste `https://webstoryapp.com/mcp`, then **Connect**                                                                                                 |
| ChatGPT          | Once Webstory is in ChatGPT's directory, find it there. Until then, with developer mode on, add a custom app with `https://webstoryapp.com/mcp` and OAuth sign-in                                   |
| Claude Code      | `claude mcp add --transport http webstory https://webstoryapp.com/mcp`, then `/mcp` to sign in. Or clone this repository: its `.mcp.json` lists the server (Claude Code asks you to approve it)                           |
| Cursor           | [Add to Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=webstory&config=eyJ1cmwiOiJodHRwczovL3dlYnN0b3J5YXBwLmNvbS9tY3AifQ%3D%3D), or add `mcp.json` from this repository                                   |
| VS Code, Copilot | [Install in VS Code](vscode:mcp/install?%7B%22name%22%3A%22webstory%22%2C%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A//webstoryapp.com/mcp%22%7D), or use `.mcp.json` from this repository                         |
| Gemini CLI       | `gemini extensions install https://github.com/WebStory-App/webstory-mcp`                                                                                                                                                  |
| Anything else    | Any MCP client that speaks Streamable HTTP and OAuth 2.1 with dynamic client registration: point it at `https://webstoryapp.com/mcp`                                                                                       |

## Safe by design

- The assistant works for you alone, in one workspace, and never does more than your team role allows.
- It changes drafts. A story doesn't go live without a person's OK in Webstory, unless you choose to let the assistant publish on its own.
- It never sees buyers' email addresses, phone numbers or postal addresses, and it can't touch payments, payouts, billing or your team.
- Every change it makes is listed in **Settings → Activity**, where you can undo it for 30 days.
- Disconnect it at any time in **Settings → AI agents**.

## More

- Docs, every tool and the REST API: [docs.webstoryapp.com/agents](https://docs.webstoryapp.com/agents)
- Privacy: [getwebstory.com/privacy](https://getwebstory.com/privacy#ai-agents) (Section 4.1, AI agents you connect)
- Terms: [getwebstory.com/terms](https://getwebstory.com/terms)
- Help: [getwebstory.com/contact](https://getwebstory.com/contact?inquiry=support) or hello@webstory.app
- Found a security problem? Email hello@webstory.app with "Security" in the subject.

The files in this repository are under the MIT License. Webstory itself is a hosted service under its own [terms](https://getwebstory.com/terms).

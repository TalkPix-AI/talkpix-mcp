# TalkPix MCP server

Make AI product ads, talking-photo videos and AI video clips from inside Claude or ChatGPT, using your [TalkPix](https://www.talkpix.ai) credits.

This is a **hosted remote MCP server**. There is nothing to install or run locally.

```
https://www.talkpix.ai/api/mcp
```

- Transport: Streamable HTTP
- Auth: OAuth 2.1 (dynamic client registration). You sign in to TalkPix and approve the connection.
- Supported clients: **Claude and ChatGPT**. Sign-in from other MCP clients is not enabled yet; for those, use the [REST API](https://www.talkpix.ai/developers) or the Node/Python clients.
- Billing: the same prepaid credits as the TalkPix website. No subscription required.

## Price first, always

Every tool that spends credits returns the price first and starts nothing. The assistant has to tell you the cost and call again with `expected_credits` before a render starts. You can also set a per-video and a daily budget on TalkPix; anything above it opens a confirmation page instead of spending.

## Tools

| Tool | What it does | Spends credits |
|---|---|---|
| `create_product_ad` | UGC-style ad: a TalkPix presenter holds your product and says the script the assistant writes, in the language you pick | yes, after price check |
| `create_talking_photo` | Makes the person in a photo speak a script the assistant writes, in a voice it picks | yes, after price check |
| `start_generation` | AI video from a prompt (optionally from a photo) | yes, after price check |
| `estimate_cost` | Credits a video would cost | no |
| `list_models` | Video models with their lengths and credit prices | no |
| `get_balance` | Your credit balance | no |
| `get_generation_status` | Status of a render, and the video when it is ready | no |
| `list_generations` | Your recent videos | no |
| `get_upload_link` / `upload_photo` | Pass a photo from the chat to TalkPix | no |

Finished videos play inline in ChatGPT and Claude.

## Setup

### Claude
Settings → Connectors → **Add custom connector**. Name it `TalkPix`, paste `https://www.talkpix.ai/api/mcp`, press **Connect** and sign in. Full guide: https://www.talkpix.ai/claude

### ChatGPT
Add a custom connector (developer mode) with the URL above and choose OAuth. Sign in to TalkPix when ChatGPT asks. Full guide: https://www.talkpix.ai/chatgpt

## Links

- Website: https://www.talkpix.ai
- REST API for developers: https://www.talkpix.ai/developers
- API examples (curl, Node, Python): https://github.com/TalkPix-AI/talkpix-api-examples
- Clients: `npm install talkpix` · `pip install talkpix`
- Support: support@talkpix.ai

This repository holds documentation and registry metadata only; the server itself is hosted by TalkPix.

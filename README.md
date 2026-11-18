# YouTube Channel Scraper — MCP Server

Track any YouTube channel and get its new uploads as clean, structured data from your AI agent or MCP client — video ID, title, watch link, publish timestamp, channel name, thumbnail, view count at read time and a description snippet, with a Shorts flag on every record. The first run hands you the channel's latest videos, and with monitoring mode on, every run after that delivers only the new ones.

This repo is the MCP listing for the [YouTube Channel Scraper](https://apify.com/magnova/youtube-channel-scraper) Actor by Magnova on Apify. The server is hosted by Apify at the pinned endpoint below — there is nothing to install or run from this repository; you just point your MCP client at the URL.

## Tools

The pinned connection loads a focused tool set:

- **magnova--youtube-channel-scraper** — Fetch a YouTube channel's videos by channel ID, @handle or channel URL, with an optional only-new monitoring mode. Returns structured records: video ID, title, watch link, publish timestamp, channel name, thumbnail, view count, Shorts flag, and description snippet.
- **fetch-actor-details** — Fetch the Actor's full input schema, pricing, and documentation, so an agent can check parameters and cost before running it.
- **get-actor-run / get-dataset-items** — Run and storage helpers, loaded automatically, used to fetch the results a run produced.

## Connect

Pinned endpoint (Streamable HTTP):

```
https://mcp.apify.com?tools=fetch-actor-details,magnova/youtube-channel-scraper
```

On first connect, your client will ask you to sign in with your Apify account (OAuth). If your client cannot do OAuth, pass your Apify API token as an `Authorization: Bearer <YOUR_APIFY_TOKEN>` header instead.

### Cursor / VS Code / other Streamable HTTP clients

```json
{
  "mcpServers": {
    "youtube-channel-scraper": {
      "url": "https://mcp.apify.com?tools=fetch-actor-details,magnova/youtube-channel-scraper"
    }
  }
}
```

### Claude Desktop

Claude Desktop's config file only runs local commands, so use the `mcp-remote` bridge:

```json
{
  "mcpServers": {
    "youtube-channel-scraper": {
      "command": "npx",
      "args": [
        "-y",
        "mcp-remote",
        "https://mcp.apify.com?tools=fetch-actor-details,magnova/youtube-channel-scraper"
      ]
    }
  }
}
```

The same pinned URL also lives in this repo's `.mcp.json`, and `server.json` is the listing for the Official MCP Registry, published as `io.github.memeanalyst/youtube-channel-scraper-mcp`.

## Pricing

Pay per event, billed to your own Apify account: **$0.005 per video returned — $5 per 1,000 videos**. No start fee, no subscription, and you are only charged for records actually delivered.

## Links

- Actor on Apify Store: https://apify.com/magnova/youtube-channel-scraper
- MCP endpoint: https://mcp.apify.com?tools=fetch-actor-details,magnova/youtube-channel-scraper

*Video records come from YouTube's official per-channel RSS upload feeds.*

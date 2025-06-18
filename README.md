# cryptopanic-mcp-server

[![Discord](https://img.shields.io/discord/1353556181251133481?cacheSeconds=3600)](https://discord.gg/aRnuu2eJ)
![GitHub License](https://img.shields.io/github/license/kukapay/blockbeats-mcp)

Provide the latest cryptocurrency news to AI agents, powered by [CryptoPanic](https://cryptopanic.com/).

<a href="https://glama.ai/mcp/servers/dp6kztv7yx">
  <img width="380" height="200" src="https://glama.ai/mcp/servers/dp6kztv7yx/badge" alt="cryptopanic-mcp-server MCP server" />
</a>

## Tools

The server implements only one tool: 

```python
get_crypto_news(kind: str = "news", num_pages: int = 1) -> str
```
- `kind`: Content type (news, media)
- `num_pages`: Number of pages to fetch (default: 1, max: 10)

Example Output: 

```
- Bitcoin Breaks $60k Resistance Amid ETF Optimism
- Ethereum Layer 2 Solutions Gain Traction
- New Crypto Regulations Proposed in EU
- ...
```


## Configuration

- CryptoPanic API key & API plan: get one [here](https://cryptopanic.com/developers/api/)
- Add a server entry to your configuration file:

```
"mcpServers": { 
  "cryptopanic-mcp-server": { 
    "command": "uv", 
    "args": [ 
      "--directory", 
      "/your/path/to/cryptopanic-mcp-server", 
      "run", 
      "main.py" 
    ], 
    "env": { 
      "CRYPTOPANIC_API_PLAN": "your_api_plan",
      "CRYPTOPANIC_API_KEY": "your_api_key" 
    } 
  } 
}
```

- Replace `/your/path/to/cryptopanic-mcp-server` with your actual installation path.
- Replace `CRYPTOPANIC_API_PLAN` and `CRYPTOPANIC_API_KEY` with your API plan and key from CryptoPanic. 

## License

MIT License - see `LICENSE` file
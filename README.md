# cryptopanic-mcp-server

Provide the latest cryptocurrency news to AI agents, powered by [CryptoPanic](https://cryptopanic.com/).

## Tools

The server implements only one tool: 

```python
get_crypto_news(kind: str = "news", num_pages: int = 1) -> str
```
- `kind`: Content type (news, analysis, videos)
- `num_pages`: Number of pages to fetch (default: 1, max: 10)

Example Output: 

```
- Bitcoin Breaks $60k Resistance Amid ETF Optimism
- Ethereum Layer 2 Solutions Gain Traction
- New Crypto Regulations Proposed in EU
- ...
```


## Configuration

- CryptoPanic API key: get one [here](https://cryptopanic.com/developers/api/)
- Add a server entry to your configuration file:

```
"mcpServers": { 
  "cryptopanic-mcp-server": { 
    "command": "uv", 
    "args": [ 
      "--directory", "/your/path/to/cryptopanic-mcp-server", 
      "run", 
      "main.py" 
    ], 
    "env": { 
      "CRYPTOPANIC_API_KEY": "" 
    } 
  } 
}
```

## License

MIT License - see `LICENSE` file

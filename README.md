# Sponsoor agent plugins

Query [Sponsoor](https://sponsoor.cc) (YouTube sponsorship intelligence) from your coding agent through its MCP server at `https://app.sponsoor.cc/mcp`.

## 1. Get an API key

Sign in at https://app.sponsoor.cc (Google, Microsoft or GitHub; 5 free credits), open https://app.sponsoor.cc/keys, create a key, then:

```bash
export SPONSOOR_API_KEY=spk_your_key
```

## 2. Add it to your agent

### Claude Code

```
/plugin marketplace add sponsoorcc/agent-plugins
/plugin install sponsoor@sponsoor
```

Or without the plugin:

```bash
claude mcp add --transport http sponsoor https://app.sponsoor.cc/mcp --header "Authorization: Bearer $SPONSOOR_API_KEY"
```

### OpenAI Codex

```bash
codex mcp add sponsoor --url https://app.sponsoor.cc/mcp --bearer-token-env-var SPONSOOR_API_KEY
```

Or in `~/.codex/config.toml`:

```toml
[mcp_servers.sponsoor]
url = "https://app.sponsoor.cc/mcp"
bearer_token_env_var = "SPONSOOR_API_KEY"
```

## Tools and credits

`search_brands`, `brand_creators`, `search_creators`, `creator_brands`, `search_videos`, `competitors`. 1 credit per call, up to 50 rows. Docs: https://sponsoor.cc/developers/

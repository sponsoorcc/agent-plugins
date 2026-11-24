---
name: sponsoor
description: Use when the user asks which brands sponsor which YouTube creators, who a brand's sponsorship competitors are, which creators carry sponsors in a niche or category, or for sponsored YouTube videos. Queries the Sponsoor MCP server.
---

# Sponsoor

Sponsoor tracks YouTube sponsorships: brands, creators and sponsored videos. Use the `sponsoor` MCP tools:

- `search_brands`: brands, most sponsored first. Filter by name (`q`) or `category` (a parent such as "Crypto" includes its subcategories).
- `brand_creators`: creators a brand sponsors, with video counts.
- `search_creators`: creators with sponsorships. Filter by name, niche, sponsor category, country (ISO alpha-2), subscriber range.
- `creator_brands`: brands a creator sponsors, with video counts.
- `search_videos`: sponsored videos, most viewed first. Filter by brand, creator, title text or category.
- `competitors`: brands that sponsor the same creators as a given brand, ranked by shared creators.

## Rules

- Each tool call costs 1 credit and returns at most 50 rows. New accounts get 5 free credits. Plan the fewest calls that answer the question and say when a result is capped at 50.
- Authentication is the `SPONSOOR_API_KEY` environment variable (a key starting `spk_`). If calls return 401, tell the user to create a key at https://app.sponsoor.cc/keys and export it.
- Quote numbers exactly as returned. Never invent sponsors, creators or counts.

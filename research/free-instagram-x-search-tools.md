# Free tools / MCP servers for searching Instagram and X (Twitter)

_Researched 2026-10-18 via GitHub repository search. Star counts are as of that date._
_Requirement: search Instagram and x.com safely, with no subscription or paid API._

## Important caveat: "free" means "unofficial"

There is no official, free way to *search* either platform:

- **X API** free tier does not include search; read/search access is paid.
- **Instagram Graph API** is free but only covers your own Business/Creator
  account data (plus limited hashtag search) and requires a Meta app.

So every free option below uses X's / Instagram's internal web APIs, guest
tokens, or browser automation. That works, but:

- It is against both platforms' Terms of Service.
- Accounts used for logging in can be rate-limited, challenged, or banned.
- Tools break whenever the platform changes its internal API.

**"Safe" usage rules:** read-only, low request volume, use a separate
throwaway account (never your main/company account), keep cookies/session files
local and out of git, and prefer anonymous (no-login) modes where offered.

## Recommended shortlist

| Need | Pick | Why |
|---|---|---|
| X + many platforms, one tool | [Panniantong/Agent-Reach](https://github.com/Panniantong/Agent-Reach) (~99k ★) | CLI for agents, "zero API fees", covers Twitter/X, Reddit, YouTube, GitHub etc. **No Instagram.** |
| X search via MCP | [adhikasp/mcp-twikit](https://github.com/adhikasp/mcp-twikit) (236 ★) | Most-used twikit-based MCP server; needs an X login (use a burner). |
| X search via MCP (browser-based) | [ihuzaifashoukat/x-use](https://github.com/ihuzaifashoukat/x-use) (177 ★) | Playwright/patchright, no X API key, actively updated. |
| Instagram, public data, no login | [instaloader/instaloader](https://github.com/instaloader/instaloader) (13.6k ★) | Mature, works anonymously for public profiles/posts/hashtags. Not an MCP, but easy to wrap. |
| Trend research across X/Instagram/Reddit/etc. | [mvanhorn/last30days-skill](https://github.com/mvanhorn/last30days-skill) (~65k ★) | Claude Code skill (already installed in this environment as `/last30days`). Reddit/HN work free; X and others need setup. |

## X (Twitter): all candidates

### Underlying libraries (most reliable)
| Repo | ★ | Notes |
|---|---|---|
| [d60/twikit](https://github.com/d60/twikit) | 4.7k | Python, internal API, needs login. 160 open issues; see maintained fork [unclecode/twikit](https://github.com/unclecode/twikit) for 2026 patches. |
| [vladkens/twscrape](https://github.com/vladkens/twscrape) | 2.9k | Python lib + CLI, multi-account rotation, rate-limit handling. |
| [zedeus/nitter](https://github.com/zedeus/nitter) | 14.5k | Self-hosted Twitter front-end. **Archived**; public instances mostly dead. |

### MCP servers
| Repo | ★ | Auth | Notes |
|---|---|---|---|
| [adhikasp/mcp-twikit](https://github.com/adhikasp/mcp-twikit) | 236 | X login | Built on twikit. |
| [ihuzaifashoukat/x-use](https://github.com/ihuzaifashoukat/x-use) | 177 | Browser session | Multi-account, profile research, posts/replies. |
| [yuyuki-guyu/chirp](https://github.com/yuyuki-guyu/chirp) | 35 | Cookies | Read + write; new (Sep 2026). |
| [takiAA/twitter-scraper-mcp](https://github.com/takiAA/twitter-scraper-mcp) | 28 | twscrape sessions | Has credential-free public tweet lookup; posting is opt-in. |
| [Sha-Dox/xmcp](https://github.com/Sha-Dox/xmcp) | 1 | None / optional cookies | Guest-token for profiles/timelines; search needs cookies. Very new. |
| [shubhamattri/x-mcp-server](https://github.com/shubhamattri/x-mcp-server) | 0 | Browser cookies | Read-only (good for safety), but tiny/unproven. |

## Instagram: all candidates

### Underlying libraries
| Repo | ★ | Notes |
|---|---|---|
| [instaloader/instaloader](https://github.com/instaloader/instaloader) | 13.6k | Anonymous mode for public data; login optional. Safest free option. |
| [subzeroid/instagrapi](https://github.com/subzeroid/instagrapi) | 7.0k | Private mobile API, requires login, higher ban risk. Upsells paid HikerAPI. |

### MCP servers
| Repo | ★ | Auth | Notes |
|---|---|---|---|
| [duhlink/instagram-server-next-mcp](https://github.com/duhlink/instagram-server-next-mcp) | 50 | Browser session | Older but most-starred free scraping MCP. |
| [Bob-lance/instagram-engagement-mcp](https://github.com/Bob-lance/instagram-engagement-mcp) | 46 | Login | Engagement/comment analysis. |
| [pedroantonnio/Instagram-Analytics-MCP](https://github.com/pedroantonnio/Instagram-Analytics-MCP) | 0 | None | Instaloader in anonymous mode, public data only. Very new. |
| [osAlhaddad1/instagram-mcp](https://github.com/osAlhaddad1/instagram-mcp) | 0 | Login (instagrapi) | Writes disabled by default. Very new. |
| [jlbadano/ig-mcp](https://github.com/jlbadano/ig-mcp) | 197 | Official Graph API | Free and ToS-compliant, but only for your own Business account, not general search. |

## Excluded (paid or pay-per-use)
- [OneInterface/stormy-cookbook](https://github.com/OneInterface/stormy-cookbook): needs a paid API key.
- [XPOZpublic/xpoz-claude-code-plugin](https://github.com/XPOZpublic/xpoz-claude-code-plugin): hosted Xpoz service.
- [Br0ski777/twitter-scraper-x402](https://github.com/Br0ski777/twitter-scraper-x402): x402 micropayments.
- [Sharan-Kumar-R/Custom-MCP-Server](https://github.com/Sharan-Kumar-R/Custom-MCP-Server): uses RapidAPI (usually paid).
- Meta Ads MCP servers: advertising tools, not search.

## Suggested next steps
1. Shortlist: **Agent-Reach** or **mcp-twikit** for X, **instaloader** (anonymous) for Instagram.
2. Before installing anything, read the code. These tools handle your cookies/passwords.
3. Test with a throwaway account, read-only, at low volume.

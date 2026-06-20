**English** | [中文](README.zh-CN.md)

# Follow AI×Biotech Builders, Not Influencers

An AI-powered digest that tracks the top builders in AI for biology and innovative
drug discovery — the scientists, founders, and company leaders who are actually
building things — and delivers curated summaries of what they're saying.

**Philosophy:** Follow people who build products and have original opinions, not
influencers who regurgitate information.

## What You Get

A daily or weekly digest delivered to your preferred messaging app (Telegram, Discord,
WhatsApp, etc.) with:

- Summaries of new podcast episodes from top biotech / AI-bio podcasts (Ground Truths, The Long Run, Raising Health, Training Data)
- Key posts and insights from 20 curated AI×biotech builders on X/Twitter (scientists, founders, and company accounts)
- Links to all original content
- Available in English, Chinese, or bilingual

## Quick Start

1. Install the skill in your agent (OpenClaw or Claude Code)
2. Say "set up follow ai biotech builders" or invoke `/follow-ai-biotech-builders`
3. The agent walks you through setup conversationally — no config files to edit

The agent will ask you:
- How often you want your digest (daily or weekly) and what time
- What language you prefer
- How you want it delivered (Telegram, email, or in-chat)

No API keys needed — all content is fetched centrally.
Your first digest arrives immediately after setup.

## Changing Settings

Your delivery preferences are configurable through conversation. Just tell your agent:

- "Switch to weekly digests on Monday mornings"
- "Change language to Chinese"
- "Make the summaries shorter"
- "Show me my current settings"

The source list (builders and podcasts) is curated centrally and updates
automatically — you always get the latest sources without doing anything.

## Customizing the Summaries

The skill uses plain-English prompt files to control how content is summarized.
You can customize them two ways:

**Through conversation (recommended):**
Tell your agent what you want — "Make summaries more concise," "Focus on actionable
insights," "Use a more casual tone." The agent updates the prompts for you.

**Direct editing (power users):**
Edit the files in the `prompts/` folder:
- `summarize-podcast.md` — how podcast episodes are summarized
- `summarize-tweets.md` — how X/Twitter posts are summarized
- `summarize-blogs.md` — how blog posts are summarized
- `digest-intro.md` — the overall digest format and tone
- `translate.md` — how English content is translated to Chinese

These are plain English instructions, not code. Changes take effect on the next digest.

## Default Sources

### Podcasts (4)
- [Ground Truths — Eric Topol](https://erictopol.substack.com)
- [The Long Run — Luke Timmerman](https://timmermanreport.com/the-long-run/)
- [Raising Health — a16z Bio + Health](https://a16z.com/raising-health/)
- [Training Data — Sequoia](https://www.youtube.com/playlist?list=PLOhHNjZItNnMm5tdW61JpnyxeYH5NDDx8)

### AI×Biotech Builders on X (20)
[Demis Hassabis](https://x.com/demishassabis), [Eric Topol](https://x.com/EricTopol), [Mohammed AlQuraishi](https://x.com/MoAlQuraishi), [Patrick Hsu](https://x.com/pdhsu), [Jure Leskovec](https://x.com/jure), [Pranav Rajpurkar](https://x.com/pranavrajpurkar), [Anima Anandkumar](https://x.com/AnimaAnandkumar), [Sergey Ovchinnikov](https://x.com/sokrypton), [Alex Zhavoronkov](https://x.com/biogerontology), [Alexander Rives](https://x.com/alexrives), [Ali Madani](https://x.com/thisismadani), [Joshua Meier](https://x.com/joshim5), [Stef van Grieken](https://x.com/stefvangrieken), [Simon Kohl](https://x.com/saakohl), [Institute for Protein Design](https://x.com/UWproteindesign), [Arc Institute](https://x.com/arcinstitute), [Chai Discovery](https://x.com/chaidiscovery), [Profluent](https://x.com/ProfluentBio), [Recursion](https://x.com/RecursionPharma), [Moderna](https://x.com/moderna_tx)

### Official Blogs (0)
None — no blog sources are configured. You can add biotech Substacks/blogs to `config/default-sources.json` later if you want.

## Installation

### Claude Code
```bash
git clone https://github.com/lugreat7788/follow-ai-biotech-builders.git ~/.claude/skills/follow-ai-biotech-builders
cd ~/.claude/skills/follow-ai-biotech-builders/scripts && npm install
```

### OpenClaw
```bash
git clone https://github.com/lugreat7788/follow-ai-biotech-builders.git ~/skills/follow-ai-biotech-builders
cd ~/skills/follow-ai-biotech-builders/scripts && npm install
```

## Requirements

- An AI agent (OpenClaw, Claude Code, or similar)
- Internet connection (to fetch the central feed)

That's it. No API keys needed. All content (blog articles + YouTube transcripts + X/Twitter posts)
is fetched centrally and updated daily.

## How It Works

1. A central feed is updated daily with the latest content from all sources
   (blog articles via web scraping, YouTube transcripts via Supadata, X/Twitter via official API)
2. Your agent fetches the feed — one HTTP request, no API keys
3. Your agent remixes the raw content into a digestible summary using your preferences
4. The digest is delivered to your messaging app (or shown in-chat)

See [examples/sample-digest.md](examples/sample-digest.md) for what the output looks like.

## Privacy

- No API keys are sent anywhere — all content is fetched centrally
- If you use Telegram/email delivery, those keys are stored locally in `~/.follow-ai-biotech-builders/.env`
- The skill only reads public content (public blog posts, public YouTube videos, public X posts)
- Your configuration, preferences, and reading history stay on your machine

## License

MIT


# 🎌 MangaLore — AI Manga Companion on Solana

<div align="center">

![MangaLore Banner](https://raw.githubusercontent.com/agentmangalore/mangalore/main/assets/cover_1_hero.jpg)

[![Featured on Orynth](https://orynth.dev/api/badge/mangalore?theme=light&style=default)](https://orynth.dev/projects/mangalore)

**The first AI companion that quizzes you, rewrites manga endings, matches you to iconic characters — and pays you in SOL for knowing your lore.**

[![Telegram Bot](https://img.shields.io/badge/Telegram-@mangaloreagent__bot-26A5E4?style=flat&logo=telegram&logoColor=white)](https://t.me/mangaloreagent_bot)
[![Twitter/X](https://img.shields.io/badge/X-@mangaloredotfun-000000?style=flat&logo=x&logoColor=white)](https://x.com/mangaloredotfun)
[![Built on Solana](https://img.shields.io/badge/Blockchain-Solana-9945FF?style=flat&logo=solana&logoColor=white)](https://solana.com)
[![Powered by elizaOS](https://img.shields.io/badge/Powered%20by-elizaOS-black?style=flat)](https://github.com/elizaos/eliza)
[![License](https://img.shields.io/badge/License-MIT-E8001D?style=flat)](LICENSE)

[🤖 Launch Bot](https://t.me/mangaloreagent_bot) · [🌐 Website](https://mangalore.fun) · [🐦 Twitter/X](https://x.com/mangaloredotfun) · [💬 Discord](#)

</div>

---

## 📖 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [How It Works](#-how-it-works)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [Bot Commands](#-bot-commands)
- [LORE Token & Rewards](#-lore-token--rewards)
- [API Sources](#-api-sources)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🎯 Overview

MangaLore is an AI-powered Telegram bot built on **Solana** and **elizaOS** that transforms passive manga fandom into an interactive, rewarding experience.

For years, manga fans have poured passion into knowing every arc, every character, every plot twist — with nothing to show for it. MangaLore changes that. Every quiz answered, every alternate ending voted on, every personality match claimed becomes **LORE Points** that convert to real **SOL rewards** on-chain.

> *"Knowledge is an asset, and passion deserves real reward."*

### Why MangaLore?

| Problem | Solution |
|---|---|
| Fans have no incentive for deep lore knowledge | LORE token rewards for correct answers |
| Passive consumption — no engagement | Daily quests, streaks, leaderboard |
| Content ownership belongs to platforms | NFT character cards on Solana |
| Payment friction for global fans | SOL — borderless, instant, near-free |

---

## ✨ Features

### 🎯 Daily Quest
AI-generated trivia from **18,000+ manga titles** across three difficulty tiers:

| Tier | Description | Points |
|---|---|---|
| 🟢 Easy | Main characters, iconic scenes, basic plot | +5 LORE |
| 🟡 Hard | Supporting characters, specific arcs, author details | +10 LORE |
| 🔴 Legendary | Deep lore, minor characters, chapter-specific details | +25 LORE |

- 30-second countdown per question
- Daily streak system with multiplier bonuses
- Questions freshly generated each day via AI — never repeating

---

### ✍️ Alternative Universe
The AI rewrites iconic manga scenes in **400–600 words** — faithful to the lore you love.

**Available styles:**
- 🖤 **Dark & Tragic** — sacrifice, loss, bittersweet resolution
- 🌸 **Hopeful & Wholesome** — redemption, second chances, found family
- ⚔️ **Epic & Climactic** — grand battles, world-changing moments
- 🌀 **Chaotic & Unpredictable** — unexpected alliances, genre-bending twists

Vote the best community endings. Request custom scenarios using LORE Points.

---

### 🎴 Character Match
Five personality questions → **500+ manga characters** → one perfect match.

After matching, receive a **free NFT character card** minted on Solana via Metaplex:
- Unique card for each character
- Tradeable on Solana NFT marketplaces
- Upgradeable to Rare / Legendary tiers (Phase 3)

---

### 🏆 Leaderboard & Rewards
- Global rankings updated weekly
- **Top 10 monthly players receive SOL directly** to their connected wallet
- Automated smart contract distribution — no manual claims
- Streak bonuses multiply your LORE earnings

---

## ⚙️ How It Works

```
User sends command via Telegram
          ↓
MangaLore AI Agent (elizaOS)
          ↓               ↓               ↓
    AI Engine         Manga APIs       Solana
    (Quiz Gen,        (AniList,        (Wallet,
     Story Gen,       MangaDex,        LORE Token,
     Personality)     Jikan, Kitsu)    NFT Mint)
```

### Flow Example — Daily Quest

```
1. User sends /quiz
2. Bot asks: pick manga or random?
3. User selects manga + difficulty
4. AI generates lore-accurate question via AniList/Jikan data
5. User answers A/B/C/D within 30 seconds
6. Correct → LORE Points added to account
7. Streak updated → bonus if 7+ days
8. Points sync to Solana wallet (if connected)
```

---

## 🛠 Tech Stack

| Layer | Technology |
|---|---|
| **Bot Framework** | [Telegraf.js](https://telegraf.js.org/) / [Grammy](https://grammy.dev/) |
| **AI Agent** | [elizaOS](https://github.com/elizaos/eliza) |
| **Language Model** | Claude API (Anthropic) |
| **Manga Data** | AniList GraphQL API, MangaDex REST API, Jikan API, Kitsu API |
| **Blockchain** | [Solana Web3.js](https://solana-labs.github.io/solana-web3.js/) |
| **NFT** | [Metaplex](https://www.metaplex.com/) |
| **Token Standard** | SPL Token (Solana) |
| **Database** | PostgreSQL + Redis (cache) |
| **Runtime** | Node.js 20+ |
| **Hosting** | Railway / Vercel |

---

## 📁 Project Structure

```
mangalore/
├── src/
│   ├── agent/
│   │   ├── personality.md        # elizaOS agent config
│   │   ├── behaviors.ts          # Behavior rules & handlers
│   │   └── prompts/              # AI prompt templates
│   │       ├── quiz.ts
│   │       ├── alternative.ts
│   │       └── personality.ts
│   ├── bot/
│   │   ├── index.ts              # Telegram bot entry point
│   │   ├── commands/             # Command handlers
│   │   │   ├── quiz.ts           # /quiz handler
│   │   │   ├── whatif.ts         # /whatif handler
│   │   │   ├── whoareyou.ts      # /whoareyou handler
│   │   │   ├── rank.ts           # /rank handler
│   │   │   └── wallet.ts         # /wallet handler
│   │   └── middleware/
│   │       ├── auth.ts
│   │       └── rateLimit.ts
│   ├── manga/
│   │   ├── anilist.ts            # AniList API client
│   │   ├── mangadex.ts           # MangaDex API client
│   │   ├── jikan.ts              # Jikan API client
│   │   └── aggregator.ts         # Unified data layer
│   ├── solana/
│   │   ├── wallet.ts             # Wallet connection
│   │   ├── lore-token.ts         # LORE token operations
│   │   ├── nft.ts                # NFT minting via Metaplex
│   │   └── rewards.ts            # Leaderboard reward distribution
│   ├── db/
│   │   ├── schema.sql            # PostgreSQL schema
│   │   ├── users.ts              # User model
│   │   ├── streaks.ts            # Streak tracking
│   │   └── leaderboard.ts        # Leaderboard queries
│   └── utils/
│       ├── logger.ts
│       └── config.ts
├── web/
│   └── index.html                # Landing page
├── assets/                       # Brand assets (logos, covers)
├── docs/                         # Additional documentation
├── .env.example
├── package.json
├── tsconfig.json
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites

- Node.js 20+
- PostgreSQL 15+
- Redis 7+
- Telegram Bot Token (via [@BotFather](https://t.me/botfather))
- Solana wallet (devnet for development)
- Anthropic API key (for Claude)

### Installation

```bash
# Clone the repository
git clone https://github.com/agentmangalore/mangalore.git
cd mangalore

# Install dependencies
npm install

# Copy environment variables
cp .env.example .env
```

### Environment Variables

```env
# Telegram
TELEGRAM_BOT_TOKEN=your_bot_token_here

# Anthropic (Claude API)
ANTHROPIC_API_KEY=your_anthropic_api_key

# Manga APIs
ANILIST_API_URL=https://graphql.anilist.co
MANGADEX_API_URL=https://api.mangadex.org
JIKAN_API_URL=https://api.jikan.moe/v4

# Solana
SOLANA_NETWORK=devnet
SOLANA_RPC_URL=https://api.devnet.solana.com
LORE_TOKEN_MINT_ADDRESS=your_token_mint_address
TREASURY_WALLET=your_treasury_wallet

# Database
DATABASE_URL=postgresql://user:password@localhost:5432/mangalore
REDIS_URL=redis://localhost:6379

# App
NODE_ENV=development
PORT=3000
```

### Database Setup

```bash
# Run migrations
npm run db:migrate

# Seed initial data (optional)
npm run db:seed
```

### Run Development

```bash
# Start bot in development mode
npm run dev

# Start with hot reload
npm run dev:watch
```

### Run Production

```bash
# Build
npm run build

# Start
npm start
```

---

## 🤖 Bot Commands

| Command | Description |
|---|---|
| `/start` | Welcome message + main menu |
| `/quiz` | Start a daily trivia quest |
| `/whatif [manga]` | Request an AI alternative ending |
| `/whoareyou` | Take the personality quiz |
| `/rank` | View your stats & global leaderboard |
| `/wallet` | Connect your Solana wallet |
| `/streak` | Check your current streak |
| `/help` | Show all commands |

### Command Examples

```
/quiz
→ Pick a manga or let MangaLore choose
→ Select difficulty: Easy / Hard / Legendary
→ Answer A / B / C / D within 30 seconds

/whatif attack on titan
→ Which scene do you want to reimagine?
→ Pick a style: Dark / Hopeful / Epic / Chaotic
→ AI generates 500-word alternative ending

/whoareyou
→ Answer 5 personality questions
→ Get matched to a manga character
→ Claim free NFT card on Solana

/wallet
→ Connect your Solana wallet address
→ View LORE Points balance
→ Convert LORE Points → LORE Token
→ Mint your NFT cards
```

---

## 💰 LORE Token & Rewards

### Earning LORE Points

| Action | Reward |
|---|---|
| Correct quiz answer (Easy) | +5 LORE |
| Correct quiz answer (Hard) | +10 LORE |
| Correct quiz answer (Legendary) | +25 LORE |
| 7-day streak bonus | +100 LORE |
| 30-day streak bonus | +500 LORE |
| Vote on Alternative Ending | +5 LORE |
| Refer a friend | +50 LORE |
| Top 10 monthly leaderboard | SOL direct reward |

### Conversion Rate

```
1,000 LORE Points = 0.01 SOL (base rate)
Rate adjusts monthly based on prize pool
```

### NFT Character Cards

- **Free mint** after completing personality quiz
- Stored on **Solana mainnet** via Metaplex
- Three tiers: Standard → Rare → Legendary
- Tradeable on any Solana NFT marketplace

---

## 📡 API Sources

MangaLore aggregates data from four open APIs:

| API | Data | Docs |
|---|---|---|
| [AniList](https://anilist.gitbook.io/anilist-apiv2-docs/) | 18,000+ manga, characters, synopsis | GraphQL |
| [MangaDex](https://api.mangadex.org/docs/) | Chapter data, cover art, metadata | REST |
| [Jikan](https://jikan.moe/) | MyAnimeList data, stats, ratings | REST |
| [Kitsu](https://kitsu.docs.apiary.io/) | Trending, community ratings | JSON:API |

All APIs used are **free and open** — no paid tiers required for core functionality.

---

## 🗺 Roadmap

### ✅ Phase 01 — Bot Launch *(Live Now)*
- [x] Telegram bot deployed at [@mangaloreagent_bot](https://t.me/mangaloreagent_bot)
- [x] elizaOS personality engine configured
- [x] AniList + MangaDex + Jikan API integration
- [x] Daily quiz with streak system
- [x] Personality quiz — 500+ characters
- [x] Landing page live

### 🔄 Phase 02 — AI & Rewards *(Month 2)*
- [ ] AI alternative ending engine (full lore-aware)
- [ ] LORE Points system activated on-chain
- [ ] Solana wallet connection via `/wallet`
- [ ] Global leaderboard with weekly rankings
- [ ] Referral reward system

### 📋 Phase 03 — Token & NFT *(Month 3)*
- [ ] LORE Token deployed on Solana mainnet
- [ ] Free NFT character card minting via Metaplex
- [ ] NFT upgrade system (Rare / Legendary tiers)
- [ ] Monthly SOL reward auto-distribution to top 10
- [ ] LORE Points → LORE Token conversion

### 🌐 Phase 04 — Ecosystem *(Q3 2026)*
- [ ] MangaLore Web App portal
- [ ] Publisher partnership quizzes
- [ ] Group reading clubs with shared leaderboards
- [ ] Multi-agent swarm mode (elizaOS)
- [ ] Community DAO for LORE token holders

---

## 🤝 Contributing

Contributions are welcome! Please read our contributing guidelines before submitting a pull request.

```bash
# Fork the repository
# Create a feature branch
git checkout -b feature/your-feature-name

# Commit your changes
git commit -m "feat: add your feature description"

# Push to your fork
git push origin feature/your-feature-name

# Open a Pull Request
```

### Commit Convention

We follow [Conventional Commits](https://www.conventionalcommits.org/):

```
feat:     New feature
fix:      Bug fix
docs:     Documentation changes
style:    Formatting, missing semicolons, etc.
refactor: Code restructuring
test:     Adding or updating tests
chore:    Build process or tooling changes
```

### Areas We Need Help

- 🤖 **AI prompt engineering** — better quiz generation, more accurate lore
- 🎨 **NFT card designs** — character artwork for the card collection
- 🌐 **i18n** — Indonesian, Japanese, Spanish, Portuguese translations
- 🧪 **Testing** — unit and integration test coverage
- 📚 **Documentation** — guides, tutorials, API docs

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 🔗 Links

| Resource | URL |
|---|---|
| 🤖 Telegram Bot | [@mangaloreagent_bot](https://t.me/mangaloreagent_bot) |
| 🌐 Website | [mangalore.fun](https://mangalore.fun) |
| 🐦 Twitter / X | [@mangaloredotfun](https://x.com/mangaloredotfun) |
| 💎 Orynth | [orynth.dev/projects/mangalore](https://orynth.dev/projects/mangalore) |
| ⛓️ Solana | [Solana Mainnet](https://solana.com) |
| 🤖 elizaOS | [github.com/elizaos/eliza](https://github.com/elizaos/eliza) |

---

<div align="center">

**Built with ❤️ for the manga community**

*Your fandom. Your rewards. Your lore.*

[![Telegram](https://img.shields.io/badge/Join-Telegram-26A5E4?style=for-the-badge&logo=telegram)](https://t.me/mangaloreagent_bot)
[![Twitter](https://img.shields.io/badge/Follow-@mangaloredotfun-000000?style=for-the-badge&logo=x)](https://x.com/mangaloredotfun)

</div>

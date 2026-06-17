<div align="center">

```
███████╗███████╗ ██████╗██████╗ ███████╗████████╗██████╗  █████╗ ████████╗███████╗
██╔════╝██╔════╝██╔════╝██╔══██╗██╔════╝╚══██╔══╝██╔══██╗██╔══██╗╚══██╔══╝██╔════╝
███████╗█████╗  ██║     ██████╔╝█████╗     ██║   ██║  ██║███████║   ██║   █████╗  
╚════██║██╔══╝  ██║     ██╔══██╗██╔══╝     ██║   ██║  ██║██╔══██║   ██║   ██╔══╝  
███████║███████╗╚██████╗██║  ██║███████╗   ██║   ██████╔╝██║  ██║   ██║   ███████╗
╚══════╝╚══════╝ ╚═════╝╚═╝  ╚═╝╚══════╝   ╚═╝   ╚═════╝ ╚═╝  ╚═╝   ╚═╝   ╚══════╝
```

# 🕵️ SecretDate Bot — Anonymous Telegram Chats

**Talk to anyone. Stay completely anonymous. No registration. No traces.**

[![Telegram Bot](https://img.shields.io/badge/Telegram-@secretdate7123__bot-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/secretdate7123_bot)
[![Status](https://img.shields.io/badge/Status-🟢%20Live-brightgreen?style=for-the-badge)]()
[![Anonymous](https://img.shields.io/badge/Identity-100%25%20Anonymous-blueviolet?style=for-the-badge&logo=tor-project&logoColor=white)]()
[![No Logs](https://img.shields.io/badge/Logs-Zero-red?style=for-the-badge)]()
[![Made With](https://img.shields.io/badge/Made%20with-Python%20%2B%20Love-FFD700?style=for-the-badge)]()

<br/>

> *"In a world where everything is tracked, watched, and stored — SecretDate gives you back the freedom to just... talk."*

<br/>

[**→ Launch Bot Now ←**](https://t.me/secretdate7123_bot)

---

</div>

## 📖 Table of Contents

- [What is SecretDate Bot?](#-what-is-secretdate-bot)
- [Why Anonymous Chat?](#-why-anonymous-chat)
- [Features](#-features)
- [How It Works](#-how-it-works)
- [Getting Started](#-getting-started)
- [Commands Reference](#-commands-reference)
- [Privacy & Security Model](#-privacy--security-model)
- [Architecture Overview](#-architecture-overview)
- [Tech Stack](#-tech-stack)
- [Self-Hosting Guide](#-self-hosting-guide)
- [Configuration](#-configuration)
- [Database Schema](#-database-schema)
- [Rate Limiting & Anti-Abuse](#-rate-limiting--anti-abuse)
- [FAQ](#-faq)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🕶️ What is SecretDate Bot?

**SecretDate** is a **zero-identity anonymous chat platform** built entirely inside Telegram. It pairs two strangers together for a completely private, one-on-one conversation — no phone numbers exchanged, no usernames revealed, no profile pictures exposed.

Think of it as a **confessional booth** meets **random chat roulette** — but inside the app you already use every day.

```
You          SecretDate Bot          Stranger
 │                  │                    │
 │  /start          │                    │
 │─────────────────►│                    │
 │                  │  (queued, waiting) │
 │                  │◄───────────────────│
 │  ◄──── MATCHED ──┤──── MATCHED ──────►│
 │                  │                    │
 │  "hey"           │                    │
 │─────────────────►│───────────────────►│
 │                  │        "hi there!" │
 │◄─────────────────│◄───────────────────│
 │                  │                    │
 │   NO NAMES. NO NUMBERS. JUST WORDS.   │
```

You remain a **ghost**. The bot acts as a neutral relay. When you disconnect, it's like the conversation never happened.

---

## 🔥 Why Anonymous Chat?

| Scenario | With Normal Chat | With SecretDate |
|---|---|---|
| Confess a secret | ❌ People will know | ✅ Nobody knows it's you |
| Vent about life | ❌ Judgment from friends | ✅ Stranger with no context |
| Make a new friend | ❌ Awkward cold DMs | ✅ Both opted in willingly |
| Practice a language | ❌ Embarrassing mistakes | ✅ No ego on the line |
| Just be honest | ❌ Social consequences | ✅ Radical honesty, zero risk |
| Get advice | ❌ Bias from people who know you | ✅ Fresh, unbiased perspective |

Sometimes the best conversations happen with someone who **doesn't know who you are**.

---

## ✨ Features

### 🎯 Core Experience
- **⚡ Instant Matching** — Get paired with a real stranger in seconds
- **🎭 100% Anonymous** — Your Telegram ID, username, and name are never revealed
- **🔀 Skip & Re-match** — Not clicking? Move on with one command
- **📵 Clean Disconnect** — Leave anytime. No drama, no ghost-labeling
- **🌍 Global Users** — Connect with people across the world, any time

### 🔒 Privacy First
- **Zero-knowledge relay** — Bot only forwards messages, stores nothing about content
- **Session-scoped only** — Pairings dissolve when either party leaves
- **No profile required** — Just click START and talk
- **No message history** — Conversations don't persist after disconnect

### 💬 Messaging Support
- ✅ Text messages
- ✅ Emojis & stickers
- ✅ Photos & images
- ✅ Voice messages
- ✅ GIFs & animations
- ✅ Files & documents
- ✅ Reactions (forwarded anonymously)

### 🛡️ Safety Features
- **Report system** — Flag inappropriate content
- **Rate limiting** — Prevents spam flooding
- **Keyword filters** — Configurable content moderation
- **Auto-ban** — Repeat violators removed automatically
- **Admin dashboard** — For moderation oversight

---

## 🔄 How It Works

The magic is in the simplicity. SecretDate uses a **matchmaking queue + session relay** model:

```
┌─────────────────────────────────────────────────────┐
│                  MATCHMAKING ENGINE                  │
│                                                     │
│   USER A joins queue ──────┐                        │
│                            ▼                        │
│                    ┌──────────────┐                 │
│                    │  WAIT QUEUE  │                 │
│   USER B joins ───►│   [A] [B]   │                 │
│                    └──────┬───────┘                 │
│                           │ match found!            │
│                    ┌──────▼───────┐                 │
│                    │  SESSION     │                 │
│                    │  A ◄───► B  │                 │
│                    └─────────────┘                  │
│                                                     │
│   Each user sees only: "You are connected to        │
│   a stranger. Say hello!"                           │
└─────────────────────────────────────────────────────┘
```

### Step-by-Step Flow

```
1. You open the bot            →   /start
2. Bot adds you to the queue   →   "Looking for a stranger..."
3. Match is found              →   "✅ Connected! Say hello!"
4. Messages relay in real-time →   No delay, no modification
5. Either user ends chat       →   /stop
6. Session is destroyed        →   All pairing data wiped
7. Optional: find new match    →   /next
```

### Message Relay Architecture

```
YOUR TELEGRAM CLIENT
        │
        │  (your Telegram User ID is the only identifier)
        ▼
  TELEGRAM API ──► SECRETDATE BOT SERVER
                           │
                    ┌──────┴──────┐
                    │ SESSION MAP │  { userA_id → userB_id }
                    └──────┬──────┘
                           │  (relay to partner)
                    TELEGRAM API
                           │
                           ▼
                  PARTNER'S TELEGRAM CLIENT
```

Your Telegram ID is used **only** to route messages. It is never exposed to your partner, never logged, never stored beyond the active session.

---

## 🚀 Getting Started

### For Users (Just Want to Chat)

**It's stupidly simple:**

1. Click this link: **[t.me/secretdate7123_bot](https://t.me/secretdate7123_bot)**
2. Press **START**
3. Type `/find` or just wait — you'll be matched automatically
4. **Say hello to your stranger** 👋
5. When done, type `/stop`

That's it. No account. No sign-up. No email. Nothing.

---

### For Developers (Self-Hosting)

#### Prerequisites

```bash
Python >= 3.10
Telegram Bot Token (from @BotFather)
Redis >= 6.0 (for session management)
PostgreSQL >= 13 (optional, for analytics/moderation)
```

#### Quick Start

```bash
# 1. Clone the repository
git clone https://github.com/yourusername/secretdate-bot.git
cd secretdate-bot

# 2. Create virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Configure environment
cp .env.example .env
nano .env  # Add your BOT_TOKEN and other config

# 5. Start Redis (if not running)
redis-server --daemonize yes

# 6. Run the bot
python main.py
```

The bot will be live within seconds.

---

## 📟 Commands Reference

### User Commands

| Command | Description | Example |
|---|---|---|
| `/start` | Initialize the bot & see welcome message | `/start` |
| `/find` | Join the matchmaking queue | `/find` |
| `/next` | Skip current partner, find a new one | `/next` |
| `/stop` | End current conversation | `/stop` |
| `/report` | Report inappropriate behavior | `/report spam` |
| `/help` | Show all available commands | `/help` |
| `/stats` | See your personal chat stats | `/stats` |
| `/settings` | Adjust preferences (language, etc.) | `/settings` |

### Admin Commands

> Only accessible by users with `ADMIN_IDS` configured in `.env`

| Command | Description |
|---|---|
| `/admin_stats` | Global bot statistics |
| `/admin_ban <user_id>` | Permanently ban a user |
| `/admin_unban <user_id>` | Lift a ban |
| `/admin_broadcast <msg>` | Send message to all active users |
| `/admin_sessions` | View currently active sessions |
| `/admin_queue` | View current matchmaking queue |

---

## 🔐 Privacy & Security Model

This is the heart of the project. Here's the **full transparency breakdown**:

### What We Store

| Data | Stored? | Duration | Why |
|---|---|---|---|
| Your Telegram User ID | ✅ Yes | Session only | Route messages to you |
| Your username / name | ❌ Never | — | Not needed |
| Message content | ❌ Never | — | We only relay, not store |
| Partner's identity | ❌ Never shown to you | — | Core privacy guarantee |
| Report data | ✅ Yes | 30 days | Safety & moderation |
| Ban list | ✅ Yes | Permanent | Prevent abuse |
| Aggregate stats | ✅ Yes | Indefinite | Bot health metrics |

### What Happens When You /stop

```
session_end event fires
       │
       ├──► Remove user from active_sessions map
       ├──► Remove pairing record  
       ├──► Notify partner ("Stranger has disconnected")
       └──► Partner returned to idle state

No message content is ever written to disk.
Session record contains only: [userA_id, userB_id, timestamp_start, timestamp_end]
```

### Threat Model

| Threat | Mitigation |
|---|---|
| "Can my partner find out who I am?" | No — bot only shares messages, never IDs or metadata |
| "Can the bot operator see my messages?" | Technically yes (relay server processes them), but we don't log content |
| "Can Telegram see my messages?" | Yes — Telegram is the transport layer. Use with this understanding. |
| "Can someone correlate me via timing attacks?" | Extremely difficult at scale; no timestamps are exposed to partners |
| "What if I'm reported?" | Admin gets report + your Telegram ID for review. Content of messages NOT stored. |

> 💡 **For maximum privacy**: Use a secondary Telegram account not linked to your real phone number.

---

## 🏗️ Architecture Overview

```
┌─────────────────────────────────────────────────────────────┐
│                        SECRETDATE BOT                        │
│                                                             │
│  ┌──────────────┐    ┌──────────────┐    ┌───────────────┐  │
│  │  TELEGRAM    │    │   MESSAGE    │    │  MATCHMAKING  │  │
│  │  WEBHOOK     │───►│   ROUTER     │───►│   ENGINE      │  │
│  │  HANDLER     │    │              │    │               │  │
│  └──────────────┘    └──────┬───────┘    └───────┬───────┘  │
│                             │                    │          │
│                      ┌──────▼──────────────────┐ │          │
│                      │      SESSION MANAGER     │◄┘          │
│                      │   (Redis-backed store)   │           │
│                      └──────┬───────────────────┘           │
│                             │                               │
│              ┌──────────────┼──────────────┐                │
│              ▼              ▼              ▼                │
│        ┌──────────┐  ┌──────────┐  ┌──────────┐            │
│        │  RELAY   │  │  QUEUE   │  │  MODERAT-│            │
│        │  ENGINE  │  │  MANAGER │  │  ION     │            │
│        └──────────┘  └──────────┘  └──────────┘            │
│                                                             │
│  ┌─────────────────────────────────────────────────────┐   │
│  │                   DATA LAYER                         │   │
│  │   Redis (sessions) │ PostgreSQL (moderation/stats)   │   │
│  └─────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────┘
```

### Key Design Decisions

1. **Redis for sessions**: Blazing fast key-value lookups for real-time message routing. Sessions auto-expire via TTL.
2. **Webhook over polling**: Lower latency, more efficient for production deployment.
3. **Async everywhere**: Built on `python-telegram-bot` async API — handles thousands of concurrent chats.
4. **Stateless relay**: The relay engine holds zero state. Session state lives entirely in Redis.
5. **Graceful degradation**: If Redis drops, users are disconnected cleanly rather than silently broken.

---

## 🛠️ Tech Stack

```
┌─────────────────────────────────────────────┐
│  Language    │  Python 3.11+                 │
│  Bot Library │  python-telegram-bot 20.x     │
│  Async       │  asyncio + aiohttp            │
│  Cache/Store │  Redis 7.x                    │
│  Database    │  PostgreSQL 15 (optional)     │
│  ORM         │  SQLAlchemy 2.0 (optional)    │
│  Deployment  │  Docker + Docker Compose      │
│  Reverse Proxy│ Nginx (webhook mode)         │
│  Process Mgr │  systemd / PM2                │
│  Monitoring  │  Prometheus + Grafana         │
└─────────────────────────────────────────────┘
```

### Dependencies (`requirements.txt`)

```txt
python-telegram-bot==20.7
redis==5.0.1
aioredis==2.0.1
sqlalchemy==2.0.23
asyncpg==0.29.0
alembic==1.13.0
pydantic==2.5.0
pydantic-settings==2.1.0
loguru==0.7.2
httpx==0.25.2
tenacity==8.2.3
```

---

## 🐳 Self-Hosting Guide

### Option 1: Docker (Recommended)

```bash
# Clone & configure
git clone https://github.com/yourusername/secretdate-bot.git
cd secretdate-bot
cp .env.example .env

# Edit .env with your settings
nano .env

# Launch everything
docker-compose up -d

# View logs
docker-compose logs -f bot
```

**`docker-compose.yml`:**
```yaml
version: '3.9'
services:
  bot:
    build: .
    restart: unless-stopped
    env_file: .env
    depends_on:
      - redis
      - postgres
    
  redis:
    image: redis:7-alpine
    restart: unless-stopped
    volumes:
      - redis_data:/data
    command: redis-server --appendonly yes

  postgres:
    image: postgres:15-alpine
    restart: unless-stopped
    environment:
      POSTGRES_DB: secretdate
      POSTGRES_USER: ${DB_USER}
      POSTGRES_PASSWORD: ${DB_PASS}
    volumes:
      - pg_data:/var/lib/postgresql/data

volumes:
  redis_data:
  pg_data:
```

### Option 2: Bare Metal

```bash
# Install system dependencies
sudo apt update && sudo apt install -y python3.11 python3.11-venv redis-server

# Setup
git clone https://github.com/yourusername/secretdate-bot.git
cd secretdate-bot
python3.11 -m venv venv && source venv/bin/activate
pip install -r requirements.txt
cp .env.example .env && nano .env

# Run with systemd
sudo cp deploy/secretdate.service /etc/systemd/system/
sudo systemctl enable --now secretdate
```

### Setting Up Webhook (Production)

For production, **always use webhooks** over polling:

```bash
# Set webhook URL (run once after deployment)
python scripts/set_webhook.py --url https://yourdomain.com/webhook

# Verify webhook is active
python scripts/check_webhook.py
```

---

## ⚙️ Configuration

Full `.env` reference:

```env
# ─── Required ─────────────────────────────────────
BOT_TOKEN=your_telegram_bot_token_from_botfather
BOT_USERNAME=secretdate7123_bot

# ─── Redis ────────────────────────────────────────
REDIS_HOST=localhost
REDIS_PORT=6379
REDIS_PASSWORD=
REDIS_DB=0
SESSION_TTL_HOURS=24          # Auto-expire inactive sessions

# ─── Database (Optional) ──────────────────────────
DATABASE_URL=postgresql+asyncpg://user:pass@localhost/secretdate

# ─── Admin ────────────────────────────────────────
ADMIN_IDS=123456789,987654321  # Comma-separated Telegram user IDs

# ─── Webhook (Production) ─────────────────────────
WEBHOOK_URL=https://yourdomain.com
WEBHOOK_PATH=/webhook
WEBHOOK_PORT=8443

# ─── Moderation ───────────────────────────────────
ENABLE_CONTENT_FILTER=true
MAX_REPORTS_BEFORE_BAN=3
RATE_LIMIT_MESSAGES_PER_MIN=30
RATE_LIMIT_QUEUE_JOINS_PER_HOUR=10

# ─── Features ─────────────────────────────────────
ALLOW_MEDIA=true              # Allow photo/video/voice relay
ALLOW_STICKERS=true
MATCH_BY_LANGUAGE=false       # Experimental: match users by language
QUEUE_TIMEOUT_MINUTES=10      # Auto-remove from queue after N minutes

# ─── Logging ──────────────────────────────────────
LOG_LEVEL=INFO
LOG_FILE=logs/bot.log
```

---

## 🗄️ Database Schema

> Only used when PostgreSQL is enabled for moderation/analytics features.

```sql
-- Users table (minimal footprint by design)
CREATE TABLE users (
    telegram_id     BIGINT PRIMARY KEY,
    first_seen      TIMESTAMP DEFAULT NOW(),
    last_active     TIMESTAMP DEFAULT NOW(),
    is_banned       BOOLEAN DEFAULT FALSE,
    ban_reason      TEXT,
    total_chats     INTEGER DEFAULT 0
);

-- Sessions (historical record, content-free)
CREATE TABLE sessions (
    id              UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    user_a_id       BIGINT REFERENCES users(telegram_id),
    user_b_id       BIGINT REFERENCES users(telegram_id),
    started_at      TIMESTAMP DEFAULT NOW(),
    ended_at        TIMESTAMP,
    ended_by        BIGINT,  -- which user ended it (or NULL if timeout)
    message_count   INTEGER DEFAULT 0
    -- ⚠️ No message content is ever stored
);

-- Reports
CREATE TABLE reports (
    id              UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    reporter_id     BIGINT REFERENCES users(telegram_id),
    reported_id     BIGINT REFERENCES users(telegram_id),
    session_id      UUID REFERENCES sessions(id),
    reason          TEXT,
    created_at      TIMESTAMP DEFAULT NOW(),
    reviewed        BOOLEAN DEFAULT FALSE
);
```

---

## 🛡️ Rate Limiting & Anti-Abuse

SecretDate has a layered defense system:

```
Layer 1: Telegram-side (Bot API limits)
         └── 30 messages/second global hard cap (Telegram enforces)

Layer 2: Redis-based rate limiting (per user)
         ├── 30 messages per minute
         ├── 10 queue joins per hour  
         └── 5 reports per day

Layer 3: Content filtering (if enabled)
         ├── Configurable blocklist (words/phrases)
         ├── Link detection
         └── Phone number detection

Layer 4: Report-triggered moderation
         ├── 3 reports → temp mute (1 hour)
         ├── 5 reports → admin review
         └── Admin ban → permanent (can appeal)
```

### Redis Rate Limit Keys

```
rate:msg:{user_id}          → message count, TTL 60s
rate:queue:{user_id}        → queue join count, TTL 3600s
rate:report:{user_id}       → report count, TTL 86400s
ban:{user_id}               → ban flag, TTL based on ban type
```

---

## ❓ FAQ

**Q: Is this truly anonymous?**  
A: Your identity is never revealed to your chat partner. The server technically processes your Telegram ID to route messages, but we don't log or expose it. For maximum anonymity, use a secondary Telegram account.

**Q: Can I be matched with the same person twice?**  
A: Yes, it's possible — especially in lower-traffic periods. We don't track previous matches to prevent this (that would require storing history).

**Q: What happens if the other person blocks me on Telegram?**  
A: Since the bot is the relay, blocking the other person has no effect on your chat session. You'd need to `/stop` the conversation within the bot.

**Q: Can I send location/contact cards?**  
A: Location sharing is disabled by default to protect privacy. Contact sharing is disabled entirely.

**Q: Is there a message size limit?**  
A: Telegram's standard limits apply — 4096 characters for text, 50MB for files.

**Q: What if no one is in the queue?**  
A: You'll wait until someone joins. The bot checks every 5 seconds and will notify you when matched. You can set a timeout in config.

**Q: Can admins read my messages?**  
A: No. We don't store message content. Admins can only see reports and ban history.

**Q: Is the source code auditable?**  
A: Yes! This is open source. You can verify our privacy claims by reading the code.

---

## 🗺️ Roadmap

### Version 1.1 (Next)
- [ ] **Language-based matching** — optionally match with people who speak the same language
- [ ] **Chat topics** — join themed queues (e.g. `#vent`, `#advice`, `#language-practice`)
- [ ] **Message reactions relay** — forward emoji reactions anonymously
- [ ] **Session timer** — optional auto-end after X minutes

### Version 1.2
- [ ] **Group anonymous chat** — 3-5 strangers in one anonymous group
- [ ] **Anonymous polls** — send quick polls to your partner
- [ ] **Better admin dashboard** — web UI for moderation

### Version 2.0
- [ ] **End-to-end encryption layer** — additional encryption on top of Telegram
- [ ] **Interest-based matching** — match by self-selected tags
- [ ] **Mobile companion app** — standalone app with extra privacy features

---

## 🤝 Contributing

Contributions are warmly welcome! Here's how to get involved:

### Development Setup

```bash
git clone https://github.com/yourusername/secretdate-bot.git
cd secretdate-bot
python -m venv venv && source venv/bin/activate
pip install -r requirements-dev.txt
cp .env.example .env.test
```

### Running Tests

```bash
pytest tests/ -v --cov=bot --cov-report=html
```

### Pull Request Guidelines

1. **Fork** the repo
2. Create a **feature branch**: `git checkout -b feature/my-amazing-feature`
3. Write **tests** for your changes
4. Ensure all tests pass: `pytest`
5. Follow the existing code style (we use `black` + `isort`)
6. Submit a **Pull Request** with a clear description

### Code Style

```bash
black .                    # Format code
isort .                    # Sort imports
flake8 .                   # Lint check
mypy bot/                  # Type check
```

---

## 📊 Stats & Badges

<div align="center">

![GitHub Stars](https://img.shields.io/github/stars/yourusername/secretdate-bot?style=social)
![GitHub Forks](https://img.shields.io/github/forks/yourusername/secretdate-bot?style=social)
![GitHub Issues](https://img.shields.io/github/issues/yourusername/secretdate-bot)
![GitHub Pull Requests](https://img.shields.io/github/issues-pr/yourusername/secretdate-bot)
![Python Version](https://img.shields.io/badge/python-3.10%2B-blue)
![License](https://img.shields.io/badge/license-MIT-green)

</div>

---

## 📜 License

```
MIT License

Copyright (c) 2024 SecretDate Bot

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND...
```

See [LICENSE](./LICENSE) for full text.

---

## 🙏 Acknowledgements

- [python-telegram-bot](https://github.com/python-telegram-bot/python-telegram-bot) — the incredible async Telegram library
- [Telegram Bot API](https://core.telegram.org/bots/api) — for making bots this powerful
- The open-source privacy community — for inspiring this project

---

<div align="center">

**Built BY 🖤K R HARI PRAJWAL  for people who just want to talk.**

[**→ Start Chatting Now ←**](https://t.me/secretdate7123_bot)

*No account. No name. No history. Just conversations.*

---

<sub>SecretDate Bot is open source software. We are not responsible for misuse. By using this bot, users agree to Telegram's Terms of Service and our community guidelines.</sub>

</div>

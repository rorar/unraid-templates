# Unraid Docker Templates

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Unraid Community Applications](https://img.shields.io/badge/Unraid-Community%20Apps-blue.svg)](https://forums.unraid.net/categories/category-45/)
[![GitHub repo size](https://img.shields.io/github/repo-size/rorar/unraid-templates)](https://github.com/rorar/unraid-templates)
[![Contributors](https://img.shields.io/github/contributors/rorar/unraid-templates)](https://github.com/rorar/unraid-templates/graphs/contributors)
[![Last commit](https://img.shields.io/github/last-commit/rorar/unraid-templates/main)](https://github.com/rorar/unraid-templates/commits/main)

Personal collection of Unraid Docker container templates for [Community Applications](https://forums.unraid.net/categories/category-45/).

## Templates

### Vibe Kanban

[![Docker Image Size](https://img.shields.io/docker/image-size/rorar/vibe-kanban-docker/latest)](https://github.com/rorar/vibe-kanban-docker)
[![Docker Pulls](https://img.shields.io/docker/pulls/rorar/vibe-kanban-docker)](https://github.com/rorar/vibe-kanban-docker)
[![GitHub stars](https://img.shields.io/github/stars/rorar/vibe-kanban-docker?style=flat)](https://github.com/rorar/vibe-kanban-docker/stargazers)
[![Vibe Kanban Version](https://img.shields.io/github/v/tag/rorar/vibe-kanban-docker?label=version)](https://github.com/rorar/vibe-kanban-docker/releases)

**Vibe Kanban** - AI-first software development project management tool by [BloopAI](https://github.com/BloopAI/vibe-kanban).

| Template | Description |
|----------|-------------|
| `vibe-kanban.xml` | Main container with AI-powered project management |

#### Features

- **AI-Powered**: Uses AI agents to help manage and track software development tasks
- **GitHub Integration**: Built-in GitHub CLI for repository operations
- **OpenAI Codex**: Includes Codex CLI for AI-assisted development
- **Docker Support**: Docker-in-Docker capability for containerized development
- **Persistent Storage**: All data persists across container restarts

#### Setup Notes

1. The container runs on port **8085** by default
2. Configure volume paths for persistent storage
3. Set git author information for commits
4. Optionally add API keys (GH_TOKEN, OPENAI_API_KEY)

#### Documentation

- [Official Docs](https://vibekanban.com/docs)
- [Self-Hosting Guide](https://vibekanban.com/docs/self-hosting/deploy-docker)
- [Docker Repository](https://github.com/JKamsker/vibe-kanban-docker)

---

### Hermes Agent

[![License](https://img.shields.io/github/license/NousResearch/hermes-agent)](https://github.com/NousResearch/hermes-agent/blob/main/LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/NousResearch/hermes-agent?style=flat)](https://github.com/NousResearch/hermes-agent/stargazers)
[![Last Updated](https://img.shields.io/github/last-commit/NousResearch/hermes-agent/main)](https://github.com/NousResearch/hermes-agent/commits/main)

**Hermes Agent** - A self-improving AI agent built by [Nous Research](https://nousresearch.com).

| Template | Description |
|----------|-------------|
| `hermes-agent.xml` | Main container with messaging gateway, web dashboard, and all platform integrations |

#### Features

- Built-in learning loop — creates skills from experience
- Memory system with persistent context across sessions
- 40+ tools and skill system
- **Messaging platforms**: Telegram, Discord, Slack, WhatsApp, Matrix, Email, Signal, SMS, and more
- Web dashboard for monitoring and control
- Scheduled automations (cron)
- Terminal and code execution

#### Supported Platforms

| Platform | Status |
|----------|--------|
| Matrix | ✅ Full E2EE support |
| Telegram | ✅ |
| Discord | ✅ |
| Slack | ✅ |
| WhatsApp | ✅ |
| Email (IMAP/SMTP) | ✅ |
| Signal | ✅ |
| SMS (Twilio) | ✅ |
| Home Assistant | ✅ |
| Mattermost | ✅ |
| DingTalk | ✅ |
| Feishu / Lark | ✅ |
| WeCom | ✅ |
| And more... | |

#### Setup Notes

1. **Important:** The container uses `--user 0:0` to allow internal permission fixing. The `HERMES_UID` and `HERMES_GID` variables adjust the user to match your Unraid filesystem.
2. Access the **web dashboard** at the same port as the gateway API (default: 8642).
3. Set `MATRIX_ALLOWED_USERS` to restrict who can interact with the bot.

#### Matrix E2EE Notes

For end-to-end encryption with Matrix:
- Set `MATRIX_ENCRYPTION=true`
- Install `libolm-dev` on the host if using rootless Podman
- Set `MATRIX_RECOVERY_KEY` for cross-signing support

---

### WGER (Fitness Tracker)

[![License: AGPL-3.0](https://img.shields.io/badge/License-AGPL--3.0-green.svg)](https://www.gnu.org/licenses/agpl-3.0)
[![GitHub stars](https://img.shields.io/github/stars/wger-project/wger?style=flat)](https://github.com/wger-project/wger/stargazers)
[![Docker Hub](https://img.shields.io/badge/Docker-Hub-blue.svg)](https://hub.docker.com/u/wger)

**WGER** - Self-hosted fitness tracker, workout logger and nutrition calculator.

| Template | Description |
|----------|-------------|
| `my-wger-unraid.xml` | Main WGER application |
| `my-wger-db.xml` | PostgreSQL database |
| `my-wger-redis.xml` | Redis cache |
| `my-wger-nginx.xml` | Nginx reverse proxy |
| `my-wger-celery-worker.xml` | Celery background worker |
| `my-wger-celery-beat.xml` | Celery beat scheduler |
| `my-wger-celery-flower.xml` | Celery monitoring UI |

---

## Installation

### Via Community Applications

1. Go to **Apps** in your Unraid WebUI
2. Search for **Hermes Agent** or **WGER**
3. Click **Install**

### Manual Repository

Add this repository manually:
- **Settings → Docker → Template Repositories**
- Add: `https://raw.githubusercontent.com/rorar/unraid-templates/main/templates`

### Manual Installation

Download the XML file and import via Unraid's Docker page.

---

## Requirements

- Unraid 6.x or later
- Docker plugin installed

---

## Documentation

### Hermes Agent
- [Official Docs](https://hermes-agent.nousresearch.com/docs/)
- [GitHub Repository](https://github.com/NousResearch/hermes-agent)
- [Nous Research Discord](https://discord.gg/NousResearch)

### WGER
- [Official Website](https://wger.de)
- [GitHub Repository](https://github.com/wger-project/wger)

---

## License

MIT License — See individual container images for their respective licenses.

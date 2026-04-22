# Unraid Docker Templates

Personal collection of Unraid Docker container templates for [Community Applications](https://forums.unraid.net/categories/category-45/).

## Templates

### Hermes Agent

**Hermes Agent** - A self-improving AI agent built by [Nous Research](https://nousresearch.com).

| Template | Description |
|----------|-------------|
| `hermes-agent.xml` | Main container with messaging gateway (Telegram, Discord, Slack, WhatsApp, Matrix, Email, etc.) |
| `hermes-dashboard.xml` | Web-based dashboard UI for monitoring and control |

#### Hermes Features

- Built-in learning loop — creates skills from experience
- Memory system with persistent context across sessions
- 40+ tools and skill system
- Multiple messaging platform support
- Scheduled automations (cron)
- Terminal and code execution

#### Hermes Setup Notes

- Requires `HERMES_UID` and `HERMES_GID` to match your Unraid user for proper file permissions
- The container uses `--user 0:0` to allow internal permission fixing
- Matrix support requires additional configuration in the app

---

### WGER (Fitness Tracker)

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

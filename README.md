# Unraid Docker Templates

Personal collection of Unraid Docker container templates for [Community Applications](https://forums.unraid.net/categories/カテゴリー-45/).

## Templates

### Hermes Agent

**Hermes Agent** - A self-improving AI agent built by [Nous Research](https://nousresearch.com).

- **Main Container**: Core Hermes agent with messaging gateway (Telegram, Discord, Slack, etc.)
- **Dashboard**: Web-based dashboard UI for monitoring and control

#### Features

- Built-in learning loop — creates skills from experience
- Memory system with persistent context across sessions
- 40+ tools and skill system
- Multiple messaging platform support
- Scheduled automations (cron)
- Terminal and code execution

## Installation

### Via Community Applications

1. Go to **Apps** in your Unraid WebUI
2. Search for **Hermes Agent**
3. Click **Install**

Or add this repository manually:
- **Settings → Docker → Template Repositories**
- Add: `https://raw.githubusercontent.com/rorar/unraid-templates/main/templates`

### Manual Installation

Download the XML file and import via Unraid's Docker page.

## Requirements

- Unraid 6.x or later
- Docker plugin installed

## Documentation

- [Hermes Agent Docs](https://hermes-agent.nousresearch.com/docs/)
- [Nous Research Discord](https://discord.gg/NousResearch)

## License

MIT License — See individual container licenses for dependencies.

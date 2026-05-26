# Unraid Docker Templates

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Unraid Community Applications](https://img.shields.io/badge/Unraid-Community%20Apps-blue.svg)](https://ca.unraid.net)
[![GitHub repo size](https://img.shields.io/github/repo-size/rorar/unraid-templates)](https://github.com/rorar/unraid-templates)
[![Contributors](https://img.shields.io/github/contributors/rorar/unraid-templates)](https://github.com/rorar/unraid-templates/graphs/contributors)
[![Last commit](https://img.shields.io/github/last-commit/rorar/unraid-templates/main)](https://github.com/rorar/unraid-templates/commits/main)

Docker container templates for [Unraid Community Applications](https://ca.unraid.net).

## Templates

### Immich (Photo & Video Management)

[![GitHub stars](https://img.shields.io/github/stars/immich-app/immich?style=flat)](https://github.com/immich-app/immich/stargazers)
[![Docker Pulls](https://img.shields.io/docker/pulls/altran1502/immich-server)](https://hub.docker.com/r/altran1502/immich-server)

**Immich** - High-performance self-hosted photo and video management with ML-powered search, face recognition, and automatic organization.

| Template | Description |
|----------|-------------|
| `immich-server.xml` | Main server (CPU-only) |
| `immich-server-qsv-vaapi.xml` | Server with Intel QSV / AMD VAAPI transcoding |
| `immich-server-nvenc.xml` | Server with NVIDIA NVENC transcoding |
| `immich-machine-learning.xml` | Machine learning service (CPU) |
| `immich-machine-learning-cuda.xml` | ML with NVIDIA CUDA |
| `immich-machine-learning-rocm.xml` | ML with AMD ROCm |
| `immich-machine-learning-openvino.xml` | ML with Intel OpenVINO |
| `immich-vectorchord-db.xml` | PostgreSQL 18 with VectorChord + pgvector |
| `immich-postgres-official.xml` | Official Immich PostgreSQL image |
| `immich-valkey.xml` | Valkey (Redis-compatible) cache |
| `immich-power-tools.xml` | Advanced library management UI |

#### Setup Notes

1. All Immich containers must be on the same Docker network (`immich_internal`)
2. Storage is split: HDD (Array) for uploads/backups, SSD (Cache) for thumbnails/encoded video
3. Create two Unraid shares before deploying: `immich` (Array) and `immich-gen` (Cache)

#### Documentation

- [Official Docs](https://docs.immich.app)
- [GitHub Repository](https://github.com/immich-app/immich)

---

### Vibe Kanban

[![Docker Image Size](https://img.shields.io/docker/image-size/rorar/vibe-kanban-docker/latest)](https://github.com/rorar/vibe-kanban-docker)
[![Docker Pulls](https://img.shields.io/docker/pulls/rorar/vibe-kanban-docker)](https://github.com/rorar/vibe-kanban-docker)
[![GitHub stars](https://img.shields.io/github/stars/rorar/vibe-kanban-docker?style=flat)](https://github.com/rorar/vibe-kanban-docker/stargazers)

**Vibe Kanban** - AI-first software development project management tool by [BloopAI](https://github.com/BloopAI/vibe-kanban).

| Template | Description |
|----------|-------------|
| `vibe-kanban.xml` | Main container with AI-powered project management |
| `vibe-kanban-cloud.xml` | Cloud edition with Docker-in-Docker (Postgres, ElectricSQL, Caddy) |

#### Setup Notes

1. `vibe-kanban.xml` runs on port **8085** by default
2. `vibe-kanban-cloud.xml` requires **Privileged mode** for its internal Docker daemon

#### Documentation

- [Official Docs](https://vibekanban.com/docs)
- [Self-Hosting Guide](https://vibekanban.com/docs/self-hosting/deploy-docker)
- [Docker Repository](https://github.com/rorar/vibe-kanban-docker)

---

### Hermes Agent

[![License](https://img.shields.io/github/license/NousResearch/hermes-agent)](https://github.com/NousResearch/hermes-agent/blob/main/LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/NousResearch/hermes-agent?style=flat)](https://github.com/NousResearch/hermes-agent/stargazers)

**Hermes Agent** - A self-improving AI agent built by [Nous Research](https://nousresearch.com) with 40+ tools and multi-platform messaging.

| Template | Description |
|----------|-------------|
| `hermes-agent.xml` | Main container with messaging gateway, web dashboard, and all platform integrations |

#### Supported Platforms

Matrix (E2EE), Telegram, Discord, Slack, WhatsApp, Email (IMAP/SMTP), Signal, SMS (Twilio), Home Assistant, Mattermost, and more.

#### Documentation

- [Official Docs](https://hermes-agent.nousresearch.com/docs/)
- [GitHub Repository](https://github.com/NousResearch/hermes-agent)

---

### PhotoMigrator

[![License: GPL-3.0](https://img.shields.io/badge/License-GPL--3.0-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![GitHub stars](https://img.shields.io/github/stars/jaimetur/PhotoMigrator?style=flat)](https://github.com/jaimetur/PhotoMigrator/stargazers)
[![Docker Pulls](https://img.shields.io/docker/pulls/jaimetur/photomigrator)](https://hub.docker.com/r/jaimetur/photomigrator)

**PhotoMigrator** - Migrate between photo services (Google Photos, Synology, Immich, NextCloud, Google Takeout) by [Jaime Tur](https://github.com/jaimetur).

| Template | Description |
|----------|-------------|
| `photomigrator.xml` | Main container with web UI for photo service migration |

#### Documentation

- [GitHub Repository](https://github.com/jaimetur/PhotoMigrator)

---

### WGER (Fitness Tracker)

[![License: AGPL-3.0](https://img.shields.io/badge/License-AGPL--3.0-green.svg)](https://www.gnu.org/licenses/agpl-3.0)
[![GitHub stars](https://img.shields.io/github/stars/wger-project/wger?style=flat)](https://github.com/wger-project/wger/stargazers)

**WGER** - Self-hosted fitness tracker, workout logger and nutrition calculator.

| Template | Description |
|----------|-------------|
| `wger-server.xml` | Main WGER application server |
| `wger-db.xml` | PostgreSQL database |
| `wger-redis.xml` | Redis cache and Celery broker |
| `wger-nginx.xml` | Nginx reverse proxy |
| `wger-celery-worker.xml` | Celery background worker |
| `wger-celery-beat.xml` | Celery beat scheduler |
| `wger-celery-flower.xml` | Celery monitoring UI |

#### Setup Notes

1. All containers must be on the same Docker network (`wger_network`)
2. Change the dummy `SECRET_KEY` and `SIGNING_KEY` in all containers before use

#### Documentation

- [Official Website](https://wger.de)
- [GitHub Repository](https://github.com/wger-project/wger)

---

## Installation

### Via Community Applications

1. Go to **Apps** in your Unraid WebUI
2. Search for the app name
3. Click **Install**

### Manual Repository

Add this repository manually:
- **Settings -> Docker -> Template Repositories**
- Add: `https://raw.githubusercontent.com/rorar/unraid-templates/main/templates`

---

## License

MIT License -- See individual container images for their respective licenses.

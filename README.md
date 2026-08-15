# 🚀 StackForge

<div align="center">

## ⚡ Radarr · Sonarr · Plex · Jellyfin · Traefik — wired, validated, deployed.

### Stop hand-editing YAML. Stop chasing broken *arr API paths. Get a production-ready media stack in minutes.

**Hosted wizard · Docker Compose · Auto-wiring for Home Lab operators**

<br>

[![Launch StackForge](https://img.shields.io/badge/Open_Wizard-→_stackforge.tannerap.ch-22c55e?style=for-the-badge&logo=docker&logoColor=white)](https://stackforge.tannerap.ch)
[![Preview stack](https://img.shields.io/badge/Live_Preview-Compose_+_Sandbox-0ea5e9?style=for-the-badge)](https://stackforge.tannerap.ch)

<br>

![StackForge Demo](docs/assets/demo.gif)

<br>

**[stackforge.tannerap.ch](https://stackforge.tannerap.ch)** — configure your stack in the browser. Deploy to your NAS, server, or workstation.

*We host the platform. Your containers run on your metal.*

</div>

---

## 😤 The pain StackForge removes

If you have ever stood up a media stack from scratch, you know the drill:

| Without StackForge | With StackForge |
|---|---|
| Copy-paste `docker-compose.yml` fragments from five forum threads | One wizard → one validated Compose bundle |
| Manually wire **Radarr ↔ Sonarr ↔ Prowlarr ↔ download clients** in each UI | Download clients, categories, and root folders pre-connected *(Premium)* |
| Hunt down why **remote path mappings** do not match `/downloads` | Consistent paths across SABnzbd, NZBGet, qBittorrent, and *arr |
| Debug **Traefik** labels, networks, and TLS for every service | Edge routing and TLS templates generated for you |
| Rebuild **quality profiles & custom formats** after every Radarr/Sonarr update | Battle-tested WEB\|Bluray ladders and CF scoring — provisioned via API *(Premium)* |
| Fix init scripts that call the wrong **API endpoint or auth header** | Init sidecars tested against real Radarr/Sonarr OpenAPI contracts |
| Maintain a dozen `.env` files and secret placeholders by hand | Generated `.env`, secrets, and `setup.sh` in one export *(Premium)* |

> **No more YAML archaeology.** StackForge turns weeks of fragile copy-paste into a guided flow — from service selection to a stack that actually boots wired.

---

## 🧱 What you configure (explicit integrations)

StackForge speaks the tools Home Lab admins already run:

| Layer | Services |
|-------|----------|
| **Edge & TLS** | [Traefik](https://traefik.io) — reverse proxy, Host rules, optional Cloudflare DNS |
| **Movies & TV** | [Radarr](https://radarr.video) · [Sonarr](https://sonarr.tv) · optional 4K split instances |
| **Music** | [Lidarr](https://lidarr.audio) |
| **Indexers** | [Prowlarr](https://prowlarr.com) — central indexer management for all *arr apps |
| **Requests** | [Seerr](https://github.com/seerr-team/seerr) · [Maintainerr](https://github.com/Maintainerr/Maintainerr) |
| **Playback** | [Plex](https://plex.tv) · [Jellyfin](https://jellyfin.org) — hardware transcoding options included |
| **Usenet** | [SABnzbd](https://sabnzbd.org) · [NZBGet](https://nzbget.net) |
| **Torrents** | [qBittorrent](https://www.qbittorrent.org) |
| **Quality** | Custom formats, cutoff scores, language filters — pushed into Radarr/Sonarr via API *(Premium)* |

Toggle what you need. Dependencies, networks, and init order stay consistent.

---

## 🏗️ Architecture at a glance

```
┌─────────────────────────────────────────────────────────────────┐
│  stackforge.tannerap.ch  (hosted by us — you don't clone this)  │
│  ┌──────────────┐    ┌─────────────────────────────────────┐    │
│  │ Visual       │───▶│ Compose generator + quality engine  │    │
│  │ wizard UI    │    │ (Traefik, *arr, downloads, media)   │    │
│  └──────────────┘    └─────────────────────────────────────┘    │
│         │                          │                            │
│         │ Free: preview + export   │ Premium: full bundle       │
│         ▼                          ▼                            │
│   docker-compose.yml         .env · setup.sh · init sidecars      │
│   (basic export)             · auto-wiring · quality provision  │
└──────────────────────────────┬──────────────────────────────────┘
                               │ deploy to YOUR hardware
                               ▼
┌─────────────────────────────────────────────────────────────────┐
│  Your Home Lab (NAS / server / workstation)                     │
│                                                                 │
│  Traefik ──▶ Plex/Jellyfin                                      │
│     │                                                           │
│     ├── Radarr ── Sonarr ── Lidarr ── Prowlarr                  │
│     │       │        │                                          │
│     │       └────────┴── SABnzbd / NZBGet / qBittorrent         │
│     └── TLS termination · Host routing · Docker networks        │
└─────────────────────────────────────────────────────────────────┘
```

**Centrally hosted platform, locally deployed stack.** Open [stackforge.tannerap.ch](https://stackforge.tannerap.ch) — no `git clone`, no self-hosting StackForge. Your libraries and media never leave your network.

---

## ✨ Why operators choose StackForge

| Capability | Detail |
|------------|--------|
| **🚀 Compose in minutes** | Point-and-click wizard → validated `docker-compose.yml` with correct images, networks, and volume mounts |
| **🔌 Auto-wiring** *(Premium)* | Radarr/Sonarr download clients, Prowlarr app links, remote path mappings, and root folders — connected before first import |
| **🧠 Quality intelligence** *(Premium)* | WEB\|Bluray tiers, custom formats, min-format scores — provisioned directly via Radarr/Sonarr API, not hand-copied JSON |
| **🛡️ Contract-tested inits** | Init sidecars aligned with real *arr OpenAPI — fewer 400/401 surprises on `Library/VirtualFolders`, quality profiles, and auth headers |
| **🧪 Live sandbox** *(Premium)* | Spin up a disposable demo stack on our infrastructure before you commit to your Home Lab |
| **📦 Export you own** | YAML, `.env`, Traefik config, and setup scripts — run `docker compose up` on hardware you control |

---

## 💎 Free vs Premium

| | **Free** | **Premium** |
|---|---|---|
| Hosted wizard at [stackforge.tannerap.ch](https://stackforge.tannerap.ch) | ✅ | ✅ |
| Live Compose preview | ✅ | ✅ |
| Basic `docker-compose.yml` export | ✅ | ✅ |
| Self-hosting StackForge | ❌ — we host it | ❌ — we host it |
| Full auto-wiring (Radarr, Sonarr, Prowlarr, downloads) | — | ✅ |
| Quality profiles & custom formats via API | — | ✅ |
| `.env`, Traefik, `setup.sh`, init sidecars | — | ✅ |
| Managed sandbox preview | — | ✅ |
| Early Access / Beta Services (Tdarr, CrowdSec, etc.) | ❌ | ✅ |

> **Free** — design and export; finish wiring yourself.  
> **Premium** — full automation unlocked on our platform, deployed to your metal.

---

## 🎯 Get started — 2 minutes to a wired stack

<div align="center">

### 1. Open the wizard → 2. Pick Radarr, Sonarr, Plex, Traefik & co. → 3. Deploy on your Home Lab

<br>

[![Configure your media stack now](https://img.shields.io/badge/Configure_Your_Media_Stack-→_stackforge.tannerap.ch-22c55e?style=for-the-badge&logo=docker&logoColor=white)](https://stackforge.tannerap.ch)

<br>

*No YAML rabbit holes. No broken *arr wiring. Just a solid Plex/Radarr/Sonarr stack — yours.*

</div>

---

## 🛠️ Developers

> *This repository serves as the public documentation, issue tracker, and community hub for StackForge. To request features or report bugs, please open an issue.*

<p align="center">
  <sub><a href="https://stackforge.tannerap.ch">stackforge.tannerap.ch</a> · <a href="https://github.com/tannerap/StackForge">GitHub</a></sub>
</p>

# 🍊 Orange Pi 4 Pro Homelab

A reproducible Docker-based homelab running on an **Orange Pi 4 Pro** with **Debian**.

The main goal of this project is to make my server easy to rebuild after a fresh OS installation. By keeping every Docker Compose stack under version control and storing persistent data on a dedicated HDD, I can restore my homelab quickly and reliably.

This repository documents the evolution of my self-hosted infrastructure as I continue adding services and improving the setup.

---

# 🚀 Services

| Service     |          Status          |
| ----------- | :----------------------: |
| Jellyfin    |         ✅ Running        |
| qBittorrent |         ✅ Running        |
| Navidrome   |         ✅ Running        |
| Pi-hole     |         ✅ Running        |
| Ghost       | 🚧 Migration in progress |
| VPN         | 🚧 Migration in progress |

More services will be added over time.

---

# 📂 Repository Structure

```text
stacks/
```

Docker Compose files for each service.

```text
appdata/
```

Persistent application data stored on the HDD.

> **Note:** `appdata` is intentionally excluded from this repository because it contains user data and service configuration.

---

# 💾 Storage Layout

```text
/mnt/media
├── docker
│   ├── appdata
│   └── stacks
├── downloads
├── movies
├── music
└── series
```
## 🏗 Architecture

```text
                Internet
                    │
                    ▼
          Orange Pi 4 Pro (Debian)
                    │
        ┌───────────┴───────────┐
        │                       │
    Docker Engine         Persistent Data
        │                  (/mnt/media/docker/appdata)
        │
        ├── Jellyfin
        ├── qBittorrent
        ├── Navidrome
        ├── Pi-hole
        ├── Ghost (WIP)
        └── Tinc VPN (WIP)
```

All media libraries and application data are stored on the HDD, while only the operating system remains on the SD card. This approach reduces SD card wear and makes the server easier to recover after a fresh installation.

---

# 🛠 Deployment

Clone the repository:

```bash
git clone git@github.com:jrodsan/orangepi-homelab.git
```

Go to the desired stack:

```bash
cd stacks/jellyfin
```

Start the service:

```bash
docker compose up -d
```

Some services require additional environment variables. Copy the example file before starting the stack:

```bash
cp .env.example .env
```

Then edit the `.env` file with your own values.

---

# 🎯 Project Goals

* Build a reproducible homelab.
* Store persistent data on the HDD instead of the SD card.
* Keep every Docker Compose stack under version control.
* Avoid unnecessary complexity.
* Document the infrastructure as it evolves.

---

# 🗺 Roadmap

## Infrastructure

* [x] Move Docker data from the SD card to the HDD.
* [x] Organize Docker Compose stacks.
* [x] Version control the infrastructure with GitHub.
* [ ] Document every service.
* [ ] Automate backups.
* [ ] Add monitoring.
* [ ] Automatic container updates.

## Future Services

* [ ] Finish Ghost migration.
* [ ] Finish Tinc VPN migration.
* [ ] Homepage Dashboard.
* [ ] Immich.

---

# 🖥 Hardware

* Orange Pi 4 Pro
* Debian
* Docker
* Docker Compose

---

# 📄 License

This project is licensed under the MIT License.


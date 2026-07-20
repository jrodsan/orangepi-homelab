# Orange Pi 4 Pro Homelab

A reproducible Docker-based homelab running on an Orange Pi 4 Pro with Debian.

The goal of this repository is to make rebuilding the server as simple as possible after a fresh OS installation.

## Current services

| Service | Status |
|----------|--------|
| Jellyfin | ✅ |
| qBittorrent | ✅ |
| Navidrome | ✅ |
| Pi-hole | ✅ |

More services will be added over time.

---

## Project structure

```
stacks/
```

Contains every Docker Compose stack.

```
appdata/
```

Contains persistent application data.

**appdata is intentionally NOT part of this repository.**

---

## Storage layout

```
/mnt/media
├── docker
│   ├── appdata
│   └── stacks
├── downloads
├── movies
├── music
└── series
```

---

## Deploy

Clone the repository.

```bash
git clone https://github.com/jrodsan/orangepi-homelab
```

Navigate to a stack.

```bash
cd stacks/jellyfin
```

Start the service.

```bash
docker compose up -d
```

---

## Philosophy

- Simple
- Reproducible
- Easy to maintain
- No Docker GUI
- Configuration stored on HDD instead of the SD card

---

## Hardware

- Orange Pi 4 Pro
- Debian
- Docker
- Docker Compose

---

## License

MIT

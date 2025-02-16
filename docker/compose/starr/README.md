# Starr Media Stack

A Docker Compose configuration for running a complete media automation stack behind a VPN.

## Services

- **Gluetun**: VPN client container that handles all external traffic
- **Sonarr**: TV shows management and automation
- **Radarr**: Movie management and automation
- **Prowlarr**: Indexer manager
- **Bazarr**: Subtitle management
- **qBittorrent**: Torrent client

## Prerequisites

- Docker and Docker Compose installed
- Volume paths set up:
  - `/volume1/Media/TV` for TV shows
  - `/volume1/Media/Movies` for movies
  - `/volume1/docker/starr/` for service configurations

## Configuration

1. Copy `.env.example` to `.env` and configure:
   - WireGuard VPN settings

2. All services run through the Gluetun VPN container for security

## Ports

- Gluetun:
  - 8888: HTTP proxy
  - 8388: Shadowsocks (TCP/UDP)
- Media Services:
  - 8090: qBittorrent Web UI
  - 8989: Sonarr Web UI
  - 7878: Radarr Web UI
  - 9696: Prowlarr Web UI
  - 6767: Bazarr Web UI


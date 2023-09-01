# All-In-One Media Server with Docker

This repository provides a Docker Compose configuration for setting up a comprehensive media server environment using Docker containers. The configuration includes various media management tools such as Plex, Sonarr, Radarr, Bazarr, Overseerr, Tautulli, Flaresolverr, VPN for secure network connectivity, Netdata for system monitoring, and Watchtower for automatic container updates.

## Table of Contents

- [All-In-One Media Server with Docker](#all-in-one-media-server-with-docker)
  - [Table of Contents](#table-of-contents)
  - [Prerequisites](#prerequisites)
  - [Getting Started](#getting-started)
  - [Services Included](#services-included)
  - [Customization](#customization)
  - [Configuring Services](#configuring-services)
    - [Bazarr](#bazarr)
    - [Overseerr](#overseerr)
    - [Plex](#plex)
    - [Prowlarr](#prowlarr)
    - [Radarr](#radarr)
    - [Sonarr](#sonarr)
    - [Tautulli](#tautulli)
    - [Portainer](#portainer)
    - [VPN](#vpn)
    - [Flaresolverr](#flaresolverr)
    - [Deluge](#deluge)
    - [Netdata](#netdata)
    - [Watchtower](#watchtower)
  - [Notes](#notes)
  - [License](#license)

## Prerequisites

- A VPN service (I use [NordVPN](https://nordvpn.com/))
- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

## Getting Started

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/izm20/all-in-one-media-server.git
   cd all-in-one-media-server
   ```

2. Customize the `.env` file with your configuration:

   Before you start using the Docker Compose setup, make sure to configure the `.env` file to match your environment and preferences. Here's a breakdown of the variables you can set in the `.env` file:

   #### General Configuration

   - `PUID`: 0
   - `PGID`: 0
   - `TZ`: Your desired timezone (e.g., `"America/New_York"`).

   #### Media and Configuration Directories

   - `MEDIADIR`: Path to your media directory where your media files are located.
   - `CONFIGDIR`: Path to your configuration directory where your tool configurations will be stored.

   #### Plex Configuration

   - `PLEX_PUID`: UID of the user for Plex.
   - `PLEX_PGID`: GID of the group for Plex.
   - `PLEXMEDIA`: Path to your Plex libraries.
   - `PLEX_ADVERTISE_IP`: URL for Plex server access.

  #### Plex Configuration

   - `ORGANIZR_PUID`: UID of the user for Organizr.
   - `ORGANIZR_PGID`: GID of the group for Organizr.

   #### Flaresolverr Configuration

   - `CAPTCHA_SOLVER`: Type of CAPTCHA solver to use (e.g., `"hcaptcha-solver"`).

   #### VPN Configuration

   - `VPN_SERVICE_PROVIDER`: Your VPN provider's name.
   - `OPENVPN_USER`: Encrypted username for VPN.
   - `OPENVPN_PASSWORD`: Encrypted password for VPN.
   - `SERVER_REGIONS`: Desired server regions for VPN.
   - `VPN_TYPE`: Type of VPN service to use (e.g., `"wireguard"`, `"openvpn"`).

   Refer to the [gluetun GitHub repository](https://github.com/qdm12/gluetun) for more information on configuring the VPN service.

   Make sure to replace the placeholders (`<...>`) with your actual values.

   **Note**: Be cautious with sensitive information like passwords and encrypted credentials in the `.env` file. Keep it secure and never share it publicly.

3. Configure Services:

   - Open `docker-compose.yml` and adjust the environment variables, volumes, ports, etc., for each service as needed.

4. Start the Containers:

   ```bash
   docker-compose up -d
   ```

## Services Included

- **Plex**: Media server.
- **Prowlarr**: Indexer manager for Sonarr & Radarr.
- **Radarr**: Movie search agent.
- **Sonarr**: TV show search agent.
- **Bazarr**: Subtitle grabber.
- **Overseerr**: Media requesting tool.
- **Tautulli**: Plex monitoring.
- **VPN**: Secure network connectivity.
- **Deluge**: Torrent downloader.
- **Flaresolverr**: DNS resolver for CAPTCHA bypass.
- **Portainer**: Container management.
- **Netdata**: System monitoring.
- **Watchtower**: Automatic container updates.
- **Organizr**: A customized homepage for your services.

## Customization

- Each service's configuration can be modified in the `docker-compose.yml` file.
- Adjust environment variables, volumes, ports, etc., to meet your requirements.

## Configuring Services

### Bazarr

- Access Bazarr web UI at http://localhost:6767.
- Configure your preferred subtitle download providers.
- Set up movie and TV show libraries to automatically fetch subtitles.

### Overseerr

- Access Overseerr web UI at http://localhost:5055.
- Set up your media requests and integration with other services.

### Plex

- Access Plex web UI at http://localhost:32400/web.
- Sign in or create a Plex account.
- Add libraries for your media content.

### Prowlarr

- Access Prowlarr web UI at http://localhost:9696.
- Configure indexers for Sonarr and Radarr.

### Radarr

- Access Radarr web UI at http://localhost:7878.
- Add movies to your library and configure your download client.

### Sonarr

- Access Sonarr web UI at http://localhost:8989.
- Add TV shows to your library and configure your download client.

### Tautulli

- Access Tautulli web UI at http://localhost:8181.
- Configure Plex monitoring and notifications.

### Portainer

- Access Portainer web UI at http://localhost:9000.
- Manage and monitor your Docker containers with ease.

### VPN

- Connects your services securely to the VPN network.

### Flaresolverr

- Access Flaresolverr configuration via http://localhost:8191.
- Configure CAPTCHA solving options for various services.
- Now this service is under the VPN network.

### Deluge

- Access Deluge web UI at http://localhost:8112.
- Set up your download directories and preferences.
- Now this service is under the VPN network.

### Organizr

- Access Organizr web UI at http://localhost:9983.
- Configure Organizr to access and manage all your media server tools in one place.

### Netdata

- Access Netdata web UI at http://localhost:19999.
- Monitor system performance and resource usage in real-time.

### Watchtower

- Watchtower is responsible for automatic container updates.
- Configuration options for Watchtower can be found in the `docker-compose.yml` file under the `watchtower` service.
- By default, Watchtower is scheduled to check for updates every Sunday at 4:00 AM (00:00:00 UTC on Sundays). You can adjust the schedule as needed.

## Notes

- Keep sensitive information (e.g., tokens, passwords) secure in the `.env` file.
- This setup is extensible and can be further customized to fit your needs.

## License

This project is licensed under the [MIT License](LICENSE).

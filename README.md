# Media Server Docker Compose Setup

This repository provides a Docker Compose configuration for setting up a comprehensive media server environment using Docker containers. The configuration includes various media management tools such as Plex, Sonarr, Radarr, NZBGet, Bazarr, Flaresolverr, and more.

## Table of Contents

- [Media Server Docker Compose Setup](#media-server-docker-compose-setup)
  - [Table of Contents](#table-of-contents)
  - [Prerequisites](#prerequisites)
  - [Getting Started](#getting-started)
  - [Services Included](#services-included)
  - [Customization](#customization)
  - [Configuring Services](#configuring-services)
    - [Bazarr](#bazarr)
    - [Flaresolverr](#flaresolverr)
    - [Deluge](#deluge)
    - [NZBGet](#nzbget)
    - [Overseerr](#overseerr)
    - [Plex](#plex)
    - [Prowlarr](#prowlarr)
    - [Radarr](#radarr)
    - [Sonarr](#sonarr)
    - [Tautulli](#tautulli)
  - [Notes](#notes)
  - [License](#license)

## Prerequisites

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

## Getting Started

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/izm20/docker-media-server.git
   cd docker-media-server
   ```

2. Customize the `.env` file with your configuration:

   - Set `PUID` and `PGID` to your user and group IDs (to match permissions).
   - Set `TZ` to your desired timezone.
   - Define `MEDIADIR` and `PLEXMEDIA` paths for your media and Plex libraries.
   - Set `PLEX_CLAIM`, `PLEX_PASS`, and `PLEX_ADVERTISE_IP` for Plex configuration.

3. Configure Services:

   - Open `docker-compose.yml` and adjust the environment variables, volumes, and ports for each service as needed.

4. Start the Containers:

   ```bash
   docker network create media
   docker-compose -p "media" up -d
   ```

## Services Included

- **Bazarr**: Subtitle grabber.
- **Flaresolverr**: DNS resolver for CAPTCHA bypass.
- **Deluge**: Torrent downloader.
- **NZBGet**: Usenet download agent.
- **Overseerr**: Media requesting tool.
- **Plex**: Media server.
- **Prowlarr**: Indexer manager for Sonarr & Radarr.
- **Radarr**: Movie search agent.
- **Sonarr**: TV show search agent.
- **Tautulli**: Plex monitoring.

## Customization

- Each service's configuration can be modified in the `docker-compose.yml` file.
- Adjust environment variables, volumes, ports, etc., to meet your requirements.

## Configuring Services

### Bazarr

- Access Bazarr web UI at http://localhost:6767.
- Configure your preferred subtitle download providers.
- Set up movie and TV show libraries to automatically fetch subtitles.

### Flaresolverr

- Access Flaresolverr configuration via http://localhost:8191.
- Configure CAPTCHA solving options for various services.

### Deluge

- Access Deluge web UI at http://localhost:8112.
- Set up your download directories and preferences.

### NZBGet

- Access NZBGet web UI at http://localhost:6789.
- Configure your Usenet servers and download preferences.

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

## Notes

- Keep sensitive information (e.g., tokens, passwords) secure in the `.env` file.
- This setup is extensible and can be further customized to fit your needs.

## Tutorial Reference

This repository was inspired by the tutorial: [All-In-One Media Server with Docker](https://academy.pointtosource.com/containers/all-in-one-media-server-docker/). In this tutorial, you can find detailed instructions on how to configure each tool.

## License

This project is licensed under the [MIT License](LICENSE).

This updated README includes detailed instructions on how to configure each tool within the Docker Compose setup. Make sure to customize the configuration for each tool according to your needs.

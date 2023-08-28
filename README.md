# All-In-One Media Server with Docker

This repository provides a Docker Compose configuration for setting up a comprehensive media server environment using Docker containers. The configuration includes various media management tools such as Plex, Sonarr, Radarr, NZBGet, Bazarr, Flaresolverr, and more.

## Table of Contents

- [All-In-One Media Server with Docker](#all-in-one-media-server-with-docker)
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
    - [Portainer (Optional)](#portainer-optional)
    - [Jackett (Optional)](#jackett-optional)
    - [Ombi (Optional)](#ombi-optional)
  - [Notes](#notes)
  - [Tutorial Reference](#tutorial-reference)
  - [License](#license)

## Prerequisites

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

## Getting Started

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/izm20/all-in-one-media-server.git
   cd all-in-one-media-server
   ```

2. Customize the `.env` file with your configuration:

   - Only change `PUID` and `PGID` to your user and group IDs if is neccessary.
   - Set `PLEX_PUID` and `PLEX_PGID` to your user and group IDs.
   - Set `TZ` to your desired timezone.
   - Define `MEDIADIR`, `PLEXMEDIA` and `CONFIGDIR` paths for your media, Plex libraries and docker apps config.
   - Set `PLEX_CLAIM`, `PLEX_PASS`, and `PLEX_ADVERTISE_IP` for Plex configuration.

3. Configure Services:

   - Open `docker-compose.yml` and adjust the environment variables, volumes, ports, etc., for each service as needed.

4. Start the Containers:

   ```bash
   docker-compose up -d
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

-

 Access Tautulli web UI at http://localhost:8181.
- Configure Plex monitoring and notifications.

### Portainer (Optional)

- Access Portainer web UI at http://localhost:9000.
- Manage and monitor your Docker containers with ease.

### Jackett (Optional)

- Configure Jackett indexers for enhanced content searching.

### Ombi (Optional)

- Set up Ombi to allow users to request media content.

## Notes

- Keep sensitive information (e.g., tokens, passwords) secure in the `.env` file.
- This setup is extensible and can be further customized to fit your needs.

## Tutorial Reference

This repository was inspired by the tutorial: [All-In-One Media Server with Docker](https://academy.pointtosource.com/containers/all-in-one-media-server-docker/). In this tutorial, you can find detailed instructions on how to configure each tool.

## License

This project is licensed under the [MIT License](LICENSE).

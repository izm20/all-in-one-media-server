# Media Server Docker Compose Setup

This repository provides a Docker Compose configuration for setting up a comprehensive media server environment using Docker containers. The configuration includes various media management tools such as Plex, Sonarr, Radarr, NZBGet, Bazarr, Flaresolverr, and more.

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

## Usage

- Access services via their respective ports (e.g., Plex at <http://localhost:32400>).
- Follow service documentation to configure and manage your media library.

## Notes

- Keep sensitive information (e.g., tokens, passwords) secure in the `.env` file.
- This setup is extensible and can be further customized to fit your needs.

## License

This project is licensed under the [MIT License](LICENSE).

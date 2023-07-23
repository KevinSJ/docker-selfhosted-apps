## Wallabag

[Wallabag Home Page](https://wallabag.org)
[Wallabag GitHub Repo](https://github.com/wallabag/wallabag/tree/master)

Wallabag is a self-hosted application for saving links and article. It's a free and open source replacement for Pocket.

This folder is an attempt to self-host Wallabag using Docker-compose. The wallabag will be behind Traefik proxy.

### Folder structure
- wallabag
 |
 |- docker-compose.yaml -- Docker compose file
 |- .env.example        -- Example environment file

### How to
- To run Wallabag as a container behind Traefik proxy, first fill in the required environment variables in .env.example file
- You would need to start Traefik proxy first, and then start the Wallabag container.
- Start Docker container: `docker compose up`

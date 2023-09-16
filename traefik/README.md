# Traefik configuration

- [Traefik Home Page](https://traefik.io/traefik/)

- [Traefik GitHub Repo](https://github.com/traefik/traefik)

### Folder structure
```
traefik/
├── docker-compose.yaml
├── .env.example
├── README.md
└── traefik.toml
```
### Why
- Traefik works almost seamlessly with Docker, making it easy to run every app through Docker
- Traefik can be configured through both dynamic and static configuration, this folder demonstrates both **dynamic** and **static** configuration

### How
To use Traefik proxy in this folder, you would need to first create `.env` file first.
Copy `.env.example` to `.env`, and configure the variables.

Keep the following rules in mind when you configure those variables:
- All of the environment variables can be omitted. If that's the case, the variables will be set to empty string by Docker compose.
- Please see the comment in the file for what these variables are used for.
- Variables:
    - **GLOBAL_HTTPS_REDIRECT**: decides if the http to https middleware is enabled. If this is set to true, all the http traffic will be redirect to https
    - **DASHBOARD_DOMAIN**: Domain for Traefik dashboard. If this is set, Traefik dashboard will be enabled (***NEED TO BE USED IN CONJUNCTION WITH DASHBOARD_AUTH***)
    - **DASHBOARD_AUTH**: Basic auth to protect for Traefik dashboard. Need to be hashed password generated from htpassword. If this is set, Traefik dashboard will be protected.(***NEED TO BE USED IN CONJUNCTION WITH DASHBOARD_DOMAIN***)

Once this is done, you can start the Traefik container as follows:
```bash
docker-compose up -d --force-recreate && docker-compose logs -f
```

Go to the domain you set for your dashboard to verify if it's there. 

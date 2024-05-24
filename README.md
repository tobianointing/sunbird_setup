## Setup code for sunbird

### My Docker Resources settings:
- CPU: 4 cores 
- RAM: 6 GB
- Disk: 120 GB

clone the repo 

if you are not using macros, go to docker-compose.yml file and replace the keycloak image with: 
```
ghcr.io/sunbird-rc/sunbird-rc-keycloak:latest
```

```
docker compose down
```

create a .env file and copy what is in the .env.example into it.

```
bash setup_vault_override.sh docker-compose.yml vault
```

Spin up the needed services

```
docker compose up -d db
docker compose up -d credential
docker compose up -d keycloak
docker compose up -d es
docker compose up -d registry 
```

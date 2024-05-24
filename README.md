## Setup code for sunbird

clone the repo 

go to docker-compose.yml file and replace the keycloak image with: 
```
ghcr.io/sunbird-rc/sunbird-rc-keycloak:latest
```
if you are not using macros.

```
docker compose down
```

create a .env file and ask me for the content to paste there.

```
bash setup_vault.sh docker-compose.yml vault
```

Spin up the needed services

```
docker compose up -d db
docker compose up -d credential
docker compose up -d keycloak
docker compose up -d es
docker compose up -d registry 
```

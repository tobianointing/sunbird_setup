## Setup code for sunbird

```
docker compose down
```

Download setup_vault.sh vault.json from rc.sunbird.org github

```
bash setup_vault.sh docker-compose.yml vault
```

```
docker compose up -d vault

docker compose ps
```

This is for unsealing the vault making it healthy. run this for 3 different keys in the key.txt file.

```
docker compose exec -T vault vault operator unseal “$key”
```

This is require one time. you can take the VAULT_TOKEN from the key.txt file. (it is called Initial Root Token)

```
docker compose exec -e VAULT_TOKEN=hvs.rYK3m9LpKHxNfsAWdHvDDgzB -T vault vault secrets enable -path=kv kv-v2
```

Spin the needed services

```
docker compose up -d keycloak es registry claim-ms credential
```

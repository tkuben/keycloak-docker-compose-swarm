Keycloak Identity Management - Docker Compose
====

This repository is a reference place for quickly getting started with Keycloak.

* A docker-compose file to start KeyCloak and Postgres in a dockerised fashion
* Docker Volume based Keycloak theme mounting
* Docker Swarm Secrets to store passwords
* SSL configuration to allow to serve keycloak via https
* Custom Theming option

Getting Started
=====

Docker swarm will bring up all the services needed.
```
docker stack deploy --compose-file docker-compose.yml keycloak
```

### Database

Keycloak supports many database backend. In this demo, we are using Postgres.

### Themes

Keycloak supports themes for the web application. Our custom themes are maintained in themes directory.

### Secrets

When deploying through swarm using docker stack apply, you'll need to have these secrets created ahead of time. 

```
echo "admin" | docker secret create keycloak_user -
echo "letmein" | docker secret create keycloak_password -
echo "db_user" | docker secret create keycloak_db_user -
echo "letmein" | docker secret create keycloak_db_password -
```

If you are using docker-compose locally, it will read from the docker-compose.override.yml file which contains local files of password vs using the secrets Raft db. 


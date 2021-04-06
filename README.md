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
docker swarm deploy -f docker-compose.yml keycloak
```

### Database

Keycloak supports many database backend. In this demo, we are using Postgres.

### Themes

Keycloak supports themes for the web application. Our custom themes are maintained in themes directory.


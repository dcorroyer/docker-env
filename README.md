# Dockerized php app setup with https

### Prerequisites

You need to have:

- __Docker__ and __Docker Compose__ installed on your computer.
- Your __SSH Keys__ configured on your __Gitea__ settings
- __Mkcert__ installed on your computer

### Installation

First step, clone the project on your computer

    git clone git@github.com:dcorroyer/repository-name.git src

You need to create mkcert keys in the __/docker/nginx__ directory:

    mkcert -key-file app.key.pem -cert-file app.cert.pem app.local
    mkcert -install

A shell script is used to set up the docker containers and de project,
it also write the url __app.local__ in your __/etc/hosts__:

run command:

    ./install

### Others

A `Makefile` is up to provide some useful commands:

    make up <=> docker-compose up -d

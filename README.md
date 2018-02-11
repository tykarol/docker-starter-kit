# Docker

Apache2, PHP5, MySQL, Adminer, NodeJS, Supervisor

## Commands

- `docker-compose up` - run
- `docker-compose up -d` - run in the background
- `docker-compose up --force-recreate --remove-orphans` - recreate containers and remove not defined containers
- `docker-compose exec [container] bash` - enter to container
- `docker-compose exec [container] [command]` - run command in container

### Generate a Self-Signed Certificate:

- `openssl req -newkey rsa:2048 -nodes -keyout docker/cert/cert.key -x509 -days 365 -out docker/cert/cert.crt`

## Configuration

You can create the `.env` file to overwrite values from `.env.default`.

You can also change the files in `docker` folder.

The application files are in the `app` folder.

## Before first run

Before first run you should:

- generate the new self-signed certificate
- override values from `.env.default` to `.env`
- also you can change configuration in the `docker/*.ini` and `docker/*.conf` files

## Run

- run containers: `docker-compose up`
- open app: [127.10.0.1](https://127.10.0.1/)
- open adminer: [127.10.0.1:8080](https://127.10.0.1:8080/)
- enter to the `application` container: `docker-compose exec application bash`

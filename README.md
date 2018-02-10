# Docker

Apache2, PHP5, MySQL, Adminer, NodeJS, Supervisor

## Commands

- `docker-compose up` - run
- `docker-compose up -d` - run in the background
- `docker-compose up --force-recreate --remove-orphans` - recreate containers and remove not defined containers
- `docker-compose exec [container] bash` - enter to container
- `docker-compose exec [container] [command]` - run command in container

## Configuration

You can change the IP addres in `.env` file.

You can also change the files in `docker` folder.

The application files are in the `app` folder.

## Run

- run containers: `docker-compose up`
- open app: [127.10.0.1](https://127.10.0.1/)
- open adminer: [127.10.0.1:8080](https://127.10.0.1:8080/)
- enter to the `application` container: `docker-compose exec application bash`

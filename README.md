# Docker

Apache2, PHP5, MySQL, NodeJS, Supervisor

## Commands

- `docker-compose up` - run
- `docker-compose up -d` - run in the background
- `docker-compose up --force-recreate --remove-orphans` - recreate containers and remove not defined containers
- `docker-compose exec [container] bash` - enter to container
- `docker-compose exec [container] [command]` - run command in container

## Configuration

You can change the IP addres in `.env` file.

You can also change the files in `docker` folder.

## Run

- run containers: `docker-compose up`
- open [127.10.0.1](http://127.10.0.1/) in your browser
- enter to the `application` container: `docker-compose exec application bash`

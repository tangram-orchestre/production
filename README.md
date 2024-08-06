# Tangram's Production Environment

This repository holds Tangram website production environment.

## Docker Compose

It is managed using [docker compose](https://docs.docker.com/compose/). Each service is put in its separate folder with its own `docker-compose.yaml` configuration.

At the top level a single `docker-compose.yaml` includes the ones in the subfolders to provide grouped action.

- To start the infrastructure simply run:
    ```bash
    docker compose up -d
    ```
- To update containers, update versions in `docker-compose.yaml` and then:
    ```bash
    docker compose pull
    docker compose up -d
    ```

## .env files

To keep secret secret, we use `.env` file that are not tracked by `git`, samples files are commited to know what key are needed.

You can run [check-env-file-coherency.py](scripts/check-env-file-coherency.py) to assert real and samples files are synchronised. Adding the script in your [pre-commit hooks](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks) is also a good idea.

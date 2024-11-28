# Dockerized Qtap environment

If you do not have docker on your machine, please follow steps in here [Docker Setup](./DOCKER_SETUP.md)

## Setting Up Environment

1. Clone the repository.
2. Create a 'repos' directory in root level. Clone QTAP and ptseries into this `repos` directory.
3. Navigate to the `docker` directory.
4. Build the Docker image:

```bash
docker build -t my_conda_env_image .

```

4. Run the Docker container:

```bash
docker run -it \
  -v $(cd ../repos && pwd):/app/repos \
  -p 8888:8888 \
  my_conda_env_image
```

This will output logs. Control + click on this: `[I 10:25:43.217 ServerApp] http://0.0.0.0:8888/?token=YOUR_TOKEN` which should open up a jupyter notebooks in your browser.

## Dependencies

List of dependencies in `environment_env1.yml`.

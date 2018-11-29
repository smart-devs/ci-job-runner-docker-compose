# CI job runner docker-compose

This Repo contains the build instructions for the ci docker-compose job runner. it can contain secrets to push and pull images from/to registries based on the parent image ci-job-runner-docker.

## Documentation

### How to use this image

This image can be used for following pipeline stages:

- run testing stack via docker-compose

### Environment vars

| Argument                              | Default Value                                             | Description |
| :---                                  | :---                                                      | :---         |
| DOCKER_HOST                           | tcp://localhost:2375                                      | Path to docker host or unix socket    |

### Build Arguments

All build arguments should be prefixed with DOCKER_BUILD_ARG. They can be set as pipeline Variable / Job variable. 

note: `DOCKER_BUILD_ARG_` prefix should prepend to all shown variables.

| Argument                              | Default Value                                             | Description |
| :---                                  | :---                                                      | :---         |
| FROM                                  | ci-job-runner-docker:latest                               | Base image to build from    |
| CONTAINER_RUNTIME_REQUIREMENTS        | python3                                                   | Packages for container during runtime  |
| CONTAINER_BUILD_REQUIREMENTS          | curl gnupg apt-transport-https software-properties-common | Packages for container required during build  |
| CONTAINER_EXTRA_RUNTIME_REQUIREMENTS  | *empty                                                    | extra runtime requirements to keep merge / rebase possible  |
| CONTAINER_EXTRA_BUILD_REQUIREMENTS    | *empty                                                    | extra build requirements to keep merge / rebase possible  |
| DOCKER_COMPOSE_VERSION                | 1.23.1                                                    | Docker version to install  |

## Contributing

See [CONTRIBUTING.md](./docs/CONTRIBUTING.md).

## Changelog

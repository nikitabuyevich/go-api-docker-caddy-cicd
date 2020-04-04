![Picture of an API](./api.png)

# API Webserver w/ Docker, Caddy, and CI/CD &middot; [![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](./LICENSE)

This is a sample of an almost plug-n-play API webserver that utilizes Docker, Caddyserver, and Gitlab's CI/CD for a seamless development experience.

The API is written in Go (golang) but the implementation of the pipeline is the same. Modifying the `Dockerfile` and the `docker-compose.yml` file is all that's required to switch to a different language.

## Features

- Docker is used to build and serve software
- Caddyserver is used to proxy requests from the API as well as automatically serve HTTPS
- Gitlab's CI/CD is used to build the Docker containers, run tests, and deploy the final images to a server of your choice

## Getting Started

Follow along with the [Docker Build to Deploy CI/CD](https://github.com/nikitabuyevich/gitlab-docker-build-to-deploy-cicd) README to understand how to utilize Gitlab's CI/CD.

Run API
```bash
docker-compose up api
```

Run Tests
```bash
go test -v ./...
```

### Prerequisites

- [Docker](https://docker.com/) - Build and run images / containers
- [Gitlab Runner](https://docs.gitlab.com/runner/) - Integrate a Gitlab CI/CD pipeline with a server

## Authors

- **Nikita Buyevich** - [nikitabuyevich.com](https://nikitabuyevich.com/)

## License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

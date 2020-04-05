![Picture of an API](./api.png)

# API Webserver w/ Docker, Caddy, and CI/CD &middot; [![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](./LICENSE)

This is a sample of a plug-n-play API webserver that utilizes Docker, Caddyserver, and Gitlab's CI/CD for a seamless development experience.

The API is written in Go (golang) but the implementation of the pipeline is the same. Modifying the `Dockerfile` and the `docker-compose.yml` file is all that's required to switch to a different language.

You can use the [Caddy Server Docker](https://github.com/nikitabuyevich/caddy-docker) example as your Caddy image.

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

### Cloudflare

If you wish to use Cloudflare to secure your DNS, follow along this guide: https://www.cylindric.net/web/caddyserver-and-cloudflare

#### TL;DR

- Make sure your caddy image has the `cloudflare` plugin
- Export a `CLOUDFLARE_EMAIL` and `CLOUDFLARE_API_KEY` environment variable in your caddy image
  - Pass the `CLOUDFLARE_API_KEY` through Gitlab's CI/CD variables
- Set your Cloudflare's SSL option as `Full (Strict)`

### Prerequisites

- [Docker](https://docker.com/) - Build and run images / containers
- [Gitlab Runner](https://docs.gitlab.com/runner/) - Integrate a Gitlab CI/CD pipeline with a server

## Authors

- **Nikita Buyevich** - [nikitabuyevich.com](https://nikitabuyevich.com/)

## License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

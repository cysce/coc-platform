# coc-platform
Docker Compose files to deploy CYSCE Operations Center Platform using containers

![Grafana][grafana-version] ![Influx][influx-version]

## Usage

#### docker-compose file

To use this image, create a container in your `docker-compose.yml` file as shown below:

```yaml
version: "3.8"

volumes:
  dashboard-data:

services:
  dashboard:
    image: balenablocks/dashboard
    restart: always
    volumes:
      - "dashboard-data:/data"
    ports:
      - "80"
```

You can set your `docker-compose.yml` to build a `Dockerfile` file and use the dashboard block as the base image.
_docker-compose.yml:_

```yaml
version: "2"

volumes:
  dashboard-data:

services:
  dashboard:
    build: ./
    restart: always
    volumes:
      - "dashboard-data:/data"
    ports:
      - "80"
```

_Dockerfile_

```dockerfile
FROM balenablocks/dashboard
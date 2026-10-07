# Docker lecture (exercises)

Install the docker extension!

## 1. Hello World!

Build a small Dockerfile that uses the latest version of the official "hello world" example from Docker.io; and build its image

```bash
# You can simply run but this is a bit outdated
docker build .

# It is preferable to use
docker buildx build .

# But this will create an image without name; to set a name
docker buildx build -t v-stamenova/hello-world .

# Then to finally start the container
docker container run v-stamenova/hello-world
```
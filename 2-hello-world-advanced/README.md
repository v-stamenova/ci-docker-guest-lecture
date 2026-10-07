# Docker lecture (exercises)

## 2. Hello World (advanced)!

Let's hear the cow!

```bash
# Tag the old image!
docker tag v-stamenova/hello-world v-stamenova/hello-world:1

# You know the drill!
docker buildx build -t v-stamenova/hello-world .
docker container run -it v-stamenova/hello-world

usr/games/cowsay "Hi from Docker!"
```
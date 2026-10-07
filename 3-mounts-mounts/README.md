# Docker lecture (exercises)

## 3. Mounts and mounts

```bash
# You know the drill!
docker buildx build -t v-stamenova/hello-world .
docker container run -it v-stamenova/hello-world

# Check the file!
cat data/i-was-here.txt

# Create new one!
echo "Hi from the container" > /data/container.txt
# show it doesn't show up in the data folder of the IDE but only in the container

# To mount it
docker run -it --rm   -v "$(pwd)/data:/data"   v-stamenova/hello-world:latest
```
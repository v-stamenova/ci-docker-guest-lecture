# Docker lecture (exercises)

## 4. Talking talking

```bash
mkdir backend
cd backend
git clone git@github.com:HZ-HBO-ICT/allegro.git .
docker run -it --rm -v "$(pwd):/app" node:24 sh
> cd app
> npm install
> npm run prisma:generate
> npm run prisma:migrate
> npm run prisma:seed
> npm run dev # should break (cant connect to server: http://localhost:4000/health)

docker run -it --rm -v "$(pwd):/app" -p 4000:4000 --name "backend" node:24 sh

# new terminal
docker run -it --rm --name "frontend" curlimages/curl:latest sh
> curl http://backend:4000/health # can't resolve

docker network create -d bridge year-2 (docker network ls)

docker run -it --rm -v "$(pwd):/app" -p 4000:4000 --name "backend" --network "year-2" node:24 sh
docker run -it --rm --name "frontend" --network "year-2 "curlimages/curl:latest sh
> curl http://backend:4000/health
```
# Week 1 — App Containerization

Installed Docker VSCode extension for ease of working with Docker

## Container Images using using Dockerfile
Wrote Dockerfiles for Backend and frontend apps and built images out of it
```sh
docker build -t  frontend-react-js ./frontend-react-js  
docker build -t  backend-flask ./backend-flask  
```

## Run Containers from the above images
```sh
FRONTEND_CONTAINER_ID=$(docker run -p 3000:3000 -d frontend-react-js)
BACKEND_CONTAINER_ID=$(docker run --rm -p 4567:4567 -d backend-flask)
```

## Use docker-compose to configure & deal with multi-app-container setup
Added services (postgres & dynamodb), volumes & volume-mapping
[docker-compose.yml](../../main/docker-compose.yml)

## Helpful Commands 
```sh
# To list the built images
docker images 

# To check running & all containers
docker ps [-a]

# To check container logs
docker logs <CONTAINER_ID | NAME> -f  
docker logs $BACKEND_CONTAINER_ID -f   
docker logs backend-flask -f  

# To delete an image
docker image rm <IMAGE> --force   
```   

## Tagged & Pushed the frontend & backend Docker Images to Dockerhub
https://hub.docker.com/r/phalani/aws-bootcamp-cruddur-2023-frontend-react-js  
https://hub.docker.com/r/phalani/aws-bootcamp-cruddur-2023-backend-flask

Also, ran containers also by pulling the above pushed images

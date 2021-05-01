# Part 2 - answers

## 2.1

[docker-compose.yml](./2.1/docker-compose.yml)

## 2.2

[docker-compose.yml](./2.2/docker-compose.yml)

## 2.3

[docker-compose.yml](./2.3/docker-compose.yml)

*I found the assignment instructions to be a bit vague, but I suppose the idea was to use Docker compose simply for building and starting the containers based on the existing Dockerfiles..?*

## 2.4

[docker-compose.yml](./2.4/docker-compose.yml)

## 2.5

```
docker-compose up --scale compute=3 -d
```

## 2.6

[docker-compose.yml](./2.6/docker-compose.yml)

## 2.7

[docker-compose.yml](./2.7/docker-compose.yml)

## 2.8

[docker-compose.yml](./2.8/docker-compose.yml)

## 2.9

[docker-compose.yml](./2.9/docker-compose.yml)

## 2.10

[docker-compose.yml](./2.10docker-compose.yml)

[Dockerfile (frontend)](./2.10/example-frontend/Dockerfile)

[Dockerfile (backend](./2.10/example-backend/Dockerfile)

To make things work, I had to change the env variables in both dockerfiles. Since the react backend url defaults tp /api, I simply commented out the env variable.

# Part 1 - answers

## 1.1: Getting started

```
$ docker ps -a
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS                     PORTS     NAMES
a81dd5676303   nginx     "/docker-entrypoint.…"   20 seconds ago   Up 19 seconds              80/tcp    crazy_volhard
df563a868651   nginx     "/docker-entrypoint.…"   21 seconds ago   Exited (0) 3 seconds ago             friendly_chandrasekhar
483c8cf2b100   nginx     "/docker-entrypoint.…"   2 minutes ago    Exited (0) 3 seconds ago             busy_almeida
```

## 1.2: Cleanup

```
$ docker ps -a
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES

$ docker images
REPOSITORY   TAG       IMAGE ID   CREATED   SIZE
```

## 1.3: Secret message

```
$ docker run -d devopsdockeruh/simple-web-service:ubuntu
$ docker exec -it crazy_ride bash
root@be5bd944dc26:/usr/src/app# tail -f ./text.log
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
2021-04-07 14:20:32 +0000 UTC
```

## 1.4: Missing dependencies

```
$ docker run -d -it ubuntu sh -c 'echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;'
$ docker exec -it heuristic_almeida bash
root@96d5acadc649:/# apt update && apt install -y curl
root@96d5acadc649:/# exit
$ docker attach heuristic_almeida
helsinki.fi
Searching..
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>301 Moved Permanently</title>
</head><body>
<h1>Moved Permanently</h1>
<p>The document has moved <a href="http://www.helsinki.fi/">here</a>.</p>
</body></html>
```

## 1.5: Sizes of images

```
$ docker pull devopsdockeruh/simple-web-service:alpine
$ docker images
devopsdockeruh/simple-web-service   ubuntu    4e3362e907d5   3 weeks ago   83MB
devopsdockeruh/simple-web-service   alpine    fd312adc88e0   3 weeks ago   15.7MB
$ docker run -d fd
$ docker exec -it hopeful_heyrovsky sh
/usr/src/app # tail -f ./text.log
2021-04-07 14:35:56 +0000 UTC
2021-04-07 14:35:58 +0000 UTC
2021-04-07 14:36:00 +0000 UTC
2021-04-07 14:36:02 +0000 UTC
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
/usr/src/app # exit
```

## 1.6: Hello Docker Hub

```
$ docker run -it devopsdockeruh/pull_exercise
Give me the password: basics
You found the correct password. Secret message is:
"This is the secret message"
```

## 1.7: Two line Dockerfile

[Dockerfile](./1.7/Dockerfile)

```
$ docker build . -t web-server
$ docker run web-server
[GIN-debug] [WARNING] Creating an Engine instance with the Logger and Recovery middleware already attached.

[GIN-debug] [WARNING] Running in "debug" mode. Switch to "release" mode in production.
 - using env:   export GIN_MODE=release
 - using code:  gin.SetMode(gin.ReleaseMode)

[GIN-debug] GET    /*path                    --> server.Start.func1 (3 handlers)
[GIN-debug] Listening and serving HTTP on :8080
```

## 1.8: Image for script

[Dockerfile](./1.8/Dockerfile)

```
$ docker run -it curler
Input website:
helsinki.fi
Searching..
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>301 Moved Permanently</title>
</head><body>
<h1>Moved Permanently</h1>
<p>The document has moved <a href="http://www.helsinki.fi/">here</a>.</p>
</body></html>
```

## 1.9: Volumes

```
$ docker run  --mount type=bind,src=$(pwd)/log.log,dst=/usr/src/app/text.log devopsdock
eruh/simple-web-service
```

## 1.10: Ports open

```
$ docker run -p 8989:8080 devopsdockeruh/simple-web-service server
```

## 1.11: Spring

[Dockerfile](./1.11/Dockerfile)

```
$ docker build -t spring-project .
$ docker run -p 8080:8080 spring-project
```

## 1.12: Hello, frontend!

[Dockerfile](./1.12/Dockerfile)

## 1.13: Hello, backend!

[Dockerfile](./1.13/Dockerfile)

## 1.14: Environment

[Dockerfile (backend)](./1.14/back/Dockerfile)

```
$ docker run -p 8080:8080 example-backend
```

[Dockerfile (frontend)](./1.14/front/Dockerfile)

```
$ docker run -p 5000:5000 example-frontend
```

## 1.15: Homework

Skipped

## 1.16: Heroku

[Deployed application](https://docker-example-412345.herokuapp.com/)
# seleniumDocker
## How to use this image

```
$ docker run -d -p 4444:4444 --name selenium-hub selenium/hub
```

Note: You can optionally override default configuration settings using environment variables.
See the [Hub's Dockerfile](Dockerfile) to view the list of variables and their default values.

```
$ docker run -d -p 4444:4444 --name selenium-hub -e GRID_TIMEOUT=10 selenium/hub
```


Once the hub is up and running will want to launch nodes that can run tests. You can run as many nodes as you wish.

```
$ docker run -d --link selenium-hub:hub -v /dev/shm:/dev/shm selenium/node-chrome
$ docker run -d --link selenium-hub:hub -v /dev/shm:/dev/shm selenium/node-firefox
```

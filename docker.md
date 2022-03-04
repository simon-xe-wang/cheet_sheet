# Image

```
$ docker image pull myregistry.local:5000/<repo>[:tag]
$ docker image inspect nigelpoulton/pluralsight-docker-ci
```

# Container

## Lifecycle

stop, start, pause, restart, delete

```
$ docker container run  # run = create + start

$ docker container start

# stop container gracefully by sending SIGTERM to PID 1
$ docker container stop 

$ docker container rm

# list all running containers. -a: list exited containers
$ docker container list # -a 

# run a new process inside a container
$ docker container exec

# always auto restart container 
docker container run --name neversaydie -it --restart always microsoft/powershell:nanoserver

# will not restart if using stop command
docker container run --name neversaydie -it --restart unless-stopped microsoft/powershell:nanoserver

# restart when exit with non-zero exit code
docker container run --name neversaydie -it --restart unless-stopped microsoft/powershell:nanoserver

# delete all running containers on localhost
$ docker container rm $(docker container ls -aq) -f

# check the detailed configuration and runtime information about a container
$ docker container inspect <name or id>

```


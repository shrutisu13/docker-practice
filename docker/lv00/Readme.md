### Basic Docker Commands :
- [Docker Basic Commands](https://docs.docker.com/engine/reference/commandline/docker/) <br/>
- docker --help
```
$ docker --help
```

```
Usage:	docker [OPTIONS] COMMAND

Management Commands:
  builder     Manage builds
  config      Manage Docker configs
  container   Manage containers
  context     Manage contexts
  image       Manage images
  network     Manage networks
  node        Manage Swarm nodes
  plugin      Manage plugins
  secret      Manage Docker secrets
  service     Manage services
  stack       Manage Docker stacks
  swarm       Manage Swarm
  system      Manage Docker
  trust       Manage trust on Docker images
  volume      Manage volumes

Commands:
  attach      Attach local standard input, output, and error streams to a running container
  build       Build an image from a Dockerfile
  commit      Create a new image from a container's changes
  cp          Copy files/folders between a container and the local filesystem
  create      Create a new container
  diff        Inspect changes to files or directories on a container's filesystem
  events      Get real time events from the server
  exec        Run a command in a running container
  export      Export a container's filesystem as a tar archive
  history     Show the history of an image
  images      List images
  import      Import the contents from a tarball to create a filesystem image
  info        Display system-wide information
  inspect     Return low-level information on Docker objects
  kill        Kill one or more running containers
  load        Load an image from a tar archive or STDIN
  login       Log in to a Docker registry
  logout      Log out from a Docker registry
  logs        Fetch the logs of a container
  pause       Pause all processes within one or more containers
  port        List port mappings or a specific mapping for the container
  ps          List containers
  pull        Pull an image or a repository from a registry
  push        Push an image or a repository to a registry
  rename      Rename a container
  restart     Restart one or more containers
  rm          Remove one or more containers
  rmi         Remove one or more images
  run         Run a command in a new container
  save        Save one or more images to a tar archive (streamed to STDOUT by default)
  search      Search the Docker Hub for images
  start       Start one or more stopped containers
  stats       Display a live stream of container(s) resource usage statistics
  stop        Stop one or more running containers
  tag         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE
  top         Display the running processes of a container
  unpause     Unpause all processes within one or more containers
  update      Update configuration of one or more containers
  version     Show the Docker version information
  wait        Block until one or more containers stop, then print their exit codes

Run 'docker COMMAND --help' for more information on a command.

```
<br/>

- docker pull

```
$ docker pull <image_name>
```
This command is used to pull images from the docker repository(hub.docker.com) . <br/>
Example :

```
$ docker pull hello-world

Using default tag: latest
latest: Pulling from library/hello-world
0e03bdcc26d7: Pull complete
Digest: sha256:6a65f928fb91fcfbc963f7aa6d57c8eeb426ad9a20c7ee045538ef34847f44f1
Status: Downloaded newer image for hello-world:latest
docker.io/library/hello-world:latest
```
<br/>

- docker run
```
$ docker run 
Usage: docker run -it -d <image name>
```
This command is used to create a container from an image . <br/>
Example :

```
$ docker run hello-world

Hello from Docker!
This message shows that your installation appears to be working correctly.

$ docker run -it -d ubuntu

e33151e2ebb209f2c93d605e3c15f47bdaea7d1a7c22fe2c7a995fb6e923273e
```
<br/>

- docker ps
```
$ docker ps
```
This command is used to list the running containers . <br/>
Example :
```
CONTAINER ID        IMAGE         COMMAND         CREATED           STATUS              PORTS               NAMES
e33151e2ebb2        ubuntu       "/bin/bash"     3 minutes ago     Up 3 minutes                            zen_bhabha

```
<br/>

- docker ps -a

```
$ docker ps -a
```
This command is used to show all the running and exited containers . <br/>
Example :
```

$ docker ps -a

CONTAINER ID        IMAGE                COMMAND              CREATED             STATUS                     PORTS                NAMES
787aa0582432        hello-world          "/hello"           7 minutes ago       Exited (0) 7 minutes ago                        wizardly_wing
e33151e2ebb2        ubuntu               "/bin/bash"        9 minutes ago       Up 9 minutes                                    zen_bhabha
```
<br/>

- docker exec

```
$ docker exec 
Usage: docker exec -it <container id> bash
```
This command is used to access the running container . <br/>
Example :
```
$ docker exec -it e33151e2ebb2 bash
root@e33151e2ebb2:/#
```
<br/>

- docker stop

```
$ docker stop 
Usage: docker stop <container id>
```
This command stops a running container . <br/>
Example :
```
$ docker stop e33151e2ebb2
e33151e2ebb2
```
<br/>

- docker Kill

```
$ docker kill
```
This command kills the container by stopping its execution immediately. The difference between ```docker kill``` and ```docker stop``` is that ```docker stop``` gives the container time to shutdown gracefully, in situations when it is taking too much time for getting the container to stop, one can opt to kill it . <br/>
Example :
```
$ docker stop e33151e2ebb2
e33151e2ebb2
```
<br/>

- docker commit
```
$ docker commit 
Usage: docker commit <conatainer id> <username/imagename>
```
This command creates a new image of an edited container on the local system . <br/>
Example :
```
$ docker commit 787aa0582432 user4/ubuntu
sha256:1d16c270f29fc152eec2194a8c57949f1cafcc264ce2bec63bff6942cd3c0ec8
```
<br/>

- docker login
```
$ docker login
```
This command is used to login to the docker hub repository . <br/>
Example :
```
$ docker login
Login with your Docker ID to push and pull images from Docker Hub. If you don't have a Docker ID, head over to https://hub.docker.com to create one.
Username: user4
Password:
Login Succeeded
```
<br/>

- docker push

```
$ docker push 
Usage: docker push <username/image name>
```
This command is used to push an image to the docker hub repository . <br/>
Example :
```
$ docker push user4/ubuntu
```
<br/>

- docker images

```
$ docker images
```
This command lists all the locally stored docker images . <br/>
Example :
```
docker images
REPOSITORY            TAG            IMAGE ID            CREATED             SIZE
user4/ubuntu         latest         1d16c270f29f        14 minutes ago      13.3kB
busybox              latest         1c35c4412082        2 weeks ago         1.22MB
ubuntu               latest         1d622ef86b13        7 weeks ago         73.9MB
```
<br/>

- docker rm

```
$ docker rm 
Usage: docker rm <container id>
```
This command is used to delete a stopped container . <br/>
For Deleting all running and stopped containers , Use ```docker container rm -f $(docker ps -aq) ``` . <br/>
Example :
```
$ docker rm 787aa0582432
787aa0582432
```
<br/>

- docker rmi

```
$ docker rmi

Usage: docker rmi <image-id>
```
This command is used to delete an image from local storage . <br/>
Example :
```
$ docker rmi 1d16c270f29f
Untagged: user4/ubuntu:latest
Deleted: sha256:1d16c270f29fc152eec2194a8c57949f1cafcc264ce2bec63bff6942cd3c0ec8
```
<br/>

- docker build

```
$ docker build 
Usage: docker build <path to docker file>
```
This command is used to build an image from a specified docker file . <br/>
Example :
```
docker build -t myimage:1.0 .
```
<br/>

- docker tag

```
$ docker tag
```
This command is used retag a local image with a new image name
and tag . <br/>
Example :
```
$ docker tag ubuntu user4/ubuntu

For checking , Use  "docker images" 
REPOSITORY             TAG            IMAGE ID            CREATED             SIZE
user4/ubuntu          latest         1d622ef86b13        7 weeks ago         73.9MB
```
<br/>

- $ docker container logs

```
$ docker container logs --tail 100 <CONTAINER_NAME>
```
This command is used print the last 100 lines of a container’s logs .  <br/>

- docker network <br/>
```
docker network ls
```
This command is used list the networks . <br/>
Example :
```
$ docker network ls
NETWORK ID          NAME                DRIVER              SCOPE
d949f37474cd        bridge              bridge              local
ac9682988f59        host                host                local
7d033fd85881        none                null                local
```
<br/>

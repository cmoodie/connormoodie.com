# Docker
```query
children:.
```
---

Docker allows for any service to be run the same way on any machine. This is done using **docker images**. These contain not only the service to be run, but a condensed version of the operating system and environment used to run it. When a docker image is run, docker creates a **docker container** which is a running instance of that docker image.

#### Docker Compose
Usually, to create a docker container, you have to input a very long and annoying docker cli command. Docker compose allows you to create multiple docker containers with different arguments and such with the use of a nice yaml file.

#### Kubernetes
Docker compose is not built for large complicated projects, whereas Kubernetes can deal with a huge number of different docker containers requiring automated deployment, scaling, and management.

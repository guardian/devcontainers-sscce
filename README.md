Devcontainers SSCCE
===================

A simple demonstration of IntelliJ's broken docker-in-docker support in dev containers.

This appears to be broken since IntelliJ 2026, but we don't have an exact version number. We get the same results with and without the "Open devcontainer projects natively" setting applied.

## Reproduce the problem

Open this project in a devcontainer by clicking the box in the gutter of the config file at
[.devcontainer/devcontainer.json](.devcontainer/devcontainer.json).
Choose "Create Dev Container and Clone Sources".

Wait a bit for the dev container to start up.

In the Dev Container, open the IDE terminal, and run `docker compose up`.

### Expected 

The example app should run. It simply prints "hello, world" and exits.

```
hello-1  | hello, world
hello-1 exited with code 0
```

### Actual

We see the following error.

```
unable to get image 'alpine:latest': Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running?
```

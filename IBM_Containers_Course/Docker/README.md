# Docker Notes
A container is a runnable instance of a image.

## Network, Storage(volumes and binds) & Plugins (external storage platforms)

## Commands
| Command | Usage | Example |
| ----------- | ----------- | ----------- |
| build | Create container images from a Dockerfile | docker build -t my-app:v1|
| images | List all imgs, repos, tags and sizes | docker images |
| run | Creates a running container from an image | docker run -p 8080:80 nginx|
| push |Stores images in a configured registry | docker push my-app:v1|
| pull | Retrieve images form a configured registry | docker pull nginx|
| ps | Verify details| docker ps -a|

## Dockerfile Instructions
Text file containing instructions to create an image in any editor feom console or terminal
| Instruction | Example |
| ----------- | ----------- |
| FROM | Define base image|
| RUN | Execution |
| CMD | Define default command for container execution; <br>Usually 1, if multiple the last one is effective|

## Docker Image
> hostname/repository:tag = Docker hub registry/Group of images:Version<br>
> ex: docker.io/ubuntu:18.04

Read only template with instructions for creating Docker container using Dockerfile instructions;<br>
New creates read-only image layer for each instruction;<br>
One writeble layer per container;<br>
Layers can be shared between images, saving disk space and bandwidth.


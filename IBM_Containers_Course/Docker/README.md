# Docker Notes
A container is a runnable instance of an image.

## Architecture & Workflow
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/d714a3d0-a7cf-49a6-aee3-40cf36693706)

1. docker build: Client creates Images with Docker file;
2. docker push: Client stores Images in Registry;
3. docker pull (if needed): Docekr host (Daemon/dockerd) retrives Images from Registry;
4. docker run: Docker host creates containers from retreived Images.

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

### Cheatsheet
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/e8c77330-7dcf-4493-b714-5a0b48e9cc8a)


## Dockerfile Instructions
Text file containing instructions to create an image in any editor feom console or terminal
| Instruction | Example |
| ----------- | ----------- |
| FROM | Define base image|
| RUN | Execute commands |
| CMD | Define default command for container execution; <br>Usually 1, if multiple the last one is effective|
| EXPOSE | Expose a particular port with a specified protocol inside a Docker Container. |

## Docker Image
```
hostname/repository:tag == Docker hub registry/Group of images:Version
ex: docker.io/ubuntu:18.04
```
1. Read only template with instructions for creating Docker container using Dockerfile instructions;<br>
2. New creates read-only image layer for each instruction;<br>
3. One writeble layer per container;<br>
4. Layers can be shared between images, saving disk space and bandwidth.


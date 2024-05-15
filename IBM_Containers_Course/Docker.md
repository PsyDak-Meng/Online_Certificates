# Docker Notes
A container is a runnable instance of an image.<br>
See definitions of container techs [here.](https://www.coursera.org/learn/ibm-containers-docker-kubernetes-openshift/ungradedWidget/d2mif/module-1-glossary-containers-basics)

## Architecture & Workflow
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/d714a3d0-a7cf-49a6-aee3-40cf36693706)

1. **docker build**: Client creates Images with Docker file,<br>
                    ex: docker build . -t myimage:v1;
2. **docker pull (if needed)**: Docker host (Daemon/dockerd) retrieves Images from Registry;
3. **docker push**: Client stores Images in Registry;<br>
  3-1 **Set environmental variable**: export MY_NAMESPACE=sn-labs-$USERNAME;<br>
  3-2 **docker tag**: tag to be pushed,<br>
   ex: docker tag myimage:v1 us.icr.io/$MY_NAMESPACE/hello-world:1<br>
  3-3 **docker push**: docker push us.icr.io/$MY_NAMESPACE/hello-world:1
4. **docker run**: Docker host creates containers from retreived Images.
5. **curl**: ping the application, ex: curl localhost:8080;
6. **docker stop**: docker stop $(docker ps -q)/docker stop `docker ps -qa`,<br>
   docker ps- -q passes in all containers to be stopped;<br>
   **docker container rm <container_id>**: remove a container;
7. **docker ps -a**: check the container has stopped.

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
**Dockerfile**: Text file containing instructions to create an image in any editor feom console or terminal
| Instruction | Example |
| ----------- | ----------- |
| FROM | Define base image|
| COPY | Copy files to the image |
| RUN | Execute commands |
| EXPOSE | Expose a particular port with a specified protocol inside a Docker Container. |
| CMD | Define default command for container execution; <br>Usually 1, if multiple the last one is effective|

![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/c03ec4ac-348e-4a37-ab3a-acfa4e3948b1)



## Docker Image
**Image naming**
```
hostname/repository:tag == Docker hub registry/Group of images:Version
ex: docker.io/ubuntu:18.04
```
1. Read only template with instructions for creating Docker container using Dockerfile instructions;<br>
2. New creates read-only image layer for each instruction;<br>
3. One writeble layer per container;<br>
4. Layers can be shared between images, saving disk space and bandwidth.

## Labs
- Lab 1-Pull, build & push images: https://labs.cognitiveclass.ai/v2/tools/cloud-ide-kubernetes?ulid=ulid-890236321f9b1051ba114502cc1abb3eb9cbdf6b

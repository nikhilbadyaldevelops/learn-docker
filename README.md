# Docker Commands

## Conainers

1. `docker --help` - To get help for commands.
1. `docker <command> --help` - To get help for a particular command.
1. `docker ps -a` - lists all running ports. `-a` shows all containers without that it shows only running.
1. `docker stop <container-name` - Stops the container mentioned
1. `docker run --env/-e <envVariables> --env-file  <fileLocation> --rm -p <p1:p2> --name <SomeName>  -it -d -v <pathInHost:pathInContainer> <image-name:tag>` - create container from image and run. if not available then download from docker hub. `-it` flags tells us to expose interactive terminal from container to our local machine. By default, it runs in attach mode.`-d` to run the container in detach mode.`--rm` flag tells to remove the container when it stops and anonymous volumes are also removed.`--name` to give custom name to the container.`-p` flags is to `publish`, under which port on our local machine the docker port should be accessible. `p1` is the local port and `p2` is container port.`-v` to add volumes.I can add `-v` two times to add bind mount.`--env` to set envioronment variables.
1. `docker build -t <name:tag> --build-args <ARGNAME> <dir>` - Build an image from Dockerfile.`-t` to give custom tag to the
   image. `<name:tag>` specifies the format of the tag.
1. `docker start -a -i <containerID/containerName>` - To start an existing container. By default, it starts in detach
   mode.`-a` to start container in attach mode.`-i` for interactive shell.
1. `docker logs -f <containerName/ID>` - To print the past logs in console.`-f` to tell docker that we want to follow
   the future logs.(Kind of attach state)
1. `docker attach <containerName>` - Attach to a running container.
1. `docker rm <containerName/s>` - Remove container. Cannot remove running container.Can write multiple names separated
   by space.
1. `docker container prune` - delete a stopped containers.
1. `docker images` - to list all images.
1. `docker rmi <imageName/s:tagName>` - to remove **`images`**. Only images which are not used.Mention tag if exist.
1. `docker image prune -a inspect` - `prune` remove all images.`inspect` used to inspect the image.`-a` tag to prune
   images incl. tagged images.
1. `docker cp <src> <containerName:dest>` - to copy in/out to/from the container.`dest` will be created if it doesn't
   exist.
1. `docker push <hostName>:tagname` - It pushed the image to the host mentioned.
1. `docker pull <image:tagName` - To pull image from docker
1. `docker tag <oldName> <newName>` - To rename a image.
1. `docker login` - To loign to docker hub
1. `docker logout` - to logout from docker hub.

## Volumes(Anonymous Volumes, Named Volumes, Bind Mounts)

1. `docker volume rm <volumneName> prune ls inspect <volumeName> create <volumeName>` - `create` to create volume  manually.`ls` to list all volumes.`inspect` to see details of a volume.`prune` to remove all unused **local** volumes.`rm` remove volume by name.
   1. -v "%cd%:/app" in windows ( For Bind mounds)  
   1. -v ${pwd}:app in mac/linux
1. `docker run -v /app/data` - Anonymous Voumes.Survives shutdown/stopping of containers but not removal. Can't be shared by container. Created by `--v` flag or by writting docker file.
1. `docker run -v data:/app/data` - Named Volumes. Created by `--v` flages. In general and not linked to particular container. also survive removals. Can be shared across containers.  
1. `docker run -v /path/to/code:/app/code` - Bind Mount. Not tied to particular container. Can be shared across containers. survives restart and removal.`ro` can be added to tell docker that its a read only volume.

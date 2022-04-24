# Docker Cheat Sheet

This repository contains examples of docker commands and also examples of dockerfiles.

```shell
# search for an image
docker search python

# search only for official images
docker search --filter is-official=true python

# remove all images from host
docker image rm -f $(docker image ls -a -q)

# show history of commands executed in a image
# useful to see what was done in each layer creating the image
docker history imageid

# create a container withou running it
docker create image

# start a container
docker start imageid

# pull, create,  run a container
docker run image

# run a container and open a terminal
docker run -it python /bin/bash

# run a container in a detached mode
docker run -d image

# execute a command in a container
docker container exec containerid command

# get container data
docker container inspect containerid
```

## Difference CMD and ENTRYPOINT

*ENTRYPOINT* is the command executed when the contianer starts.

*CMD* is the argument passed to the entrypoint.

For example, the next set of commands would run *python app.py*.

```Dockerfile
ENTRYPOINT ["python"]

CMD ["app.py"]
```


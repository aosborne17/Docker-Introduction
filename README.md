# Introduction To Docker

### Common Commands
```
docker ps -> checks for running containers
docker rm -f container_id --> stops and deletes a running container
docker images --> shows us all the images we have pulled
docker run -p 80:80 nginx --> Here we are running an nginx image and mapping it to port 80
docker run -d -p 80:80 nginx --> Here we are running the same command in detached mode, thus we
                                can continue to use the terminal

```


## Port mapping

```
docker run -p 80:80 nginx
```
With the command below we have changed our nginx so that is shows on port 99 instead
of port 80
```
docker run -p 99:80 nginx
```

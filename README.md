# Introduction To Docker :whale:

### Common Commands
```
docker ps -> checks for running containers
docker rm -f container_id --> stops and deletes a running container
docker images --> shows us all the images we have pulled
docker run -p 80:80 nginx --> Here we are running an nginx image and mapping it to port 80
docker run -d -p 80:80 nginx --> Here we are running the same command in detached mode, thus we
                                can continue to use the terminal
```
- As we can see below, when we run docker images it shows us all the images we have
available

![](/images/run-docker-images)


## Adding winpty docker to ENV variables

- Adding this allows windows users to easily enter docker containers
- We run the following command in our git bash, or add it to our advanced
system variables so that it persists

```
alias docker="winpty docker"
```

## Entering your container

- When we run a container, we can then enter it using the below command

```
docker exec -it container_id sh
```
- Once in we can then run commands that we would run on a virtual machine to see
the folders present, env variables etc

![](/images/Entering-Docker-Container)

## Creating a repository on Docker

#### 2) Create a Docker hub account and locate to the website https://hub.docker.com/

#### 2) Click on Create repository
![](/images/create-repo-docker)


#### 3) Give the repo a convenient name and then click Create

![](/images/Click-create)

## Pushing an image to your own Docker repository

#### 1) We will create an image of nginx running the following command

```
docker run -d -p 80:80 nginx
```

#### 2) Note that if this the fist time running the command, Docker will pull the image and then run a container from it

#### 3) When we run ``docker ps`` it will show us the image id of all the images we have pulled

![](/images/pushing-nginx-image)

#### 4) We can now push this image to our own repository running the following commands

```
# Here we have tagged the image that we want to push
# We have then specified our docker id and the repo we want to push to
# Finally we add a tag to the end that will describe the image

docker tag 4bb46517cac3 aosborne17/andrew-eng-67:Second_Commit

# Now that we have tagged the image, we can then push it to our repository, allowing anyone to access that image
docker push aosborne17/andrew-eng-67

```

## Pulling someone's image from a Docker repository

#### 1) Running the following command will pull the repository from this user and then run the nginx image on port 200

```
docker run -d -p 200:80 danteegan/daniel-teegan-eng-67:First_commit_docker
```

#### 2) We can now see the image we pulled is now running as a container

![](/images/daniel-app-running)

#### 3) We can now go to port 200 on our local host and see the nginx container running successfully
![](/images/nginx-port-200)


## Port mapping

- With the below command we are running nginx on our local host port 90
```
docker run -p 80:80 nginx
```
- With the command below we have changed our nginx so that is shows on port 99 instead
of port 80
```
docker run -p 99:80 nginx
```

installation on ubuntu,
https://docs.docker.com/v17.09/engine/installation/linux/docker-ce/ubuntu/

Create a Docker image,
````
docker build -t <DockerImageName> -f <DockerFilePath> 
````
List Docker images (active or passive - not running),
````
docker image list
````

Remove a docker image,
````
docker rmi <ImageId>
````

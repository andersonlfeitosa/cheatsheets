## Docker

This is a little cheatsheet about [Docker](https://www.docker.com).

### Create a docker machine on your host system operation (you can change the driver)
```
docker-machine create --driver virtualbox default
```

### List all docker machines created
```
docker-machine ls
```

### Docker Registry Login using OpenShift credentials
```
docker login -u developer -p $(oc whoami -t) docker-registry-default.apps.cabal.com.br
```


### List images from internal docker registry
```
curl -X GET http://192.168.99.100:5000/v2/_catalog
```

### Check running containers
```
docker ps
docker ps -a 
```

### Remove container
```
docker rm -f container_name
docker rm -v $(docker ps -a -q -f status=exited)
```
### Tag container
```
docker tag my_image andersonlfeitosa/my_image
```

### Run Docker Registry
```
docker run -d -p 5000:5000 --name registry registry:2
docker run -d --name container_name --restart=always -p 8080:8080 image_name
```

### Remove images not used by containers
```
docker rmi $(docker images -f "dangling=true" -q)
```

### Build new images
```
docker build --no-cache -t remote_docker_registry:5000/ubuntu/my-image
docker build -t hello-app .
```

### Push new images
```
docker push remote_docker_registry:5000/ubuntu/my-image
```

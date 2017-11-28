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

### List images from internal docker registry
```
curl -X GET http://192.168.99.100:5000/v2/_catalog
```

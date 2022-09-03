# Docker cheatsheet
Docker cheatsheet commands for delete old images, limit memory use of logs, special run flags for GPU

## Image and containers memory management
View memory shared between containers:
```sh
$ sudo docker system df -v
```
Stop all containers:
```sh
$ sudo docker kill $(sudo docker ps -q)
```
Delete all stopped containers:
```sh
$ docker container prune
```
Delete old image without tag (unstage):
```sh
$ sudo docker rmi $(sudo docker images -f "dangling=true" -q) --force
```
Delete all image that start with a specific imagename:
```sh
$ docker rmi $(docker images | grep 'imagename') --force
```
Delete all images and containers not in use:
```sh
$ sudo docker system prune -a
```
Delete all images and containers without use in the last 6 month:
```sh
$ sudo docker system prune -a --filter "until=4320h" 
```

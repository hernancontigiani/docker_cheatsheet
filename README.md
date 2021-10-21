# Docker cheatsheet
Docker cheatsheet commands for delete old images, limit memory use of logs, special run flags for GPU

## Image and containers memory management
View memory shared between containers:
```sh
$ sudo docker system df -v
```
Delete old image without tag (unstage):
```sh
$ sudo docker rmi $(sudo docker images -f "dangling=true" -q) --force
```
Delete all images and containers not in use:
```sh
$ sudo docker system prune -a
```

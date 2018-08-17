# Docker Tips & Tricks

## All existing containers (not only running)

```
docker ps     - show only running 
docker ps -a  - show all containers
```
## Remove all containers with status=exited
when running a lot of container, can be case that exists list of containers which has status exited. Command below can help to remove it in one command.
```
docker rm $(docker ps -q -f status=exited)
```
## Stop all containers
```
docker stop $(docker ps -q)    - will run stop only for active
docker stop $(docker ps -aq) - will run stop for all
```
## Remove all docker images
```
docker rmi $(docker images -q)
don't forget image shouldn't have reference to container 
```
## Build image (from folder with Dockerfile)
In case if you want to create your own image use command below
```
docker build -t <image_name> .
```
## See logs in container
you can check logs of container. Use the following:
```
docker logs -f <container_name>
```
## Believe bash is your best friend
Manydeveloper or admins who are working close with command line create their own aliases for various commands. you can do it too, just make your working process easy. Just add these to your ~/.bashrc
```
#docker commands
alias dr='docker rm $(docker ps -aq)'
alias ds='docker stop $(docker ps -aq)'
alias di='docker images'
alias dri='docker rmi $(docker images -q)'
alias dsr='ds && dr'
alias dps='docker ps -a'
alias dcup='docker-compose up'
```
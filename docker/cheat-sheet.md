# Docker - Cheat Sheet

## Docker

### Containers
- Show running containers
    - `docker ps`
- Search container by name
    - `docker ps -a | grep "needle"`
- Stop all containers
    - `docker stop $(docker ps -a -q)`
- Stop all containers by name
    - `docker ps -a | grep "study" | awk '{print $1}' | xargs docker stop`
- Remove all stopped containers:
    - `docker rm $(docker ps -a -q)`
- Remove containers by search name
    - `docker ps -a | grep "needle" | awk '{print $1}' | xargs docker rm`
- Run container in shell
    - `docker exec -it <container_id> bash`
- Run command on container
    - Example: `docker exec <container_id> django-admin.py startproject composeexample .`
    - Example: `docker exec <container_id> web python manage.py migrate`
- Copy files from container to host
    - `docker cp container_id:/container/path/test ./test`
- Copy files from host to container
    - `docker cp test.txt container_id:/test.txt`
- Attach to container
    - `docker attach <container_id> --sig-proxy=false`

#### Images
- Show all images
    - `docker images`
- Search images by name
    - `docker images -a | grep "myname"`
- Remove all images
    - `docker rmi $(docker images -q)`
- Remove all <none> images
    - `docker rmi $(docker images | grep "^<none>" | awk "{print $3}")`
- Remove by search term
    - `docker images -a | grep "searchterm" | awk '{print $3}' | xargs docker rmi`
- Remove all dangling images
    - `docker images -q --filter "dangling=true" | xargs docker rmi`
- Remove image
    - `docker rmi <image id>`
- Build image
    - `docker build <imagename>`
- Build image with reporo+tag
    - `docker build -t <user>/<imagename>:<version> <path_to_image_dir>`
    Example:
        - `docker build -t marteinn/ansible-example-django:v1.0.0 django`
- Keep the five most recent versions of an image (excluding latest)
    - `docker images | grep marteinn/ansible-example-django | grep -v latest | sort -r | awk '{print "marteinn/ansible-example-django:"$2}' | tail -n +6 | xargs -n 1 docker rmi`

## Docker compose
- Start containers
    - `docker-compose up`
- Run command on container
    - `docker-compose run web django-admin.py startproject composeexample .`
    - `docker-compose run web python manage.py migrate`
- Show containers
    - `docker-compose ps`
- Stop all containers
    - `docker stop $(docker-compose ps -q)`
- Rebuild images
    - `docker-compose build`
- Remove all stopped containers
    - `docker rm $(docker-compose ps -q)`
- Get container id by compose name
    - `$(docker-compose ps -q <name>)`
- Run exec by compose name
    - `docker exec $(docker-compose ps -q <name>) ls -la`

## Docker-machine
- Create default virtualbox machine
    - `docker-machine create --driver virtualbox default`
- SSH into machine
    - `docker-machine ssh default`
- List machines
    - `docker-machine ls`
- Show machine ip
    - `docker-machine ip <name>`
- Run commands against machine
    - `eval "$(docker-machine env default)"`
- Resize virtualbox machine
    - `docker-machine stop`
    - `VBoxManage modifyvm default --memory 4096`
    - `VBoxManage modifyvm default --cpus 2`
    - `docker-machine start`
- Show available space
    - `docker-machine ssh`
    - `df -h`
- Run container with service ports exposed
    - `docker-compose run --service-ports <container_name>`

## References
- https://github.com/wsargent/docker-cheat-sheet

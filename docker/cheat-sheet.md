# Docker - Cheat Sheet

## Docker
- Show running containers
    - `docker ps`
- Stop all containers
    - `docker stop $(docker ps -a -q)`
- Show all images
    - `docker images`
- Remove all images
    - `docker rmi $(docker images -q)`
- Remove all containers
    - `docker rm $(docker ps -a -q)`
- Remove all dangling images
    - `docker images -q --filter "dangling=true" | xargs docker rmi`
- Remove all stopped containers:
    - `docker rm $(docker ps -a -q)`
- Remove image
    - `docker rmi <image id>`
- Build image
    - `docker build <imagename>`
- Build image with reporo+tag
    - `docker build -t <user>/<imagename>:<version> <path_to_image_dir>`
    Example:
        - `docker build -t marteinn/ansible-example-django:v1.0.0 django`
- Run container in shell
    - `docker exec -it <container_id> bash`
- Run command on container
    - Example: `docker exec <container_id> django-admin.py startproject composeexample .`
    - Example: `docker exec <container_id> web python manage.py migrate`
- Keep the five most recent versions of an image (excluding latest)
    - `docker images | grep marteinn/ansible-example-django | grep -v latest | sort -r | awk '{print "marteinn/ansible-example-django:"$2}' | tail -n +6 | xargs -n 1 docker rmi`


## Docker-machine
- Create default virtualbox machine
    - `docker-machine create --driver virtualbox default`
- `docker-machine ssh default`
- `docker-machine ls`
- Show machine ip
    - `docker-machine ip <name>`
- `eval "$(docker-machine env default)"`


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
- Remove containers
    - `docker rm $(docker-compose ps -q)`
- Get container id by compose name
    - `$(docker-compose ps -q <name>)`
- Run exec by compose name
    - `docker exec $(docker-compose ps -q <name>) ls -la`



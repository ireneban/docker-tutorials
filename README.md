# Docker Help

Docker란 리눅스 컨테이너를 기반으로 하여 특정한 서비스를 패키징하고 비포하는데 유용한 오픈소스 프로그램이다.  
기본적인 형태는 도커파일(Docker File)이라는 것을 만들어서 '나는 어떠한 소프트웨어를 컨테이너에 담아서 구동시킬 것이다.' 라는 것만 정확히 명시해주고 빌드를 해주면, 알아서 도커 이미지가 그에 맞게 생성이 된다.

# Docker Commands

### Show commands

`$ docker`

### Authentication

`$ docker login`

## CONTAINERS

### See running containers

`$ docker container ls`  
or
`$ docker ps`

### See all containers

`$ docker container ls -a`

### Create and run a container in foreground

`$ docker container run -it -p 80:80 <container name>`

### Create and run a container in background

`$ docker container run -d -p 80:80 <container name>`

### Give name to containers

`$ docker container run -d -p 80:80 --name <your container name> <container name>`

### Stop a container

`$ docker container stop <container name>`

### Stop all running containers

`$ docker container stop $(docker ps -aq)`

### Remove container

`$ docker container rm <containerID>`

### Remove a running container

`$ docker container rm -f <containerID>`

### Remove all containers

`docker rm $(docker ps -aq)`

## ACCESSING CONTAINERS

### Create new a container and bash into

`$ docker container run -it --name <your container name> <container name> bash`

## EXAMPLE OF BIND MOUNTS AND PUSHING INTO DOCKERHUB

### 1. Run and edit index.html file

`$ docker container run -d -p 8080:80 -v $(pwd):/usr/share/nginx/html --name nginx-website nginx`

### 2. Add index.html file and Dockerfile

```dockerfile
FROM nginx:latest

WORKDIR /usr/share/nginx/html

COPY . .
```

### 3. Build image based on Dockerfile that you just wrote

`$ docker image build -t halfundecided/nginx-website .`

### 4. Build and run a container from this image

`$ docker container run -d -p 8082:80 halfundecided/nginx-website`

### 5. Push this image to my Dockerhub

`$ docker push halfundecided/nginx-website`

# Docker Tutorials

## Intro

### Docker란?

Docker란 리눅스 컨테이너를 기반으로 하여 특정한 서비스를 패키징하고 비포하는데 유용한 오픈소스 프로그램이다.  
기본적인 형태는 도커파일(Docker File)이라는 것을 만들어서 '나는 어떠한 소프트웨어를 컨테이너에 담아서 구동시킬 것이다.' 라는 것만 정확히 명시해주고 빌드를 해주면, 알아서 도커 이미지가 그에 맞게 생성이 된다.

## Docker commands

- `docker container ls`: to see all containers
- `docker image ls`: to see all images
- `docker container rm <containerID>`: delete container
- `docker image rm <imageID>`: delete image

- `docker container run -d -p 8080:80 --name <myContainerName> <containerName>`: running container in background
- `docker ps`: see running containers

## Um pouquinho de Docker

1) Para visualizarmos a versão do Docker instalado em nosso sistema, basta usar o comando `docker --version`
```
docker --version 
Docker version 18.06.1-ce, build e68fc7a
```
2) Para ver mais informações, basta digitar o comando `docker info`
```
docker info 
Containers: 33
 Running: 3
 Paused: 0
 Stopped: 30
```
3) Agora vamos testar a instalação do Docker:
```
docker run hello-world

Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
d1725b59e92d: Already exists 
Digest: sha256:0add3ace90ecb4adbf7777e9aacf18357296e799f81cabc9fde470971e499788
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
```



## Agora, um exemplo básico usando Docker

#### Para esse primeiro contato com Docker, fiz a criação de um container com Debian 8, instalei o webserver Nginx, para mostrar a execução da página default do Nginx de dentro do container, ficou massa:

![Docker](images/docker1.png)

![Docker](images/docker.png)

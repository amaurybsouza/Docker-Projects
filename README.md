## Um pouquinho de Docker

Pessoal, nessa documentação serei bem direto ao ponto, "na prática mesmo" para que a galera entenda de forma rápida, os comandos sobre essa tecnologia que está facilitando e impactando a vide muitos profissionais.



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

4) Mostrando as nossas images que já temos no sistema:
```
docker images

REPOSITORY            TAG                 IMAGE ID            CREATED             SIZE
debian                latest              id_container        3 days ago          101MB
mamau/apache          1.0                 id_container        10 days ago         216MB
amaury/nginx-debian   1.0                 id_container        11 days ago         206MB
nginx                 latest              id_container        12 days ago         109MB
ubuntu                16.04               id_container        4 weeks ago         116MB
ubuntu                14.04               id_container        4 weeks ago         188MB
ubuntu                18.04               id_container        4 weeks ago         85.8MB
ubuntu                latest              id_container        4 weeks ago         85.8MB
debian                8                   id_container        4 weeks ago         127MB
centos                latest              id_container        5 weeks ago         200MB
hello-world           latest              id_container        2 months ago        1.84kB
```

- Outro comando interessante é o `docker ps` que mostra os containers que estão ativos no sistema, veja abaixo:
```
docker ps
CONTAINER ID    IMAGE         COMMAND          CREATED             STATUS              PORTS               NAMES
id_container    debian        "bash"           2 hours ago         Up 2 hours                              quirky_kare
id_container    ubuntu        "/bin/bash"      2 hours ago         Up 2 hours                              practical_jang
id_container    ubuntu:18.04  "/bin/bash"      24 hours ago        Up 24 hours                             goofy_varahamihira
```

- Agora irei demonstrar um exemplo de uso do comando `docker exec`:
```
docker exec id_container mkdir /tmp/Amaury
```

- Se acessarmos o container com o comando `docker attach id_container`, veremos que o diretório *Amaury* foi criado em /tmp
```
id_container:/tmp# ls
Amaury
```

- Um exemplo de utilização de container, confira abaixo:
```
docker run -ti fedora:28 /bin/bash
```

- Se essa imagem não existir localmente no sistema da minha máquina, ele irá fazer download do repositório do Docker no Docker Hub. Estamos usando apenas um processo, que  o /bin/bash

- Repare que estamos agora dentro do container:
```
[root@id_container /]# cat /etc/os-release 
NAME=Fedora
VERSION="28 (Twenty Eight)"
ID=fedora
VERSION_ID=28
PLATFORM_ID="platform:f28"
PRETTY_NAME="Fedora 28 (Twenty Eight)"
ANSI_COLOR="0;34"
CPE_NAME="cpe:/o:fedoraproject:fedora:28"
HOME_URL="https://fedoraproject.org/"
SUPPORT_URL="https://fedoraproject.org/wiki/Communicating_and_getting_help"
BUG_REPORT_URL="https://bugzilla.redhat.com/"
REDHAT_BUGZILLA_PRODUCT="Fedora"
REDHAT_BUGZILLA_PRODUCT_VERSION=28
REDHAT_SUPPORT_PRODUCT="Fedora"
REDHAT_SUPPORT_PRODUCT_VERSION=28
PRIVACY_POLICY_URL="https://fedoraproject.org/wiki/Legal:PrivacyPolicy"
```
## Agora, um exemplo básico usando Docker

Para esse primeiro contato com Docker, fiz a criação de um container com Debian 8, instalei o webserver Nginx, para mostrar a execução da página default do Nginx de dentro do container, ficou massa:

![Docker](images/docker1.png)

![Docker](images/docker.png)

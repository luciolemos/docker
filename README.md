# Hey! 👤

[![Github Badge](https://img.shields.io/badge/-Github-000?style=flat-square&logo=Github&logoColor=white&link=https://github.com/luciolemos)](https://github.com/luciolemos)
[![Linkedin Badge](https://img.shields.io/badge/-LinkedIn-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/lucio-lemos-a550441a1/)](https://www.linkedin.com/in/lucio-lemos-a550441a1/)
[![Twitter Badge](https://img.shields.io/badge/-Twitter-1ca0f1?style=flat-square&labelColor=1ca0f1&logo=twitter&logoColor=white&link=https://twitter.com/lucciolemos)](https://twitter.com/lucciolemos)
[![Youtube Badge](https://img.shields.io/badge/-YouTube-ff0000?style=flat-square&labelColor=ff0000&logo=youtube&logoColor=white&link=https://studio.youtube.com/channel/UCrNM1nr2nw0lSqMD10m6rLw)](#)
## 1ª Parte
### Listando e removendo diretórios para refazer o projeto

#### ✔️ Mostrando o diretótio corrente:
    luciolemos@dev:~$ pwd
    /home/luciolemos
#### ✔️ Listando arquivos/diretórios em `luciolemos`:
    luciolemos@dev:~$ ls -l
    total 16
    drwxr-xr-x 2 luciolemos luciolemos 4096 Apr  6 20:24 my_documents
    drwxr-xr-x 2 luciolemos luciolemos 4096 May  8 08:59 my_downloads
    drwxr-xr-x 2 luciolemos luciolemos 4096 Apr  6 20:26 my_exemples
    drwxr-xr-x 3 luciolemos luciolemos 4096 May  2 09:53 my_projects
#### ✔️ Navegando para a raís de `my_projects`:
    luciolemos@dev:~$ cd my_projects
    luciolemos@dev:~/my_projects$
#### ✔️ Listando arquivos/diretórios existentes em `my_projects`:
    luciolemos@dev:~/my_projects$ ls -l
    total 4
    drwxr-xr-x 3 luciolemos luciolemos 4096 May  8 09:23 docker_projects
#### ✔️ Navegando para a raís de `my_docker_projects`:
    luciolemos@dev:~/my_projects$ cd docker_projects
    luciolemos@dev:~/my_projects/docker_projects$
#### ✔️ Listando arquivos/diretórios em `my_docker_projects`:
    luciolemos@dev:~/my_projects/docker_projects$ ls -l
    total 4
    drwxr-xr-x 6 luciolemos luciolemos 4096 May  8 09:23 getting-started
#### ✔️ Removendo com  `rm` o diretório `getting-started`: 
    luciolemos@dev:~/my_projects/docker_projects$ sudo rm -r getting-started
    [sudo] password for luciolemos:
#### ✔️ Listando novamente arquivos/diretórios em `docker_projects`:
    luciolemos@dev:~/my_projects/docker_projects$ ls -l
    total 0
## 2ª Parte
### Listando os serviços em execução e "startando" o docker:
#### ✔️ Verificando o status dos serviços com `service --status-all`:
    luciolemos@dev:~/my_projects/docker_projects$ service --status-all
     [ - ]  apparmor
     [ - ]  docker
     [ ? ]  hwclock.sh
#### ✔️ Startando o serviço `docker`:
    luciolemos@dev:~/my_projects/docker_projects$ sudo service docker start
     * Starting Docker: docker [ OK ]
#### ✔️ Verificando se o serviço `docker` foi corretamente iniciado: 
    luciolemos@dev:~/my_projects/docker_projects$ service --status-all
     [ - ]  apparmor
     [ + ]  docker
     [ ? ]  hwclock.sh
## 3ª Parte
### Listando e removendo imagens e container existentes para refazer o projeto
#### ✔️ Listando as ` docker images` instaladas: 
    luciolemos@dev:~/my_projects/docker_projects$ docker images
    REPOSITORY        TAG       IMAGE ID       CREATED       SIZE
    getting-started   latest    0f375ca4f10e   5 hours ago   383MB
#### ✔️ Listando os containers instalados:
    luciolemos@dev:~/my_projects/docker_projects$ docker ps -a
    CONTAINER ID   IMAGE             COMMAND                  CREATED       STATUS                       PORTS                    NAMES
    78c4bac8bd1f   getting-started   "docker-entrypoint.s…"   4 hours ago   Exited (255) 2 minutes ago   0.0.0.0:3000->3000/tcp   sharp_rhodes
#### ✔️ Removendo o container de `ID 78c4bac8bd1f`:
    luciolemos@dev:~/my_projects/docker_projects$ docker rm 78c4bac8bd1f
    78c4bac8bd1f
#### ✔️ Removendo a imagem `ID 0f375ca4f10e`:
    luciolemos@dev:~/my_projects/docker_projects$ docker rmi 0f375ca4f10e
    Untagged: getting-started:latest
    Deleted: sha256:0f375ca4f10ed3dc43a24ff05f3f8df1a421b991d2dbb226c79f6e9715a7d612
#### ✔️ Listando novamente os containers:  
    luciolemos@dev:~/my_projects/docker_projects$ docker ps -a
    CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
#### ✔️ Listando novamente as imagens:
    luciolemos@dev:~/my_projects/docker_projects$ docker images
    REPOSITORY   TAG       IMAGE ID   CREATED   SIZE
#### ✔️ Removendo imagens e containers com `docker system prune -a`:
    luciolemos@dev:~$ docker system prune -a
    WARNING! This will remove:
    - all stopped containers
    - all networks not used by at least one container
    - all images without at least one container associated to them
    - all build cache

    Are you sure you want to continue? [y/N] y
## 4ª Parte
### Clonando o projeto
#### ✔️ Clonando o projeto de exemplo do repositório remoto com `git clone`:
    luciolemos@dev:~/my_projects/docker_projects$ git clone https://github.com/docker/getting-started.git
    Cloning into 'getting-started'...
    remote: Enumerating objects: 479, done.
    remote: Counting objects: 100% (17/17), done.
    remote: Compressing objects: 100% (12/12), done.
    remote: Total 479 (delta 8), reused 11 (delta 5), pack-reused 462
    Receiving objects: 100% (479/479), 3.68 MiB | 1.65 MiB/s, done.
    Resolving deltas: 100% (241/241), done.
#### ✔️ Listando arquivos/diretórios em `docker_projects`, verificamos a existência do diretório `getting-started`:
    luciolemos@dev:~/my_projects/docker_projects$ ls -l
    total 4
    drwxr-xr-x 6 luciolemos luciolemos 4096 May  9 05:53 getting-started
#### ✔️ Navegando para dentro de `getting-started`:
    luciolemos@dev:~/my_projects/docker_projects$ cd getting-started
#### ✔️ Listando arquivos/diretórios existentes em `getting-started`, verificamos a existência do diretório `app`:
    luciolemos@dev:~/my_projects/docker_projects/getting-started$ ls -l
    total 52
    -rw-r--r-- 1 luciolemos luciolemos  1004 May  9 05:53 Dockerfile
    -rw-r--r-- 1 luciolemos luciolemos   535 May  9 05:53 Jenkinsfile
    -rw-r--r-- 1 luciolemos luciolemos 11356 May  9 05:53 LICENSE
    -rw-r--r-- 1 luciolemos luciolemos  1668 May  9 05:53 README.md
    drwxr-xr-x 4 luciolemos luciolemos  4096 May  9 05:53 app
    -rwxr-xr-x 1 luciolemos luciolemos   253 May  9 05:53 build.sh
    -rw-r--r-- 1 luciolemos luciolemos   167 May  9 05:53 docker-compose.yml
    drwxr-xr-x 6 luciolemos luciolemos  4096 May  9 05:53 docs
    -rw-r--r-- 1 luciolemos luciolemos  1990 May  9 05:53 mkdocs.yml
    -rw-r--r-- 1 luciolemos luciolemos   105 May  9 05:53 requirements.txt
    -rw-r--r-- 1 luciolemos luciolemos    86 May  9 05:53 yarn.lock
#### ✔️ Navegando para dentro do diretório `app` do projeto:
    luciolemos@dev:~/my_projects/docker_projects/getting-started$ cd app
#### ✔️ Listando arquivos/diretórios em `app`:
    luciolemos@dev:~/my_projects/docker_projects/getting-started/app$ ls -l
    total 188
    -rw-r--r-- 1 luciolemos luciolemos    626 May  9 05:53 package.json
    drwxr-xr-x 4 luciolemos luciolemos   4096 May  9 05:53 spec
    drwxr-xr-x 5 luciolemos luciolemos   4096 May  9 05:53 src
    -rw-r--r-- 1 luciolemos luciolemos 179361 May  9 05:53 yarn.lock
#### ✔️ Criando na raís do projeto o arquivo `Dockerfile`:
    luciolemos@dev:~/my_projects/docker_projects/getting-started/app$ touch Dockerfile
#### ✔️ Listando novamente arquivos/diretórios, veremos que foi criado na raís do projeto, o arquivo `Dockerfile`:
    luciolemos@dev:~/my_projects/docker_projects/getting-started/app$ ls -l
    total 188
    -rw-r--r-- 1 luciolemos luciolemos      0 May  9 09:46 Dockerfile
    -rw-r--r-- 1 luciolemos luciolemos    626 May  9 09:45 package.json
    drwxr-xr-x 4 luciolemos luciolemos   4096 May  9 09:45 spec
    drwxr-xr-x 5 luciolemos luciolemos   4096 May  9 09:45 src
    -rw-r--r-- 1 luciolemos luciolemos 179361 May  9 09:45 yarn.lock
 #### ✔️ Criando o arquivo `README.md`, adicionando `README.md` ao arquivo de índices, inicializando, adicionando, commitando e pushando com git:
    echo "# docker" >> README.md
    git init
    git add README.md
    git commit -m "first commit"
    git branch -M main
    git remote add origin https://github.com/luciolemos/docker.git
    git push -u origin main
#### ✔️ Abrindo o projeto `app` com o VSCode:
    luciolemos@dev:~/my_projects/docker_projects/getting-started/app$ code .
## 5ª Parte
### Configurando o `Dockerfile`, criando imagem, criando o container, 
#### ✔️ Acrescente ao arquivo `Dockerfile` o seguinte bloco de código:
    # syntax=docker/dockerfile:1
    FROM node:12-alpine
    RUN apk add --no-cache python g++ make
    WORKDIR /app
    COPY . .
    RUN yarn install --production
    CMD ["node", "src/index.js"]

#### ✔️ Criando a imagem. Este comando usa o Dockerfile para construir uma nova imagem de contêiner.
O "."  no final do comando  `docker build`, informa que o Docker deve procurar o arquivo `Dockerfile` no diretório atual.

    luciolemos@dev:~/my_projects/docker_projects/getting-started/app$ docker build -t getting-started  .
#### ✔️ Inicie o  contêiner usando o comando `docker run` referenciado a imagem  `getting-started`, criada no passo anterior:
    luciolemos@dev:~/my_projects/docker_projects/getting-started/app$ docker run -dp 3000:3000 getting-started

     luciolemos@dev:~/my_projects/docker_projects/getting-started/app$ docker run -dp 3000:3000 getting-started
    38ab9af111173d2ed7622e805da83526c5e576e8850859e54530e54a674d2d8f
    
    luciolemos@dev:~/my_projects/docker_projects/getting-started/app$ docker ps
    CONTAINER ID   IMAGE             COMMAND                  CREATED          STATUS          PORTS                                       NAMES
    38ab9af11117   getting-started   "docker-entrypoint.s…"   21 minutes ago   Up 21 minutes   0.0.0.0:3000->3000/tcp, :::3000->3000/tcp   gallant_meninsky
    l
    uciolemos@dev:~/my_projects/docker_projects/getting-started/app$ docker images
    REPOSITORY        TAG         IMAGE ID       CREATED       SIZE
    getting-started   latest      cd7de3b48f41   7 hours ago   385MB
    node              12-alpine   deeae3752431   3 weeks ago   88.9MB
    
    luciolemos@dev:~/my_projects/docker_projects/getting-started/app$
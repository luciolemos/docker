# Hey! 馃懁

[![Github Badge](https://img.shields.io/badge/-Github-000?style=flat-square&logo=Github&logoColor=white&link=https://github.com/luciolemos)](https://github.com/luciolemos)
[![Linkedin Badge](https://img.shields.io/badge/-LinkedIn-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/lucio-lemos-a550441a1/)](https://www.linkedin.com/in/lucio-lemos-a550441a1/)
[![Twitter Badge](https://img.shields.io/badge/-Twitter-1ca0f1?style=flat-square&labelColor=1ca0f1&logo=twitter&logoColor=white&link=https://twitter.com/lucciolemos)](https://twitter.com/lucciolemos)
[![Youtube Badge](https://img.shields.io/badge/-YouTube-ff0000?style=flat-square&labelColor=ff0000&logo=youtube&logoColor=white&link=https://studio.youtube.com/channel/UCrNM1nr2nw0lSqMD10m6rLw)](#)
# Parte - I
## Listando e removendo diret贸rios para refazer o projeto
### 鉁旓笍 Mostrando o diret贸tio corrente com o comando `$ pwd`:
    luciolemos@dev:~$ pwd
    /home/luciolemos
### 鉁旓笍 Listando arquivos/diret贸rios em `luciolemos` com o comando `$ ls -l`:
    luciolemos@dev:~$ ls -l
    total 16
    drwxr-xr-x 2 luciolemos luciolemos 4096 Apr  6 20:24 my_documents
    drwxr-xr-x 2 luciolemos luciolemos 4096 May  8 08:59 my_downloads
    drwxr-xr-x 2 luciolemos luciolemos 4096 Apr  6 20:26 my_exemples
    drwxr-xr-x 3 luciolemos luciolemos 4096 May  2 09:53 my_projects
### 鉁旓笍 Navegando para a ra铆s de `my_projects` com change diretory `$ cd`:
    luciolemos@dev:~$ cd my_projects
    luciolemos@dev:~/my_projects$
### 鉁旓笍 Listando arquivos/diret贸rios existentes em `my_projects`:
    luciolemos@dev:~/my_projects$ ls -l
    total 4
    drwxr-xr-x 3 luciolemos luciolemos 4096 May  8 09:23 docker_projects
### 鉁旓笍 Navegando para a ra铆s de `docker_projects`:
    luciolemos@dev:~/my_projects$ cd docker_projects
    luciolemos@dev:~/my_projects/docker_projects$
### 鉁旓笍 Listando arquivos/diret贸rios em `docker_projects`:
    luciolemos@dev:~/my_projects/docker_projects$ ls -l
    total 4
    drwxr-xr-x 6 luciolemos luciolemos 4096 May  8 09:23 getting-started
### 鉁旓笍 Removendo com  `$ rm` o diret贸rio `getting-started`: 
    luciolemos@dev:~/my_projects/docker_projects$ sudo rm -r getting-started
    [sudo] password for luciolemos:
### 鉁旓笍 Removendo com  `$ rm -rf` todo o cote煤do do diret贸rio, inclusive diret贸rios ocultos: 
    luciolemos@dev:~/my_projects/docker_projects$ sudo rm -rf /home/luciolemos//my_projects/docker_projects/ *
    [sudo] password for luciolemos:   
   
#### 鉁旓笍 Listando novamente arquivos/diret贸rios em `docker_projects`:
    luciolemos@dev:~/my_projects/docker_projects$ ls -l
    total 0
# Parte - II
## Listando os servi莽os em execu莽茫o e "startando" o docker:
### 鉁旓笍 Verificando o status dos servi莽os com `$ service --status-all`:
    luciolemos@dev:~/my_projects/docker_projects$ service --status-all
     [ - ]  apparmor
     [ - ]  docker
     [ ? ]  hwclock.sh
### 鉁旓笍 Startando o servi莽o `docker` com `$ sudo service docker start`:
    luciolemos@dev:~/my_projects/docker_projects$ sudo service docker start
     * Starting Docker: docker [ OK ]
### 鉁旓笍 Verificando se o servi莽o `docker` foi corretamente iniciado com `$ service --status-all`: 
    luciolemos@dev:~/my_projects/docker_projects$ service --status-all
     [ - ]  apparmor
     [ + ]  docker
     [ ? ]  hwclock.sh
# Parte - III
## Listando e removendo imagens e container existentes para refazer o projeto
### 鉁旓笍 Listando as ` docker images` instaladas com `$ docker images`: 
    luciolemos@dev:~/my_projects/docker_projects/getting-started/app$ docker images
    REPOSITORY   TAG       IMAGE ID       CREATED              SIZE
    app          latest    268cc5123b5a   About a minute ago   386MB
### 鉁旓笍 Listando todos os containers instalados, ativos (em execu莽茫o) ou n茫o, com `$ docker ps -a`:
    luciolemos@dev:~/my_projects/docker_projects$ docker ps -a
    CONTAINER ID   IMAGE     COMMAND                  CREATED       STATUS       PORTS                                       NAMES
    3f3ff603e9d0   app       "docker-entrypoint.s鈥?"   3 hours ago   Up 3 hours   0.0.0.0:3000->3000/tcp, :::3000->3000/tcp   epic_joliot
### 鉁旓笍 Parando um container em execu莽茫o, com `$ docker stop <CONTAINER ID>`, antes de remov锚-lo:
    luciolemos@dev:~/my_projects/docker_projects$ docker stop 3f3ff603e9d0 
    3f3ff603e9d0 
### 鉁旓笍 Removendo o container de `ID 3f3ff603e9d0` com a CLI `$ docker rm <CONTAINER ID>`:
    luciolemos@dev:~/my_projects/docker_projects$ docker rm 3f3ff603e9d0
    3f3ff603e9d0
### 鉁旓笍 Removendo a imagem `ID 268cc5123b5a` com a CLI `$ docker rmi <IMAGE ID>`::
    luciolemos@dev:~/my_projects/docker_projects$ docker rmi 268cc5123b5a
    Untagged: getting-started:latest
    Deleted: sha256:0f375ca4f10ed3dc43a24ff05f3f8df1a421b991d2dbb226c79f6e9715a7d612
### 鉁旓笍 Listando novamente os containers:  
    luciolemos@dev:~/my_projects/docker_projects$ docker ps -a
    CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
### 鉁旓笍 Listando novamente as imagens:
    luciolemos@dev:~/my_projects/docker_projects$ docker images
    REPOSITORY   TAG       IMAGE ID   CREATED   SIZE
### 鉁旓笍 Removendo imagens e containers com `$ docker system prune -a`:
    luciolemos@dev:~$ docker system prune -a
    WARNING! This will remove:
    - all stopped containers
    - all networks not used by at least one container
    - all images without at least one container associated to them
    - all build cache

    Are you sure you want to continue? [y/N] y
# Parte - IV
## Clonando o projeto
### 鉁旓笍 Clonando o projeto de exemplo do reposit贸rio remoto com `$ git clone <URL>`:
    luciolemos@dev:~/my_projects/docker_projects$ git clone https://github.com/docker/getting-started.git
    Cloning into 'getting-started'...
    remote: Enumerating objects: 479, done.
    remote: Counting objects: 100% (17/17), done.
    remote: Compressing objects: 100% (12/12), done.
    remote: Total 479 (delta 8), reused 11 (delta 5), pack-reused 462
    Receiving objects: 100% (479/479), 3.68 MiB | 1.65 MiB/s, done.
    Resolving deltas: 100% (241/241), done.
### 鉁旓笍 Listando arquivos/diret贸rios em `docker_projects`, verificamos a exist锚ncia do diret贸rio `getting-started`:
    luciolemos@dev:~/my_projects/docker_projects$ ls -l
    total 4
    drwxr-xr-x 6 luciolemos luciolemos 4096 May  9 05:53 getting-started
### 鉁旓笍 Navegando para dentro de `getting-started`:
    luciolemos@dev:~/my_projects/docker_projects$ cd getting-started
### 鉁旓笍 Listando arquivos/diret贸rios existentes em `getting-started`, verificamos a exist锚ncia do diret贸rio `app`:
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
### 鉁旓笍 Navegando para dentro do diret贸rio `app` do projeto:
    luciolemos@dev:~/my_projects/docker_projects/getting-started$ cd app
### 鉁旓笍 Listando arquivos/diret贸rios em `app`:
    luciolemos@dev:~/my_projects/docker_projects/getting-started/app$ ls -l
    total 188
    -rw-r--r-- 1 luciolemos luciolemos    626 May  9 05:53 package.json
    drwxr-xr-x 4 luciolemos luciolemos   4096 May  9 05:53 spec
    drwxr-xr-x 5 luciolemos luciolemos   4096 May  9 05:53 src
    -rw-r--r-- 1 luciolemos luciolemos 179361 May  9 05:53 yarn.lock
### 鉁旓笍 Criando na ra铆s do projeto o arquivo `Dockerfile`:
    luciolemos@dev:~/my_projects/docker_projects/getting-started/app$ touch Dockerfile
### 鉁旓笍 Listando novamente arquivos/diret贸rios, veremos que foi criado na ra铆s do projeto, o arquivo `Dockerfile`:
    luciolemos@dev:~/my_projects/docker_projects/getting-started/app$ ls -l
    total 188
    -rw-r--r-- 1 luciolemos luciolemos      0 May  9 09:46 Dockerfile
    -rw-r--r-- 1 luciolemos luciolemos    626 May  9 09:45 package.json
    drwxr-xr-x 4 luciolemos luciolemos   4096 May  9 09:45 spec
    drwxr-xr-x 5 luciolemos luciolemos   4096 May  9 09:45 src
    -rw-r--r-- 1 luciolemos luciolemos 179361 May  9 09:45 yarn.lock
 ### 鉁旓笍 Criando o arquivo `README.md`, adicionando `README.md` ao arquivo de 铆ndices, inicializando, adicionando, commitando e pushando com git:
 O bloco de c贸digo a seguir 茅 gerado por ocasi茫o da cria莽茫o do reposit贸rio remoto no github:


    echo "# docker" >> README.md
    git init
    git add README.md
    git commit -m "first commit"
    git branch -M main
    git remote add origin https://github.com/luciolemos/docker.git
    git push -u origin main
### 鉁旓笍 Abrindo o projeto `app` com o VSCode:
    luciolemos@dev:~/my_projects/docker_projects/getting-started/app$ code .
# Parte - V
## Configurando o `Dockerfile`, criando a imagem, criando o container, ...
### 鉁旓笍 Acrescente ao arquivo `Dockerfile` o seguinte bloco de c贸digo:
    # syntax=docker/dockerfile:1
    FROM node:12-alpine
    RUN apk add --no-cache python g++ make
    WORKDIR /app
    COPY . .
    RUN yarn install --production
    CMD ["node", "src/index.js"]

### 鉁旓笍 Criando a imagem. Este comando usa o Dockerfile para construir uma nova imagem de cont锚iner.
O "."  no final do comando  `docker build`, informa que o Docker deve procurar o arquivo `Dockerfile` no diret贸rio atual.

    luciolemos@dev:~/my_projects/docker_projects/getting-started/app$ docker build -t app  .
### 鉁旓笍 Inicie o  cont锚iner usando o comando `docker run` referenciando a imagem  `app`, criada no passo anterior:
    luciolemos@dev:~/my_projects/docker_projects/getting-started/app$ docker run -dp 3000:3000 app
    38ab9af111173d2ed7622e805da83526c5e576e8850859e54530e54a674d2d8f
### 鉁旓笍 Listando os containers    
    luciolemos@dev:~/my_projects/docker_projects/getting-started/app$ docker ps -a
    CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS         PORTS                    NAMES
    aee7d3183e6c   app       "docker-entrypoint.s鈥?"   3 minutes ago   Up 3 minutes   0.0.0.0:3000->3000/tcp   cool_albattani
### 鉁旓笍 Listando as imagens
    luciolemos@dev:~/my_projects/docker_projects/getting-started/app$ docker images
    REPOSITORY   TAG       IMAGE ID       CREATED              SIZE
    app          latest    268cc5123b5a   About a minute ago   386MB
### 鉁旓笍 Ao iniciar um novo container, se houver ainda algum container em excu莽茫o na porta 3000, o seguinte erro ser谩 retornado:
    luciolemos@dev:~/my_projects/docker_projects/getting-started/app$ docker run -dp 3000:3000 app
    f4d0b2712feeb006917cd33b26d8f46b1f94452b4adcece15b04b9f06ef87b08
    docker: Error response from daemon: driver failed programming external connectivity on endpoint dreamy_elion (03345e8c6a3ee5048e7ef1e928acffd17d52c252ac179eaa4fc67f5ac7406367): Bind for 0.0.0.0:3000 failed: port is already allocated.
### 鉁旓笍 Atualize o navegador: http://localhost:3000

# Parte - VI
## Logando, renomeando a imagem , enviando imagem para registro:
### 鉁旓笍 Logando no docker via terminal
    luciolemos@dev:~/my_projects/docker_projects/getting-started/app$ docker login -u luciolemos
    Password: Diferent@1968
    Login Succeeded
### 鉁旓笍 Realizando o push da imagem. 
Repare que a 煤ltima linha do bloco de c贸digo abixo nos informa que a imagem `app` n茫o existe em nosso reposit贸rio local. 


    luciolemos@dev:~/my_projects/docker_projects/getting-started/app$ docker push luciolemos/app
    Using default tag: latest
    The push refers to repository [docker.io/luciolemos/app]
    An image does not exist locally with the tag: luciolemos/app
### 鉁旓笍 Renomeie a imagem local para `luciolemos/app`.
O comando a seguir `$ docker tag app luciolemos/app`,  renomeia a imagem no reposit贸rio  local de `app` para `luciolemos/app`.


    luciolemos@dev:~/my_projects/docker_projects/getting-started/app$ docker tag app luciolemos/app
### 鉁旓笍Execute novamente o push da imagem
    luciolemos@dev:~/my_projects/docker_projects/getting-started/app$ docker push luciolemos/app
    Using default tag: latest
    The push refers to repository [docker.io/luciolemos/app]
    64083c9fc6fb: Pushed 
    11d1b3c527c5: Pushed 
    b33a09848dc5: Pushed 
    679a91a094bb: Pushed 
    c29549fbad68: Mounted from library/node 
    efc48a5f6f42: Mounted from library/node 
    33816ea3af7a: Mounted from library/node 
    9a5d14f9f550: Mounted from library/node 
    latest: digest: sha256:ad1468f274c3a055e067b2aafb7727e4f694f5efc8ee222e1199d61a7867a1cf size: 2000
   
    luciolemos@dev:~/my_projects/docker_projects/getting-started/app$ 

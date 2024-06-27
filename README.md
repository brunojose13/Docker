<h3>Configuração</h3>

<p>Para configurar seu ambiênte utilizando docker, siga os passos abaixo:</p>

NO DIRETORIO RAIZ DO SEU PROJETO LARAVEL
1) Execute o comando: 
    $ git clone git@github.com:brunojose13/docker.git

2) Crie e/ou configure o seu arquivo .env.
    Caso ainda não tenha criado, execute o comando: $ cp .env.example .env

3) Execute os comandos: 
    $ cp docker/Dockerfile Dockerfile 
        && cp docker/docker-compose.yml docker-compose.yml 
        && rm -rf docker

4) Para criar/iniciar um container docker:
    $ docker-compose up -d

5) Instale as dependencias do laravel em seu projeto utilizando docker:
    $ docker exec php composer install

6) Para trabalhar com o servidor artisan, execute o seguinte comando:
    $ docker exec php php artisan serve --host=0.0.0.0 --port=8000

7) Caso precisar iniciar novamente o servidor artisan, execute os seguintes comandos:
    $ docker-compose stop 
        && docker-compose up -d 
        && docker restart php
        && docker exec php php artisan serve --host=0.0.0.0 --port=8000


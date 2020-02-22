# B3 Devops - Projet 1

Team 10

## Info

mail: florian.armenoult@ynov.com
github_username: Floo42

mail: matthieu.dabin@ynov.com
github_username: Coolcall

## Objectif

Le but du projet est d'automatiser la création d'une image Docker lorsque l'on réalise un push Github.

L'image que l'on crée contient une API NodeJs qui retourne des informations selon l'URL utilisée.

## Prérequis

-   Docker

-   Docker compose

-   Un shell (ex: powershell)

-   CircleCi

## Installation

L'installation du projet s'effectue à partir d'un shell via la commande :

`docker pull florianarmenoult/projet1-team-10`

Ensuite, pour lancer seulement l'API on utilise la commande :

`docker run -p 3000:3000 florianarmenoult/projet1-team-10`

Pour lancer le projet en entier on utilise la commande :

`docker run florianarmenoult/projet1-team-10`

## URL

`localhost/` → Page de base de nginx

`localhost/api` → Page de l'API

`localhost/api/status` → Page spécifique de l'API qui retourne le nombre d'utilisateur connecté et l'heure de connection

## CircleCi

`docker-compose -f docker-compose.yml build --compress --force-rm --no-cache --pull --parallel` : build de l'image

`docker tag project_api florianarmenoult/projet1-team-10:latest` : renommage de l'image

`echo $DOCKER_PASSWORD | base64 --decode | docker login -u $DOCKER_USER --password-stdin docker push florianarmenoult/projet1-team-10:latest` : Publication de l'image sur Dockerhub

## Liens

DockerHub : https://hub.docker.com/r/florianarmenoult/projet1-team-10
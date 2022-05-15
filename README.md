# TABSISSI_Hamdy_ASI-3-22-SR-D_2022_Docker

# Projet Docker avec une architecture backend / frontend
## OBJECTIF

1. Récupérer le projet API REST qui comporte une partie backend (API rest) et une partie
frontend (reactJS) : deux dossiers backend et frontend
2. Créer un/des fichier(s) DockerFile(s) pour builder notre image pour les serveurs de
production
3. Créer un fichier docker-compose.yml pour démarrer nos containers, nos services
4. Modifier la documentation qui va expliquer le contenu de ces deux fichiers et de
l’architecture dans un fichier README.md :
- DockerFile(s) pour builder notre image
- Docker-compose pour démarrer le(s) container(s) (Bien décrire l’ensemble des
différentes étapes d’exécution des commandes associés aux services)
- Architecture de l’application

## /backend/Dockerfile
```FROM node:14

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 8080

CMD ["npm","start"] 
```

## /frontend/Dockerfile

```FROM node:alpine as builder
WORKDIR /frontend
COPY ./package.json /frontend
RUN npm install
COPY . .
CMD [ "npm", "run", "start" ] 
```

![alt text](archi_project.png)


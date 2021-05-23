# Infrastructure de développement

## 1. Prérequis

- Avoir Docker d'installer sur son système ([ lien d'installation ](https://docs.docker.com/engine/install/))

- Avoir docker-compose d'installer sur son système ([ lien d'installation ](https://docs.docker.com/compose/install/))

## 2. Introduction

Ce projet permet d'initialiser les **Bases de Données** nécéssaire au développement de différents projets ainsi que leurs **interfaces d'aminitsitration**.

Tout sera administré via les commandes **docker** ou **docker-compose**.

## 3. installation

### *3.1 Networks*

Après avoir cloné le repo, il sera nécessaire de créer les différents **networks** que nos **containers**  vont tuliser

```bash
docker network create proxy_bridge \
&& docker network create mariadb_bridge \
&& docker network create mongodb_bridge \
&& docker network create postgres_bridge
```

### *3.2 Création du `.env` et paramétrage des variables*

Duppliquer les fichier `.env.sample` et le renomer en `.env` puis remplacer les valeurs des variable par les votre

### *3.3 Création et démarrage des containers*

Une fois les networks créés et variables paramétrées, il faudra alors démarrer les services

```bash
docker-compose up -d
```

## 4. Les services

### *4.1 Traefik*

Sert de *reverse proxy*, il permet d'accéder aux conteneurs via un nom de domaine. 
Vous pouvez accéder à l'interface de suivi ici : [traefik.docker.localhost](http://traefik.docker.localhost)


### *4.2 Portainer*

Permet de gérer vos conteneurs graphiqement via : [portainer.docker.localhost](http://portainer.docker.localhost)

### *4.3 PhpMyAdmin*

Permet de gérer vos base de données MySQL, vous pouvez accéder à l'interface ici : [myadmin.docker.localhost](http://myadmin.docker.localhost)

| Champ        | Valeur           |
| ------------ | ---------------- |
| Serveur      | _vide_           |
| Utilisateur  | Votre username   |
| Mot de passe | Votre password   |

### *4.4 MongoExpress*

Permet de gérer vos base de données MySQL, vous pouvez accéder à l'interface ici : [mongoadmin.docker.localhost](http://mongoadmin.docker.localhost)

### *4.4 PostGresAdmin*

Permet de gérer vos base de données Postgres, vous pouvez accéder à l'interface ici : [pgadmin.docker.localhost](http://pgadmin.docker.localhost)

| Champ    | Valeur              |
| -------- | ------------------- |
| Login    | Votre email         |
| Password | admin               |








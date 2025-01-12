# Projet Grafana : Déploiement de Grafana

## Description
Ceci est un petit projet Grafana conçu pour déployer une instance Grafana à l'aide de Docker. L'objectif est de fournir une base simple et fonctionnelle pour intégrer Grafana dans d'autres projets. 

Grafana est un outil open-source puissant pour la visualisation de données et la surveillance, souvent utilisé avec des bases de données comme Prometheus, Elasticsearch, ou InfluxDB. Il permet de créer des tableaux de bord interactifs pour analyser vos métriques en temps réel.

---

## Contenu du projet

### Docker Compose Configuration
Voici les points clés du fichier `docker-compose.yml` utilisé :

- **Service Grafana** :
  - Image utilisée : `grafana/grafana:10.2.2` (disponible sur Docker Hub).
  - Port exposé : `3000`, accessible via `http://localhost:3000`.
  - Volumes mappés :
    - `/var/lib/grafana` pour les données persistantes de Grafana.
    - `/var/logs/grafana` pour les journaux.
    - `/var/lib/grafana/plugins` pour les plugins installés.
  - Réseau : Défini par `monprojetgrafana` pour une isolation entre services.

---

## Comment démarrer le projet

### Prérequis
1. **Installer Docker** :
   Assurez-vous que Docker et Docker Compose sont installés sur votre système.
   - [Guide d'installation Docker](https://docs.docker.com/get-docker/)
   - [Guide d'installation Docker Compose](https://docs.docker.com/compose/install/)

2. **Configurer les permissions des volumes** :
   - Avant de lancer Grafana, assurez-vous que les répertoires mappés disposent des bonnes permissions :
     
     sudo chmod -R 777 ./data
    

### Lancer Grafana
1. **Cloner le projet** :

   git clone https://github.com/Githbri/projet_grafana
   cd /projet_grafana


2. **Lancer Docker Compose** :

   docker-compose up -d


3. **Accéder à Grafana** :
   - Une fois le conteneur lancé, ouvrez votre navigateur et rendez-vous sur :
     
     http://localhost:3000
     
   - Identifiants par défaut :
     - **Utilisateur** : `admin`
     - **Mot de passe** : `admin`
     - Vous serez invité à changer le mot de passe à la première connexion.

### Arrêter le conteneur
Pour arrêter le conteneur :

sudo docker-compose down


---

## Notes
- Ce projet est conçu pour être facilement intégrable dans d'autres configurations Docker Compose.
- Vous pouvez ajouter des bases de données ou des outils de surveillance supplémentaires en étendant le fichier `docker-compose.yml`.

---

## Ressources utiles
- [Documentation officielle de Grafana](https://grafana.com/docs/)
- [Docker Hub - Image Grafana](https://hub.docker.com/r/grafana/grafana)

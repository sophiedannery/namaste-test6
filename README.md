# Namaste Yoga Studio - Site de réservation de cours de yoga

**Namaste Yoga Studio** est une application web et web mobile destinée à la gestion des cours de yoga du centre "Namaste Yoga Studio" situé à Buis-les-Baronnies.
Le site permettra aux visiteurs de découvrir les cours et professeurs, et aux élèves de **réserver une place en ligne**.

## 🎯 Objectifs

- Digitaliser la réservation des cours.
- Permettre la gestion des plannings pour les professeurs.
- Offrir à l'administrateur une vision d'ensemble via un tableau de bord.

## 🧩 Stack technique

| Service               | Technologie                          | Rôle                                                    |
| --------------------- | ------------------------------------ | ------------------------------------------------------- |
| Front-end             | HTML5 / CSS3 (Bootstrap), JavaScript | Maquettage et dynamisme des interfaces                  |
| Back-end              | PHP 8 / Symfony                      | Traitements serveurs, sécurité                          |
| Base de données SQL   | MySQL                                | Données principales : utilisateurs, cours, réservations |
| Base de données NoSQL | MongoDB                              | Stockage de logs et statistiques                        |
| Conteneurisation      | Docker Compose                       | Environnement reproductible et isolé                    |
| Serveur web           | Nginx                                | Gestion des requêtes HTTP                               |
| Versioning            | Git / GitHub                         | Suivi de versions et collaboration                      |

## ⚙️ Installation et configuration de l'environnement

### 1. Prérequis

- Docker et Docker compose installés
- Git installé
- Port **8080** libre pour l'application
- Port **3306** libre pour MySQL
- Port **27017** libre pour MongoDB

### 2. Cloner le projet

```bash
git clone https://github.com/dannerysophie/namaste-test6.git
cd <ton-repo>
```
### 2. Configurer les variables d'environnement 

Créer le fichier .env.local puis configure les variables suivantes : 

```bash
APP_ENV=dev
DATABASE_URL="mysql://namaste_user:<voir_le_mdp_dans_docker-compose>d@db:3306/namaste_test2?serverVersion=8.0&charset=utf8mb4"
MONGODB_URL="mongodb://root:root@mongo:27017/namaste_test2?authSource=admin"
```

### 3. Lancer les conteneurs

```bash
docker compose up -d
```

_Note : si vous avez modifié le Dockerfile :_

```bash
docker compose up --build -d
```

### 4. Vérifier les services

```bash
docker compose ps
```

Résultat attendu :

```bash
SERVICE   STATUS    PORTS
app       Up        9000/tcp
web       Up        0.0.0.0:8080->80/tcp
db        Up        3306/tcp
mongo     Up        27017/tcp
```

### 5. Vendor
A cette étape, si le dossier vendor est vide ou manquant : 
```bash
docker compose exec app composer install -n --prefer-dist
```
pour installer les dépendances Symfony dans le conteneur PHP.


### 5. Vérifier les connexions

```bash
docker compose exec db mysql -u namaste_user -p -e "SHOW DATABASES;"
docker compose exec mongo mongosh -u root -p root --authenticationDatabase admin --eval "show dbs"
```

## 🚀 Étapes suivantes

1. Maquettage

2. Création des wireframes et maquettes desktop/mobile.

3. Intégration front-end statique, HTML / CSS responsive (Bootstrap).

4. Développement dynamique (JS), Filtres, formulaires, API Google Avis.

5. Base de données MySQL & MongoDB, Modélisation, scripts schema.sql et data.sql.

6. Développement back-end Symfony, Sécurité, gestion utilisateurs, réservations, API REST.

7. Déploiement et documentation, Docker + Heroku / OVH, guide d’installation, manuel utilisateur.

## Licence et Contrat

Projet développé par Dannery Sophie dans le cadre de la formation **TP Développeur Web et Web mobile** (RNCP37674) - 2025

Encadrement pédagogique : **STUDI /DREETS**

📧 Contact : **dannery.sophie@gmail.com**

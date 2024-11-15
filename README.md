Présentation du projet
L'objectif de ce TP est de déployer une application web complète en utilisant Docker et Docker Compose. Cette application comprend un frontend développé en React, un backend en Flask, une base de données MySQL, ainsi qu'un service de gestion via PHPMyAdmin. Le but est de conteneuriser chaque composant de l'application et d'automatiser leur déploiement à l'aide de Docker Compose.

Le but est de :
1.	Conteneuriser chaque service pour faciliter le déploiement.
2.	Utiliser Docker Compose pour automatiser l'orchestration des services.
3.	Implémenter un reverse proxy avec Nginx pour gérer le routage entre le frontend et le backend.

Configuration et explication de la stack technique
1. Architecture générale
Le projet est divisé en plusieurs services distincts :
•	Base de données MySQL pour stocker les données.
•	PHPMyAdmin pour gérer la base de données.
•	Backend Flask pour la logique de l'application.
•	Frontend React pour l'interface utilisateur.
•	Nginx comme reverse proxy pour rediriger les requêtes vers le frontend ou le backend.

2. Création des Dockerfiles
Dockerfile du backend (Flask) : Ce Dockerfile permet de conteneuriser le backend en Flask en installant toutes les dépendances nécessaires depuis requirements.txt et en exposant le port 5000.

Dockerfile du frontend (React) : Le frontend est d'abord construit avec Node.js, puis servi avec Nginx pour des performances optimales.

3. Configuration du fichier docker-compose.yml
•	Ce fichier permet d'orchestrer tous les services, afin qu'ils fonctionnent ensemble dans des conteneurs distincts connectés sur le même réseau.

4. Configuration du reverse proxy Nginx (nginx.conf)
Cette configuration redirige les requêtes vers le frontend, tandis que les requêtes avec /api/ sont redirigées vers le backend Flask.


Instructions pour exécuter le projet
1.	Cloner le repository :
git clone <URL_DU_REPO>
cd course_docker_tp_wamp
2.	Construire et démarrer les conteneurs :
docker-compose up –build

3.	Accéder aux services :
o	Frontend React : http://localhost:8080
o	PHPMyAdmin : http://localhost:8081

4.	Se connecter à PHPMyAdmin avec les identifiants suivants :
o	Utilisateur : root
o	Mot de passe : rootpassword

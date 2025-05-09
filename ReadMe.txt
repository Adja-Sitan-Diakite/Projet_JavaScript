## Guide d’utilisation de la plateforme d’examen en ligne – Projet 2

### Pré-requis techniques

Avant de commencer, assurez-vous d’avoir :

* Node.js et npm installés sur votre système
* Docker et Docker Compose opérationnels
* Une connexion Internet active

---

### Installation et démarrage de la plateforme

1. Cloner le dépôt GitHub :
   git clone [https://github.com/projet-JS/projet.git](https://github.com/projet-JS/projet.git)

2. Se placer dans le dossier du projet :
   cd projet

3. Lancer MongoDB et Mongo Express avec Docker :
   docker compose up -d

4. Accéder au dossier backend :
   cd backend

5. Installer les dépendances et démarrer le serveur :
   npm install
   node server.js

Le serveur est accessible à l’adresse [http://localhost:3000](http://localhost:3000)

---

### Création et gestion de compte

**Inscription**

* Accéder à [http://localhost:3000/register.html](http://localhost:3000/register.html)
* Remplir tous les champs requis : email, mot de passe, nom, prénom, date de naissance, sexe, établissement, filière
* Cliquer sur Créer un compte
* En cas de succès, redirection automatique vers la page de sélection

**Connexion**

* Accéder à [http://localhost:3000](http://localhost:3000) ou directement à login.html
* Saisir les identifiants (email et mot de passe)
* Cliquer sur Se connecter
* En cas de succès, affichage de la page de sélection

---

### Page de sélection

Deux choix sont proposés :

* Créer un examen
* Passer un examen

---

### Création d’un examen

1. Depuis la page de sélection, sélectionner Créer un examen
2. Saisir le titre, la description, le public visé
3. Ajouter des questions via le bouton prévu à cet effet
4. Prévisualiser l’examen
5. Terminer la création et enregistrer

---

### Passage d’un examen

1. Cliquer sur Passer un examen depuis la page de sélection
2. Coller le lien de l’examen à passer
3. Cliquer sur Commencer

Le chronomètre se lance automatiquement, les questions s’affichent une à une, et la notation est gérée en temps réel.

Il est également possible de coller directement le lien de l’examen dans la barre d’adresse du navigateur pour commencer immédiatement.

---

### Présentation des pages

register.html :
Page d’inscription. 
Redirige vers selection.html une fois le compte créé.

login.html :
Page de connexion. 
Redirige vers les options de création ou passage d’un examen après authentification.

selection.html :
Interface de sélection permettant de choisir entre créer ou passer un examen.

examen.html :
Interface complète de création d’examen avec ajout
 modification et suppression de questions.

---

### Organisation du projet

* node\_modules : dépendances utilisées (express, mongoose, cors…)
* docker-compose.yml : configuration des services Docker
* backend/server.js : serveur Node.js chargé de servir les pages, traiter les requêtes et gérer les erreurs
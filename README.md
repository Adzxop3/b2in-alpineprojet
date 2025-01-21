# Projet de formulaire d'inscription et de connexion en Alpine.js
Ce projet est un exemple d'application web permettant à un utilisateur de s'inscrire et de se connecter. Les données sont stockées localement dans un fichier JSON grâce à json-server.
## Fonctionnalités
1. **Inscription** :
- Saisie d'un nom d'utilisateur, d'une adresse e-mail et d'un mot de passe.
- Vérification de la disponibilité de l'e-mail (pas de duplication).
- Vérification de la validité de l'e-mail.
- Vérification que les mots de passe concordent.
- Enregistrement des informations dans la « base de données » JSON.
2. **Connexion** :
- Saisie de l'e-mail et du mot de passe.
- Vérification des identifiants par rapport aux données stockées.
3. **Stockage des données** utilisateurs dans le [fichier](bdd.json) contenant la base de donnée.

## Prérequis
- [Node](https://nodejs.org/fr) (version 12 ou supérieure).
- [Npm](https://www.npmjs.com) (Fourni avec Node).

## Installations 
### Installation de json-server
```bash
npm install -g json-server
```
Ensuite démarrer le serveur JSON, pour le démarrer, veuillez ouvrir le terminal du dossier dans lequel se trouve le fichier bdd.json
```bash
json-server --watch bdd.json
```
## Structure du projet 
- [Page d'inscription](index3.html)
- [Page de connexion](html4.html)
- [Base de donnée](bdd.json)

## Explications 
### Inscription (index3.html)
- Formulaire comprenant :

  - Nom d'utilisateur
  - Adresse e-mail
  - Mot de passe
  - Confirmation du mot de passe
- Logique gérée par Alpine.js.

  - Récupère la liste des utilisateurs depuis http://localhost:3000/users.
  - Vérifie si l'adresse e-mail est déjà utilisée.
  - Vérifie la validité de l'adresse e-mail (via une expression régulière).
  - Vérifie la correspondance des mots de passe.
  - Si tout est correct, envoie une requête POST à json-server pour ajouter le nouvel utilisateur dans bdd.json.
  - Redirige ensuite vers la page de connexion.
### Connexion (html4.html)
- Formulaire comprenant :

  - Adresse e-mail
  - Mot de passe
- Logique gérée par Alpine.js.

  - Récupère la liste des utilisateurs depuis http://localhost:3000/users.
  - Compare les identifiants (e-mail / mot de passe) avec ceux stockés.
  - Affiche un message d'erreur si la combinaison ne correspond pas à un utilisateur.
  - Affiche un message de succès si la connexion est réussie.
 
### bdd.json
Le fichier JSON contient un tableau `users`:
```json
{
  "users": []
}
```
Lors de l'inscription, de nouveaux objets sont ajoutés à ce tableau: 
```json
{
  "users": [
    {
      "id": "acc9",
      "username": "Exemple",
      "email": exemple@exemple.fr",
      "password": "exemple"
    }
  ]
}
```
## Dépendances principales
- Bulma : Framework CSS
- Alpine.js : Framework JavaScript
- json-server : Simule une API REST pour lire et écrire des données en JSON

## Collaborateurs
- Adzxop3
- Nash920

# Loldle

Jeu de devinettes sur les champions de League of Legends, inspiré de Loldle.
On propose un champion, le jeu compare ses caractéristiques (genre, type d'attaque, année de sortie, région, rôle, ressource…) avec celles du champion à trouver, jusqu'à la bonne réponse.

Projet personnel réalisé à Ynov (projet solo).

## Fonctionnalités

- **Mode illimité** : autant de parties que tu veux.
- **Défi du jour** : un champion par jour, le même pour tout le monde.
- **Comptes** : inscription et connexion (mots de passe hachés avec bcrypt, jetons JWT), photo de profil.
- **Classements** : du jour, de la semaine et du mois, avec séries de victoires.

## Technologies

Node.js · Express · PostgreSQL · bcrypt · JWT · HTML / CSS / JavaScript

## Lancer le projet en local

### Prérequis

- [Node.js](https://nodejs.org) 18 ou plus récent
- [PostgreSQL](https://www.postgresql.org/download/) 14 ou plus récent

### 1. Récupérer le code

```bash
git clone https://github.com/zTatoune/Scalingo.git
```

```bash
cd Scalingo
```

### 2. Installer les dépendances

```bash
npm install
```

### 3. Créer la base de données

Dans `psql` (ou pgAdmin), crée un utilisateur et une base vide :

```sql
CREATE USER loldle WITH PASSWORD 'loldle';
CREATE DATABASE loldle OWNER loldle;
```

Les tables et la liste des 170 champions (`data/champions.json`) sont créées automatiquement au premier lancement.

### 4. Configurer

Copie `.env.example` en `.env` (sous Windows : `copy .env.example .env`), puis adapte `DATABASE_URL` et choisis un `JWT_SECRET`.

### 5. Démarrer

```bash
npm start
```

Le jeu est accessible sur **http://localhost:3000**.

## Structure

| Fichier | Rôle |
|---|---|
| `server.js` | Serveur Express et routes de l'API |
| `database.js` | Création des tables, parties, comparaison des champions, classements |
| `auth.js` | Inscription, connexion, profils et statistiques |
| `db.js` | Connexion à PostgreSQL |
| `data/champions.json` | Caractéristiques des champions |
| `public/` | Pages et scripts du navigateur |

Les images des champions viennent du CDN public de Riot (Data Dragon).

---

Loldle n'est pas affilié à Riot Games. League of Legends est une marque de Riot Games, Inc.

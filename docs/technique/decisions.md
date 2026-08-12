# Décisions techniques — GL Prime

## 1. Framework Backend

**Question :** Quel framework utiliser pour développer l'API backend ?

**Options considérées :**

* FastAPI (Python)
* Express (Node.js)
* Django (Python)

**Choix :** FastAPI

**Raison :**
FastAPI est léger, rapide et fournit un typage natif avec Pydantic. Il est également cohérent avec les compétences de Landry et Goh Mema en Python.

---

## 2. Framework Frontend

**Question :** Quel framework utiliser pour développer l'interface utilisateur ?

**Options considérées :**

* React avec Vite
* Vue.js
* Angular

**Choix :** React avec Vite

**Raison :**
React avec Vite correspond à l'architecture frontend prévue dans le projet et permet de construire l'application à partir de composants réutilisables. Vite fournit également un environnement de développement rapide.

---

## 3. Base de données

**Question :** Quelle base de données utiliser pour stocker les données de l'application ?

**Options considérées :**

* PostgreSQL
* MySQL
* SQLite

**Choix :** PostgreSQL

**Raison :**
PostgreSQL est le choix prévu pour le projet et convient au modèle relationnel de l'application. Il permettra notamment de gérer les relations entre utilisateurs, établissements, exercices, évaluations et résultats.

---

## 4. ORM et migrations

**Question :** Comment gérer l'accès à la base de données et l'évolution du schéma ?

**Options considérées :**

* SQLAlchemy + Alembic
* Django ORM + migrations
* Requêtes SQL manuelles

**Choix :** SQLAlchemy + Alembic

**Raison :**
Le backend étant basé sur FastAPI, SQLAlchemy permet de gérer les modèles et les interactions avec PostgreSQL, tandis qu'Alembic permet de versionner les modifications du schéma de la base de données.

---

## 5. Authentification

**Question :** Comment authentifier les utilisateurs de l'application ?

**Options considérées :**

* Sessions serveur
* JWT
* OAuth uniquement

**Choix :** JWT

**Raison :**
Le modèle d'authentification prévu dans le projet repose sur un token JWT envoyé dans le header `Authorization`. Le token aura une durée de validité définie, avec une durée de 24 heures proposée dans les spécifications.

---

## 6. Stockage des mots de passe

**Question :** Comment stocker les mots de passe ?

**Options considérées :**

* Texte en clair
* MD5 / SHA1
* bcrypt ou Argon2

**Choix :** bcrypt ou Argon2

**Raison :**
Les mots de passe ne doivent jamais être stockés en clair. MD5 et SHA1 sont explicitement exclus car trop faibles. Le mot de passe sera stocké sous forme de hash sécurisé.

---

## 8. CI — Intégration continue

**Question :** Comment vérifier automatiquement la qualité du code avant fusion ?

**Options considérées :**

* Vérifications manuelles uniquement
* GitHub Actions
* Autre service CI

**Choix :** GitHub Actions

**Raison :**
Le projet utilise GitHub pour héberger ses repositories. GitHub Actions permettra d'exécuter automatiquement le linter et les tests lors des changements de code.

Une Pull Request dont les vérifications échouent ne devra pas être fusionnée.

---

## 9. Stratégie Git

**Question :** Comment protéger le code source et organiser les contributions ?

**Options considérées :**

* Push direct sur `main`
* Git Flow simplifié avec `main`, `develop` et branches de fonctionnalité
* Une seule branche commune

**Choix :** `main` + `develop` + branches de fonctionnalité

**Raison :**
Les branches `main` et `develop` seront protégées. Les modifications devront passer par une Pull Request avec au minimum une approbation avant fusion.

Cela permet de faire relire le code avant son intégration.

---

## 10. Convention des commits

**Question :** Comment uniformiser les messages de commit ?

**Choix :** Convention de type Conventional Commits.

**Format :**

```text
type(scope): description
```

**Exemples :**

```text
feat(auth): add login endpoint
fix(auth): handle invalid credentials
docs(technique): document backend choice
chore(ci): add GitHub Actions workflow
refactor(auth): simplify JWT validation
test(auth): add login endpoint tests
```

**Raison :**
Une convention commune permet de comprendre rapidement la nature de chaque modification et facilite l'historique du projet.

---

## 11. API

**Question :** Quelle convention utiliser pour les endpoints API ?

**Choix :** Endpoints en anglais et au pluriel.

**Exemples :**

```text
GET /users
POST /exercises
GET /exercises/:id
```

**Raison :**
Cette convention est définie dans les conventions techniques du projet et doit être appliquée de manière uniforme par l'équipe backend.

---

## Historique des décisions

| Date      | Décision                                         | Responsable               |
| --------- | ------------------------------------------------ | ------------------------- |
| Août 2026 | FastAPI pour le backend                          | Christ-Phanuel            |
| Août 2026 | React + Vite pour le frontend                    | Christ-Phanuel            |
| Août 2026 | PostgreSQL pour la base de données               | Christ-Phanuel / Landry   |
| Août 2026 | JWT pour l'authentification                      | Christ-Phanuel / Backend  |
| Août 2026 | GitHub Actions pour la CI                        | Christ-Phanuel / Équipe   |
| Août 2026 | `main` et `develop` protégées                    | Christ-Phanuel            |
| Août 2026 | Conventional Commits                             | Christ-Phanuel            |
| Août 2026 | Docker jetable envisagé pour l'exécution du code | Christ-Phanuel / Sécurité |

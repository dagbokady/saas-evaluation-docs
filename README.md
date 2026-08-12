# saas-evaluation-docs

Documentation, comptes rendus et procédures de **GL Prime**, la plateforme d'évaluation de code : les enseignants y créent des exercices et des évaluations, les apprenants y écrivent et exécutent du code, et la correction est calculée automatiquement.

Ce dépôt centralise tout ce qui concerne les deux autres briques du projet : [saas-evaluation-backend](../saas-evaluation-backend) (API, base de données, exécution du code) et [saas-evaluation-frontend](../saas-evaluation-frontend) (interface enseignant + interface apprenant).

## Sommaire

- [Organisation des dépôts](#organisation-des-dépôts)
- [Arborescence](#arborescence)
- [Démarrage](#démarrage)
- [Workflow Git](#workflow-git)
- [Convention de commit](#convention-de-commit)
- [Pull Requests](#pull-requests)
- [Roadmap](#roadmap)

## Organisation des dépôts

| Dépôt | Rôle |
|---|---|
| `saas-evaluation-backend` | API, base de données, logique métier, exécution du code |
| `saas-evaluation-frontend` | Interface enseignant + interface apprenant |
| `saas-evaluation-docs` | Documentation, comptes rendus, procédures |

Chaque dépôt avance et se déploie à son rythme sans bloquer les autres.

## Arborescence

```
specs/              spécifications fonctionnelles détaillées (à partir du cahier des charges)
manuel-utilisateur/ manuel utilisateur enseignant et apprenant, fiche par fonctionnalité
technique/           schéma de base de données, conventions de nommage, endpoints, décisions techniques
comptes-rendus/      compte rendu de fin de sprint, rapports de recette et de pentest
glossaire.md         glossaire des termes du projet
```

## Démarrage

1. Se faire ajouter comme collaborateur sur ce dépôt.
2. Configurer Git :
   ```bash
   git config --global user.name "Prénom Nom"
   git config --global user.email "email@exemple.com"
   ```
3. Cloner le dépôt.
4. Lire le guide de collaboration en entier et lire le cahier des charges avant de contribuer.

## Workflow Git

On ne travaille **jamais** directement sur `main` ou `develop`.

| Branche | Rôle | Qui peut y pousser |
|---|---|---|
| `main` | Version stable de la documentation | Personne (PR uniquement) |
| `develop` | Branche d'intégration | Personne (PR uniquement) |
| `feature/<nom>` | Rédaction en cours | Le rédacteur qui la porte |
| `fix/<nom>` | Correction de doc | Le rédacteur qui la porte |

À chaque session de travail :

```bash
git checkout develop
git pull origin develop
git checkout -b feature/ma-fiche
```

Partir d'un `develop` à jour évite la grande majorité des conflits de merge.

## Convention de commit

On suit [Conventional Commits](https://www.conventionalcommits.org/) : `<type>(<portée>): <description courte au présent>`. Pour ce dépôt, le type le plus courant est `docs`.

| Type | Quand l'utiliser |
|---|---|
| `docs` | Rédaction ou mise à jour de documentation |
| `fix` | Correction (erreur, information obsolète) |
| `chore` | Tâche technique (arborescence, config) |

Exemples :
```
docs: rédige le manuel utilisateur enseignant
docs: écrit la fiche "Créer un exercice" du manuel enseignant
```

Un commit = un changement logique cohérent, décrit à l'impératif présent ("rédige", "corrige" — pas "rédigé"). Pas de commit `wip` ou `fix` tout seul.

## Pull Requests

1. Pousser sa branche : `git push origin feature/ma-fiche`.
2. Ouvrir la PR sur GitHub : `base: develop ← compare: feature/ma-branche` — jamais vers `main`.
3. Titre au même format que les commits, description au format Quoi / Pourquoi / Comment vérifier.
4. Ajouter au moins un reviewer.
5. Une PR ne se fusionne qu'après au moins une approbation — personne ne fusionne sa propre PR sans relecture.

Reviewer obligatoire sur toutes les PR : Christ-Phanuel (validation finale).

Quand une fonctionnalité touche backend et frontend, la documentation associée ici doit être liée aux deux Pull Requests correspondantes dans leurs dépôts respectifs.

## Roadmap

# Sprint 0 — Cadrage & Setup

**Durée :** 2 semaines  
**Objectif :** préparer l'environnement technique, documentaire et organisationnel avant le développement des fonctionnalités du produit.

---

## 1. Christ-Phanuel — Product Owner / Tech Lead

- [ ] Choisir les technologies du projet :
    - Backend
    - Frontend
    - Base de données
    - Exécution sécurisée du code
- [ ] Rédiger `docs/technique/decisions.md`
- [ ] Créer les 3 repositories :
    - `saas-evaluation-backend`
    - `saas-evaluation-frontend`
    - `saas-evaluation-docs`
- [ ] Configurer la protection des branches `main` et `develop`
- [ ] Ajouter les membres de l'équipe comme collaborateurs
- [ ] Créer les README des repositories
- [ ] Découper le cahier des charges en tickets
- [ ] Attribuer les tickets aux membres de l'équipe
- [ ] Définir le sprint associé à chaque ticket
- [ ] Organiser et animer le kickoff du projet

---

## 2. Frean — Documentation

- [ ] Rédiger les spécifications fonctionnelles
- [ ] Préparer l'arborescence de la documentation
- [ ] Commencer le glossaire du projet

---

## 3. Rabi — QA

- [ ] Rédiger la stratégie de test
- [ ] Préparer les premiers scénarios utilisateurs

---

## 4. Moussa Mohamed — QA

- [ ] Rédiger les scénarios de cas limites
- [ ] Préparer le template de rapport de bug

---

## 5. Kpassokro Bryan — UI/UX

- [ ] Réaliser les wireframes des écrans MVP
- [ ] Poser les bases du design system

---

## 6. Koffi Landry — BDD / API / Documentation technique

- [ ] Dessiner le schéma initial de la base de données
- [ ] Définir les conventions de nommage

---

## 7. Goh Mema — Backend

- [ ] Initialiser le projet backend
- [ ] Mettre en place la CI
- [ ] Préparer l'endpoint `GET /health`

---

## 8. Akré Ange David — Frontend

- [ ] Initialiser le projet frontend
- [ ] Intégrer le design system
- [ ] Créer la page de test de communication frontend ↔ backend

---

## 9. Gapka Esaïe — Frontend

- [ ] Implémenter les composants UI réutilisables
- [ ] Créer la galerie `/dev/components`

---

## 10. Koffi Auphocey — Sécurité / Authentification

- [ ] Documenter le modèle d'authentification
- [ ] Définir les rôles et permissions

---

## 11. Bakayoko Muhammed — Pentest / Sécurité

- [ ] Rédiger le plan de sécurité

---

## 12. Douzan Bi Emmanuel — Développeur Junior

- [ ] Installer l'environnement de développement
- [ ] Réaliser une première Pull Request

---

## 13. Kassem Dehou — Développeur Junior

- [ ] Installer l'environnement de développement
- [ ] Préparer le script de démarrage

---

# Livrables attendus à la fin du Sprint 0

- [ ] Stack technique décidée et documentée
- [ ] 3 repositories GitHub opérationnels
- [ ] Branches `main` et `develop` protégées
- [ ] Équipe ajoutée aux repositories
- [ ] Documentation initiale en place
- [ ] Schéma initial de la BDD disponible
- [ ] Wireframes MVP disponibles
- [ ] Design system initial disponible
- [ ] Backend initialisé
- [ ] Frontend initialisé
- [ ] CI configurée
- [ ] Stratégie de test définie
- [ ] Modèle d'authentification documenté
- [ ] Plan de sécurité défini
- [ ] Environnements de développement fonctionnels
- [ ] Première Pull Request réalisée
- [ ] Cahier des charges découpé en tickets
- [ ] Kickoff réalisé
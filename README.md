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

MVP découpé en 7 sprints (~14 semaines). Ce qui concerne la documentation sprint par sprint :

| Sprint | Objectif | Documentation |
|---|---|---|
| S0 | Cadrage & Setup | Spécifications fonctionnelles détaillées, arborescence du dépôt, début du glossaire |
| S1 | Connexion & Comptes | Fiche "Comment se connecter", compte rendu de fin de sprint |
| S2 | Création d'exercice | Fiche "Créer un exercice" |
| S3 | Éditeur & exécution | Documentation du fonctionnement de l'éditeur, journal des décisions techniques |
| S4 | Session d'évaluation | Fiches "Lancer une évaluation" et "Passer une évaluation" |
| S5 | Correction & résultats | Fiches "Consulter les résultats", "Ajuster une note", "Exporter" |
| S6 | Stabilisation & démo | Manuel utilisateur complet, documentation technique complète, rapport de pentest final, compte rendu final du MVP |

Après validation du MVP par un premier client, le projet passe à sa phase Avancée (banque d'exercices réutilisables, détection de similarité de code, mode examen surveillé, validation par IA, mode entraînement libre, statistiques pédagogiques) — dont le plan sera documenté ici.

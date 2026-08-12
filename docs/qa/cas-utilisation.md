# Cas d'utilisation — GL Prime

## 1. Présentation

Ce document recense les principaux cas d'utilisation identifiés à partir du cahier des charges du projet **GL Prime — SaaS d'évaluation pratique pour les cours de programmation et d'algorithmique**.

Les acteurs identifiés dans le cahier des charges sont :

- **Enseignant**
- **Apprenant**
- **Établissement / Administration**

---

# 2. Acteurs

## UC-ACT-01 — Enseignant

L'enseignant utilise la plateforme pour :

- créer des évaluations ;
- définir les règles d'une évaluation ;
- choisir les langages autorisés ;
- créer des exercices ;
- définir les jeux de tests ;
- définir le barème ;
- définir la durée et les dates ;
- attribuer les évaluations aux apprenants ;
- lancer une session d'évaluation ;
- consulter les résultats ;
- ajuster manuellement les notes ;
- exporter les résultats.

---

## UC-ACT-02 — Apprenant

L'apprenant utilise la plateforme pour :

- se connecter à la plateforme ;
- accéder aux évaluations qui lui sont attribuées ;
- écrire son code dans l'éditeur intégré ;
- exécuter son code ;
- tester son code ;
- sauvegarder automatiquement son travail ;
- soumettre son travail ;
- consulter les résultats selon les fonctionnalités prévues.

---

## UC-ACT-03 — Établissement / Administration

L'établissement ou l'administration utilise la plateforme pour :

- gérer les licences ;
- gérer les abonnements ;
- administrer les accès au niveau de l'établissement.

---

# 3. Cas d'utilisation — Enseignant

## UC-ENS-01 — Créer une évaluation

**Acteur principal :** Enseignant

**Objectif :** Créer une nouvelle évaluation destinée aux apprenants.

### Préconditions

- L'enseignant est connecté.
- L'enseignant dispose des droits nécessaires.

### Scénario nominal

1. L'enseignant accède à la création d'une évaluation.
2. Il renseigne le titre.
3. Il renseigne la description.
4. Il définit les consignes.
5. Il définit les règles de l'épreuve.
6. Il sélectionne les langages autorisés ou le mode algorithme.
7. Il ajoute les exercices.
8. Il définit les jeux de tests.
9. Il définit le barème.
10. Il définit la durée.
11. Il définit la date et l'heure de début.
12. Il définit la date et l'heure de fin.
13. Il enregistre l'évaluation.

### Résultat attendu

L'évaluation est créée et peut être attribuée aux apprenants concernés.

---

## UC-ENS-02 — Choisir les langages autorisés

**Acteur principal :** Enseignant

**Objectif :** Définir les langages utilisables pendant une évaluation.

### Scénario nominal

1. L'enseignant configure une évaluation.
2. Il accède au choix du langage.
3. Il sélectionne un ou plusieurs langages autorisés.
4. Il enregistre la configuration.

### Langages mentionnés dans le cahier des charges

- Python
- Java
- C
- C++
- JavaScript
- etc.

---

## UC-ENS-03 — Ajouter un exercice

**Acteur principal :** Enseignant

**Objectif :** Ajouter un exercice qu'un apprenant devra résoudre.

### Scénario nominal

1. L'enseignant crée ou configure une évaluation.
2. Il ajoute un exercice.
3. Il rédige l'énoncé.
4. Il enregistre l'exercice.

### Résultat attendu

L'exercice est associé à l'évaluation.

---

## UC-ENS-04 — Définir les jeux de tests

**Acteur principal :** Enseignant

**Objectif :** Définir les entrées et sorties attendues permettant la correction automatique.

### Scénario nominal

1. L'enseignant sélectionne un exercice.
2. Il crée un jeu de tests.
3. Il définit les données d'entrée.
4. Il définit la sortie attendue.
5. Il enregistre le test.
6. Il peut définir plusieurs jeux de tests.

### Résultat attendu

Les jeux de tests sont associés à l'exercice et peuvent être utilisés pour la correction automatique.

---

## UC-ENS-05 — Définir le barème

**Acteur principal :** Enseignant

**Objectif :** Déterminer les points attribués aux tests et les éventuelles pénalités.

### Scénario nominal

1. L'enseignant accède au paramétrage du barème.
2. Il attribue des points aux tests.
3. Il définit éventuellement des pénalités.
4. Il enregistre le barème.

---

## UC-ENS-06 — Paramétrer la durée et les dates

**Acteur principal :** Enseignant

**Objectif :** Définir les conditions temporelles de l'évaluation.

### Données configurables

- Durée de l'épreuve
- Date de début
- Heure de début
- Date de fin
- Heure de fin

---

## UC-ENS-07 — Attribuer une évaluation

**Acteur principal :** Enseignant

**Objectif :** Rendre une évaluation accessible aux apprenants concernés.

### Scénario nominal

1. L'enseignant sélectionne une évaluation.
2. Il sélectionne les apprenants ou une classe entière.
3. Il attribue l'évaluation.
4. Les apprenants concernés peuvent accéder à l'épreuve selon les paramètres définis.

---

## UC-ENS-08 — Lancer une session d'évaluation

**Acteur principal :** Enseignant

**Objectif :** Démarrer une épreuve et la rendre accessible aux apprenants concernés.

### Scénario nominal

1. L'enseignant sélectionne l'évaluation.
2. Il vérifie sa configuration.
3. Il lance la session.
4. L'épreuve devient accessible aux apprenants concernés.

---

## UC-ENS-09 — Consulter les résultats

**Acteur principal :** Enseignant

**Objectif :** Consulter les résultats des apprenants.

### Informations disponibles

- Note automatique
- Code soumis
- Tests réussis
- Tests échoués

### Résultat attendu

L'enseignant peut consulter le résultat de chaque apprenant.

---

## UC-ENS-10 — Réajuster une note

**Acteur principal :** Enseignant

**Objectif :** Modifier manuellement une note automatique.

### Cas mentionnés dans le cahier des charges

- Plagiat
- Bonus

### Scénario nominal

1. L'enseignant consulte un résultat.
2. Il constate qu'un ajustement est nécessaire.
3. Il modifie manuellement la note.
4. La nouvelle note est enregistrée.

---

## UC-ENS-11 — Configurer l'apparence des exports

**Acteur principal :** Enseignant

**Objectif :** Définir la présentation des fichiers de résultats exportés.

### Paramètres mentionnés

- Logo
- Nomenclature des colonnes
- Données à inclure

---

## UC-ENS-12 — Exporter les résultats

**Acteur principal :** Enseignant

**Objectif :** Générer un fichier contenant les notes et résultats.

### Scénario nominal

1. L'enseignant accède aux résultats.
2. Il sélectionne les données à exporter.
3. Il applique les paramètres d'apparence.
4. Il demande l'export.
5. La plateforme génère le fichier.

---

# 4. Cas d'utilisation — Apprenant

## UC-APP-01 — Se connecter à la plateforme

**Acteur principal :** Apprenant

**Objectif :** Accéder à son espace personnel.

### Modes d'accès mentionnés

- Compte personnel
- Code donné par l'enseignant

---

## UC-APP-02 — Accéder à une évaluation

**Acteur principal :** Apprenant

**Objectif :** Accéder à une évaluation qui lui a été attribuée.

### Scénario nominal

1. L'apprenant se connecte.
2. Il consulte ses évaluations.
3. Il sélectionne une évaluation accessible.
4. Il accède à l'environnement de travail.

---

## UC-APP-03 — Écrire du code

**Acteur principal :** Apprenant

**Objectif :** Rédiger la solution d'un exercice directement dans le navigateur.

### Scénario nominal

1. L'apprenant ouvre un exercice.
2. Il accède à l'éditeur de code.
3. Il écrit son code.
4. Il modifie son code si nécessaire.

---

## UC-APP-04 — Exécuter le code

**Acteur principal :** Apprenant

**Objectif :** Compiler ou exécuter son code dans l'environnement prévu.

### Scénario nominal

1. L'apprenant écrit son code.
2. Il demande l'exécution.
3. La plateforme exécute le code.
4. Le résultat de l'exécution est retourné à l'apprenant.

---

## UC-APP-05 — Tester son code

**Acteur principal :** Apprenant

**Objectif :** Vérifier le comportement de son code avant sa soumission.

### Scénario nominal

1. L'apprenant écrit son code.
2. Il exécute le code.
3. Il consulte le résultat.
4. Il corrige son code si nécessaire.
5. Il recommence les tests.

---

## UC-APP-06 — Sauvegarder automatiquement son travail

**Acteur principal :** Apprenant

**Objectif :** Éviter la perte du code pendant l'évaluation.

### Résultat attendu

Le code de l'apprenant est sauvegardé en continu pendant son travail.

---

## UC-APP-07 — Soumettre son travail

**Acteur principal :** Apprenant

**Objectif :** Envoyer sa solution pour évaluation.

### Scénario nominal

1. L'apprenant termine son travail.
2. Il soumet son code.
3. La plateforme enregistre la soumission.
4. Le code peut être évalué automatiquement.

---

# 5. Cas d'utilisation — Établissement / Administration

## UC-ADM-01 — Gérer les licences

**Acteur principal :** Établissement / Administration

**Objectif :** Administrer les licences de l'établissement.

---

## UC-ADM-02 — Gérer les abonnements

**Acteur principal :** Établissement / Administration

**Objectif :** Administrer les abonnements de l'établissement.

---

## UC-ADM-03 — Gérer les accès

**Acteur principal :** Établissement / Administration

**Objectif :** Administrer les accès à la plateforme au niveau de l'établissement.

---

# 6. Fonctionnalités avancées

Les cas suivants sont identifiés dans le cahier des charges comme **fonctionnalités avancées**. Ils ne doivent donc pas être confondus avec les cas d'utilisation MVP.

## UC-ADV-01 — Utiliser la banque d'exercices

**Acteur principal :** Enseignant

- Consulter une bibliothèque d'exercices.
- Réutiliser des exercices.
- Partager des exercices entre enseignants.

---

## UC-ADV-02 — Détecter les similarités de code

**Acteur principal :** Enseignant

La plateforme identifie les soumissions présentant une forte similarité afin de limiter la triche.

---

## UC-ADV-03 — Utiliser le mode examen surveillé

**Acteur principal :** Apprenant / Enseignant

Fonctionnalités mentionnées :

- verrouillage de l'environnement ;
- détection du changement d'onglet ;
- webcam optionnelle.

---

## UC-ADV-04 — Obtenir un feedback pédagogique par IA

**Acteur principal :** Apprenant

Dans le cadre de la formation personnelle, l'IA évalue les exercices et fournit un retour pédagogique.

---

## UC-ADV-05 — Utiliser le mode entraînement libre

**Acteur principal :** Apprenant

L'apprenant peut s'exercer librement sur des exercices en dehors d'une évaluation notée.

---

# 7. Vue synthétique des cas d'utilisation

| ID | Acteur | Cas d'utilisation | MVP |
|---|---|---|---|
| UC-ENS-01 | Enseignant | Créer une évaluation | Oui |
| UC-ENS-02 | Enseignant | Choisir les langages | Oui |
| UC-ENS-03 | Enseignant | Ajouter un exercice | Oui |
| UC-ENS-04 | Enseignant | Définir les jeux de tests | Oui |
| UC-ENS-05 | Enseignant | Définir le barème | Oui |
| UC-ENS-06 | Enseignant | Paramétrer durée et dates | Oui |
| UC-ENS-07 | Enseignant | Attribuer une évaluation | Oui |
| UC-ENS-08 | Enseignant | Lancer une session | Oui |
| UC-ENS-09 | Enseignant | Consulter les résultats | Oui |
| UC-ENS-10 | Enseignant | Réajuster une note | Oui |
| UC-ENS-11 | Enseignant | Configurer l'export | Oui |
| UC-ENS-12 | Enseignant | Exporter les résultats | Oui |
| UC-APP-01 | Apprenant | Se connecter | Oui |
| UC-APP-02 | Apprenant | Accéder à une évaluation | Oui |
| UC-APP-03 | Apprenant | Écrire du code | Oui |
| UC-APP-04 | Apprenant | Exécuter du code | Oui |
| UC-APP-05 | Apprenant | Tester son code | Oui |
| UC-APP-06 | Apprenant | Sauvegarder automatiquement | Oui |
| UC-APP-07 | Apprenant | Soumettre son travail | Oui |
| UC-ADM-01 | Administration | Gérer les licences | Oui |
| UC-ADM-02 | Administration | Gérer les abonnements | Oui |
| UC-ADM-03 | Administration | Gérer les accès | Oui |
| UC-ADV-01 | Enseignant | Banque d'exercices | Non |
| UC-ADV-02 | Enseignant | Détection de similarité | Non |
| UC-ADV-03 | Apprenant/Enseignant | Mode examen surveillé | Non |
| UC-ADV-04 | Apprenant | Feedback IA | Non |
| UC-ADV-05 | Apprenant | Entraînement libre | Non |

---

# 8. Remarque

Cette liste est construite à partir des fonctionnalités explicitement présentes dans le cahier des charges.

Les détails techniques tels que :

- endpoints API ;
- modèles de base de données ;
- mécanismes JWT ;
- technologies d'exécution du code ;
- architecture frontend/backend ;

ne sont pas considérés ici comme des cas d'utilisation. Ils seront documentés dans les documents techniques correspondants.
# Guide de Contribution

Ce document décrit les conventions à suivre pour contribuer à ce projet.

## Messages de Commit 📝

### Format
```
type(bot): titre du commit
```

#### Type
Doit être l'un des suivants ([convention Angular](https://github.com/angular/angular/blob/main/CONTRIBUTING.md#type)):

* **build**: Modifications du système de build ou des dépendances externes
* **ci**: Modifications des fichiers et scripts de CI
* **docs**: Modifications de la documentation uniquement
* **feat**: Nouvelle fonctionnalité
* **fix**: Correction d'un bug
* **perf**: Amélioration des performances
* **refactor**: Modification du code qui ne corrige pas de bug et n'ajoute pas de fonctionnalité
* **style**: Modifications n'affectant pas le sens du code (espaces, formatage, points-virgules manquants, etc.)
* **test**: Ajout ou correction de tests

#### Bot
Le nom du bot concerné par la modification.

#### Titre du commit
* En anglais
* Maximum 50 caractères
* Commence par un verbe à l'infinitif
* Pas de point final

### Corps du Commit (Body)
* En anglais
* Obligatoire si le titre n'est pas suffisamment explicite
* Doit préciser les fichiers modifiés si nécessaire
* Explique le "pourquoi" plutôt que le "comment"

### Commits Atomiques
Chaque commit doit :
* Se concentrer sur une seule modification
* Être indépendant
* Permettre au projet de compiler

## Pull Requests 🔄

### Nommage
* Titre en anglais
* Clair et descriptif
* Suit le même format que les commits

### Labels
Chaque PR doit avoir au minimum :
* Un label pour le type de changement
* Un label pour le bot concerné

### Processus de Review

#### Critères de Validation
* Minimum 3 reviewers dont :
  * 1 membre du groupe émetteur
  * Le Tech Lead du groupe émetteur
  * Des membres externes au groupe

#### Règles de Fusion
* L'émetteur ne peut pas fusionner sa propre PR
* Le Tech Lead qui approuve est responsable de la fusion
* Les approbations sont annulées si de nouveaux commits sont poussés

### Demandes de Modifications
* Les reviewers doivent détailler clairement les changements requis
* Les commentaires doivent être explicites et constructifs

## Conventions de Nommage 📋

### Fichiers
* Noms en français
* Format kebab-case (exemple : `gestion-utilisateurs.js`)
* Tout en minuscules
* Mots séparés par des tirets 
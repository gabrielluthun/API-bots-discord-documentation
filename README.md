
# Sommaire

1. [Normes pour les commits et les pull requests](#normes-pour-les-commits-et-les-pull-requests)
   - [Messages de commit](#messages-de-commit)
   - [Body du commit (corps détaillé)](#body-du-commit-corps-détaillé)
   - [Longueur des commits](#longueur-des-commits)
   - [Commits atomiques](#commits-atomiques)
   - [Noms des pull requests](#noms-des-pull-requests)
   - [Labels sur les pull requests](#labels-sur-les-pull-requests)
   - [Noms de fichiers](#noms-de-fichiers)
   - [Suivi des changements dans les pull requests](#suivi-des-changements-dans-les-pull-requests)
   - [Processus d'approbation et de fusion des pull requests](#processus-dapprobation-et-de-fusion-des-pull-requests)
2. [Fichiers communs](./doc/) 📂
    - [Contexte](doc/contexte.md) 📄
    - [Contraintes et opportunités](doc/contraintes-opportunités.md) 📄
    - [Enjeux](doc/enjeux.md) 📄
    - [Objectifs](doc/objectifs.md) 📄
    - [RBAC](doc/RBAC.md) 📄
3. [Bot Feedback](./doc/bot-feedback/) 📂
    - [Echanges clients](doc/bot-feedback/echanges-client/) 📂
    - [Daily meeting](doc/bot-feedback/daily-meeting.md) 📄
    - [Exigences](doc/bot-feedback/exigences.md) 📄
    - [Problématiques](doc/bot-feedback/problematiques.md) 📄
    - [Règles de gestion](doc/bot-feedback/regles-gestion.md) 📄
4. [Bot Onboarding](./doc/bot-onboarding/) 📂
    - [Echanges clients](doc/bot-onboarding/echanges-client/) 📂
    - [Daily meeting](doc/bot-onboarding/daily-meeting.md) 📄
    - [Exigences](doc/bot-onboarding/exigences.md) 📄
    - [Problématiques](doc/bot-onboarding/problematiques.md) 📄
    - [Règles de gestion](doc/bot-onboarding/regles-gestion.md) 📄
    - [Schéma fonctionnel client](doc/bot-onboarding/schema-fonctionnel-client.md) 📄
5. [Bot Signature](./doc/bot-signature/) 📂
    - [Echanges clients](doc/bot-signature/echanges-client/) 📂
    - [Daily meeting](doc/bot-signature/daily-meeting.md) 📄
    - [Questionnaire](doc/bot-signature/questionnaire.md) 📄
    - [Problématiques](doc/bot-signature/problematiques.md) 📄
    - [Règles de gestion](doc/bot-signature/regles-gestion.md) 📄



<br>
<br>

--------------------------------------------

# Normes pour les commits et les pull requests ✍️

Afin de maintenir une cohérence et une clarté dans notre travail collaboratif, nous avons mis en place des normes pour les messages de commit et les pull requests.

## Messages de commit

Les messages de commit doivent suivre ce format :

    type(bot): titre du commit

### Explication :

**_type_** : Le type de modification, par exemple "docs" ou "feat".

**_bot_** : Le nom du bot.

**_titre du commit_**: Une description concise du changement apporté. (en anglais)

### Exemple :

    docs(bot-feedback): add problems

## Body du commit (corps détaillé)

**_Ajouter un body_** : Si le titre du commit n'est pas assez explicite sur la localisation de la modification, le nom du fichier doit être précisé dans le body.

Cela permet de donner plus d’informations sur les raisons du changement, son impact ou les fichiers modifiés.

## Longueur des commits

**_Bonne pratique_** : Respecter une longueur maximale d'environ 50 caractères pour les titres des commits. Cela permet d'avoir des messages concis, faciles à lire et à comprendre.

## Commits atomiques

**_Commits atomiques_** : Chaque commit doit être atomique, c’est-à-dire qu’il doit se concentrer sur une seule fonctionnalité ou un seul changement.

Cela garantit une meilleure traçabilité et simplifie la gestion des erreurs.

## Noms des pull requests

**_Nom en anglais_** : Les titres des pull requests doivent être rédigés en anglais pour garantir une compréhension globale de l'équipe.

## Labels sur les pull requests

**_Ajout de labels_** : Chaque pull request doit inclure un ou plusieurs labels pour faciliter la gestion des PRs.

Les labels peuvent indiquer le type de changement, la partie du projet concernée, ou des informations spécifiques comme la documentation ou le nom d’un bot.

Par exemple :

![Onboarding](https://img.shields.io/badge/bot%20onboarding-ff0000?style=flat)
![Documentation](https://img.shields.io/badge/documentation-blue?style=flat)

## Noms de fichiers

**_Nom des fichiers en français_** : Les noms des fichiers dans le projet doivent être en français pour garder une cohérence avec la langue principale du projet.

Utiliser le **kebab-case** : Les noms de fichiers doivent être écrits en kebab-case, c’est-à-dire tout en minuscules, avec des mots séparés par des tirets.

**_Exemple_** :

    gestion-utilisateurs.js
    verifier-email.md

## Suivi des changements dans les pull requests

**_Demandes de changements détaillées par les reviewers_** : Si un reviewer exige des modifications sur une pull request, il doit clairement spécifier dans un commentaire les changements à effectuer.

Le reviewer doit fournir une explication détaillée pour s'assurer que le contributeur comprend bien les modifications demandées. Cela favorise la transparence et permet à tous les membres de l'équipe de suivre l'évolution de la pull request.

## Processus d'approbation et de fusion des pull requests



**_Approbation partagée_** : Une pull request doit être validée par au moins un membre du groupe émetteur de la PR en question.

**_Nombre minimum de reviewers_** : Pour qu'une pull request soit fusionnée, elle doit être approuvée par un minimum de trois reviewers, y compris des membres externes au groupe émetteur, afin de garantir une évaluation complète et de qualité.


**_Validation du Tech Lead_** : Parmi les reviewers, le Tech Lead du groupe émetteur de la pull request doit obligatoirement faire partie des approbateurs. L'approbation finale du Tech Lead est nécessaire pour qu'un membre du groupe puisse procéder à la fusion. Il revient au Tech Lead de donner l'aval définitif, assurant que la pull request est prête à être intégrée dans la base de code principale.

**_Responsabilité lors de la fusion_** : Le tech lead qui approuve le merge d'une pull request est responsable de la fusion de celle-ci. En acceptant de fusionner la pull request, il accepte également de prendre la responsabilité en cas de problèmes futurs liés à cette pull request.

**_Interdiction pour l'émetteur de fusionner sa pull request_** : L'émetteur de la pull request n'est pas autorisé à fusionner sa propre pull request. Cela permet de garantir une validation externe par les autres membres du groupe ou par des reviewers indépendants, pour renforcer la qualité et la fiabilité des modifications apportées.

**_Annulation des approbations de pull requests lorsque de nouveaux commits sont poussés_** : La règle "Dismiss stale pull request approvals when new commits are pushed" doit être activée. Cela signifie que si des commits supplémentaires sont ajoutés à une pull request déjà approuvée, les approbations précédentes seront automatiquement révoquées. Cette règle garantit que les modifications récentes sont également examinées par les reviewers, assurant ainsi que l'évaluation de la pull request reste valide et à jour.

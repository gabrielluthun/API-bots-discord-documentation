## Normes pour les commits et les pull requests

Afin de maintenir une cohérence et une clarté dans notre travail collaboratif, nous avons mis en place des normes pour les messages de commit et les pull requests.

## Messages de commit

Les messages de commit doivent suivre ce format :


    type(bot/fichier): titre du commit

Explication :

 type : Le type de modification, par exemple "docs" ou "feat".

 bot/fichier : Le nom du bot puis du fichier concerné par la modification.

 titre du commit : Une description concise du changement apporté. (en anglais)
 
 Exemple :

    docs(bot-feedback/problematiques.md): add problems

## Body du commit (corps détaillé)

Ajouter un body : Si nécessaire, détailler davantage les changements dans le body du commit. 

Cela permet de donner plus d’informations sur les raisons du changement, son impact ou les fichiers modifiés.

## Longueur des commits

Bonne pratique : Respecter une longueur maximale d'environ 50 caractères pour les titres des commits. Cela permet d'avoir des messages concis, faciles à lire et à comprendre.

## Commits atomiques

 Commits atomiques : Chaque commit doit être atomique, c’est-à-dire qu’il doit se concentrer sur une seule fonctionnalité ou un seul changement.
    
Cela garantit une meilleure traçabilité et simplifie la gestion des erreurs.

## Noms des pull requests

Nom en anglais : Les titres des pull requests doivent être rédigés en anglais pour garantir une compréhension globale de l'équipe.


## Labels sur les pull requests

Ajout de labels : Chaque pull request doit inclure un ou plusieurs labels pour faciliter la gestion des PRs. 

Les labels peuvent indiquer le type de changement, la partie du projet concernée, ou des informations spécifiques comme la documentation ou le nom d’un bot.

## Noms de fichiers

 Nom des fichiers en français : Les noms des fichiers dans le projet doivent être en français pour garder une cohérence avec la langue principale du projet.

 Utiliser le **kebab-case** : Les noms de fichiers doivent être écrits en kebab-case, c’est-à-dire tout en minuscules, avec des mots séparés par des tirets.

Exemple :

    gestion-utilisateurs.js
    verifier-email.md

## Suivi des changements dans les pull requests

 Demandes de changements détaillées par les reviewers : Si un reviewer exige des modifications sur une pull request, il doit clairement spécifier dans un commentaire les changements à effectuer.
 
  Le reviewer doit fournir une explication détaillée pour s'assurer que le contributeur comprend bien les modifications demandées. Cela favorise la transparence et permet à tous les membres de l'équipe de suivre l'évolution de la pull request.
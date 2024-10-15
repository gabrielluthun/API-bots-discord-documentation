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

## Commits atomiques

 Commits atomiques : Chaque commit doit être atomique, c’est-à-dire qu’il doit se concentrer sur une seule fonctionnalité ou un seul changement.
    
Cela garantit une meilleure traçabilité et simplifie la gestion des erreurs.

## Noms des pull requests

Nom en anglais : Les titres des pull requests doivent être rédigés en anglais pour garantir une compréhension globale de l'équipe.


## Tags sur les pull requests

Ajout de tags : Chaque pull request doit inclure un ou plusieurs tags pour faciliter la gestion des PRs. 

Les tags peuvent indiquer le type de changement, la partie du projet concernée, ou des informations spécifiques comme la documentation ou le nom d’un bot.
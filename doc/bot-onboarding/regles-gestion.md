# Règles de gestion

Les règles de gestion d'un bot ont pour but de rassembler l'ensemble de ses fonctionnalités et les règles qui y sont associées. Vous trouverez donc ci-dessous les règles de gestions du bot onboarding.

## Gestion de promotion
- **RG1** : Une promotion contient un nom qui la décrit 
- **RG2** : Une promotion contient une date de début et une date de fin
- **RG3** : Seuls un administrateur et un directeur peuvent créer une promotion
- **RG4** : Seuls un administrateur et un directeur peuvent modifier une promotion 
- **RG5** : Seuls un administrateur et un directeur peuvent supprimer une promotion 
- **RG6** : Lors de la modification, un message pour confirmer apparait
- **RG7** : Lors de la suppression, un message pour confirmer apparait
- **RG8** : Lors de la création, un message pour confirmer apparait
- **RG9** : Pour créer une promotion il sera nécesssaire de sélectionner sa formation et sa fabrique associé
- **RG10** : La création d'une promotion crée également un rôle associé avec le nom de la promo
- **RG11** : La promotion disparaît un mois après la fin de la session associée
- **RG12** : Une promotion est forcément lié à une fabrique
- **RG13** : Une promotion est forcément lié à une promotion
- **RG14** : Les promotions seront triées visuellement par fabrique

## Gestion de formation
- **RG11** : Une formation contient un nom qui l'a décrit
- **RG12** : Une formation contient un nom qui la décrit 
- **RG13** : Seuls un administrateur et un directeur peuvent créer une formation
- **RG14** : Seuls un administrateur et un directeur peuvent modifier une formation 
- **RG15** : Seuls un administrateur et un directeur peuvent supprimer une formation 
- **RG16** : Lors de la modification, un message pour confirmer apparait
- **RG17** : Lors de la suppression, un message pour confirmer apparait
- **RG18** : Lors de la création, un message pour confirmer apparait
- **RG18** : Lors de la création d'une formation, il sera possible de sélectionner des canaux déjà pré-enregistré
- **RG19** : Lors de la modification d'une formation, il sera possible de sélectionner des canaux déjà pré-enregistré
- **RG20** : Une formation contient un template de channels organisé qui lui est dédié

## Gestion de fabrique
- **RG21** : Une fabrique contient un nom qui la décrit 
- **RG22** : Seuls un administrateur et un directeur peuvent créer une fabrique
- **RG23** : Seuls un administrateur et un directeur peuvent modifier une fabrique
- **RG24** : Seuls un administrateur et un directeur peuvent supprimer une fabrique
- **RG25** : Lors de la modification, un message pour confirmer apparait
- **RG26** : Lors de la suppression, un message pour confirmer apparait
- **RG27** : Lors de la création, un message pour confirmer apparait
- **RGX** : Une fabrique est lié à tous les apprenants en cours de formation dans celle-ci
- **RGX** : Une fabrique n'est plus lié à un apprenant lorsqu'il termine sa formation
- **RG28** : Une création de fabrique a pour conséquence la création de son rôle discord associé
- **RG28** : Seuls un administrateur et un directeur peuvent notifier les personnes concerné par une fabrique 

## Gestion des channels
- **RG22** : Seuls un administrateur et un directeur peuvent créer un channel dans le stock de channel
- **RG23** : Seuls un administrateur et un directeur peuvent modifier un channel dans le stock de channel
- **RG24** : Seuls un administrateur et un directeur peuvent supprimer un channel dans le stock de channel
- **RGX** : Un channel contient un nom unique qui le décrit 
- **RGX** : Un channel a un emoji qui le défini
- **RGX** : Deux channels peuvent avoir le même emoji
- **RGX** : Lors de la création d'un channel, celui-ci peut être stocké en tant que template de channel
- **RGX** : Un template de channels générique est disponible
- **RGX** : Les channels disparaissent un mois après la fin de la session associé
- **RGX** : Une template de channels est une liste de channels organisés
- **RGX** : Les channels disparaissent un mois après la fin de la session associé

## Gestion des channels vocaux
- **RGX** : Les channels vocaux peuvent être temporaire

## Gestion des Forums
- **RGX** : Un forum contient un nom unique qui le décrit
- **RGX** : Un forum peut être privé
- **RGX** : Dans le cas d'un forum privé, l'administrateur choisir les membres ou rôles qui peuvent rejoindre ce forum
- **RGX** : Seuls un administrateur et un directeur peuvent créer un forum
- **RGX** : Seuls un administrateur et un directeur peuvent modifier un forum
- **RGX** : Seuls un administrateur et un directeur peuvent supprimer un forum
- **RGX** : Un forum peut contenir une guideline indiquant la nature de ce forum
- **RGX** : Un forum peut contenir des tags qui lui sont propres pour filtrer les posts

## Gestion des Posts
- **RGX** : Empêcher les apprenants de créer des posts
- **RGX** : Un post contient un titre
- **RGX** : Un post contient un message
- **RGX** : Un post peut contenir un emoji
- **RGX** : Un post peut contenir une image
- **RGX** : Un post peut contenir une réaction par défaut
- **RGX** : Un post peut contenir un ou plusieurs tags
- **RGX** : Seul un administrateur peut créer un post
- **RGX** : Lors de la création d'un post, celui-ci peut être stocké en tant que template de post
- **RGX** :  Un template de posts générique est disponible
- **RGX** : Seul un administrateur peut modifier un post
- **RGX** : Seul un admnistrateur peut vérouiller un post
- **RGX** : Seul un admnistrateur et un modérateur peut écrire sur un post vérouillé
- **RGX** : Seul un admnistrateur peut dévérouiller un post
- **RGX** : Seul un admnistrateur peut fermer un post
- **RGX** : Seul un admnistrateur peut supprimer un post

## Gestion d'identification
- **RGX** : Une demande d'identification est effectuée par un nouvel arrivant
- **RGX** : Une demande d'identification passe par un formulaire
- **RGX** : Un formulaire de demande d'identification contient le nom de la personne
- **RGX** : Un formulaire de demande d'identification contient le prénom de la personne
- **RGX** : Un formulaire de demande d'identification contient l'username discord de la personne
- **RGX** : Un formulaire de demande d'identification contient l'adresse email de la personne
- **RGX** : Un formulaire de demande d'identification contient des informations supplémentaires de la personne
- **RGX** : Seul un administrateur, un CDP, un membre du staff peut accepter/refuser une demande d'identification
- **RGX** : La personne acceptant la demande d'identification peut attribuer le rôle de staff ou apprenant
- **RGX** : Lorsque ce rôle est apprenant, la personne acceptant la demande d'identification lui attribue le rôle de sa formation
- **RGX** : Une fois un rôle attribué au nouvel arrivant, ce rôle de nouvel arrivant lui est retiré
- **RGX** : Une fois le processus d'identification terminé, la demande d'identification est supprimée
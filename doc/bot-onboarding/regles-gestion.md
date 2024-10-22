# Règles de gestion

Les règles de gestion d'un bot ont pour but de rassembler l'ensemble de ses fonctionnalités et les règles qui y sont associées. Vous trouverez donc ci-dessous les règles de gestions du bot onboarding.

Attention, ***les règles de gestions en italiques** sont des suggestions et **ne sont pas prioritaires***.

## Gestion de promotion

- **RG1** : Une promotion contient un nom qui la décrit
- **RG2** : Une promotion contient une date de début et une date de fin
- **RG3** : Un administrateur, un directeur et un chargé de projet peuvent créer une promotion
- **RG4** : Un administrateur et un directeur et un chargé de projet peuvent modifier une promotion
- **RG5** : Un administrateur et un directeur et un chargé de projet peuvent supprimer une promotion
- **RG6** : Lors de la modification, un message de confirmation apparait
- **RG7** : Lors de la suppression, un message de confirmation apparait
- **RG8** : Lors de la création, un message de confirmation apparait
- **RG9** : Pour créer une promotion il sera nécessaire de sélectionner sa formation et sa fabrique associées
- **RG10** : La création d'une promotion crée également un rôle associé avec le nom de la promo
- **RG11** : La promotion est archivée un mois après la fin de la session associée
- **RG12** : Une promotion est forcément lié à une fabrique
- **RG13** : Une promotion est forcément lié à une formation
- **RG14** : Dans le client discord, les promotions seront groupées visuellement par fabrique

## Gestion de formation

- **RG15** : Une formation contient un nom qui l'a décrit
- **RG16** : Un administrateur, un directeur et un chargé de projet peuvent créer une formation
- **RG17** : Un administrateur, un directeur et un chargé de projet peuvent modifier une formation
- **RG18** : Un administrateur, un directeur et un chargé de projet peuvent supprimer une formation
- **RG19** : Lors de la modification, un message de confirmation apparait
- **RG20** : Lors de la suppression, un message de confirmation apparait
- **RG21** : Lors de la création, un message de confirmation apparait
- **RG22** : Lors de la création d'une formation, il sera possible de sélectionner des canaux déjà pré-enregistrés (template)
- **RG23** : Lors de la modification d'une formation, il sera possible de choisir des autres canaux déjà pré-enregistrés (template)
- **RG24** : Une formation contient un template de channels organisé qui lui est dédié

## Gestion de fabrique

- **RG25** : Une fabrique contient un nom qui la décrit
- **RG26** : Un administrateur, un directeur et un chargé de projet peuvent créer une fabrique
- **RG27** : Un administrateur, un directeur et un chargé de projet peuvent modifier une fabrique
- **RG28** : Un administrateur, un directeur et un chargé de projet peuvent supprimer une fabrique
- **RG29** : Lors de la modification, un message de confirmation apparait
- **RG30** : Lors de la suppression, un message de confirmation apparait
- **RG31** : Lors de la création, un message de confirmation apparait
- **RG32** : Une fabrique est liée à tous les apprenants en cours de formation dans celle-ci
- **RG33** : Une fabrique n'est plus liée à un apprenant lorsqu'il termine sa formation (doit âtre lié à l'apprenant)
- **RG34** : Une création de fabrique a pour conséquence la création de son rôle discord associé
- **RG35** : Seuls un administrateur et un directeur peuvent notifier les personnes concerné par une fabrique

## Gestion des channels

- **RG36** : Un administrateur, un directeur et un chargé de projet peuvent créer un channel dans le stock de channel
- **RG37** : Un administrateur, un directeur et un chargé de projet peuvent modifier un channel dans le stock de channel
- **RG38** : Un administrateur, un directeur et un chargé de projet peuvent supprimer un channel dans le stock de channel
- **RG39** : Un channel contient un nom unique qui le décrit
- ***RG40** : Un channel a un emoji qui le défini*
- **RG41** : Deux channels peuvent avoir le même emoji
- **RG42** : Lors de la création d'un channel, celui-ci peut être stocké en tant que template de channel
- **RG43** : Un template de channels générique est disponible et modifiable
- **RG44** : Une template de channels est une liste de channels organisés

## Gestion des channels vocaux

- **RG45** : un channel vocal général et un channel vocal SOS sont présents par défaut, le reste est créé à la demande
- **RG46** : Les channels vocaux créés sont temporaires

## Gestion des Forums

- **RG47** : Un forum contient un nom unique qui le décrit
- **RG48** : Un forum peut être privé
- **RG49** : Dans le cas d'un forum privé, l'administrateur choisir les membres ou rôles qui peuvent rejoindre ce forum
- **RG50** : Seuls un administrateur et un directeur peuvent créer un forum
- **RG51** : Seuls un administrateur et un directeur peuvent modifier un forum
- **RG52** : Seuls un administrateur et un directeur peuvent supprimer un forum
- **RG53** : Un forum peut contenir une guideline indiquant la nature de ce forum
- **RG54** : Un forum peut contenir des tags qui lui sont propres pour filtrer les posts

## Gestion des Posts

- **RG55** : Empêcher les apprenants de créer des posts
- **RG56** : Un post contient un titre
- **RG57** : Un post contient un message
- **RG58** : Un post peut contenir un emoji
- **RG59** : Un post peut contenir une image
- **RG60** : Un post peut contenir une réaction par défaut
- **RG61** : Un post peut contenir un ou plusieurs tags
- **RG62** : Seuls un administrateur et un directeur peuvent créer un post dans le stock de post
- **RG63** : Lors de la création d'un post, celui-ci peut être stocké en tant que template de post
- **RG64** : Un template de posts générique est disponible
- **RG65** : Seuls un administrateuret un directeur peuvent modifier un post dans le stock de post
- **RG66** : Seuls un administrateur et un directeur peuvent supprimer un post dans le stock de post

## Gestion d'identification

- **RG67** : Une demande d'identification est effectuée par un nouvel arrivant
- **RG68** : Une demande d'identification passe par un formulaire
- **RG69** : Un formulaire de demande d'identification contient le nom de la personne
- **RG70** : Un formulaire de demande d'identification contient le prénom de la personne
- **RG71** : Un formulaire de demande d'identification contient l'adresse email de la personne
- **RG72** : Un formulaire de demande d'identification contient un champs libre de données complémentaires de la personne
- **RG73** : Un formulaire de demande d'identification contient des listes déroulantes permettant de cibler le profil de l'utilisateur (ex. sa formation)
- **RG74** : Un formulaire de demande d'identification contient un encart lié au RGPD selon lequel la personne consent au traitement de ses données personnelles
- **RG75** : Un administrateur, un directeur, un chargé de projet peuvent accepter/refuser une demande d'identification
- **RG76** : La personne acceptant la demande d'identification peut attribuer le rôle en question
- **RG77** : Une fois la demande d'identification acceptée, la personne sera automatiquement renommée par son nom et prénom
- **RG78** : Lorsque ce rôle est apprenant, la personne acceptant la demande d'identification lui attribue le rôle de sa formation et de la promotion
- **RG79** : Une fois un rôle attribué au nouvel arrivant, ce rôle de nouvel arrivant lui est retiré
- **RG80** : Une fois le processus d'identification terminé, la demande d'identification est masquée pour l'utilisateur

## Ciblages

- **RG81** : Un administrateur, un directeur et un chargé de projet peuvent notifier les personnes avec @everyone et @here

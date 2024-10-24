# Règles de gestion

Les règles de gestion d'un bot ont pour but de rassembler l'ensemble de ses fonctionnalités et les règles qui y sont associées. Vous trouverez donc ci-dessous les règles de gestions du bot onboarding.

Attention, ***les règles de gestions en italiques** sont des suggestions et **ne sont pas prioritaires***.

## Glossaire

- Stock de channels vocaux : il s'agit de channels stockés dans une "category" discord. Il devient alors possible de les dupliquer lors de la création d'une nouvelle promotion par exemple. 

- Stock de forums : il s'agit de template de forums avec des posts dédiés que l'on peut sélectionner lors de la création d'une formation.

## Gestion de promotion

- **RG1** : Une promotion possède un nom qui la décrit
- **RG2** : Une promotion contient une date de début et une date de fin
- **RG3** : Un administrateur, un directeur et un chargé de projet peuvent créer une promotion
- **RG4** : Un administrateur et un directeur et un chargé de projet peuvent modifier une promotion
- **RG5** : Un administrateur et un directeur et un chargé de projet peuvent supprimer une promotion
- **RG6** : Lors de la modification, un message de confirmation apparait
- **RG7** : Lors de la suppression, un message de confirmation apparait
- **RG8** : Lors de la création, un message de confirmation apparait
- **RG9** : Pour créer une promotion il sera nécessaire de renseigner son nom puis de sélectionner sa formation et sa fabrique associées
- **RG10** : La création d'une promotion crée également un rôle associé avec le nom de la promo
- **RG11** : La promotion est archivée un mois après la fin de la session associée
- **RG12** : Une promotion est forcément liée à une fabrique
- **RG13** : Une promotion est forcément liée à une formation
- **RG14** : Dans le client discord, les promotions seront groupées visuellement par fabrique

## Gestion de formation

- **RG15** : Une formation possède un nom qui l'a décrit
- **RG16** : Un administrateur, un directeur et un chargé de projet peuvent créer une formation
- **RG17** : Un administrateur, un directeur et un chargé de projet peuvent modifier une formation
- **RG18** : Un administrateur, un directeur et un chargé de projet peuvent supprimer une formation
- **RG19** : Lors de la modification, un message de confirmation apparait
- **RG20** : Lors de la suppression, un message de confirmation apparait
- **RG21** : Lors de la création, un message de confirmation apparait
- **RG22** : Lors de la création d'une formation, il sera possible de sélectionner des channels vocaux dans le stocks de channels vocaux
- **RG23** : Lors de la modification d'une formation, il sera possible de sélectionner d'autres channels disponibles dans le stock de channels vocaux
- **RG25** : Un apprenant est toujours lié à sa formation une fois sa promotion archivée

## Gestion de fabrique

- **RG26** : Une fabrique possède un nom qui la décrit
- **RG27** : Un administrateur, un directeur et un chargé de projet peuvent créer une fabrique
- **RG28** : Un administrateur, un directeur et un chargé de projet peuvent modifier une fabrique
- **RG29** : Un administrateur, un directeur et un chargé de projet peuvent supprimer une fabrique
- **RG30** : Lors de la modification, un message de confirmation apparait
- **RG31** : Lors de la suppression, un message de confirmation apparait
- **RG32** : Lors de la création, un message de confirmation apparait
- **RG33** : Les apprenants en cours de formation dans une fabrique sont liés à cette dernière 
- **RG34** : Un apprenant n'est plus lié à la fabrique une fois sa promotion archivée
- **RG35** : Une création de fabrique a pour conséquence la création de son rôle discord associé
- **RG36** : Un administrateur, un directeur et un chargé de projet peuvent notifier les personnes concernées par une fabrique
- **RG37** : Lorsqu'une fabrique est supprimée, toutes les promotions actives qui y sont liées sont supprimées aussi

## Gestion des channels

- **RG38** : Un administrateur, un directeur et un chargé de projet peuvent créer un channel dans le stock de channel
- **RG39** : Un administrateur, un directeur et un chargé de projet peuvent modifier un channel dans le stock de channel
- **RG40** : Un administrateur, un directeur et un chargé de projet peuvent supprimer un channel dans le stock de channel
- **RG41** : Un channel possède un nom unique qui le décrit
- ***RG42** : Un channel a un emoji qui le défini*
- **RG43** : Deux channels peuvent avoir le même emoji
- **RG44** : Lors de la création d'un channel, celui-ci peut être stocké en tant que template de channel
- **RG45** : Un template de channels générique est disponible et modifiable
- **RG46** : Une template de channels est une liste de channels organisés

## Gestion des channels vocaux

- **RG47** : un channel vocal général et un channel vocal SOS sont présents par défaut, le reste est créé à la demande
- **RG48** : Les channels vocaux créés sont temporaires

## Gestion des Forums

- **RG49** : Un forum possède un nom unique qui le décrit
- **RG51** : Un administrateur, un directeur et un chargé de projet peuvent créer un forum pré-enregistré
- **RG52** : Un administrateur, un directeur et un chargé de projet peuvent modifier un forum pré-enregistré
- **RG53** : Un administrateur, un directeur et un chargé de projet peuvent supprimer un forum pré-enregistré
- ***RG56** : Un forum peut contenir une guideline indiquant la nature de ce forum*

## Gestion des Posts

- **RG57** : Les apprenants ne doivent pas pouvoir créer des postes
- **RG58** : Un post possède un titre
- **RG59** : Un post contient un message
- ***RG60** : Un post peut contenir un emoji*
- ***RG61** : Un post peut contenir une image*
- ***RG62** : Un post peut contenir une réaction par défaut*
- ***RG63** : Un post peut contenir un ou plusieurs tags*

## Gestion d'identification

- **RG64** : Une demande d'identification est effectuée par un nouvel arrivant
- **RG65** : Une demande d'identification passe par un formulaire
- **RG66** : Un formulaire de demande d'identification contient le nom de la personne
- **RG67** : Un formulaire de demande d'identification contient le prénom de la personne
- **RG68** : Un formulaire de demande d'identification contient l'adresse email de la personne
- **RG69** : Un formulaire de demande d'identification contient un champs libre de données complémentaires de la personne
- **RG70** : Un formulaire de demande d'identification contient des listes déroulantes permettant de cibler le profil de l'utilisateur (ex. sa formation)
- **RG71** : Un formulaire de demande d'identification contient un encart lié au RGPD selon lequel la personne consent au traitement de ses données personnelles
- **RG72** : Un administrateur, un directeur, un chargé de projet peuvent accepter/refuser une demande d'identification
- **RG73** : La personne acceptant la demande d'identification peut attribuer le rôle en question
- **RG74** : Une fois la demande d'identification acceptée, la personne sera automatiquement renommée par son nom et prénom
- **RG75** : Lorsque ce rôle est apprenant, la personne acceptant la demande d'identification lui attribue le rôle de sa formation et de la promotion
- **RG76** : Une fois un rôle attribué au nouvel arrivant, ce rôle de nouvel arrivant lui est retiré
- **RG77** : Une fois le processus d'identification terminé, la demande d'identification est masquée pour l'utilisateur

## Ciblages

- **RG78** : Un administrateur, un directeur et un chargé de projet peuvent notifier les personnes avec @everyone et @here

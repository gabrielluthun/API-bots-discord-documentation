# Règles de gestion

Les règles de gestion d'un bot ont pour but de rassembler l'ensemble de ses fonctionnalités et les règles qui y sont associées. Vous trouverez donc ci-dessous les règles de gestions du bot onboarding.

Attention, ***les règles de gestions en italiques** sont des suggestions et **ne sont pas prioritaires***.

## Glossaire

- Stock de channels vocaux : il s'agit de channels stockés dans une "category" discord. Il devient alors possible de les dupliquer lors de la création d'une nouvelle formation. Ils servent aussi à la création de post dans la mesure on l'on pourra récupérer les noms des channels stockés pour les utiliser en tant que "nom" et "message" pour créer des posts.

## Gestion de promotion

- **RG1** : Une promotion possède un nom qui la décrit
- **RG2** : Une promotion contient une date de début et une date de fin
- **RG3** : Un administrateur, un directeur et un chargé de projet peuvent créer une promotion
- **RG4** : Un administrateur et un directeur et un chargé de projet peuvent modifier une promotion
- **RG5** : Un administrateur et un directeur et un chargé de projet peuvent supprimer une promotion
- **RG6** : Lors de la modification, un message de confirmation apparait
- **RG7** : Lors de la suppression, un message de confirmation apparait
- **RG8** : Lors de la création, un message de confirmation apparait
- **RG9** : Pour créer une promotion il sera nécessaire de renseigner son nom puis de sélectionner sa formation et son campus associées
- **RG10** : La création d'une promotion crée également un rôle associé avec le nom de la promo
- **RG11** : La promotion est archivée un mois après la fin de la session associée
- **RG12** : Une semaine avant la fin d'une promotion, une notification automatique doit être envoyée sur le channel général de la promotion concernée pour prévenir qu'elle sera archivée un mois à compter de la fin de leur formation 
- **RG13** : Une promotion est forcément liée à un campus
- **RG14** : Une promotion est forcément liée à une formation
- **RG15** : Dans le client discord, les promotions seront groupées visuellement par campus

## Gestion de formation

- **RG15** : Une formation possède un nom qui l'a décrit
- **RG16** : Un administrateur, un directeur et un chargé de projet peuvent créer une formation
- **RG17** : Un administrateur, un directeur et un chargé de projet peuvent modifier une formation
- **RG18** : Un administrateur, un directeur et un chargé de projet peuvent supprimer une formation
- **RG19** : Lors de la modification, un message de confirmation apparait
- **RG20** : Lors de la suppression, un message de confirmation apparait
- **RG21** : Lors de la création, un message de confirmation apparait
- **RG22** : Lors de la création d'une formation, les channels disponibles dans la category "stock-channels" seront sélectionnés par défaut
- **RG23** : Dans le contexte de la création de formation, il existera une category "stock-posts" qui contiendra un forum "posts-generiques" dans lequel il sera possible de retrouver les posts que l'on retrouvera toujours dans chaque formation
- **RG24** : Dans la category "stock-posts", on retrouvera aussi un forum "posts-specifiques" dans lequel il sera possible de retrouver les posts spécifiques à chaque formation
- **RG25** : Lors de la création d'une formation, les posts présents dans le forum "posts-generiques" seront sélectionnés par défaut
- **RG26** : Lors de la création d'une formation, il sera possible de sélectionner des posts plus spécifiques dans le forum "posts-specifiques"
- **RG27** : Lors de la modification d'une formation, il sera possible d'ajouter ou de retirer des posts
- **RG28** : Un étudiant est toujours lié à sa formation une fois sa promotion archivée

## Gestion de campus

- **RG29** : Un campus possède un nom qui la décrit
- **RG30** : Un administrateur, un directeur et un chargé de projet peuvent créer un campus
- **RG31** : Un administrateur, un directeur et un chargé de projet peuvent modifier un campus
- **RG32** : Un administrateur, un directeur et un chargé de projet peuvent supprimer un campus
- **RG33** : Lors de la modification, un message de confirmation apparait
- **RG34** : Lors de la suppression, un message de confirmation apparait
- **RG35** : Lors de la création, un message de confirmation apparait
- **RG36** : Un étudiant en cours de formation dans un campus sont liés à ce dernier
- **RG37** : Un étudiant n'est plus lié au campus une fois sa promotion archivée
- **RG38** : Une création de campus a pour conséquence la création de son rôle discord associé
- **RG39** : Un administrateur, un directeur et un chargé de projet peuvent notifier les personnes concernées par un campus
- **RG40** : Lorsqu'un campus est supprimée il y a un choix entre supprimer ou archiver les promotions qui y sont liées.

## Gestion des channels vocaux

- **RG41** : Un channel vocal possède un nom qui le décrit
- **RG42** : Un channel vocal a un emoji qui le défini
- **RG43** : Un administrateur, un directeur et un chargé de projet peuvent créer un channel vocal dans le stock de channel
- **RG44** : Un administrateur, un directeur et un chargé de projet peuvent modifier un channel vocal dans le stock de channel
- **RG45** : Un administrateur, un directeur et un chargé de projet peuvent supprimer un channel vocal dans le stock de channel
- **RG46** : Il n'y a que trois chanels vocaux fixes par promotion : un SOS, un général et un On demand
- **RG47** : Des channels vocaux temporaires sont disponibles pour chaque promotion
- **RG48** : Un channel vocal temporaire disparaît quand il n'y a personne dedans 

## Gestion des Forums

- **RG49** : Un forum possède un nom qui le décrit
- **RG50** : Un forum contient des posts qui lui sont propres 
- **RG51** : Un administrateur, un directeur et un chargé de projet peuvent enregistrer un forum au moment de la création de la formation
- **RG52** : Un administrateur, un directeur et un chargé de projet peuvent modifier un forum 
- **RG53** : Un administrateur, un directeur et un chargé de projet peuvent supprimer un forum 
- ***RG54** : Un forum peut contenir une guideline indiquant la nature de ce forum*

## Gestion des Posts

- **RG55** : Les étudiants ne doivent pas pouvoir créer des posts
- **RG56** : Un post possède un titre
- **RG57** : Un post contient un message
- ***RG58** : Un post peut contenir un emoji*
- ***RG59** : Un post peut contenir une image*
- ***RG60** : Un post peut contenir une réaction par défaut*
- ***RG61** : Un post peut contenir un ou plusieurs tags*

## Gestion d'identification

- **RG62** : Une demande d'identification est effectuée par un nouvel arrivant
- **RG63** : Une demande d'identification passe par un formulaire
- **RG64** : Un formulaire de demande d'identification contient le nom de la personne
- **RG65** : Un formulaire de demande d'identification contient le prénom de la personne
- **RG66** : Un formulaire de demande d'identification contient l'adresse email de la personne
- **RG67** : Un formulaire de demande d'identification contient des listes déroulantes permettant de cibler le profil de l'utilisateur (ex. sa formation)
- **RG68** : Un formulaire de demande d'identification contient un encart lié au RGPD selon lequel la personne consent au traitement de ses données personnelles
- **RG69** : Un formulaire de demande d'identification contient un encart lié aux règles de gestions du serveur Discord Simplon Hauts-de-France auxquelles le nouvel arrivant devra accepter de se soumettre
- **RG70** : Un administrateur, un directeur, un chargé de projet peuvent accepter/refuser une demande d'identification
- **RG71** : La personne acceptant la demande d'identification permettra au bot d'attribuer automatiquement le rôle ou les rôles destinés
- **RG72** : Une fois la demande d'identification acceptée, la personne sera automatiquement renommée par son nom et prénom
- **RG73** : Une fois qu'un rôle est attribué à un nouvel arrivant, son rôle de nouvel arrivant lui est retiré
- **RG74** : Une fois le processus d'identification terminé, la demande d'identification est masquée pour l'utilisateur

## Ciblages

- **RG75** : Un administrateur, un directeur et un chargé de projet peuvent notifier les personnes avec @everyone et @here

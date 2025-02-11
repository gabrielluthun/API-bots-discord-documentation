# Notes de réunion du rendez-vous du  janvier 2025 à 15h

(rappel de notre équipe de la réunion précédente)

## Les diagrammes:
### le MCD:
Question BJ: a t on vu l'ancien MCD? Explication du MCD de remaster

on niveau des users: il devrait y avoir des infos dans user telles que name, discriminator, created at,updated at (à voir avec les formateurs si les deux derniers champs sont à mettre dans un MCD). Il manque des infos dans notre entité
  (account était pour l'ancien panel admin, ne pas prendre en compte)  

BJ: on n'a pas une approche par guilde. Le bot doit être prévu pour être scalable.

on n'a pas d'entité membre, qui regroupe tous les membre du serveur (un membre est lié à une guilde)

Notre MCD n'est pas assez complet

on doit toujours se poser la question de ce qu'on doit stocker ou pas (tout doit avoir une raison)

question de stock discord et/ou base de données. Pouquoi stocker une structure de donnée en bdd alros qu'elle est déjà stockée par l'API discord? > parce que DIscordJS peut hook, c'est plus facile à maintenir. (on risque de doubler de la donnée et que c'est compliqué sans BDD)

On associe un utilisateur discord à ses informations personnelles.

pour trouver les apprenants, on peut le faire via discord ou bdd, la bdd permet d'avoir un maillage logique de données, d'optimiser les requêtes discord, pour ne prendre qu'une tranche de données plutot que devoir parcourir tout le serveur discord

entité message: pour les template de post: le message plutot que le stocker en bdd, est ce qu'on peut pas dire que le message c'est le nom du post? cette entité n'est donc pas pertinente (par exemple nommer un message alors qu'il n'y a pas d'auteur) le plus simple est de ne pas avoir besoin de stocker ces messages (et le nom est mal choisi)


grosse refonte à faire, penser aux 3nf

### user case authentification: tout le monde, quel que soit le type d'utilisateur, passe d'abord par nouvel arrivant (ajouter l'héritage manquant)

attention, un bot ne s'auto configure pas (revoir le trait entre le bot et l'action gérer le bot)

rajouter des lien entre le bot et ses actions effectives  
Renommer système: "authentification..."  

Globalement, ce use case focntionne  

### User case Création: 
Pas d'admin parce qu'il n'a pas plus de droit que le staff: BJ permet le rajouter même si il n'a pas d'action propre à lui  

système: nom "création"  

c'est un système qui représente beaucoup de choses. La finalité, c'est la création de la promotion, qui inclue tout le reste

BJ ne trouve rien de trop étrange à ce user case  

### Diagramme de classe: Il ressemble trop au MCD

Le diagrmme de remaster, c'est le diagramme de l'API
Voir le code de l'API  

BJ: il est parti de l'organisation du code NestJS et a brodé autour

Diagramme de classe est un diagramme de conception applicatif. Il doit bien refléter notre code.

(bien rajouter entités, DTO, vraiment absolument toutes le classes qui seront présentent. Les intéractions entre les classes etc.)

BJ: toutes interaction entre tout les composant sont listés dans son diagramme de classe

question modification du diagramme en cours de développement ? BJ : oui ça m'arrivait. La conception, même bien réfléchie en amont, arrive que l'on doit y retoucher par la suite pour tout prendre en compte

S'inspirer du diagramme de classe pour bien comprendre sont fonctionnement et son intérêt

BJ: le diagramme de classe côté bot. Lorsque BJ est arrivé sur le diagramme de classe, à l'époque il a fait comme nous, retranscrire le MCD pour le diagramem de classe (ce qui n'est pas bon)

BJ: lorsqu'il est arrivé sur le dev, c'est là qu'il s'st rendu compte qu'il y avait des manques.

note: ce que l'on a fait n'est pas faux, mais c'est une base à laquelle il y a beaucoup de manques

question modification promotion: pour les changements majeurs, on suprrime, on ne garde que les modifications simples.

la suppression de propotion est meilleure via le bot ou sans bot? > si manuel, attention à la BDD. Que ce soit manuel ou avec un bouton, le resultat devra être le même (suppression bien effectuée partout). Les CAP nativement n'ont pas la possibilité de supprimer des category et des chans

ici la suppression, c'est pour la suppression d'une promotion mal faite. Là c'est à caluler la quelle façon est la plus rapide. (plus rapide 8 clic ou une suppression en terme d'UX. IL vaut mieux donc le bouton de suppression automatique)

### le cas de quelqu'un qui s'est déjà identifié pour lui attribuer une nouvelle formation.

C'est un point qui n'a pas dé réponse pour le moment, a y réfléchir, quelques pistes évoquées sans aucune affirmation :il faudra peut être ajouter tout le modne en BDD. CLaire: avant c'est les cdp qui font en manuel. Mais c'est rébaratif car il y a beaucoup de suites de parcours. Question: changmenet de rôle à partir du même email, comment faire pour les anciens? récupérer les membre du serveur et dmander à ceux qui n'ont pas de rajouter leur email (ça ferait 3000 notifs d'un coup)? Pas possible.
Par cotnre idée de laisser l'onboarding pour les alumnis, voires les alumnis qui n'ont pas refait de formation (pas de réponse claire sur cette question, il faut y réfléchir).  

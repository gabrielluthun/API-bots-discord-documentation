# Introduction
Ce document vise à présenter de manière claire et accessible la stratégie globale de sécurisation appliquée aux projets de bots Discord, ainsi qu’à l’API et au tableau de bord associés. Pour garantir une sécurité optimale, nous nous appuyons sur les recommandations de l’ANSSI (Agence Nationale de la Sécurité des Systèmes d’Information), de l’OWASP (Open Web Application Security Project) et des bonnes pratiques issues de MDN Security.
## Défense en profondeur
Le système repose sur plusieurs composants distincts : les bots Discord, l’API, la base de données et le tableau de bord (dashboard). Pour garantir une sécurité robuste, chaque composant sera traité comme un point de contrôle stratégique. Ces points de contrôle joueront un rôle clé dans la détection, le filtrage et la neutralisation des menaces, limitant ainsi leur propagation au sein du système.

## Réduction de la surface d'attaque
Dans le cadre du principe de réduction de la surface d'attaque, nous limiterons l'exposition des points d'entrée au strict minimum nécessaire. Chaque composant disposera de permissions et d'accès restreints, et toutes les fonctionnalités ou services non essentiels au bon fonctionnement du système seront désactivés.
```
Exemple :
Communication dédiée : Le bot Discord "signature" interagira avec l'API uniquement via des routes spécifiques et isolées du reste du système.
```
En complément, l’exposition réseau sera également limitée grâce à l’utilisation d’une liste blanche de ports autorisés.
```
Exemple:
Port dédié : Le bot Discord "signature" utilisera exclusivement le port 5239 pour ses communications.
```
Enfin, tous les services inutiles seront désactivés pour réduire les risques d’exploitation. (exemple: service FTP).
## RGPD
Pour chaque utilisateur du système, certaines parties interagiront avec des données personnelles telles que le nom, le prénom et l’adresse e-mail. Conformément à la réglementation en vigueur, notamment le RGPD, nous respecterons les directives de la CNIL (Commission Nationale de l'Informatique et des Libertés). Ces mesures garantiront une collecte, un stockage et un traitement des données personnelles dans des conditions sécurisées et transparentes.

### Consentement explicite
Nous demanderons de façon claire et explicite à l'utilisateur son accord pour la collecte et l'utilisation de ses données personnelles. 

### Droit de consultation
Nous nous assurerons que l'utilisateur est en mesure de pouvoir consulter les données qui lui sont associées.

### Droit de modification
Nous permettrons à l'utilisateur de pouvoir modifier simplement ses données lorsqu'il le souhaite.

### Droit à l'oubli
Nous permettrons à l'utilisateur de pouvoir supprimier totalement ses informations du système.

### Prévention
En cas de faille dans le systèmes, nous avertirons que leurs données personnelles ont été compromises.
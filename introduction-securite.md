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
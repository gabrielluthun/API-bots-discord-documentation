# Back-end

## Sommaire

## Introduction

- Politique de moindre privilège
- RBAC
- Journalisation

### Politique de moindre privilège

Cette politique a pour objectif de ne donner que les permissions strictement nécessaires aux acteurs et éléments du système pour fonctionner. L'objectif est de limiter le risque de vol, d’altération ou de destruction de données dans le cas de compromission d’un ou plusieurs éléments. Cette politique contribue à la réduction de la surface d'attaque, et s'applique au niveau de la base de données ainsi que de l'API.

#### 1. **Moindre privilège dans la BDD**

Les comptes utilisés pour acceder à la base de données doivent être configurés de manière à limiter les privilèges :

   - **Accès rôle spécifique** : Un utilisateur ayant un rôle "lecteur" dans la base de données ne doit avoir que des privilèges en lecture, et non des privilèges en écriture ou en suppression.

#### 2. **Moindre privilège dans l'API**

Chaque utilisateur doit avoir accès uniquement aux ressources nécessaires pour ses fonctions. Cela implique de :

   - **Limiter les rôles et permissions** : Par exemple, un utilisateur standard n'a pas besoin d'accéder à des données administratives ou de configurer les paramètres du serveur. Seuls les administrateurs devraient avoir ces privilèges.

   - **Sépararer les rôles** : La création de rôles différents, comme "utilisateur", "modérateur", "administrateur", permet de restreindre l'accès aux fonctionnalités spécifiques selon les besoins des utilisateurs.

La politique de moindre privilège est essentielle pour plusieurs raisons :

   - **Réduction des risques de compromission** : En limitant les permissions, on réduit la surface d'attaque de l'application. Si un utilisateur ou un processus malveillant réussit à compromettre un compte, l'impact sera réduit puisque les privilèges sont restreints.

   - **Prévention des escalades de privilèges** : L'application des principes de moindre privilège limite les possibilités pour un attaquant d'escalader ses privilèges dans le système.


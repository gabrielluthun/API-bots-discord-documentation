# Back-end

## Introduction

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

### RBAC

Le **RBAC** (**R**ole **B**ased **A**ccess **C**ontrol), souvent représenté sous forme d'un tableau, permet de définir les permissions pour chaque rôle. Etablir un RBAC permet de s'assurer de la bonne distribution des permissions dans l'application, et contribue à la mise en place de la politique de moindre privilège.

### Journalisation

La **journalisation** consiste à enregistrer des événements et actions importantes afin de faciliter la surveillance, le débogage, la sécurité, et la maintenance de l'application. C'est une mesure importante pour assurer la sécurité, la maintenance, et l’optimisation. Voici plusieurs objectifs de la journalisation :

   - **Surveiller les actions des utilisateurs** : Mettre en place des mécanismes de surveillance pour détecter des comportements suspects ou des tentatives d'escalade de privilèges.

   - **Effectuer des audits réguliers** : Analyser périodiquement les droits d'accès et les privilèges des utilisateurs, ainsi que les configurations des systèmes pour détecter des anomalies et garantir que les privilèges n'ont pas été excessivement élargis.

Cependant, il convient de respecter les bonnes pratiques, en faisant en sorte que les journaux ne puissent pas être utilisés à des fins malveillants. Par exemple, des données pourraient être dérobées via ces journaux. Ou encore, la création de journaux pourrait servir à une attaque par déni de service.

## Base de données

### Utilisation des UUID

Un UUID (Universally Unique Identifier) est un identifiant standardisé de 128 bits garantissant l'unicité à l'échelle mondiale.

**Pourquoi mettre en place les UUID ?**

L’utilisation des UUID (Universally Unique Identifier) dans une architecture back-end offre un moyen robuste et universel pour identifier des entités.

Il vise à remplacer les identifiants séquentiels par des identifiants uniques, aléatoires et non prédictibles.

En effet, si un individu malveillant venait à récupérer les informations d’un compte utilisateur et son identifiant, il pourrait savoir aisément s’il y a d'autres comptes avant ou après dans la base de données. L’utilisation d’un UUID rend les identifiants utilisateur totalement indépendants les uns des autres.

**Pour lutter contre quelle menace ?**

L’utilisation des UUID renforce la sécurité dans plusieurs contextes. Voici les attaques courantes et la manière dont les UUID aident à les contrer :

1. **Prévention des attaques par force brute :**

   - **Problème avec les IDs séquentiels**: Lorsqu'un système utilise des IDs séquentiels (par ex. `user_id=1, user_id=2`), un attaquant peut facilement deviner ou itérer sur les identifiants pour accéder à des données ou des ressources qu’il ne devrait pas voir.
   - **Solution UUID** : Les UUID, particulièrement ceux générés de manière aléatoire, sont imprévisibles. Leur longueur et leur format rendent une attaque par force brute ou devinette beaucoup plus difficile.
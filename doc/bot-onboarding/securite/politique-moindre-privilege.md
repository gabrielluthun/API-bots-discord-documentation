# Politique de moindre privilège
1. **Gestion des rôles utilisateur via Discord** :
   - Les utilisateurs sont segmentés en rôles (admin, modérateur, utilisateur) avec des permissions spécifiques au sein du serveur Discord.
   - Les commandes critiques (ex. : suppression de messages, bannissement) sont limitées aux administrateurs ou modérateurs.

2. **Sécurité des bots dans Discord** :
   - Le bot Discord est configuré avec des rôles distincts, n’ayant accès qu’aux channels où il doit interagir.
   - Des règles strictes sont appliquées pour empêcher que le bot n’exécute des commandes non prévues ou provenant de sources externes.

3. **Permissions dans l’API** :
   - Implémentation d’un contrôle d’accès basé sur les rôles (RBAC) pour les endpoints API, avec des autorisations adaptées à chaque niveau (lecture, écriture, administration).
   - Les tokens d’accès API expirent automatiquement après une période définie (ex. : 15 minutes), limitant les risques liés à leur compromission.

4. **Authentification des administrateurs** :
   - Utilisation d’OAuth2 pour authentifier les administrateurs du serveur Discord avant qu’ils puissent effectuer des actions via l’API.

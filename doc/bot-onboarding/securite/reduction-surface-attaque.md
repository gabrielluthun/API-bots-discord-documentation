
# Réduction de la surface d’attaque
1. **Gestion des permissions Discord** :
   - Le bot utilise uniquement les permissions minimales nécessaires (ex. : gestion des messages, accès à certains channels) pour réduire le risque de compromission.
   - Désactivation des permissions inutiles comme la modification de paramètres globaux sur le serveur.

2. **Protection des webhooks Discord** :
   - Les webhooks utilisés par le bot sont protégés par des secrets et ne sont accessibles que via des IP ou domaines autorisés.
   - Les webhooks ne doivent jamais être exposés dans le code source ou les logs.

3. **Isolation des composants API** :
   - L’API est déployée dans un environnement isolé (Docker ou Kubernetes), avec des règles réseau restreintes pour n’autoriser que le trafic provenant de Discord.
   - Segmentation des bases de données pour limiter les accès directs à l’API.

4. **CSP et CORS pour l’API** :
   - Configuration de **CORS (Cross-Origin Resource Sharing)** pour n’accepter que les requêtes provenant de domaines autorisés.
   - Les réponses API intègrent des en-têtes de sécurité comme **Content Security Policy (CSP)** pour limiter les ressources exécutées.




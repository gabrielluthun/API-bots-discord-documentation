# Règles de gestion

# Configuration du bot
- R.G 1: Le bot possède une fonctionnalité pour s'arrêter.
- R.G 2: Le bot possède une fonctionnalité pour démarrer.
- R.G 3: Le bot possède une fonctionnalité pour redémarrer.
- R.G 4: Le bot possède une fonctionnalité pour créer un message dans le thread signature du channel des promos qui gère l'interface de vote (R.G 10 à R.G 20).
- R.G 5: Le bot possède une fonctionnalité pour créer un message dans le thread signature du channel des promos qui gère l'interface notification que les apprenants peuvent signer (R.G 21 à R.G 27).
- R.G 6: Le bot possède une fonctionnalité pour créer un message dans le thread signature du channel des promos qui gère l'interface de rappel de signature (R.G 28 à R.G 36).
- R.G 7: Le bot possède une fonctionnalité pour créer les trois messages d'un coup.
- R.G 8: Le bot possède une fonctionnalité pour créer les messages dans plusieurs threads signature d'un coup.
- R.G 9: Le bot possède une fonctionnalité pour créer les messages dans tous les threads signature d'un coup (pour l'initialisation du bot).

# Rappeler à un formateur qu'il a oublié de faire signer
- R.G 10: Le message est lié à un channel de promo.
- R.G 11: Le message prend la forme d'un vote.
- R.G 12: Le message contient une liste de boutons.
- R.G 13: Il y a un bouton par formateur de la promo.
- R.G 14: Les boutons ont deux états : actif et inactif.
- R.G 15: Un seul bouton peut être actif à la fois.
- R.G 16: Activer un bouton désactive les autres.
- R.G 17: Il faut un bouton actif pour lancer le vote.
- R.G 18: Il y a un bouton pour démarrer le vote.
- R.G 19: Il faut trois votes pour que le vote soit un succès.
- R.G 20: Dès que le vote est un succès, le bot envoie un message privé au formateur pour l'avertir qu'il doit autoriser les apprenants à signer.

# Prévenir les apprenants qu'ils peuvent signer
- R.G 21: Le message est lié à un channel de promo.
- R.G 22: Le message possède un bouton.
- R.G 23: Seuls les formateurs peuvent utiliser le bouton.
- R.G 24: Le message est envoyé directement dans le thread signature.
- R.G 25: La promo est notifiée via un tag @.
- R.G 26: Le bot peut sauvegarder l'ID du message.
- R.G 27: Le bot peut supprimer le message quand il n'est plus utile.
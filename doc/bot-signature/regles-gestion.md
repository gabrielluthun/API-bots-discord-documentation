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

# Rappeler à un apprenant qu'il a oublié de signer
- R.G 28: Le message est lié à un channel de promo.
- R.G 29: Le message contient une liste de boutons.
- R.G 30: Seuls les formateurs peuvent interagir avec les boutons.
- R.G 31: Il y a un bouton par apprenant de la promo.
- R.G 32: Les boutons ont deux états : actif et inactif.
- R.G 33: Plusieurs boutons peuvent être actifs en même temps.
- R.G 34: Il y a un bouton pour valider l'envoi des rappels.
- R.G 35: Lorsqu'un rappel est validé, le bot dresse une liste d'apprenants à notifier selon l'état "activé" des boutons.
- R.G 36: Les apprenants sélectionnés sont notifiés par message privé.

# Journalisation
- R.G 37: Le bot enregistre chaque fois qu'un utilisateur fait appel à lui dans un journal.
    - R.G 38: Le journal écrit les informations de la manière suivante :
    - R.G 39: À quelle date a été lancée la commande.
    - R.G 40: Quel utilisateur a lancé la commande.
    - R.G 41: Quelle commande a été utilisée.
    - R.G 42: À quel utilisateur la commande est-elle destinée.

# Structuration de l'organisation
- R.G 43: Un formateur est lié à une ou plusieurs promotions.
- R.G 44: Une promotion est liée à un ou plusieurs formateurs.
- R.G 45: Un apprenant suit une formation à la fois.
- R.G 46: Une promotion regroupe plusieurs apprenants.
- R.G 47: Un apprenant appartient à une promotion.
- R.G 48: Une promotion a un chargé de projets.
- R.G 49: Un chargé de projets a une ou plusieurs promotions.
- R.G 50: Une formation peut être dispensée dans un ou plusieurs centres.
- R.G 51: Un centre peut proposer une ou plusieurs formations.

# Données nécessaires au bot
- R.G 52: Le bot doit avoir accès à la liste des formateurs.
- R.G 53: Le bot doit avoir accès à la liste des formations.
- R.G 54: Le bot doit avoir accès à la liste des promotions.
- R.G 55: Le bot doit avoir accès à la liste des apprenants.
- R.G 56: Le bot doit avoir accès à la liste des chargés de projets.
- R.G 57: Le bot doit avoir accès à l'ID Discord des utilisateurs.
- R.G 58: Le bot doit avoir accès à l'ID des canaux Discord des promotions.
- R.G 59: Le bot doit avoir accès à l'ID des fils Discord de signature.
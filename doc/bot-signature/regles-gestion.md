# Règles de gestion
# Configuration du bot
- R.G 1: Le système peut être arrêté, démarré ou en pause.
- R.G 2: L'état de pause peut être associé à une ou plusieurs promos.
- R.G 3: Le bot peut créer les messages à la demande.
- L'administrateur peut generer
# Rappeler à un formateur qu'il a oublié de faire signer
- R.G 4: Le message est lié à un channel de promo.
- R.G 5: Le message prend la forme d'un vote.
- **R.G 6: Un apprenant de la promo peut utiliser la fonctionnalité du bot pour rappeler au formateur ou au cdp qu'il a oublié de faire signer.
- R.G 7: Il y a un une liste selectionable contenant les formateurs liés et le cdp a la promo.
- R.G 8: Un seul formateur ou cdp peut être sélectionné à la fois.
- R.G 9: Il faut qu'un formateur ou cdp soit sélectionné pour envoyer le message.
- Un apprenant doit attendre 30 minutes avant de réutiliser la commande.
- **R.G 11: Le bot envoie un message privé au formateur ou au cdp séléctionné pour l'avertir qu'il doit autoriser les apprenants à signer.**
- **Le message propose d'envoyer directement la nofication aux apprenants pour leur signaler qu'ils peuvent signer**
- **Le message propose au formateur ou cdp de signer qu'ils ne peuvent pas faire signer les apprenants**
- **Si le formateur signale qu'il n'est pas responsable des signatures, le bot lui envoie un second message privé pour prévenir le formateur ou cdp concerné**
- **Le second message envoyé au formateur ou cdp reprend le modèle défini par les rg 7 8 et 9**
# Prévenir les apprenants qu'ils peuvent signer
- R.G 12: Le message est lié à un channel de promo.
- R.G 13: Le message permet de notifier les apprenants qu'ils peuvent signer.
- R.G 14: Seul les formateurs et cdp peuvent peuvent utiliser cette fonction.
- R.G 15: Le message est envoyé sous forme de message privé à chaque apprenant.
# Rappeler à un apprenant qu'il a oublié de signer
- R.G 20: Le message est lié à un channel de promo.
- R.G 21: Le message contient la liste des apprenants liés a la promo.
- R.G 22: Seuls les formateurs et les cdp peuvent interagir avec le message.
- R.G 23: Les formateurs et les cdp peuvent selectionner un ou plusieurs apprenants.
- R.G 24: Il faut au moins un apprenant sélectionné pour valider le rappel.
- R.G 25: Les apprenants sélectionnés sont notifiés par message privé.
# Journalisation
- R.G 26: Le bot enregistre chaque fois qu'un utilisateur fait appel à lui dans un journal.
- R.G 27: Le journal écrit les informations de la manière suivante: date, émetteur, action, destinataire.
# Structuration de l'organisation
- R.G 28: Un formateur est lié à une ou plusieurs promotions.
- R.G 29: Une promotion est liée à un ou plusieurs formateurs.
- R.G 30: Un apprenant suit une formation à la fois.
- R.G 31: Une promotion regroupe plusieurs apprenants.
- R.G 32: Un apprenant appartient à une promotion.
- R.G 33: Une promotion a un chargé de projets.
- R.G 34: Un chargé de projets est lié a une ou plusieurs promotions.
- R.G 35: Une formation peut être dispensée dans un ou plusieurs centres.
- R.G 36: Un centre peut proposer une ou plusieurs formations.
# Données nécessaires au bot
- R.G 37: Le bot a accès à la liste des formateurs.
- R.G 38: Le bot a accès à la liste des formations.
- R.G 39: Le bot a accès à la liste des promotions.
- R.G 40: Le bot a accès à la liste des apprenants.
- R.G 41: Le bot a accès à la liste des chargés de projets.
- R.G 42: Le bot a accès à l'ID Discord des utilisateurs.
- R.G 43: Le bot a accès à l'ID des canaux Discord des promotions.
- R.G 44: Le bot a accès à l'ID des fils Discord de signature.
- le bot sauvegarde l'heure a laquelle les apprenants, formateurs ou cdp ont utilisé une fonction du bot
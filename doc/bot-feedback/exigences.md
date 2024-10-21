# Exigences fonctionnelles

1. **Notifications automatiques** :
   - Le bot doit permettre l’envoi de messages automatiques par messages privés ou sur un canal.
   - Le bot doit permettre la configuration de rappels par messages privés ou par canal
   - Le bot doit permettre de personnaliser les messages envoyés en privée ou dans un canal

2. **Sondages exclusivement sur Discord** :
   - Le bot doit permettre la gestion de sondages directement via Discord.
   - Le bot doit permettre la création de sondages directement via Discord.

3. **Personnalisation de la portée des sondages** :
   - Le bot doit permettre de créer des sondages ciblant des groupes spécifiques ou toute la communauté.

4. **Sondages standardisés et non standardisés** :
   - Le bot doit permettre la gestion de sondages standardisés (questions fixes) et non standardisés (questions personnalisées).

5. **Automatisation des sondages** :
   - Le bot doit permettre l’automatisation des envois de sondages à des dates précises, en fonction des étapes du parcours des apprenants.
   - Le bot doit permettre l'ajout des réponses afin de générer des statistiques

6. **Sécurité et confidentialité des données** :
   - Le bot doit permettre la protection des données collectées, avec conformité RGPD.
   - Le bot doit permettre l’anonymisation des réponses pour garantir la confidentialité des participants.

7. **Facilité d'utilisation** :
   - Le bot doit permettre une utilisation simple avec une interface intuitive.
   - Le bot doit simplifier la reception des sondages aux apprenants.
   - Le bot doit permettre une gestion fluide des sondages et des notifications, réduisant le besoin d’interventions manuelles.

8. **Formulaires existants non modifiés** :
   - Le bot ne doit pas modifier les formulaires existants (région, Qualiopi, Simplon).


# Exigences non fonctionnelles

1. **API**
   - Le bot doit intéragir avec l'API de Discord
   - Le bot doit intéragir avec l'API de Simplon

#### Schéma fonctionnel discord

Ici le bot feedback sur lequel nous travaillons est representé par le rectangle "bot discord"

![schemafonctionnel](../assets/images/schema-fonctionnel.jpg)


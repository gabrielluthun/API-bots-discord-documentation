## Objet : Remerciements et compte-rendu suite à notre rendez-vous du 16 décembre

Bonjour Claire et Benjamin,

Nous tenons à vous remercier sincèrement pour le temps précieux que vous nous avez accordé lors de notre rencontre du 16 décembre.

Ce fut un véritable plaisir d'échanger avec vous, et nous avons particulièrement apprécié la qualité de vos retours ainsi que votre vision claire du projet.

Vos idées et suggestions ont été extrêmement enrichissantes pour nous, et elles contribueront sans aucun doute à la réussite de ce projet.

**Pour rappel, lors de cet entretien, nous avons convenu que :**

- Les salons vocaux seront sélectionnés automatiquement lors de la création d’une nouvelle promotion, afin de simplifier les opérations pour les chefs de projet (cdp) non techniques.  
- Des posts de forum seront pré-sélectionnés par défaut lors de la création de la formation, avec la possibilité pour les cdp d’en ajouter d’autres si nécessaire.

**Durant notre rendez-vous, nous avons discuté des points suivants :**

- La proposition de Benjamin d’avoir une seule catégorie "template" pour les forums et les salons vocaux, plutôt que deux catégories distinctes comme initialement prévu.  
- L’importance de l’automatisation pour les cdp, afin de limiter leurs actions techniques.  
- La prise en compte du type de formation pour la création de template de formation(alternance / pas alternance, pro / intensif).  
- La nécessité, pour les titres professionnels, de prolonger la durée d’activation des canaux avant archivage (3 mois supplémentaires) afin de tenir compte du délai d’obtention du diplôme.  
- La possibilité d’associer des posts spécifiques à un campus, ou de modifier les templates de formation lors de la création d’une promotion.  
- Le choix de sélectionner une formation dans un premier temps plutôt qu’un campus comme critère logique pour la structuration des canaux.  
- Le stockage des templates de forum dans une catégorie dédiée, afin de mieux organiser les données.  
- Les bonnes pratiques concernant l’utilisation d’identifiants (UUID et snowflakes Discord) pour assurer une structure de données cohérente et sécurisée.  
- Les limitations techniques de Discord en matière de nombre de rôles et de canaux, et la nécessité d’en tenir compte.
- Au niveau des entités Channel et Forum du MCD, ils pourront être fusionné en une seule et même entité
- Relier l'entité Rôles à Campus , promotion et Formation.
- Séparer l'entité Users en deux entités distinctes : Users_information (info de l'identification) et Users ( info discord de la personne)
- La possibilité de rajouter des posts dans le stock de posts via deux forum différent dans un forum générique et un forum spécifique

**Les décisions suivantes ont été prises ensemble :**

- Mettre en place une automatisation maximale de la configuration pour les cdp, afin de réduire leurs interventions manuelles.  
- Utiliser des UUID et des snowflakes Discord pour le stockage des données, garantissant une meilleure cohérence et une sécurité accrue.  
- Ne pas implémenter immédiatement la fonctionnalité d’archivage, en privilégiant la suppression pour éviter des contraintes techniques supplémentaires. L’archivage sera éventuellement réévalué par la suite.
- Regrouper les forums des stock de post et les channels vocaux au sein d'une même category discord
- Au niveau des entités Channel et Forum du MCD, ils pourront être fusionné en une seule et même entité
- Relier l'entité Rôles à Campus , promotion et Formation.
- Séparer l'entité Users en deux entités distinctes : Users_information (info de l'identification) et Users ( info discord de la personne)

**À l'issue de notre discussion, les actions suivantes ont été définies :**

- Créer des catégories de template formation (forums, posts) pour centraliser l’ensemble des modèles.  
- Ajouter à l’e-mail la demande de statistiques (KPI) nécessaires à l’analyse des promotions.  
- Fournir le template du serveur, comme demandé (en passant par Discord).
- La possibilité d'être dans deux promos différentes pour l'apprenant en vue que parfois certains apprenant enchaîne les formations chez Simplon.
- Benjamin doit nous envoyer la documentation sur Discord JS et précisement la partie sur "comment les channels sont stockés".

**Nous avons également validé les éléments suivants :**

- Les cdp pourront ajouter des posts supplémentaires dans les forums pré-sélectionnés lors de la création de la promotion, afin de gagner en flexibilité.  
- La prolongation de la durée d’activation des canaux pour les formations menant à un titre professionnel est validée, afin de tenir compte du temps nécessaire à l’obtention du diplôme.

**Comme convenu, les prochaines étapes seront les suivantes :**
  
- Recevoir de la part de Benjamin la documentation Discord nécessaire pour mieux comprendre la structure interne des channels et forums.  
- Définir plus précisément les statistiques à conserver pour l’analyse des promotions, en collaboration avec Rémi et l’équipe concernée.

**Je vous confirme que nous avons bien pris en compte les remarques suivantes :**

- L’impératif de limiter les tâches techniques pour les cdp, afin d’assurer leur adhésion au processus.  
- L’utilisation d’identifiants unifiés (UUID, snowflakes) pour une gestion cohérente des données.  
- La prise en compte des spécificités de chaque type de formation (alternance, intensif, titre pro) pour adapter les durées de disponibilité des canaux et les modalités de leur suppression ou archivage.

Si vous avez des réserves sur un des points évoqués plus haut, d'autres éléments à ajouter ou des sujets que vous souhaiteriez aborder lors de nos prochains échanges, n’hésitez pas à nous en faire part. Nous sommes très heureux de collaborer avec vous et sommes enthousiastes à l'idée d'avancer ensemble sur les prochaines phases du projet.

Nous restons bien entendu à votre disposition pour toute question complémentaire. Aussi, n'hésitez pas à revenir vers nous si vous avez besoin de précisions sur les points abordés lors de notre rendez-vous.

Dans l’attente de vous lire, nous vous souhaitons une excellente journée.

Bien cordialement,

**Messaoud Houri**

Le groupe Discord onboarding
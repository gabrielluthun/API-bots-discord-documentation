## Objet : Remerciements et compte-rendu suite à notre rendez-vous du _31-01-25_

Bonjour Claire et Benjamin,

Nous tenons à vous remercier sincèrement pour le temps précieux que vous nous avez accordé lors de notre rencontre du **vendredi 31 janvier 2025 à 15h00**.

Ce fut un véritable plaisir d'échanger avec vous, et nous avons particulièrement apprécié la qualité de vos retours ainsi que votre vision claire du projet.

Vos réponses, idées et suggestions ont été extrêmement enrichissantes pour nous, et elles contribueront sans aucun doute à la réussite de ce projet.

Durant notre rendez-vous, nous avons discuté des points suivants :

- Le MCD sur lequel nous avons travaillé.
- Le MCD de la précédente version du bot.
- Le diagramme de classe.
- Les deux diagrammes de cas d'utilisation.
- Le code de l'API de la précédente version du bot.
- L'utilité de passer par une base de données concernant les bots discord.
- Le cas de quelqu'un qui s'est déjà identifié pour lui attribuer une nouvelle formation.
- Le RGPD
- La sécurité liée aux snowflakes.

Pendant notre discussion, vous nous avez rappelé les points suivants:

- Le bot doit être prévu pour être scalable.
- La structure de nos données devra respecter les trois premières formes normales.
- Le diagramme de classe est lié à la structure des classes de notre code.
- Lorsque l'on passe au code il est normal de remarquer à ce moment là qu'il manque des éléments sur la conception et de retravailler la conception.

À l'issue de notre discussion, nous avons convenu des actions suivantes:

- Retravailler le MCD en reprenant chaque entité une à une afin de s'interroger sur l'utilité et la pertinence de chacune.
- Effectuer quelques corrections mineures des use case, qui sont globalement cohérents.
- Observer comment le code de l'API de la précédente version du bot a été organisé.
- Revoir en profondeur le diagramme de classe en rajoutant bien chaque classe, qu'il s'agisse des entités, des DTO, etc.
- Réfléchir au cas de quelqu'un qui s'est déjà identifié pour lui attribuer une nouvelle formation, ceci est une problématique complexe.

Nous avons également validé les éléments suivants pour le développement du bot:

- Une base de données permet des actions ciblées du bot bien plus efficacement que s'il n'y avait pas eu de base de données.
- Concernant la modification d'une promotion, la développer uniquement pour les modifications simples. S'il faut effectuer une modification plus importante, supprimer une promotion pour en recréer une nouvelle sera plus facile.
- La suppression d'une promotion devra se faire via une action du bot, ce sera plus rapide et simple pour l'utilisateur que si il devait y retoucher partout.
- Actuellement les CAP n'ont pas la possibilité de supprimer des catégories et des channels.
- Nous pouvons utiliser les snowflakes comme prévu. Etant donné que l'API n'est pas prévue pour être publique, cela ne devrait pas poser de problème de sécurité.
- Lors de la réunion des tech leads, nous avons posé la question concernant le MOOC sur le RGPD, et nous avons obtenu le feu vert pour donner davantage de détails sur le projet afin d'obtenir des réponses.

Si vous avez des réserves sur un des points évoqués plus haut, d'autres éléments à ajouter ou des sujets que vous souhaiteriez aborder lors de nos prochains échanges; n’hésitez pas à nous en faire part. Nous sommes très heureux de collaborer avec vous et sommes enthousiastes à l'idée d'avancer ensemble sur les prochaines phases du projet.

Nous restons bien entendu à votre disposition pour toute question complémentaire. Aussi, n'hésitez pas à revenir vers nous si vous avez besoin de précisions sur les points abordés lors de notre rendez-vous.

Dans l’attente de vous lire, nous vous souhaitons une excellente journée.

Bien cordialement,

**Aurore Reynier**

Le groupe Discord onboarding

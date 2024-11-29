## Dictionnaire de données pour le bot onboarding

| Nom de la colonne    | Type         | Description                                      |
|----------------------|--------------|--------------------------------------------------|
| `promotion_id`       | integer      | Identifiant unique de l'utilisateur              |
| `promotion_name`     | text         | nom de la promotion                              |
| `start_date`         | date         | date de début de la promotion                    |
| `end_date`           | date         | date de fin de la promotion                      |
| `course_id`          | integer      | identifiant de la formation                      |
| `course_name`        | text         | nom de la formation                              |
| `campus_id`          | integer      | identifiant du campus                            |
| `campus_name`        | text         | nom du campus                                    |
| `channel_id`         | integer      | identifiant du channel                           |
| `channel_name`       | text         | nom du channel                                   |
| `is_temporary`       | bool         | indique si le channel est temporaire ou non      |
| `forum_id`           | integer      | Identifiant unique du forum                      |
| `forum_name`         | text         | nom de la promotion                              |
| `post_id`            | integer      | identifiant unique du post                       |
| `post_name`          | text         | nom du post                                      |
| `post_content`       | text         | le message du post                               |
| `post_reaction`      | text         | la reaction du post                              |
| `tag_id`             | integer      | Identifiant unique d'un tag lié à un post        |
| `tag_name`           | text         | nom du tag                                       |
| `tag_emoji`          | text         | emote du tag                                     |
| `user_uuid`          | uuid         | identifiant unique et universel de l'utilisateur |
| `user_name`          | text         | nom de famille de l'utilisateur                  |
| `user_firstname`     | text         | prénom de l'utilisateur                          |
| `user_email`         | text         | mail de l'utilisateur                            |
| `role_id`            | integer      | identifiant du role                              |
| `role_name`          | text         | nom du role                                      |
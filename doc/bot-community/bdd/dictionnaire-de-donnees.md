## Dictionnaire de données

# Super Dictionnaire de Données

## Table : Utilisateurs

| **Nom de la colonne**         | **Type**   | **Taille** | **Description**                                  |
| ----------------------------- | ---------- | ---------- | ------------------------------------------------ |
| uuid_utilisateurs             | UUID       |            | Identifiant unique de l'utilisateur.             |
| pseudo_utilisateurs           | VARCHAR    | 255        | Pseudonyme ou nom d'affichage de l'utilisateur.  |
| email_utilisateurs            | VARCHAR    | 255        | Adresse email de l'utilisateur.                  |
| id_roles                      | INTEGER    |            | Identifiant du rôle attribué à l'utilisateur.    |
| nom_roles                     | VARCHAR    | 100        | Nom descriptif du rôle attribué à l'utilisateur. |
| xp_utilisateurs               | INTEGER    |            | Points d'expérience accumulés par l'utilisateur. |
| niveau_utilisateurs           | INTEGER    |            | Niveau de l'utilisateur.                         |
| badges_utilisateurs           | VARCHAR[]  |            | Liste des badges obtenus par l'utilisateur.      |
| statut_utilisateurs           | VARCHAR    | 50         | Statut de l'utilisateur (actif, inactif, banni). |
| date_inscription_utilisateurs | TIMESTAMPZ |            | Date et heure d'inscription de l'utilisateur.    |
| dernier_acces_utilisateurs    | TIMESTAMPZ |            | Dernière connexion de l'utilisateur.             |

## Table : Ressources

| **Nom de la colonne**        | **Type**   | **Taille** | **Description**                                       |
| ---------------------------- | ---------- | ---------- | ----------------------------------------------------- |
| uuid_ressources              | UUID       |            | Identifiant unique de la ressource.                   |
| titre_ressources             | VARCHAR    | 255        | Titre de la ressource.                                |
| description_ressources       | TEXT       |            | Description détaillée de la ressource.                |
| tags_ressources              | VARCHAR[]  |            | Liste des tags associés à la ressource.               |
| contenu_ressources           | TEXT       |            | Contenu de la ressource (URL, fichier, etc.).         |
| statut_ressources            | VARCHAR    | 50         | Statut de la ressource (actif, obsolète).             |
| createur_ressources          | UUID       |            | Identifiant de l'utilisateur ayant créé la ressource. |
| date_creation_ressources     | TIMESTAMPZ |            | Date et heure de création de la ressource.            |
| date_modification_ressources | TIMESTAMPZ |            | Date et heure de la dernière modification.            |
| signalements_ressources      | INTEGER    |            | Nombre de signalements reçus par la ressource.        |

## Table : Signalements

| **Nom de la colonne**  | **Type**   | **Taille** | **Description**                                         |
| ---------------------- | ---------- | ---------- | ------------------------------------------------------- |
| uuid_signalements      | UUID       |            | Identifiant unique du signalement.                      |
| categorie_signalements | VARCHAR    | 100        | Catégorie du signalement (contenu illégal, spam, etc.). |
| raison_signalements    | TEXT       |            | Raison détaillée du signalement.                        |
| status_signalements    | VARCHAR    | 50         | Statut du signalement (en attente, validé, rejeté).     |
| createur_signalements  | UUID       |            | Identifiant de l'utilisateur ayant créé le signalement. |
| ressource_signalements | UUID       |            | Identifiant de la ressource signalée.                   |
| date_signalements      | TIMESTAMPZ |            | Date et heure de création du signalement.               |

## Table : Historique des Événements

| **Nom de la colonne**  | **Type**   | **Taille** | **Description**                                         |
| ---------------------- | ---------- | ---------- | ------------------------------------------------------- |
| uuid_evenements        | UUID       |            | Identifiant unique de l’événement.                      |
| type_evenements        | VARCHAR    | 50         | Type d'événement (création, modification, suppression). |
| utilisateur_evenements | UUID       |            | Identifiant de l'utilisateur lié à l’événement.         |
| ressource_evenements   | UUID       |            | Identifiant de la ressource liée à l’événement.         |
| date_evenements        | TIMESTAMPZ |            | Date et heure de l’événement.                           |
| details_evenements     | JSON       |            | Détails spécifiques de l’événement (champs modifiés).   |

## Table : Liste Noire

| **Nom de la colonne**   | **Type**   | **Taille** | **Description**                                     |
| ----------------------- | ---------- | ---------- | --------------------------------------------------- |
| uuid_blacklist          | UUID       |            | Identifiant unique de l'entrée dans la liste noire. |
| valeur_blacklist        | VARCHAR    | 255        | Mot-clé, lien ou expression bloquée.                |
| type_blacklist          | VARCHAR    | 50         | Type de l'entrée (mot-clé, lien, expression).       |
| date_creation_blacklist | TIMESTAMPZ |            | Date d'ajout de l'entrée dans la liste noire.       |

## Table : XP et Récompenses

| **Nom de la colonne** | **Type**   | **Taille** | **Description**                                           |
| --------------------- | ---------- | ---------- | --------------------------------------------------------- |
| uuid_rewards          | UUID       |            | Identifiant unique de la récompense ou pénalité d'XP.     |
| utilisateur_rewards   | UUID       |            | Identifiant de l'utilisateur ayant reçu/perdu des points. |
| raison_rewards        | VARCHAR    | 255        | Raison spécifique de la récompense ou pénalité.           |
| valeur_rewards        | INTEGER    |            | Valeur de l'XP gagnée ou perdue.                          |
| date_rewards          | TIMESTAMPZ |            | Date et heure d'attribution de la récompense/pénalité.    |

# Dictionnaire de donées SImplonComunity
---

## Table : Users

| **Column Name**       | **Type**         | **Size** | **Description**                                                         |
|-----------------------|------------------|----------|-------------------------------------------------------------------------|
| **user_uuid**         | UUID             | –        | Identifiant unique de l'utilisateur (clé primaire).                     |
| **user_roles**        | VARCHAR(50)      | 50       | Rôles associés à l'utilisateur (ex. admin, modérateur, membre).         |
| **user_discord_uuid** | UUID             | –        | Identifiant unique Discord de l'utilisateur (obligatoire).              |
| **user_xp**           | DECIMAL(15,2)    | –        | Points d'expérience accumulés par l'utilisateur.                        |
| **user_level**        | INT              | –        | Niveau de l'utilisateur, généralement calculé à partir de l'XP.           |
| **user_status**       | VARCHAR(50)      | 50       | Statut de l'utilisateur (ex. actif, inactif).                           |

---

## Table : Resources

| **Column Name**           | **Type**                | **Size** | **Description**                                                                  |
|---------------------------|-------------------------|----------|----------------------------------------------------------------------------------|
| **resource_uuid**         | UUID                    | –        | Identifiant unique de la ressource (clé primaire).                             |
| **resource_title**        | VARCHAR(50)             | 50       | Titre de la ressource.                                                           |
| **resource_description**  | TEXT                    | –        | Description détaillée de la ressource.                                           |
| **resource_content**      | TEXT                    | –        | Contenu de la ressource (par exemple, URL, texte, fichier, etc.).                |
| **resource_status**       | resource_status_enum    | –        | Statut de la ressource (valeurs possibles : 'draft', 'published', 'archived').     |
| **resource_updatedAt**    | TIMESTAMPTZ             | –        | Date et heure de la dernière mise à jour de la ressource.                        |
| **resource_createdAt**    | TIMESTAMPTZ             | –        | Date et heure de création de la ressource.                                       |

---

## Table : Tag

| **Column Name** | **Type**    | **Size** | **Description**                                             |
|-----------------|-------------|----------|-------------------------------------------------------------|
| **tag_uuid**    | UUID        | –        | Identifiant unique du tag (clé primaire).                   |
| **tag_name**    | VARCHAR(50) | 50       | Nom du tag, utilisé pour catégoriser les ressources.        |

---

## Table : Xp_transactions

| **Column Name**          | **Type**      | **Size** | **Description**                                                                     |
|--------------------------|---------------|----------|-------------------------------------------------------------------------------------|
| **xp_transaction_uuid**  | UUID          | –        | Identifiant unique de la transaction d'XP (clé primaire).                           |
| **transaction_type**     | VARCHAR(50)   | 50       | Type de transaction (ex. gain, perte, bonus, etc.).                                  |
| **transaction_value**    | VARCHAR(50)   | 50       | Valeur de la transaction (peut être positive ou négative).                           |
| **transaction_createdAt**| TIMESTAMPTZ   | –        | Date et heure d'enregistrement de la transaction.                                   |
| **user_uuid**            | UUID          | –        | Identifiant de l'utilisateur concerné (clé étrangère vers **Users**).               |

---

## Table : Badge

| **Column Name**    | **Type**      | **Size** | **Description**                                                             |
|--------------------|---------------|----------|-----------------------------------------------------------------------------|
| **badge_uuid**     | UUID          | –        | Identifiant unique du badge (clé primaire).                                 |
| **badge_createdAt**| TIMESTAMPTZ   | –        | Date et heure d'attribution du badge.                                       |

---

## Table : Comments

| **Column Name**       | **Type**      | **Size** | **Description**                                                                     |
|-----------------------|---------------|----------|-------------------------------------------------------------------------------------|
| **comment_uuid**      | UUID          | –        | Identifiant unique du commentaire (clé primaire).                                   |
| **comment_createdAt** | TIMESTAMPTZ   | –        | Date et heure de création du commentaire.                                           |
| **comment_content**   | TEXT          | –        | Contenu du commentaire.                                                             |
| **comment_status**    | VARCHAR(50)   | 50       | Statut du commentaire (ex. approuvé, en attente, supprimé).                         |
| **resource_uuid**     | UUID          | –        | Identifiant de la ressource associée (clé étrangère vers **Resources**).              |
| **user_uuid**         | UUID          | –        | Identifiant de l'utilisateur qui a posté le commentaire (clé étrangère vers **Users**).|


---

## Table : Moderation_Actions

| **Column Name**      | **Type**      | **Size** | **Description**                                                                 |
|----------------------|---------------|----------|---------------------------------------------------------------------------------|
| **moderation_uuid**  | UUID          | –        | Identifiant unique de l'action de modération (clé primaire).                     |
| **target_type**      | VARCHAR(50)   | 50       | Type de cible de la modération (ex. 'comment', 'resource').                      |
| **target_id**        | VARCHAR(50)   | 50       | Identifiant de la cible, selon le type (par exemple, l'UUID du commentaire).     |
| **action_type**      | VARCHAR(50)   | 50       | Type d'action effectuée (ex. avertissement, suppression).                        |
| **action_reason**    | VARCHAR(50)   | 50       | Raison de l'action de modération.                                                |
| **action_createdAt** | TIMESTAMPTZ   | –        | Date et heure à laquelle l'action a été effectuée.                               |

---

## Table : Votes

| **Column Name**      | **Type**      | **Size** | **Description**                                                                     |
|----------------------|---------------|----------|-------------------------------------------------------------------------------------|
| **vote_uuid**        | UUID          | –        | Identifiant unique du vote (clé primaire).                                           |
| **vote_type**        | VARCHAR(50)   | 50       | Type de vote (ex. upvote, downvote).                                                 |
| **vote_createdAt**   | TIMESTAMPTZ   | –        | Date et heure du vote.                                                               |
| **comment_uuid**     | UUID          | –        | Identifiant du commentaire associé (clé étrangère vers **Comments**).                |
| **user_uuid**        | UUID          | –        | Identifiant de l'utilisateur qui a voté (clé étrangère vers **Users**).              |
| **resource_uuid**    | UUID          | –        | Identifiant de la ressource associée (clé étrangère vers **Resources**).             |

---

## Table : Reports

| **Column Name**      | **Type**               | **Size** | **Description**                                                                                                     |
|----------------------|------------------------|----------|---------------------------------------------------------------------------------------------------------------------|
| **report_uuid**      | UUID                   | –        | Identifiant unique du signalement (clé primaire).                                                                   |
| **report_category**  | report_category_enum   | –        | Catégorie du signalement (ex. 'spam', 'abuse', 'other').                                                             |
| **report_reason**    | VARCHAR(50)            | 50       | Raison du signalement (description courte).                                                                         |
| **report_status**    | VARCHAR(50)            | 50       | Statut du signalement (ex. en attente, validé, rejeté).                                                              |
| **report_createdAt** | TIMESTAMPTZ            | –        | Date et heure de création du signalement.                                                                           |
| **report_updatedAt** | TIMESTAMPTZ            | –        | Date et heure de la dernière mise à jour du signalement.                                                             |
| **moderation_uuid**  | UUID                   | –        | Identifiant de l'action de modération associée (clé étrangère vers **Moderation_Actions**).                          |
| **comment_uuid**     | UUID                   | –        | Identifiant du commentaire signalé (clé étrangère vers **Comments**).                                                 |
| **user_uuid**        | UUID                   | –        | Identifiant de l'utilisateur ayant effectué le signalement (clé étrangère vers **Users**).                              |
| **resource_uuid**    | UUID                   | –        | Identifiant de la ressource signalée (clé étrangère vers **Resources**).                                              |

---

## Table : Creates (Association entre Users et Resources)

| **Column Name**   | **Type** | **Size** | **Description**                                                                              |
|-------------------|----------|----------|----------------------------------------------------------------------------------------------|
| **user_uuid**     | UUID     | –        | Identifiant de l'utilisateur créateur de la ressource (clé étrangère vers **Users**).           |
| **resource_uuid** | UUID     | –        | Identifiant de la ressource créée (clé étrangère vers **Resources**).                         |
| **Primary Key**   | Composite| –        | Clé primaire composée des colonnes **user_uuid** et **resource_uuid**.                        |

---

## Table : Assigned (Association entre Resources et Tag)

| **Column Name**   | **Type** | **Size** | **Description**                                                                              |
|-------------------|----------|----------|----------------------------------------------------------------------------------------------|
| **resource_uuid** | UUID     | –        | Identifiant de la ressource (clé étrangère vers **Resources**).                              |
| **tag_uuid**      | UUID     | –        | Identifiant du tag associé (clé étrangère vers **Tag**).                                     |
| **Primary Key**   | Composite| –        | Clé primaire composée des colonnes **resource_uuid** et **tag_uuid**.                        |

---

## Table : Has (Association entre Users et Badge)

| **Column Name**   | **Type** | **Size** | **Description**                                                                              |
|-------------------|----------|----------|----------------------------------------------------------------------------------------------|
| **user_uuid**     | UUID     | –        | Identifiant de l'utilisateur propriétaire du badge (clé étrangère vers **Users**).              |
| **badge_uuid**    | UUID     | –        | Identifiant du badge (clé étrangère vers **Badge**).                                         |
| **Primary Key**   | Composite| –        | Clé primaire composée des colonnes **user_uuid** et **badge_uuid**.                          |

---

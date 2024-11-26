# Stratégie de sécurisation :

### Introduction :

- Défense en profondeur
- Réduction de la surface d'attaque
- RGPD

## Back-end : 

### Introduction : 

- Politique de moindre privilège
- RBAC
- Journalisation

### Base de données



- **Utilisation des UUID**

- **Politique de sauvegarde**
    - Automatisation
        - Fréquence
        - Nombre
    - Politique de rétention
        - Règle 3.2.1
            - Nombres de sauvegarde
            - Support (stockage)
        - Durée de conservation

### API

- **Sécurisation des communications**
    - TLS
    - HSTS
- **Sécurité des origines**
    - SOP
    - CORS
    - CSP
- **Utilisation d'un ORM**
- **Authentification (token)**
- **Limitation d'appel API**
- **Politique des mots de passe**
    - Hachage
    - Salage 
    - Complexité
        - longueur maximale
        - Robustesse
    - Oubli des mots de passe
    - Fréquence de changement
    - Archivage des anciens mots de passe
- **Messages d'erreurs**

## Front-end :

- **Sanitization**
    - Validation des données
    - Types et formats attendus
- **HTTPS**
    - HSTS
    - TLS
- **SOP**
- **CSP**
    - Referer policy
    - SRI
- **Messages d'erreurs**
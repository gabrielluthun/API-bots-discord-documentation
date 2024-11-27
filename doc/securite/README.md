### **Sommaire**

---

### **Introduction**  
- [Défense en profondeur](#)  
- [Réduction de la surface d'attaque](#)  
- [RGPD](#)  

---
### **1. Back-end**  

#### **1.1 Introduction**  
- [Politique de moindre privilège](#)  
- [RBAC](#)  
- [Journalisation](#)  

#### **1.2 Base de données**  
- [Utilisation des UUID](#)  
- [Politique de sauvegarde](#)  
  - [Automatisation](#)  
    - [Fréquence](#)  
    - [Nombre](#)  
  - [Politique de rétention](#)  
    - [Règle 3.2.1](#)  
      - [Nombre de sauvegardes](#)  
      - [Support (stockage)](#)  
    - [Durée de conservation](#)  

#### **1.3 API**  
- [Sécurisation des communications](#)  
  - [TLS](#)  
  - [HSTS](#)  
- [Sécurité des origines](#)  
  - [SOP](#)  
  - [CORS](#)  
  - [CSP](#)  
- [Utilisation d'un ORM](#)  
- [Authentification](#)  
  - [Token](#)  
- [Limitation d'appel API](#)  
- [Utilisation de variables d'environnement](#)  
- [Politique des mots de passe](#)  
  - [Hachage](#)  
  - [Salage](#)  
  - [Complexité](#)  
    - [Longueur maximale](#)  
    - [Robustesse](#)  
  - [Mot de passe multifacteur](#)  
  - [Gestion de l'oubli des mots de passe](#)  
  - [Fréquence de changement](#)  
  - [Archivage des anciens mots de passe](#)  
- [Messages d'erreurs](#)  

---

### **2. Front-end**  

#### **2.1 Introduction**  
- [Comportement utilisateur](#)  
- [Bonnes pratiques](#)  
  - [TypeScript](#)  
  - [Ne coder que l'essentiel](#)  
  - [Gestion de la lecture/écriture](#)  


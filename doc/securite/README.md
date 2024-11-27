### **Sommaire**

---

### **Introduction**  
- [Défense en profondeur](01-introduction.md/#défense-en-profondeur)  
- [Réduction de la surface d'attaque](01-introduction.md/#réduction-de-la-surface-dattaque)  
- [RGPD](01-introduction.md/#rgpd)  

---
### **1. Back-end**  

#### **1.1 Introduction**  
- [Politique de moindre privilège](02-back-end.md/#politique-de-moindre-privilège)  
- [RBAC](02-back-end.md/#rbac)  
- [Journalisation](02-back-end.md/#journalisation)  

#### **1.2 Base de données**  
- [Utilisation des UUID](02-back-end.md/#utilisation-des-uuid)  
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

#### **2.2 Sanitization**  
- [Validation des données](#)

#### **2.3 HTTPS**  
- [HSTS](#)  
- [TLS](#)  

#### **2.4 SOP**  
- [CORS](#)  
- [Iframe](#)  

#### **2.5 CSP**  
- [Referrer policy](#)  
- [SRI](#)  

#### **2.6 Messages d'erreurs**  
- [Obfuscation](#)  

#### **2.7 Web storage**  
- [Local storage](#)  
- [Session storage](#)  

---

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
- [Politique de sauvegarde](02-back-end.md/#)  
  - [Automatisation](02-back-end.md/#)  
    - [Fréquence](02-back-end.md/#)  
    - [Nombre](02-back-end.md/#)  
  - [Politique de rétention](02-back-end.md/#)  
    - [Règle 3.2.1](02-back-end.md/#)  
      - [Nombre de sauvegardes](02-back-end.md/#)  
      - [Support (stockage)](02-back-end.md/#)  
    - [Durée de conservation](02-back-end.md/#)  

#### **1.3 API**  
- [Sécurisation des communications](02-back-end.md/#)  
  - [TLS](02-back-end.md/#)  
  - [HSTS](02-back-end.md/#)  
- [Sécurité des origines](02-back-end.md/#)  
  - [SOP](02-back-end.md/#)  
  - [CORS](02-back-end.md/#)  
  - [CSP](02-back-end.md/#)  
- [Utilisation d'un ORM](02-back-end.md/#)  
- [Authentification](02-back-end.md/#)  
  - [Token](02-back-end.md/#)  
- [Limitation d'appel API](02-back-end.md/#)  
- [Utilisation de variables d'environnement](02-back-end.md/#)  
- [Politique des mots de passe](02-back-end.md/#)  
  - [Hachage](02-back-end.md/#)  
  - [Salage](02-back-end.md/#)  
  - [Complexité](02-back-end.md/#)  
    - [Longueur maximale](02-back-end.md/#)  
    - [Robustesse](02-back-end.md/#)  
  - [Mot de passe multifacteur](02-back-end.md/#)  
  - [Gestion de l'oubli des mots de passe](02-back-end.md/#)  
  - [Fréquence de changement](02-back-end.md/#)  
  - [Archivage des anciens mots de passe](02-back-end.md/#)  
- [Messages d'erreurs](02-back-end.md/#)  

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

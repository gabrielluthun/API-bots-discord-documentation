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
- [Politique de sauvegarde](02-back-end.md/#politique-de-sauvegarde)  
  - [Automatisation](02-back-end.md/#automatisation)  
    - [Fréquence](02-back-end.md/#fréquence)  
  - [Politique de rétention](02-back-end.md/#)  
    - [Règle 3.2.1](02-back-end.md/#) 
    - [Durée de conservation](02-back-end.md/#)  

#### **1.3 API**  
- [Sécurisation des communications](02-back-end.md/#sécurisation-des-communications)  
  - [TLS](02-back-end.md/#tls)  
  - [HSTS](02-back-end.md/#hsts)  
- [Sécurité des origines](02-back-end.md/#sécurité-des-origines)  
  - [SOP](02-back-end.md/#sop-et-cors)  
  - [CORS](02-back-end.md/#sop-et-cors)  
  - [CSP](02-back-end.md/#csp)  
- [Utilisation d'un ORM](02-back-end.md/#orm)  
- [Authentification](02-back-end.md/#authentification-token)  
  - [Token](02-back-end.md/#authentification-token)  
- [Limitation d'appel API](02-back-end.md/#limitation-dappel-api)  
- [Utilisation de variables d'environnement](02-back-end.md/#utilisation-de-variables-denvironnement)  
- [Politique des mots de passe](02-back-end.md/#politique-des-mots-de-passe)  
  - [Hachage](02-back-end.md/#hachage)  
  - [Salage](02-back-end.md/#salage)  
  - [Complexité](02-back-end.md/#complexité)  
    - [Longueur maximale](02-back-end.md/#longueur-maximale-des-mots-de-passe)  
    - [Robustesse](02-back-end.md/#robustesse)  
  - [Mot de passe multifacteur](02-back-end.md/#mot-de-passe-multifacteur)  
  - [Gestion de l'oubli des mots de passe](02-back-end.md/#gestion-de-loubli-des-mots-de-passe)  
  - [Fréquence de changement](02-back-end.md/#fréquence-de-changement)  
  - [Archivage des anciens mots de passe](02-back-end.md/#archivage-des-anciens-mots-de-passe)  
- [Messages d'erreurs](02-back-end.md/#messages-derreur)  

---

### **2. Front-end**  

#### **2.1 Introduction**  
- [Comportement utilisateur](03-front-end.md/#comportement-utilisateur)  
- [Bonnes pratiques](03-front-end.md/#bonnes-pratiques)

#### **2.2 Sanitization**  
- [Validation des données](03-front-end.md/#validation-des-données)

#### **2.3 HTTPS**  
- [HSTS](03-front-end.md/#hsts)  
- [TLS](03-front-end.md/#)  

#### **2.4 SOP**  
- [CORS](03-front-end.md/#)  
- [Iframe](03-front-end.md/#)  

#### **2.5 CSP**  
- [Referrer policy](03-front-end.md/#referrer-policy)  
- [SRI](03-front-end.md/#sri)  

#### **2.6 Messages d'erreurs**  
- [Obfuscation](03-front-end.md/#obfuscation)  

#### **2.7 Web storage**  
- [Local storage](03-front-end.md/#local-storage)  
- [Session storage](03-front-end.md/#session-storage)  

---

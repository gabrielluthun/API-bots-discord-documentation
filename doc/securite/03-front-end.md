# **Stratégie de sécurisation du front-end**

## **Introduction**

Le front-end est la partie visible de l'application avec laquelle les utilisateurs interagissent directement. Bien que nous implémentions de nombreuses mesures de sécurité côté serveur, il est essentiel de ne pas négliger la sécurité du front-end. En effet, les vulnérabilités côté client peuvent être exploitées pour compromettre une application, voler des informations sensibles ou même prendre le contrôle de sessions utilisateur.

### **Comportement utilisateur**

Nous ne devons jamais faire confiance au client, c'est-à-dire le navigateur de l'utilisateur, qui peut être manipulé à tout moment. Cela inclut la modification du JavaScript exécuté, la falsification des données envoyées au serveur, ou encore l'injection de scripts malveillants. Par conséquent, toutes les données provenant du client doivent être considérées comme potentiellement non fiables ou dangereuses.

### **Bonnes pratiques**

Pour renforcer la sécurité de notre front-end, il est important d'adopter certaines bonnes pratiques, comme une approche stricte qui empêchera les attaques de types XSS d'avoir lieu. Cela réduira la surface d'attaque potentielle.

## **Sanitization**

La sanitization est le processus de nettoyage et de validation des données entrantes pour s'assurer qu'elles sont sûres à utiliser dans l'application.

### **Validation des données**

Chaque donnée entrée par l'utilisateur doit être vérifiée pour s'assurer qu'elle respecte les contraintes attendues. 

```
Par exemple, pour un champ de formulaire demandant une adresse e-mail,
nous devons vérifier que la valeur fournie correspond bien au format d'une adresse e-mail valide.
L'utilisation de REGEX (expression régulière) permet de s'assurer que les données entrées sont bien les données attendues.
```

En effectuant une validation côté serveur, nous nous assurons que seules les données conformes sont traitées et stockées.

## **HTTPS**

### **HSTS**

L'implémentation de **HSTS (HTTP Strict Transport Security)** nous permet de forcer les navigateurs à communiquer uniquement via HTTPS avec notre domaine.

En utilisant HSTS, nous renforçons la sécurité de notre application en garantissant que toutes les communications se font de manière sécurisée, même si l'utilisateur tente de se connecter via une URL HTTP par erreur.

**TLS (Transport Layer Security)** est le protocole de chiffrement standard utilisé pour sécuriser les communications sur Internet. En utilisant TLS, nous assurons que les données transmises entre le client et le serveur sont chiffrées, évitant ainsi les attaques de type man-in-the-middle.

### **SOP**

La **politique de même origine (SOP)** est un mécanisme de sécurité implémenté dans les navigateurs web.

Avec **CORS (Cross-Origin Resource Sharing)**, nous pouvons définir explicitement quelles origines sont autorisées à accéder à nos ressources. En configurant correctement les en-têtes CORS sur notre serveur, nous pouvons contrôler les domaines autorisés à accéder à nos API ou ressources, les méthodes HTTP autorisées, et les en-têtes personnalisés qui peuvent être utilisés.

L'utilisation des **iframes** n'est pas du tout recommandée dans notre application. Elles peuvent introduire des risques de sécurité, notamment des attaques de type clickjacking, où un utilisateur est amené à cliquer sur un élément de l'iframe sans s'en rendre compte.

Pour nous protéger contre ces risques, nous devons contrôler les sources des iframes intégrées en utilisant les attributs `src` avec des URL de confiance. De plus, nous pouvons utiliser l'attribut `sandbox` pour restreindre les capacités de l'iframe, en désactivant par exemple l'exécution de scripts, la soumission de formulaires, ou l'accès aux API du navigateur. Les attributs `allow-scripts` et `allow-same-origin` peuvent être utilisés pour affiner ces restrictions, mais doivent être utilisés avec prudence.

### **CSP**

La **Content Security Policy (CSP)** est un puissant mécanisme de sécurité qui nous permet de contrôler quelles ressources peuvent être chargées et exécutées dans notre application.

### **Referrer Policy**

La **Referrer Policy** est une directive CSP qui contrôle les informations envoyées dans l'en-tête `Referer` lors des requêtes HTTP. En limitant les données partagées dans le `Referer`, nous protégeons la confidentialité des utilisateurs et réduisons les risques de fuite d'informations sensibles, telles que des identifiants de session ou des paramètres de requête contenant des données privées.

### **SRI**

**SRI (Subresource Integrity)** est une fonctionnalité de sécurité qui nous permet de nous assurer que les ressources externes n'ont pas été modifiées depuis leur publication. 

Cela est particulièrement utile lorsque nous chargeons des ressources depuis des CDN ou des sources tierces. SRI nous protège contre les attaques où un attaquant aurait compromis le serveur hébergeant la ressource pour y injecter du code malveillant.

## **Messages d'erreurs**

### **Obfuscation**

Pour éviter de fournir des informations exploitables par des attaquants potentiels, nous devons veiller à ce que nos messages d'erreur soient génériques. 

```
Plutôt que d'afficher des messages indiquant précisément quelle erreur
s'est produite (par exemple, "Erreur SQL : syntaxe incorrecte près de 'SELECT'"),
nous pouvons afficher un message plus général
comme "Une erreur est survenue, veuillez réessayer plus tard".
```

Cette approche réduit les informations disponibles pour un attaquant qui pourrait utiliser les détails techniques pour identifier des vulnérabilités spécifiques dans notre application. En interne, nous pouvons conserver des logs détaillés pour le diagnostic, mais ces informations ne doivent pas être exposées aux utilisateurs finaux.

## **Web Storage**

### **Local Storage**

Nous devons éviter de stocker des informations sensibles telles que des tokens d'authentification (JWT), des identifiants de session ou des informations personnelles sur le local storage. Bien qu'il soit pratique pour stocker des préférences utilisateur ou des données non sensibles, il est accessible via JavaScript et donc vulnérable en cas d'attaques XSS.

### **Session Storage**

La **session storage** est similaire au local storage, mais les données sont effacées lorsque l'onglet ou le navigateur est fermé. Cela offre un niveau de sécurité légèrement supérieur, car les données ne persistent pas au-delà de la session en cours.

Il est préférable d'éviter de stocker des informations critiques dans la session storage. Pour les données sensibles, comme les tokens d'authentification, nous recommandons d'utiliser des cookies sécurisés avec les attributs `HttpOnly` (empêchant l'accès via JavaScript) et `Secure` (le cookie n'est transmis que via HTTPS). Ces mesures réduisent le risque d'exposition des données en cas d'attaque côté client.

```
Par exemple, si un attaquant parvient à injecter du code malveillant dans notre application via
une faille XSS, il pourrait accéder aux données stockées dans le local storage ou session storage et les envoyer à
un serveur distant. Cela pourrait compromettre la sécurité des comptes utilisateurs et de l'application dans son ensemble.
```
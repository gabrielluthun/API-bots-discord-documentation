# API 
Notre application intégrera plusieurs API, ou Application Programming Interface. Il s’agit d’un programme qui permet à deux applications distinctes de communiquer entre elles et d’échanger des données. Nos APIs seront tant développées en internes qu'externe du fait de Discord. 

## Sécurisation des communications
Toute API expose potentiellement l'application à des vecteurs d'attaque. Par exemple, dans les attaques de type *man-in-the-middle*, un tiers malveillant peut intercepter et écouter les données échangées, surtout sur des réseaux Wi-Fi publics. Les attaques de type *man-in-the middle* peuvent également altérer les communications. Notre API contiendra également des données sensibles au niveau de l'onboarding, voir la partie de sécurité dédiée sur ce point pour plus de détails(1). Ces données sont potentiellement interceptables. Pour contrer ces menaces, nous avons prévu de mettre en place un protocole TLS et un HSTS.

### TLS
Le TLS (Transport Layer Security) garantit la confidentialité et l'intégrité des données échangées entre le client (navigateur ou application mobile) et l'API. Cela empêche les attaques de type *Man-in-the-Middle* (MiTM).

Le TCP (Transmission Control Protocol) est un protocole de transport qui fonctionne à un niveau inférieur par rapport à TLS dans la pile réseau. Il est responsable de la fiabilité de la transmission. TCP, à lui seul, ne protège pas contre les attaques. Par exemple, lors d'une connexion simple via HTTP (sur TCP), les informations comme les mots de passe, des données personnelles ou des messages sont en clair.

Avec TLS, ces mêmes informations sont chiffrées avant d’être envoyées via TCP, ce qui les rend inaccessibles ou illisibles pour toute personne qui tenterait de les intercepter.

Nous forcerons l’utilisation de HTTPS pour s’assurer que toutes les communications avec l’API passent par HTTPS. Le serveur API doit avoir un certificat TLS valide pour chiffrer les connexions. il s’agit d’un fichier numérique qui prouve l'identité du site web et chiffre les données.

Nous obtiendrons cette certification via l’autorité de certification (CA) « Let’s Encrypt » qui est gratuite. Le certificat contient des informations sur le site et sur l'autorité de certification qui l’a émis. Il suffira ensuite de l’installer sur le serveur. Nous emploieront spécifiquement la version TLSv1.3.

### HSTS
La mise en œuvre de HSTS (HTTP Strict Transport Security) est une mesure de sécurité essentielle pour protéger notre application contre les attaques de type downgrade, c'est à dire des attaques visant à revenir sur une version moins sécurisée de l'application et les attaques de type *man-in-the-middle* telles que les interceptions de trafic au moyen d'accès non sécurisés générés par les utilisateurs ou un attaquant.

En forçant les navigateurs à établir des connexions uniquement via HTTPS, HSTS garantit que toutes les communications entre le client et le serveur sont chiffrées, réduisant ainsi le risque d'accès non autorisé aux données sensibles.

Pour activer HSTS, il est crucial de configurer correctement l'en-tête HTTP et de définir une période de durée minimale pour laquelle la règle doit s'appliquer, que nous définissons à un an. De plus, il est recommandé de tester régulièrement cette configuration pour s'assurer de son bon fonctionnement. Enfin, l'activation de HSTS doit être accompagnée d'une stratégie de déploiement prudente, en commençant par les domaines moins sensibles avant de l'appliquer à l'ensemble de notre infrastructure, afin de minimiser les risques d'erreurs potentielles.

## Sécurité des origines
### SOP et CORS
La SOP (Same-Origin Policy) est une politique de sécurité des navigateurs qui limite les interactions entre différentes origines (domaines). Elle permet de restreindre les requêtes HTTP pour qu’un site ne puisse accéder qu’aux ressources de son propre domaine. Cependant, la SOP n’est pas toujours suffisante, car elle peut être contournée dans certains cas via des attaques comme JSONP, des extensions malveillantes ou des redirections complexes.

Pour renforcer la sécurité et éviter les contournements de la SOP, nous utilisons CORS (Cross-Origin Resource Sharing). CORS permet de spécifier explicitement quelles origines externes sont autorisées à interagir avec les API. Cette politique fournit une couche de contrôle supplémentaire, permettant à nos serveurs de vérifier les requêtes venant d'autres domaines et d'autoriser ou de bloquer l'accès en fonction des règles définies.

Prévention des attaques XSS : Un attaquant pourrait essayer de créer un script malveillant sur un autre domaine pour exécuter des requêtes API en utilisant les informations de session d’un utilisateur légitime. La politique CORS bloque ces requêtes provenant de domaines non autorisés.
Accès non autorisé aux données : Dans le cas où un domaine non autorisé tente d’accéder à l'API (via des attaques d'extraction de données), la politique CORS empêchera cette tentative, limitant l’accès aux seules origines autorisées (comme le domaine principal de pire2pire.com).

Notre domaine principal, ses sous-domaines et ceux de Discord sont les seuls autorisés à effectuer des requêtes vers les API. Toute tentative d’accès à partir d’un autre domaine sera bloquée.


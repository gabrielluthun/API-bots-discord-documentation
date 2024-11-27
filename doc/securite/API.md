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
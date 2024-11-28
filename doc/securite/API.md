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

### CSP
Le Content Security Policy (CSP) est une mesure de sécurité qui s'applique au niveau du navigateur, mais qui est configurée côté serveur. Il permet de prévenir diverses attaques, notamment les injections de scripts telles que les attaques XSS, en limitant les sources de contenu pouvant être chargées par l'application. 

Si le navigateur permet à des scripts malveillants de se charger depuis des sources non sécurisées, ces scripts pourraient voler des informations personnelles (comme des identifiants ou des sessions utilisateurs) ou manipuler la page pour duper l’utilisateur.

Le CSP est une configuration côté serveur qui se fait sous la forme d'une en-tête HTTP. Cette politique est comme une liste de règles données au navigateur. Elle lui dit exactement d’où il est autorisé à charger du contenu (scripts, images, etc.), et empêche tout contenu non autorisé de s’exécuter. 

pour tester l'efficacité de la politique CSP mise en place, nous devons surveiller les rapports d'erreurs générés par le navigateur, ce qui nous permettra d'ajuster notre configuration en fonction des besoins et des comportements des utilisateurs.

## ORM
L'utilisation d’un ORM (Object-Relational Mapping) dans notre architecture API est essentielle pour faciliter la gestion des données tout en renforçant la sécurité.

En utilisant un ORM, nous pouvons éviter les injections SQL en garantissant que toutes les interactions avec la base de données passent par des méthodes sécurisées et validées. Cela permet également de standardiser l’accès aux données, réduisant ainsi le risque d'erreurs humaines lors de l’écriture de requêtes SQL.

Cependant, il est crucial de s'assurer que l'ORM est configuré correctement et que les mises à jour sont effectuées régulièrement pour corriger les failles de sécurité potentielles. Enfin, une vigilance constante est nécessaire pour surveiller les performances de l’ORM afin de détecter rapidement toute anomalie ou vulnérabilité.

## Authentification (token)
Les JWT permettent une gestion sécurisée et décentralisée des sessions utilisateurs. Ils évitent le besoin de stocker des sessions côté serveur, ce qui allège la charge des serveurs tout en garantissant une sécurité accrue. Le JWT est signé cryptographiquement, ce qui garantit que les données à l'intérieur du jeton ne peuvent pas être modifiées sans invalidation.

Dans un scénario où un attaquant parvient à accéder aux informations d’un utilisateur (via phishing, par exemple), le JWT limite les risques en expirant après une durée donnée. Même si l'attaquant obtient le token, il deviendra inutilisable après un certain temps.

Dans le cas où un utilisateur change ses informations sensibles (comme son mot de passe), tous les anciens JWT sont invalidés, forçant l’utilisateur à se reconnecter avec les nouvelles informations d'authentification.

Lorsqu’un utilisateur se connecte à la plateforme, il reçoit un JWT valide. Lors de chaque requête API, ce token est envoyé dans l'en-tête de la requête pour s'assurer que l'utilisateur est bien authentifié et possède les droits nécessaire. Cette approche améliore l'efficacité et la scalabilité du système, en plus d'offrir une solution robuste pour l'accès à l’API.

Il est essentiel de veiller à ce que ces tokens soient stockés et transmis de manière sécurisée, en utilisant HTTPS pour protéger les données en transit. Aussi, il est important d'analyser et de journaliser l'utilisation des tokens pour détecter toute activité suspecte et assurer la traçabilité des accès.

la limitation du temps de session sera un mécanisme crucial pour sécuriser les sessions des utilisateurs. Elle permettra de limiter la durée pendant laquelle une session utilisateur reste active, réduisant ainsi les risques d'abus ou de compromission des comptes en cas d'inactivité prolongée ou d'accès non autorisé.  La limitation des sessions est une exigence dans plusieurs standards de sécurité, notamment pour respecter les bonnes pratiques liées à la gestion des sessions en ligne (ex. RGPD).

Une déconnexion automatique après 15 minutes d'inactivité sera adéquate pour nos administrateurs. De plus chaque session sera automatiquement fermée après 8 heures de connexion, obligeant l'utilisateur à se reconnecter. Si la session expire, un message explicite devra indiquer que la session a été terminée pour des raisons de sécurité, avec une option pour se reconnecter facilement.

## Limitation d'appel API
Pour prévenir les attaques par déni de service (DoS ou DDoS), il est crucial de mettre en place des mécanismes permettant de limiter le nombre de requêtes qu'un utilisateur peut effectuer dans un laps de temps donné.

Une approche efficace consiste à restreindre le nombre d'appels à l'API à 30 requêtes par minute par utilisateur. Cette limite permet de contrôler le volume de trafic généré par chaque utilisateur et empêche un acteur malveillant de saturer les ressources du serveur en envoyant un grand nombre de requêtes en peu de temps.

Si un utilisateur dépasse ce seuil, l'application peut automatiquement bloquer temporairement les requêtes supplémentaires ou renvoyer une réponse indiquant un "trop grand nombre de requêtes" avec un code d'erreur HTTP 429.

## Utilisation de variables d'environnement
Les variables d'environnement permettent de stocker des clés et des valeurs qui servent à configurer et personnaliser le comportement de notre application. Ces informations inclueront des paramètres sensibles, comme des mots de passe ou des clés d'accès à des services.

Il est crucial de protéger ces données en veillant à ce qu'elles ne soient pas accessibles à tout le monde. Elles doivent être conservées dans des fichiers sécurisés ou des systèmes dédiés, afin d'éviter tout risque de fuite ou d'utilisation malveillante.

Dans le cadre de notre application, nous utilisons un fichier nommé .env pour stocker ces variables en toute sécurité. Nous veillons à ce que ce fichier ne soit jamais intégré dans le dépôt de code (par exemple, via Git). De plus, nous configurons l'application pour masquer ces variables autant que possible, en les exposant uniquement aux services ou fonctionnalités qui en ont strictement besoin.

## Politique des mots de passe
### Hachage
Les mots de passe ne sont jamais stockés en clair dans la base de données. Si un attaquant parvient à obtenir les données de la base de données, les mots de passe hachés et salés sont presque impossibles à inverser pour retrouver le mot de passe d'origine.

Le hachage est un processus qui convertit des données de taille variable en une chaîne de caractères de longueur fixe, garantissant ainsi l'intégrité des données. Il s'agit d'une fonction unidirectionnelle, ce qui rend pratiquement impossible la récupération des données originales à partir de leur hachage. nous utilisons pour celà un algorithme de hachage sécurisé tel que bcrypt.

Le hachage est couramment utilisé pour stocker les mots de passe de manière sécurisée et peut également servir à vérifier l'intégrité des fichiers et à valider des signatures numériques.

### Salage
Le salage renforce la sécurité des mots de passe en ajoutant une valeur aléatoire, ou "sel", à un mot de passe avant de le hacher. Cela empêche les attaques par tables arc-en-ciel qui consiste à déchiffrer des mots de passe en utilisant des tables pré-calculées de hachages, car même si deux utilisateurs partagent le même mot de passe, leurs hachages seront différents grâce au sel unique.

Le sel est généralement stocké avec le hachage, permettant ainsi de le récupérer lors de la vérification du mot de passe. En somme, le salage contribue à rendre le hachage plus résistant aux attaques et améliore la sécurité globale des systèmes d'authentification.

### Complexité
Même si nos mots de passes sont hashés et salés, cela ne veut pas pour autant dire qu’il faut accepter n’importe quoi en guise mot de passe. Dans le cadre de notre API, on peut considérer que l'accès à un dashboard adminstrateur sur le serveur Discord de Simplon Hauts-de-France est d'un niveau de sensibilité élevé. De fait, nous mettrons en place une politique des mots de passe stricte. 

#### Longueur minimale et maximale des mots de passe
##### Longueur minimale des mots passes
Pour commencer, il est important de comprendre que plus un rôle a de permissions vis-à-vis de la base de données, plus il sera nécessaire de protéger son compte, celà va de soi. Si l'on se base sur la "TABLE 3 – Recommandations concernant les longueurs minimales des mots de passe" de l'ANSSI, les comptes ayant des niveaux de permissions à sensibilité forte doivent avoir des mots de passes d'une longueur minimale de 15 caractères. 

##### Longueur maximale des mots de passe
Concernant la longueur maximale, même s’il est recommandé de ne pas fixer de limite au nombre de caractères, cela est nécessaire pour éviter une surcharge du serveur de vérification des mots de passe (bcrypt). Effectivement un utilisateur (ou un attaquant) soumettant un mot de passe extrêmement long, pourrait entraîner une surcharge du serveur.

Effectivement, un attaquant pourrait exploiter la lenteur volontaire de bcrypt en soumettant intentionnellement des mots de passe extrêmement longs pour consommer les ressources de calcul du serveur, ce qui pourrait ralentir le service ou le rendre indisponible (attaque par déni de service). Nous recommanderons donc une longueur maximale de 64 caractères.

Cette limite offre un très haut niveau de sécurité. En effet, un mot de passe de 64 caractères, même composé uniquement de lettres, offre une quantité astronomique de combinaisons possibles, rendant toute tentative d'attaque par force brute quasiment impossible dans un cadre réaliste. De plus, ce plafond est largement au-dessus des besoins typiques pour des mots de passe complexes et variés.

Dernière recommandation, employer des *passphrase* en tant que mot de passe est une bonne pratique. Une *passphrase* est l'emploi d'une phrase complète employée en tant que mot de passe. Nous recommanderons à nos utilisateur d'employer ce type de mot de passe via un message au moment de la création ou le renouvellement des mots de passe.

#### Robustesse
En plus de définir une longueur minimale et maximale pour les mots de passe, il est essentiel de garantir leur complexité afin de rendre plus difficile toute tentative de compromission par attaque de type force brute. 

Cependant, une politique de complexité mal conçue pourrait frustrer les utilisateurs ou les inciter à adopter des comportements risqués (comme la réutilisation de mots de passe ou l'utilisation de modèles simples).

Nous opterons donc pour une approche équilibrée qui reste sécurisée tout en restant gérable pour les utilisateurs. Les mots de passe doivent répondre aux critères suivants pour s'assurer qu'ils ne sont pas facilement devinables ou vulnérables à des attaques courantes :
- **Inclusion de différents types de caractères :** Chaque mot de passe doit inclure au moins une lettre majuscule, une lettre minuscule, un chiffre, et un caractère spécial (comme !, @, #, $, %, etc.). Cette variété augmente la complexité, ce qui rend plus difficile pour un attaquant d'essayer des combinaisons courantes ou d'utiliser des attaques basées sur des dictionnaires.
- **Éviter les séquences courantes et les répétitions :** Les mots de passe ne doivent pas contenir de suites simples comme 123456, abcdef, ou des répétitions évidentes telles que aaaaaa. Les utilisateurs doivent être encouragés à éviter des modèles facilement prédictibles.
- **Pas de réutilisation de mots de passe :** Nous ne permettrons pas aux utilisateurs de réutiliser leurs anciens mots de passe lors de la réinitialisation. Un historique des mots de passe récents sera conservé pour s'assurer que les 5 derniers mots de passe utilisés par un utilisateur ne soient pas réutilisables.
- **Pas de données personnelles dans les mots-de-passe :** Nous nous assurerons aussi que nos utlisateurs n'utilisent pas de données personnelles facilement trouvables tels que leur nom, prénom et date de naissance.

Pour nous assurer que nos critères de complexité soient bel et bien respectés, nous réutiliserons les expressions régulières (REGEX).

### Gestion de l'oubli des mots de passe
La fonctionnalité de récupération ou réinitialisation de mot de passe est une cible courante pour les attaques. Nous mettrons en place les mesures suivante: 
- Une limite stricte sera imposée sur le nombre de demandes de récupération pour un compte donné dans une période de temps définie, afin d'éviter des attaques par force brute. Si cette limite est passée, nous bloquerons l'utilisateur en l'invitant à contacter un administrateur.
- Un email ou un message sécurisé sera envoyé à l'adresse enregistrée, contenant un lien temporaire ou un code à usage unique (OTP). Ce lien/codé sera :
 - Temporaire (valable pendant une durée limitée, comme 10 minutes).
 - À usage unique, et invalide dès qu’il est utilisé une fois.
- Le lien de réinitialisation contiendra un jeton signé (JWT ou autre mécanisme sécurisé). Ce jeton sera stocké temporairement côté serveur pour vérifier sa validité et sera détruit après expiration ou usage.

La réinitialisation du mot de passe nécessitera une validation stricte côté serveur pour garantir que l'opération n'est pas falsifiée. 

### Fréquence de changement
Les mots de passe des administrateurs sont un élément essentiel de la sécurité, mais les forcer à les changer tous les 3 à 6 mois, comme recommandé par l'ANSSI, peut être contraignant. Nous avons donc choisi une méthode qui soit plus simple à utiliser tout en restant sécurisée et adaptée à notre contexte.

Les administrateurs du bot et du dashboard interagissent avec une interface simple et n'ont pas à gérer des données sensibles telles que des informations bancaires ou des mots de passe utilisateur. Les données collectées via le formulaire d’identification (nom, prénom, email) sont limitées et stockées de manière sécurisée.

Les administrateurs ne seront pas obligés de changer leur mot de passe régulièrement. Cette décision permet de limiter les désagréments liés à la mémorisation ou au choix de nouveaux mots de passe.

Un mot de passe devra être modifié uniquement si un problème est détecté, comme une tentative d'accès suspecte ou un risque de sécurité.

Cela simplifie la vie des administrateurs tout en évitant les mauvaises pratiques, comme l’utilisation de mots de passe trop simples ou réutilisés. En cas de problème, des mesures de sécurité supplémentaires seront mises en place pour réagir rapidement.

### Archivage des anciens mots de passe
Pour éviter que des mots de passe déjà utilisés puissent être réemployés, nous avons mis en place une gestion des anciens mots de passe. Cela limite les risques en cas de compromission passée.

Quand un administrateur change son mot de passe, le système vérifie qu’il ne réutilise pas un ancien mot de passe.

Nous stockons une liste des 5 derniers mots de passe pour chaque administrateur. Cela empêche qu’un mot de passe précédent puisse être repris par erreur. Après les 5 premiers mots de passe, tout changement de mot de passe supprimera le mot de passe le plus ancien du stock.

Les mots de passe archivés sont chiffrés avec une méthode robuste, de sorte qu’ils ne puissent pas être exploités en cas de fuite.

Les mots de passe archivés sont supprimés automatiquement après une période de 2 ans, conformément au RGPD. Cela réduit les risques d’exploitation d’anciennes données. Cela garantit que même si un mot de passe est compromis, il ne pourra pas être réutilisé. Le stockage et la suppression des mots archivés suivent les bonnes pratiques, ce qui limite tout risque supplémentaire.

## Messages d'erreur
La gestion des messages d’erreur joue un rôle crucial dans la sécurisation de notre API. Une exposition trop détaillée des messages d’erreur peut fournir des informations exploitables aux attaquants. Voici les mesures mises en place pour sécuriser cette partie.

Les messages d'erreur présentés à l'utilisateur doivent être génériques pour éviter de révéler des informations sensibles sur la structure ou le comportement de l'application. Par exemple :
- Plutôt que : "Échec de la connexion : utilisateur non trouvé dans la base de données"
- Utiliser : "Identifiants invalides, veuillez réessayer."

Toutes les erreurs seront détaillées au moyen de logs, contenant des informations techniques (comme les traces d’exception, les requêtes défaillantes, ou les configurations incorrectes) qui seront enregistrées côté serveur uniquement. Ces logs permettront une résolution efficace des problèmes sans exposer les détails au grand public.

Les codes HTTP retourneront des informations pertinentes et cohérentes, sans exposer de vulnérabilités:
- 400 Bad Request pour les requêtes mal formées.
- 401 Unauthorized pour les accès non authentifiés.
- 403 Forbidden pour les accès refusés.
- 500 Internal Server Error pour des erreurs inattendues.

Lors de tests de sécurité, nous garantirons que les réponses API ne fournissent pas d'informations involontaires, comme des chemins de fichiers ou des numéros de version de logiciels utilisés.

En suivant ces directives, nous éviterons de fournir des indices exploitables aux attaquants, tout en offrant une expérience utilisateur cohérente.
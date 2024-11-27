# API 
Notre application intégrera plusieurs API, ou Application Programming Interface. Il s’agit d’un programme qui permet à deux applications distinctes de communiquer entre elles et d’échanger des données. Nos APIs seront tant développées en internes qu'externe du fait de Discord. 

## Sécurisation des communications
Toute API expose potentiellement l'application à des vecteurs d'attaque. Par exemple, dans les attaques de type *man-in-the-middle*, un tiers malveillant peut intercepter et écouter les données échangées, surtout sur des réseaux Wi-Fi publics. Les attaques de type *man-in-the middle* peuvent également altérer les communications. Notre API contiendra également des données sensibles au niveau de l'onboarding, voir la partie de sécurité dédiée sur ce point pour plus de détails(1). Ces données sont potentiellement interceptables. Pour contrer ces menaces, nous avons prévu de mettre en place un protocole TLS et un HSTS.

### TLS


### HSTS
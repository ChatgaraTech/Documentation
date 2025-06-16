## 🎬 Description

> Ce document a pour but de référence et expliquer au maximum les failles de sécurité / manière de s'en prévenir les plus courante pour une application

## XSS

### Description

XSS (Cross-Site Scripting) est une faille de sécurité web qui permet à un attaquant d’injecter du code malveillant (souvent JavaScript) dans une page web consultée par d’autres utilisateurs.

### Objectifs 

L’objectif est généralement de :
* Voler des données (cookies, tokens de session, infos personnelles),
* Rediriger l'utilisateur vers un site malveillant,
* Manipuler l’apparence ou le comportement de la page,
* Capturer des saisies utilisateur (ex : mots de passe).

### Exemples

J'ai créé un projet avec des exemples : https://github.com/ChatgaraTech/XSS-Example

## CRSF

### Description
CSRF (Cross-Site Request Forgery) est une faille de sécurité web qui permet à un attaquant d’exploiter l’authentification d’un utilisateur connecté pour effectuer des actions à son insu sur un site web de confiance.

### Objectifs
L’objectif est généralement de :
* Réaliser des actions non autorisées au nom de l'utilisateur (ex : transfert d’argent, changement d’email),
* Exploiter la session active de l’utilisateur à son insu,
* Forcer l’utilisateur à interagir avec des fonctionnalités sensibles sans son consentement,
* Contourner les mécanismes d’autorisation côté client.

### Exemples

J'ai créé un projet avec des exemples : https://github.com/ChatgaraTech/CRSF_Example
## 📚 Sources

* Owasp TOP 10 : https://owasp.org/www-project-top-ten/


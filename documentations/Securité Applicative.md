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

### Exemple

* https://github.com/ChatgaraTech/XSS-Example

## CRSF

### Description
CSRF (Cross-Site Request Forgery) est une faille de sécurité web qui permet à un attaquant d’exploiter l’authentification d’un utilisateur connecté pour effectuer des actions à son insu sur un site web de confiance.

### Objectifs
L’objectif est généralement de :
* Réaliser des actions non autorisées au nom de l'utilisateur (ex : transfert d’argent, changement d’email)
* Exploiter la session active de l’utilisateur à son insu
* Forcer l’utilisateur à interagir avec des fonctionnalités sensibles sans son consentement
* Contourner les mécanismes d’autorisation côté client.

### Exemple

* https://github.com/ChatgaraTech/CRSF_Example

## Broken Access Control

### IDOR (Insecure Direct Object Reference)

#### Description

IDOR est une faille de sécurité liée au Broken Access Control qui survient lorsqu’une application permet à un utilisateur d’accéder directement à des objets (fichiers, données, ressources) via un identifiant prévisible (ex : un paramètre id dans l’URL ou la requête), sans vérifier que cet utilisateur a bien les droits pour accéder à cet objet.

#### Objectifs

L’objectif d’un attaquant exploitant une faille IDOR est de :
* Accéder à des données sensibles d’autres utilisateurs (ex : profils, factures, messages)
* Modifier ou supprimer des ressources qui ne lui appartiennent pas

#### Exemple

* https://github.com/ChatgaraTech/Broken_Access_Control_IDOR

## 📚 Sources

* Owasp TOP 10 : https://owasp.org/www-project-top-ten/


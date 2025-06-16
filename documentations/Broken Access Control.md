# Broken Access Control

> Le but de ce document est de référencer les différents type de défault de contrôle d'accès

## IDOR (Insecure Direct Object Reference)

* Description: Accès direct à une ressource via un identifiant (ex : user_id dans l’URL) sans vérifier que l’utilisateur connecté y a droit.
* Cause : Pas de vérification côté serveur que l’ID demandé appartient à l’utilisateur.
* Correction : Vérifier que la ressource appartient bien à l’utilisateur ou que l’utilisateur a la permission d’y accéder.

## Vertical Privilege Escalation

* Description : Un utilisateur basique accède à une fonctionnalité ou ressource réservée à un rôle supérieur (ex : utilisateur accède à l’admin).
* Cause : Mauvaise vérification des rôles ou absence de contrôle des privilèges.
* Correction : Vérifier le rôle de l’utilisateur avant d’autoriser l’accès.

## Horizontal Privilege Escalation

* Description : Un utilisateur accède aux données ou fonctions d'un autre utilisateur au même niveau.
* Cause : Manque de contrôle spécifique à la ressource (ex : modification d’un profil d’un autre utilisateur).
* Correction : Vérifier que l’utilisateur agit uniquement sur ses propres données.

## Bypass des contrôles d’accès via URL ou formulaire

* Description : Accès à des pages ou actions sensibles en accédant directement à leur URL sans contrôle.
* Cause : Pas de vérification côté serveur sur les routes sensibles.
* Correction : Protéger toutes les routes critiques avec des vérifications d’authentification et d’autorisation.

## Manipulation des paramètres de rôle ou d’accès

* Description : Modification manuelle des paramètres (cookies, champs cachés) pour changer son rôle ou ses permissions.
* Cause : Confiance excessive dans les données venant du client.
* Correction : Ne jamais faire confiance aux données clients, vérifier les rôles côté serveur.

## Failles dans les API

* Description : Une API REST ou autre service ne contrôle pas correctement les droits sur les ressources exposées.
* Cause : Absence de contrôle d’accès ou vérifications insuffisantes dans l’API.
* Correction : Implémenter un contrôle d’accès strict côté API, vérifier identité et droits.

## Exemple

* https://github.com/ChatgaraTech/Broken_Access_Control_IDOR

## Source

* https://owasp.org/Top10/A01_2021-Broken_Access_Control/

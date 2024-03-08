# DOCUMENT DE TRAVAIL

Cette documentation est un travail en cours et peut changer jusqu'à ce que la version finale soit approuvée.

# API REST de La Vitrine Culturelle (LVC)

1. [Introduction](#introduction)
2. [Caractéristiques Clés](#caractéristiques-clés)
   - [1. Aperçu des Points de Terminaison](#1-aperçu-des-points-de-terminaison)
   - [2. Structure des Données](#2-structure-des-données)
   - [3. Définition OpenAPI Swagger](#3-définition-openapi-swagger)
3. [Pour Commencer](#pour-commencer)
   - [Étape 1 : Obtenir une clé d'accès pour l'API](#étape-1--obtenir-une-clé-daccès-pour-lapi)
   - [Étape 2 : Authentification](#étape-2--authentification)
4. [Migration de l'ancien API](#migration-de-lancien-api)
5. [Notes importantes](#notes-importantes)

## Introduction

Bienvenue dans la documentation officielle de l'API REST de La Vitrine Culturelle (LVC), une interface complète conçue pour exposer les données d'événements au Québec à des partenaires externes. Cette API suit les normes OpenAPI, offrant une solution fiable et flexible pour accéder aux informations liées aux événements.

## Caractéristiques Clés

### 1. Aperçu des Points de Terminaison

L'API propose un ensemble de points de terminaison principaux, permettant aux partenaires externes de récupérer facilement des données de la base de données de La Vitrine. Les points de terminaison principaux incluent:

- **[eventCollections](v1/eventCollections.md):** Récupérez des informations sur les collections d'événements.
- **[events](v1/events.md):** Récupérez des informations sur des événements individuels.
- **[eventSeries](v1/eventSeries.md):** Récupérez des informations sur les séries d'événements (festivals, tournées, etc...)
- **[exhibitionEvents](v1/exhibitionEvents.md):** Récupérez des informations sur les expositions.
- **[contributors](v1/contributors.md):** Accédez aux détails sur les contributeurs et les artistes associés aux événements.
- **[places](v1/places.md):** Récupérez des données liées aux lieux ou aux salles des événements.
- **[disciplines](v1/disciplines.md):** Correspondent aux taxonomies pour la catégorisation des données, telles que la discipline (danse, musique, etc...)
- **[searchEvents](v1/searchEvents.md):** Un point de terminaison polyvalent permettant aux utilisateurs de rechercher tous types d'événements.

### 2. Structure des Données

Des efforts ont été faits pour aligner étroitement la structure JSON avec les normes de [Schema.org](https://www.schema.org/). Cela assure non seulement la cohérence, mais facilite également l'adaptation au format JSON-LD, améliorant l'interopérabilité des données.

### 3. Définition OpenAPI Swagger

Vous pouvez visualiser l'API dans [l'éditeur d'API Swagger](https://editor.swagger.io/) en faisant un copier-coller des contenus du fichier ci-dessus:

- **[Swagger YAML](v1/swagger/swagger.yaml):** Définition de l'API en format standard.

[Cliquer ici](https://app.screencastify.com/v3/watch/TwH4f13leSEVbsdRJePn) pour une courte vidéo qui montre comment utiliser l'éditeur.

### Politique de limitation de débit

Pour garantir un accès équitable à nos services et protéger notre infrastructure contre les abus, nous appliquons une politique de limitation de débit sur notre API. Cette politique nous aide à maintenir une qualité de service et une disponibilité élevées pour tous les partenaires.

#### Limites

Limite de débit standard: 100 requêtes par minute et par clé API.
Limite de débit étendue: 1000 requêtes par minute par clé API, disponible sur demande.

#### En-têtes de réponse

Notre API fournit les en-têtes HTTP suivants dans chaque réponse pour vous informer de l'état actuel de votre limite de débit:
- `X-RateLimit-Limit`: le nombre maximum de requêtes que vous êtes autorisé à effectuer par minute.
- `X-RateLimit-Remaining`: nombre de requêtes restantes dans la fenêtre de limite de débit actuelle.
- `X-RateLimit-Reset`: heure à laquelle la fenêtre de limite de débit actuelle se réinitialise en secondes d'époque UTC.

#### Dépassement de la limite

Si vous dépassez la limite de débit, vous recevrez un code d'état de réponse `429 Too Many Requests` et vous devrez attendre que la fenêtre de limite de débit se réinitialise avant de faire des demandes supplémentaires.

## Pour Commencer

### Étape 1 : Obtenir une clé d'accès pour l'API

Avant de commencer à utiliser l'API, vous devez obtenir une clé d'accès unique pour authentifier vos requêtes.

### Étape 2 : Authentification

Pour utiliser cette API, vous devez inclure votre clé API dans l'en-tête de chaque demande :

```
Authorization: Bearer VOTRE_CLÉ_API
```

Remplacez `VOTRE_CLÉ_API` par la clé API que nous vous avons fournie.

## Migration de l'ancien API

Référez-vous à la [documentation de migration](migration.md) pour plus d'informations sur comment faire la transition depuis [l'ancien système](https://documentation.lavitrine.com/).

## Notes importantes
- Si les données doivent être utilisées en tant que JSON-LD sur un site web, les champs suivants doivent être supprimés avant l'injection de JSON-LD car ils ne sont pas reconnus par Schema.org ou Google Rich Results :
  - `eventCollectionId`
  - `thumbnail`
  - `lastModified`
  - `exhibitionType`
  - `disciplines`
- Pour l'injection de JSON-LD, l'utilisation du champ `@id` est recommandée pour garantir une identification unique du contenu à travers le web. Consultez [Schema.org](https://schema.org/docs/jsonld) pour plus d'informations.

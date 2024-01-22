# API REST de La Vitrine Culturelle (LVC)

## Introduction

Bienvenue dans la documentation officielle de l'API REST de La Vitrine Culturelle (LVC), une interface complète conçue pour exposer les données d'événements au Québec à des partenaires externes. Cette API suit les normes OpenAPI, offrant une solution fiable et flexible pour accéder aux informations liées aux événements.

## Caractéristiques Clés

### 1. Aperçu des Points de Terminaison

L'API propose un ensemble de points de terminaison principaux, permettant aux partenaires externes de récupérer facilement des données de la base de données de La Vitrine. Les points de terminaison principaux incluent:

- **[events](v1/events.md):** Récupérer des informations sur les événements individuels.
- **[eventSeries](v1/eventSeries.md):** Récupérer des informations sur les séries d'événements (festivals, tournées, etc...)
- **[exhibitionEvents](v1/exhibitionEvents.md):** Récupérer des informations sur les expositions.
- **[contributors](v1/contributors.md):** Accéder aux détails sur les contributeurs et artistes associés aux événements.
- **[places](v1/places.md):** Récupérer des données liées aux lieux ou emplacements des événements.
- **[additionalTypes](v1/additionalTypes.md):** Correspondent à des taxonomies pour catégoriser les données, par exemple la discipline (danse, musique, etc...)
- **[search](v1/search.md):** Un point de terminaison polyvalent permettant aux utilisateurs d'effectuer des recherches sur tous les types d'événements.

### 2. Structure des Données

Des efforts ont été faits pour aligner étroitement la structure JSON avec les normes de [Schema.org](https://www.schema.org/). Cela assure non seulement la cohérence, mais facilite également l'adaptation au format JSON-LD, améliorant l'interopérabilité des données.

### 3. Points de Terminaison JSON-LD

Pour les utilisateurs recherchant une représentation plus structurée et liée du contenu clé, l'API propose des points de terminaison JSON-LD séparés. Ces points de terminaison fournissent une représentation JSON-LD de base des informations essentielles, telles que les détails des événements, permettant une consommation de données plus riche et plus contextuelle. Cela permettra aux utilisateurs d'injecter facilement du JSON-LD dans leurs pages. _NOTE: documentation à venir_

## Pour Commencer

### Étape 1 : Obtenir une clé d'accès pour l'API

Avant de commencer à utiliser l'API, vous devez obtenir une clé d'accès unique pour authentifier vos requêtes.

### Étape 2 : Authentification

Pour utiliser cette API, vous devez inclure votre clé API dans l'en-tête de chaque demande :

```
Authorization: Bearer VOTRE_CLÉ_API
```

Remplacez `VOTRE_CLÉ_API` par la clé API que nous vous avons fournie.

## Migration

Référez-vous à la [documentation de migration](migration/migration.md) pour plus d'informations sur comment faire la transition depuis [l'ancien système](https://documentation.lavitrine.com/).

## OpenAPI Swagger File

[Swagger File](v1/swagger/swagger.yaml)   
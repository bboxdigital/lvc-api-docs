# Documentation de l'API REST de La Vitrine Culturelle (LVC)

## Introduction

Bienvenue dans la documentation officielle de l'API REST de La Vitrine Culturelle (LVC), une interface complète conçue pour exposer les données d'événements sélectionnés au Québec à des partenaires externes. Cette API suit les normes OpenAPI, offrant une solution fiable et flexible pour accéder aux informations liées aux événements.

## Contexte

La Vitrine est depuis longtemps un conservateur d'événements au Québec, servant de source privilégiée pour découvrir et promouvoir diverses manifestations culturelles. Dans le but d'améliorer l'accessibilité et la fonctionnalité de leurs services, une nouvelle API RESTful a été développée. Tout en conservant l'essence de leur API existante, des améliorations significatives ont été mises en œuvre pour s'adapter à l'évolution de la structure des données et pour introduire des fonctionnalités supplémentaires.

## Caractéristiques Clés

### 1. Aperçu des Points de Terminaison

L'API propose un ensemble de points de terminaison principaux, permettant aux partenaires externes de récupérer facilement des données de la vaste base de données de La Vitrine. Les points de terminaison principaux incluent :

- **Événements :** Récupérer des informations sur les événements individuels.
- **Contributeurs :** Accéder aux détails sur les contributeurs associés aux événements.
- **Lieu :** Récupérer des données liées aux lieux ou emplacements des événements.
- **Requête :** Un point de terminaison polyvalent permettant aux utilisateurs d'effectuer des requêtes sur tous les types d'événements.

### 2. Structure des Données

Des efforts ont été faits pour aligner étroitement la structure JSON avec les normes de Schema.org. Cela assure non seulement la cohérence, mais facilite également l'adaptation au format JSON-LD, améliorant l'interopérabilité des données.

### 3. Points de Terminaison JSON-LD

Pour les utilisateurs recherchant une représentation plus structurée et liée du contenu clé, l'API propose des points de terminaison JSON-LD séparés. Ces points de terminaison fournissent une représentation JSON-LD de base des informations essentielles, telles que les détails des événements, permettant une consommation de données plus riche et plus contextuelle. Cela permettra aux utilisateurs d'injecter facilement du JSON-LD dans leurs pages.

### 4. Amélioration de la Granularité

L'une des améliorations clés de cette API est l'augmentation du niveau de granularité sur divers fronts. Les partenaires de La Vitrine ont maintenant accès à un ensemble de données plus détaillé et complet, leur donnant des informations plus riches pour une expérience utilisateur plus engageante.

## Migration

Référez-vous à la [documentation](migration/migration.md) de migration pour plus d'informations sur les différences clés et comment faire la transition depuis l'ancien système.

## Pour Commencer

Pour commencer à utiliser l'API REST de La Vitrine, référez-vous à la [documentation](documentation.md) détaillée. Explorez les fonctionnalités disponibles, comprenez les structures de requête et de réponse, et exploitez le pouvoir des données d'événements sélectionnés de La Vitrine pour vos applications.

Merci d'avoir choisi La Vitrine comme partenaire d'événements culturels. Nous sommes ravis de voir les applications innovantes et les expériences qui émergeront grâce à l'utilisation de cette API. Si vous avez des questions ou besoin d'assistance, n'hésitez pas à contacter notre équipe de support.

# La Vitrine Content API Documentation

## Migration
- [Migration Guide](migration.md)

## Endpoints
1. Events
   1. [Event](v1/event.md)
   2. [Exhibition](v1/exhibition.md)
   3. [Event Series](v1/series.md)
   4. [queryAllEvents](v1/queryAllEvents.md) (*Final query parameters TBD*)
2. Location
   1. [Location](v1/location.md)
   2. [Query Locations](v1/location.md#query-locations)
3. Contributor (*Final name TBD*)
   1. [Contributor](v1/contributor.md)
   2. [Query Contributors](v1/contributor.md#query-contributors) (*Query parameters TBD*)
4. Discipline (*Work in progress*)
   1. [Discipline](v1/discipline.md)
   2. [Query Disciplines](v1/discipline.md#query-disciplines)

## OpenAPI Swagger File
[Swagger File](v1/swagger/swagger.yaml)   

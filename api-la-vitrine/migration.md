# Guide de Migration
Cette mise à jour majeure apporte une refonte complète de l'API, en mettant l'accent sur une structure améliorée, la sécurité et l'adhésion à des normes largement reconnues.

## Changements Majeurs

- **Refonte des Points de Terminaison de l'API :**
  - Transition de l'utilisation du paramètre "command" vers l'utilisation de points de terminaison URL pour une simplicité et une clarté améliorées.

- **Restructuration des Données et Alignement avec Schema.org :**
  - Refonte des noms de champs et des structures de données pour s'aligner étroitement avec les normes de Schema.org.
  - Changements significatifs pour refléter le nouveau modèle de données de La Vitrine Culturelle.

- **Exposition Améliorée des Données :**
  - Par défaut, plus d'informations sont désormais exposées, éliminant le besoin de commandes séparées pour récupérer des données spécifiques.

- **Normes OpenAPI :**
  - Standardisation de l'API suivant les Normes OpenAPI pour améliorer l'interopérabilité et la facilité d'utilisation.

- **Améliorations de l'Authentification :**
  - Mise en œuvre d'une méthode d'authentification nouvelle, plus sécurisée et standardisée.

## Changements du Modèle de Données

- **Suppression d'organisme :**
  - L'entité `organisme` a été supprimée du modèle de données. _(Considération pour une future addition en attente.)_

- **Classification des Lieux :**
  - Les `secteurs` sont maintenant classifiés comme des `place` avec des types spécifiques.

- **Nouvelles Entités de Données :**
  - Introduction de `eventOffers` pour remplacer le concept précédent de représentations.
  - Introduction de `exhibitions` comme une entité de données distincte.
  - Introduction de `eventSeries` comme une entité de données distincte.
  - Introduction de `contributors` pour remplacer le concept précédent d'artiste.

- **Points de Terminaison JSON-LD (Travail en Cours) :**
  - Introduction de points de terminaison JSON-LD comme un travail en cours, améliorant les capacités de Données Liées.

## Migrer depuis `get_events`
Remplacé par le point de terminaison `/api/v1/searchEvents`. Voir la [documentation](v1/searchEvents.md) pour plus de détails.

## Migrer depuis `get_activity` & `get_activitypublic`
Remplacé par `/api/v1/events`, `/api/v1/exhibitionEvents`, `/api/v1/eventSeries`.

Les points de terminaison des événements ont été séparés par type, en raison du fait que dans la nouvelle structure de données, le même ID peut exister sur différents types d'événements. Les réponses retournent également des données légèrement différentes, selon le type d'événement.

Les utilisateurs peuvent maintenant récupérer des données d'événements individuels en utilisant ces points de terminaison, mais ils doivent savoir quel type utiliser pour le bon point de terminaison.

Veuillez vous référer à la documentation des points de terminaison pour plus d'informations :
- [events](v1/events.md)
- [eventOffer](v1/events.md#obtenir-un-eventoffer-representation)
- [exhibitionEvents](v1/exhibitionEvents.md)
- [eventSeries](v1/eventSeries.md)

## Migrer depuis `get_activies` & `get_activiespublic`
Remplacé par `/api/v1/searchEvents`. Ce point de terminaison servira de requête pour tous les types d'événements et avec l'introduction d'une vaste gamme de paramètres de requête, similaires aux commandes précédentes.

Veuillez vous référer à la [documentation](v1/searchEvents.md) pour une liste détaillée de tous les paramètres de requête pris en charge.

## Migrer depuis `get_locations` & `get_locationspublic`
Remplacé par `/api/v1/places`, tous les `locations` et `sectors` sont maintenant sous le même point de terminaison.

Le paramètre `organisme` a été supprimé.

Le paramètre `withShowing` a été renommé pour mieux correspondre à sa fonction.

Veuillez vous référer à la [documentation](v1/places.md) des points de terminaison pour plus d'informations.

## Migrer depuis `get_artists`
Remplacé par `/api/v1/contributors`

Veuillez vous référer à la [documentation](v1/contributors.md) pour plus d'informations.

## Migrer depuis `get_disciplines`
Remplacé par `/api/v1/additionalTypes`

_Ce point de terminaison est toujours en cours de spécification._

Veuillez vous référer à la [documentation](v1/additionalTypes.md) pour plus d'informations.

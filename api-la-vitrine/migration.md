# Guide de Migration
## Journal des Modifications
### Changements Majeurs

- **Refonte des Points de Terminaison de l'API :**
  - Transition de l'utilisation du paramètre "command" vers l'utilisation de points de terminaison URL pour une simplicité et une clarté améliorées.

- **Restructuration des Données et Alignement avec Schema.org :**
  - Refonte des noms de champs et des structures de données pour s'aligner étroitement avec les normes de Schema.org.
  - Changements significatifs pour refléter le nouveau modèle de données de La Vitrine Culturelle.

- **Exposition Améliorée des Données :**
  - Par défaut, plus d'informations sont désormais exposées, éliminant le besoin de commandes séparées pour récupérer des données spécifiques.

- **Améliorations de l'Authentification :**
  - Mise en œuvre d'une méthode d'authentification nouvelle, plus sécurisée et standardisée pour les utilisateurs.

- **Normes OpenAPI :**
  - Standardisation de l'API suivant les Normes OpenAPI pour améliorer l'interopérabilité et la facilité d'utilisation.

### Changements du Modèle de Données

- **Suppression de "Organisme" :**
  - L'entité "Organisme" a été supprimée du modèle de données. (Considération pour une future addition en attente.)

- **Classification des Lieux :**
  - Les "Secteurs" sont maintenant classifiés comme des emplacements avec des types spécifiques, tombant sous l'ombrelle des lieux.

- **Nouvelles Entités de Données :**
  - Introduction de "eventOffers" (représentations) pour remplacer le concept précédent de "représentations".
  - Introduction de "exhibitions" comme une entité de données distincte.
  - Introduction de "eventSeries" comme une entité de données distincte.
  - Introduction de "contributor" pour remplacer le concept précédent d'"artiste".

- **Points de Terminaison JSON-LD (Travail en Cours) :**
  - Introduction de points de terminaison JSON-LD comme un travail en cours, améliorant les capacités de Données Liées.

### Note : 
Cette mise à jour majeure apporte une refonte complète de l'API, en mettant l'accent sur une structure améliorée, la sécurité et l'adhésion à des normes largement reconnues. Les utilisateurs sont encouragés à consulter la documentation mise à jour pour une transition sans heurt vers les fonctionnalités améliorées fournies par cette API.

## Migrer depuis ```get_events```
Remplacé par le point de terminaison ```/api/content/allEvents/```. Voir la [documentation](../main/queryAllEvents.md) pour plus de détails.

## Migrer depuis ```get_activity``` & ```get_activitypublic```
Remplacé par ```/api/content/event```, ```api/content/exhibition```, ```/api/content/series```.

Les points de terminaison des événements ont été séparés par type, en raison du fait que dans la nouvelle structure de données, le même ID peut exister sur différents types d'événements. Les réponses retournent également des données légèrement différentes, selon le type d'événement.

Les utilisateurs peuvent maintenant récupérer des données d'événements individuels en utilisant ces points de terminaison, mais ils doivent savoir quel type utiliser pour le bon point de terminaison.

Veuillez vous référer à la documentation des points de terminaison pour plus d'informations :
- [événement](../main/event.md)
- [offre](../main/event.md#get-eventoffer-representation)
- [exposition](../main/exhibition.md)
- [série](../main/series.md)

## Migrer depuis ```get_activies``` & ```get_activiespublic```
Remplacé par ```/api/content/allEvents```
Ce point de terminaison servira de requête pour tous les types d'événements et avec l'introduction d'une vaste gamme de paramètres de requête, similaires aux commandes précédentes.

Veuillez vous référer à la [documentation](../main/queryAllEvents.md) pour une liste détaillée de tous les paramètres de requête pris en charge.

## Migrer depuis ```get_locations``` & ```get_locationspublic```
Remplacé par ```/api/content/location```, tous les "Lieux" et "Secteurs" sont maintenant sous le même point de terminaison.

Le paramètre Organisme a été supprimé.

Le paramètre withShowing a été renommé pour mieux correspondre à sa fonction.

Veuillez vous référer à la [documentation](../main/location.md) des points de terminaison pour plus d'informations.

## Migrer depuis ```get_artists```
Remplacé par ```/api/content/contributor```

Veuillez vous référer à la [documentation](../main/contributor.md) pour plus d'informations.

## Migrer depuis ```get_disciplines```
Remplacé par ```/api/content/discipline```

Ce point de terminaison est encore en cours de travail.

Veuillez vous référer à la [documentation](../main/discipline.md) pour plus d'informations.


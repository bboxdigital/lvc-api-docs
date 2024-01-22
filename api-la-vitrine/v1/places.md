# places API
## Obtenir une place
```yaml
/api/v1/places/{id}:
  get:
    summary: Obtenir les données d'une place par ID
    parameters:
      - name: id
        in: path
        required: true
        schema:
          type: string
        description: L'ID de la place
      - name: lang
        description: Langue préférée pour les données (fr ou en, fr par défaut)
        in: query
        schema:
          type: string
          default: "fr"
          enum:
            - "fr"
            - "en"
    responses:
      '200':
        description: OK
        content:
          application/json:
            example: >
              {
                "id": 492,
                "schema": "places",
                "type": "Place",
                "name": "Event Venue A",
                "description": "A beautiful place to host your next event",
                "address": {
                  "streetAddress": "789 Laughter Lane",
                  "addressLocality": "Humorville",
                  "addressRegion": "Quebec",
                  "postalCode": "G1T 4R1",
                  "addressCountry": "CA"
                },
                "latitude": 37.23332,
                "longitude": -133.43330,
                "maximumAttendeeCapacity": 240,
                "url": "https://example-venue-a.com",
                "image": {
                  "name": "event-venue-a.jpg",
                  "contentUrl": "https://example.com/event-venue-a.jpg",
                  "copyrightType": "Copyright-free",
                  "encodingFormat": "image/jpeg",
                  "copyrightNotice": "© Example 2024"
                },
                "medias": [],
                "sameAs": [
                  "https://www.linkedin.com/in/event-venue-a",
                  "https://twitter.com/event-venue-a",
                  "https://www.facebook.com/event-venue-a"
                ],
                "touristRegion": "Québec",
                "organismes": [],
                "containedInPlace": null,
                "containsPlace": null,
                "childrenIds": null,
                "grandchildrenIds": null,
                "offerIds": [53, 24, 99],
                "seriesIds": [9],
                "exhibitionIds": [11, 82],
                "lastModified": "2024-02-15T19:00:00"
              }
      '401':
        description: La clé d'API est manquante ou invalide.
      '404':
        description: Une place avec l'ID fourni n'a pas été trouvée.
      '5XX':
        description: Erreur inattendue.
```
## Chercher/lister les places
```yaml
/api/v1/places:
  get:
    summary: Chercher/lister les places
    parameters:
      - name: type
        in: query
        schema:
          type: string
          enum:
          - "Place"
          - "Sector"
        description: Filtrer par type de place, optionnel
      - name: hasOfferFilter
        in: query
        schema:
          type: boolean
          default: true
        description: Par défaut, seulement les places qui ont des offres associées seront listées
      - name: lastModified
        in: query
        description: UNIX Timestamp (UTC)
        required: false
        schema:
          type: integer
      - name: lang
        description: Langue préférée pour les données (fr ou en, fr par défaut)
        in: query
        schema:
          type: string
          default: "fr"
          enum:
            - "fr"
            - "en"
    responses:
      "200":
        description: OK
        content:
          application/json:
            example: >
              [
                {
                  "id": 492,
                  "schema": "places",
                  "type": "Place",
                  "name": "Event Venue A",
                  "description": "A beautiful place to host your next event",
                  "address": {
                    "streetAddress": "789 Laughter Lane",
                    "addressLocality": "Humorville",
                    "addressRegion": "Quebec",
                    "postalCode": "G1T 4R1",
                    "addressCountry": "CA"
                  },
                  "latitude": 37.23332,
                  "longitude": -133.43330,
                  "maximumAttendeeCapacity": 240,
                  "url": "https://example-venue-a.com",
                  "image": {
                    "name": "event-venue-a.jpg",
                    "contentUrl": "https://example.com/event-venue-a.jpg",
                    "copyrightType": "Copyright-free",
                    "encodingFormat": "image/jpeg",
                    "copyrightNotice": "© Example 2024"
                  },
                  "medias": [],
                  "sameAs": [
                    "https://www.linkedin.com/in/event-venue-a",
                    "https://twitter.com/event-venue-a",
                    "https://www.facebook.com/event-venue-a"
                  ],
                  "touristRegion": "Québec",
                  "organismes": [],
                  "containedInPlace": null,
                  "containsPlace": null,
                  "childrenIds": null,
                  "grandchildrenIds": null,
                  "offerIds": [53, 24, 99],
                  "seriesIds": [9],
                  "exhibitionIds": [11, 82],
                  "lastModified": "2024-02-15T19:00:00"
                }
              ]
      '401':
        description: La clé d'API est manquante ou invalide.
      '404':
        description: Non trouvé.
      '5XX':
        description: Erreur inattendue.
```
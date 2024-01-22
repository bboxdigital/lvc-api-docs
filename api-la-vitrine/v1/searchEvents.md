# Chercher/lister tous les événements (eventOffers, eventSeries, exhibitionEvents)
```yaml
/api/v1/searchEvents:
  get:
    summary: Chercher/lister les événements, ordonnés par startDate
    parameters:
      - name: schema
        in: query
        description: Filtrer par type d'événement
        required: false
        schema:
          type: string
          enum:
            - event
            - eventSeries
            - exhibitionEvent
      - name: eventId
        in: query
        description: Filter par eventId, retournera tous les eventOffers correspondants (type "event" seulement).
        required: false
        schema:
          type: string
      - name: contributor
        in: query
        description: Filter par contributor, retournera tous les eventOffers correspondants.
        required: false
        schema:
          type: string
      - name: location
        in: query
        description: Filter par location, retournera tous les eventOffers correspondants.
        required: false
        schema:
          type: string
      - name: additionalType
        in: query
        description: Filter par additionalType, retournera tous les eventOffers correspondants.
        required: false
        schema: 
          type: string
      - name: startDate
        in: query
        description: Filter par startDate (UNIX Timestamp), retournera tous les eventOffers correspondants.
        required: false
        schema:
          type: integer
      - name: endDate
        in: query
        description: Filtrer par plage de dates en ajoutant endDate (UNIX Timestamp) si startDate a une valeur. Si startDate est nul, filtrez uniquement sur endDate.
        required: false
        schema:
          type: integer
      - name: limit
        in: query
        description: Limiter le nombre d'items retournés (10 par défaut)
        required: false
        schema:
          type: integer
          default: 10
      - name: offset
        in: query
        description: Décalage pour la pagination des résultats (0 par défaut)
        required: false
        schema:
          type: integer
          default: 0
      - name: lastModified
        in: query
        description: UNIX Timestamp (UTC) de la dernière modification
        required: false
        schema:
          type: integer
      - name: lang
        in: query
        description: Langue préférée pour les données (fr ou en, fr par défaut)
        schema:
          type: string
          enum:
            - "fr"
            - "en"
        default: "fr"
    responses:
      '200':
        description: OK
        content:
          application/json:
            example: >
              [
                {
                  "id": 140,
                  "schema": "eventOffers",
                  "eventId": 492,
                  "eventStatus": "Scheduled",
                  "name": "John Smith Comedy Show",
                  "description": "Join us for a night of laughter with the hilarious John Smith.",
                  "eventAttendanceMode": "Offline",
                  "audience": "Adult",
                  "eventStatus": "Scheduled",
                  "startDate": "2024-02-15T19:00:00",
                  "endDate": null,
                  "isAccessibleForFree": false,
                  "minPrice": 5.00,
                  "price": 40.00,
                  "availability": "http://schema.org/InStock",
                  "availabilityStarts": "2023-11-15T19:00:00",
                  "availabilityEnds": "2024-04-15T19:00:00",
                  "advanceBookingRequirement": false,
                  "image": {
                    "name": "john-smith.jpg",
                    "contentUrl": "https://example.com/john-smith.jpg",
                    "copyrightType": "Copyright-free",
                    "encodingFormat": "image/jpeg",
                    "copyrightNotice": "© Example 2024"
                  },
                  "medias": [],
                  "contributions": [
                    {
                      "id": 402,
                      "type":"Artiste sur scene",
                      "contributors": {
                        "name": "John Smith",
                        "contributorType": "Person",
                        "image": "https://www.johnsmithcomedy.com/images/john-smith.jpg",
                        "url": "https://john-smith.com"
                      }
                    },
                    {
                      "id": 401
                    }
                  ],
                  "artists": [
                    {
                      "id": 853,
                      "type": "Person",
                      "name": "John Smith",
                      "image": "https://example.com/john-smith.jpg",
                      "sameAs": [
                        "https://www.linkedin.com/in/john-smith",
                        "https://twitter.com/john-smith",
                        "https://www.facebook.com/john-smith"
                      ]
                    }
                  ],
                  "location": {
                    "id": 102,
                    "schema": "places",
                    "type": "Place",
                    "name": "Example Place A",
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
                    "url": "https://example-place-a.com"
                  },
                  "lastModified": "2024-02-15T19:00:00"
                },
                {
                  "id": 140,
                  "schema": "exhibitionEvents",
                  "type": "Temporary",
                  "eventStatus": "Scheduled",
                  "name": "The Chuckles Exhibition",
                  "description": "Get ready to burst into laughter at The Chuckles Fest featuring top comedians.",
                  "eventAttendanceMode": "Offline",
                  "audience": "Adult",
                  "startDate": "2024-02-15T19:00:00",
                  "endDate": null,
                  "isAccessibleForFree": false,
                  "minPrice": 10.00,
                  "price": 35.00,
                  "availability": "http://schema.org/InStock",
                  "availabilityStarts": "2023-12-01T10:00:00",
                  "availabilityEnds": "2024-02-15T18:00:00",
                  "advanceBookingRequirement": true,
                  "image": {
                    "name": "chuckles-fest.jpg",
                    "contentUrl": "https://example.com/chuckles-fest.jpg",
                    "copyrightType": "Copyright",
                    "encodingFormat": "image/jpeg",
                    "copyrightNotice": "© Chuckles Fest 2024"
                  },
                  "medias": [
                    {
                      "id": 601,
                      "type": "Video",
                      "url": "https://example.com/chuckles-fest-promo.mp4"
                    },
                    {
                      "id": 602,
                      "type": "Audio",
                      "url": "https://example.com/chuckles-fest-podcast.mp3"
                    }
                  ],
                  "contributions": [
                    {
                      "id": 402,
                      "type":"Artiste sur scene",
                      "contributors": {
                        "name": "Jane Doe",
                        "contributorType": "Person",
                        "image": "https://www.janedoecomedy.com/images/jane-doe.jpg",
                        "url": "https://janedoe.com"
                      }
                    },
                    {
                      "id": 401,
                      "type": "Producteur",
                      "contributors": {
                        "name": "Bob Johnson",
                        "contributorType": "Person",
                        "image": "https://www.bobjohnsoncomedy.com/images/bob-johnson.jpg",
                        "url": "https://bobjohnson.com"
                      }
                    }
                  ],
                  "artists": [
                    {
                      "id": 853,
                      "type": "Person",
                      "name": "Jane Doe",
                      "image": "https://example.com/jane-doe.jpg",
                      "sameAs": [
                        "https://www.linkedin.com/in/jane-doe",
                        "https://twitter.com/jane-doe",
                        "https://www.facebook.com/jane-doe"
                      ]
                    }
                  ],
                  "location": {
                    "id": 102,
                    "schema": "places",
                    "type": "Place",
                    "name": "Laughter Palace",
                    "address": {
                      "streetAddress": "123 Haha Street",
                      "addressLocality": "Comedy City",
                      "addressRegion": "California",
                      "postalCode": "90210",
                      "addressCountry": "US"
                    },
                    "latitude": 34.05223,
                    "longitude": -118.24368,
                    "maximumAttendeeCapacity": 300,
                    "url": "https://laughterpalace.com"
                  },
                  "lastModified": "2024-02-10T15:30:00"
                }
              ]
      '401':
        description: La clé d'API est manquante ou invalide.
      '404':
        description: Non trouvé.
      '5XX':
        description: Erreur inattendue.
```
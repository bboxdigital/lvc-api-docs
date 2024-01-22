# Event
## Obtenir un event
```yaml
/api/v1/events/{id}:
  get:
    summary: Obtenir les données d'un event par ID
    parameters:
    - name: id
      in: path
      required: true
      schema:
        type: string
      description: L'ID de l'event
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
              {
                "id": 492,
                "schema": "events",
                "eventStatus": "Scheduled",
                "name": "John Smith Comedy Show",
                "description": "Join us for a night of laughter with the hilarious John Smith.",
                "eventAttendanceMode": "Offline",
                "audience": "Adult",
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
                    "type": "Artiste sur scene",
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
                "eventOffers": [
                  {
                    "id": 140,
                    "schema": "eventOffers",
                    "eventId": 492,
                    "eventStatus": "Scheduled",
                    "eventAttendanceMode": "Offline",
                    "audience": "Adult",
                    "startDate": "2024-02-15T19:00:00",
                    "endDate": null,
                    "isAccessibleForFree": false,
                    "minPrice": 5.00,
                    "price": 40.00,
                    "availability": "http://schema.org/InStock",
                    "availabilityStarts": "2023-11-15T19:00:00",
                    "availabilityEnds": "2024-04-15T19:00:00",
                    "advanceBookingRequirement": false,
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
                      "longitude": -133.4333,
                      "maximumAttendeeCapacity": 240,
                      "url": "https://example-place-a.com"
                    },
                    "offerArtist": {}
                  }
                ],
                "lastModified": "2024-02-15T19:00:00"
              }
      '401':
        description: La clé d'API est manquante ou invalide.
      '404':
        description: An Event avec l'ID fourni n'a pas été trouvé.
      '5XX':
        description: Erreur inattendue.
```
## Obtenir un eventOffer (representation)
```yaml
/api/v1/events/{eventId}/{offerId}:
  get:
    summary: Obtenir les données d'un eventOffer par ID
    parameters:
      - name: eventId
        in: path
        required: true
        schema:
          type: string
        description: L'ID de l'event
      - name: offerId
        in: path
        required: true
        schema:
          type: string
        description: L'ID de l'eventOffer
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
                {
                  "id": 140,
                  "schema": "eventOffers",
                  "eventId": 492,
                  "eventStatus": "Scheduled",
                  "name": "John Smith Comedy Show",
                  "description": "Join us for a night of laughter with the hilarious John Smith.",
                  "eventAttendanceMode": "Offline",
                  "audience": "Adult",
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
                      "type": "Artiste sur scene",
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
                  "otherOffers": [
                    {
                      "id": 156,
                      "schema": "eventOffers",
                      "eventId": 492,
                      "eventStatus": "Scheduled",
                      "startDate": "2024-03-15T19:00:00",
                      "endDate": null,
                      "isAccessibleForFree": false,
                      "minPrice": 5.00,
                      "price": 40.00,
                      "availability": "http://schema.org/InStock",
                      "availabilityStarts": "2023-11-15T19:00:00",
                      "availabilityEnds": "2024-04-15T19:00:00",
                      "advanceBookingRequirement": false,
                      "location": {
                        "id": 102,
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
                      "offerArtist": {}
                    }
                  ],
                  "lastModified": "2024-02-15T19:00:00"
                }
        '401':
          description: La clé d'API est manquante ou invalide.
        '404':
          description: Un eventOffer avec l'ID fourni n'a pas été trouvé.
        '5XX':
          description: Erreur inattendue.
```

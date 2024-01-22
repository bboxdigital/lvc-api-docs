# Event
## Get event
```yaml
/api/v1/event/{id}:
  get:
    summary: Get event data by ID
    parameters:
    - name: id
      in: path
      required: true
      schema:
        type: string
      description: The ID of the event
    - name: lang
      in: query
      description: Language preference for data (fr or en, default is fr)
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
        description: Authorization information is missing or invalid.
      '404':
        description: An Event with specified ID not found.
      '5XX':
        description: Unexpected error.
```
## Get eventOffer (representation)
```yaml
/api/v1/event/{eventId}/{offerId}:
  get:
    summary: Get representation data by identifier
    parameters:
      - name: eventId
        in: path
        required: true
        schema:
          type: string
        description: The identifier of the event
      - name: offerId
        in: path
        required: true
        schema:
          type: string
        description: The identifier of the eventOffer
      - name: lang
        in: query
        description: Language preference for data (fr or en, default is fr)
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
          description: Authorization information is missing or invalid.
        '404':
          description: An Event offer with specified ID not found.
        '5XX':
          description: Unexpected error.
```

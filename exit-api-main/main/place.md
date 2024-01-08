# Place API
## Get a place
```yaml
openapi: 3.0.0
info:
  title: Example API
  version: 1.0.0
paths:
  /api/content/place/{id}:
    parameters:
      - name: id
        in: path
        required: true
        schema:
          type: string
        description: The ID of the place
      - name: lang
        description: which language data to use
        in: query
        schema:
          type: string
          default: "fr"
          enum:
            - "fr"
            - "en"
    get:
      summary: Get place details by ID
      responses:
        "200":
          description: Successful response
          content:
            application/json:
              example: >
                {
                  "id": 492,
                  "schema": "places",
                  "type": "Place",
                  "name": "Event Venue A",
                  "description": "A beautiful location to host your next event",
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
        "404":
          description: Place not found
          content:
            text/plain:
              example: "Place not found"
```
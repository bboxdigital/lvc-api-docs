# Location API
## Get a location
```yaml
/api/v1/location/{id}:
  get:
    parameters:
      - name: id
        in: path
        required: true
        schema:
          type: string
        description: The ID of the location
      - name: lang
        description: which language data to use
        in: query
        schema:
          type: string
          default: "fr"
          enum:
            - "fr"
            - "en"
    summary: Get location details by ID
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
      '401':
        description: Authorization information is missing or invalid.
      '404':
        description: A location with specified ID not found.
      '5XX':
        description: Unexpected error.
```
## Query Locations
```yaml
/api/v1/location:
  get:
    summary: Query locations
    parameters:
      - name: type
        in: query
        schema:
          type: string
          enum:
          - "Place"
          - "Sector"
        description: filter by type of location, optional
      - name: hasOfferFilter
        in: query
        schema:
          type: boolean
          default: true
        description: by default, locations will be filtered by if they have offers. 
      - name: lastModified
        in: query
        description: UNIX Timestamp (UTC)
        required: false
        schema:
          type: integer
      - name: lang
        description: which language data to use
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
              ]
      '401':
        description: Authorization information is missing or invalid.
      '404':
        description: Not found.
      '5XX':
        description: Unexpected error.
```
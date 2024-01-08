# Series

## Get Series
```yaml
openapi: 3.0.0
info:
  title: Series API
  version: 1.0.0
paths:
  /api/content/series/{id}:
    parameters:
      - name: id
        in: path
        required: true
        schema:
          type: string
        description: "The ID of the series"
      - name: lang
        in: query
        schema:
          type: string
          enum:
            - fr
            - en
          default: fr
        description: "The language parameter (fr or en, default: fr)"
    get:
      summary: "Get series data by ID"
      responses:
        "200":
          description: "Successful response"
          content:
            application/json:
              example: >
                {
                  "id": 492,
                  "schema": "eventSeries",
                  "eventStatus": "Scheduled",
                  "name": "John Smith Comedy Festival",
                  "description": "Join us for a night of laughter with the hilarious John Smith.",
                  "eventAttendanceMode": "Offline",
                  "audience": "Adult",
                  "startDate": "2023-12-15T19:00:00",
                  "endDate": "2024-03-14T19:00:00",
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
                  "offers": [
                    {
                      "id": 140,
                      "eventId": 492,
                      "schema": "eventOffers",
                      "eventStatus": "Scheduled",
                      "name": "John Smith Comedy Show",
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
                        "longitude": -133.43330,
                        "maximumAttendeeCapacity": 240,
                        "url": "https://example-place-a.com"
                      },
                      "contributors": {}
                    }
                  ],
                  "exhibitions": [
                    {
                      "id": 3,
                      "schema": "exhibitionEvents",
                      "type": "Permanent",
                      "eventStatus": "Scheduled",
                      "name": "John Smith Comedy Expo",
                      "eventAttendanceMode": "Offline",
                      "audience": "Adult",
                      "startDate": "2024-01-15T19:00:00",
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
                      "contributors": {}
                    }
                  ],
                  "lastModified": "2024-02-15T19:00:00"
                }
        "404":
          description: "Series not found"
          content:
            text/plain:
              example: "Series not found"
```


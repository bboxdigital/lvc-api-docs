# Places
## Get a place
```yaml
/places/{id}:
  get:
    parameters:
      - name: id
        in: path
        required: true
        schema:
          type: string
        description: The ID of the place
      - name: lang
        in: query
        description: Language preference for data (fr or en, default is fr)
        schema:
          type: string
          enum:
            - "fr"
            - "en"
          default: "fr"
    summary: Get place details by ID
    responses:
      '200':
        description: OK
        content:
          application/json:
            example: >
              {
                "@context": "http://schema.org",
                "@type": "Place",
                "identifier": 123,
                "name": "Event Venue A",
                "description": "A beautiful location to host your next event",
                "url": "https://example-venue-a.com",
                "address": {
                  "streetAddress": "789 Laughter Lane",
                  "addressLocality": "Humorville",
                  "addressRegion": "Quebec",
                  "postalCode": "G1T 4R1",
                  "addressCountry": "CA"
                },
                "geo": {
                  "@type": "GeoCoordinates",
                  "latitude": 37.23332,
                  "longitude": -133.43330
                },
                "maximumAttendeeCapacity": 1000,
                "image": "https://example.com/some-image.jpg",
                "thumbnail": "https://example.com/some-thumbnail.jpg",
                "containedInPlace": {
                  "identifier": 1,
                  "name": "Main Event Venue"
                },
                "event": [
                  {
                    "@type": "Event",
                    "identifier": 14,
                    "name": "John Smith Comedy Show",
                    "description": "Join us for a night of laughter with the hilarious John Smith.",
                    "startDate": "2024-02-15T19:00:00",
                    "endDate": "2024-02-15T21:00:00",
                    "image": "https://example.com/some-image.jpg",
                    "thumbnail": "https://example.com/some-thumbnail.jpg",
                    "eventStatus": "EventScheduled",
                    "eventAttendanceMode": "OfflineEventAttendanceMode",
                    "location": {
                      "@type": "Place",
                      "identifier": 123,
                      "name": "Event Venue A",
                      "image": "https://example.com/some-image.jpg",
                      "thumbnail": "https://example.com/some-thumbnail.jpg",
                      "url": "https://example-venue-a.com",
                      "sameAs": ["https://www.linkedin.com/in/event-venue-a", "https://twitter.com/event-venue-a", "https://www.facebook.com/event-venue-a"],
                      "address": {
                        "streetAddress": "789 Laughter Lane",
                        "addressLocality": "Humorville",
                        "addressRegion": "Quebec",
                        "postalCode": "G1T 4R1",
                        "addressCountry": "CA"
                      },
                      "geo": {
                        "@type": "GeoCoordinates",
                        "latitude": 37.23332,
                        "longitude": -133.43330
                      },
                      "maximumAttendeeCapacity": 1000
                    },
                    "performer": {
                      "@type": "Person",
                      "identifier": 10,
                      "name": "John Smith",
                      "image": "https://www.johnsmithcomedy.com/images/john-smith.jpg",
                      "thumbnail": "https://example.com/john-smith-thumbnail.jpg",
                      "url": "https://john-smith.com",
                      "sameAs": ["https://www.linkedin.com/in/john-smith", "https://twitter.com/john-smith", "https://www.facebook.com/john-smith"]
                    },
                    "offers": {
                      "url": "http://example.com/ticket-sales-club-a",
                      "priceCurrency": "CAD",
                      "price": 600.00,
                      "availability": "InStock",
                      "availabilityEnds": "2024-03-04T10:00:00",
                      "availabilityStarts": "2023-08-04T10:00:00"
                    },
                    "isAccessibleForFree": false,
                    "disciplines": [
                      {
                        "identifier": 304,
                        "code": "UI-D-Comedy",
                        "label": "Comedy",
                        "vocabularyName": "V1UITaxoDVitrine",
                        "additionalTypeIdVitrine": "V1UITaxoDVitrine_UI-D-Comedy"
                      }
                    ]
                  },
                  {
                    "@type": "Event",
                    "identifier": 15,
                    "name": "Jane Doe Comedy Show",
                    "description": "Join us for a night of laughter with the hilarious Jane Doe.",
                    "startDate": "2024-02-15T19:00:00",
                    "endDate": "2024-02-15T21:00:00",
                    "eventStatus": "EventScheduled",
                    "eventAttendanceMode": "OfflineEventAttendanceMode",
                    "image": "https://example.com/some-image.jpg",
                    "thumbnail": "https://example.com/some-thumbnail.jpg",
                    "location": {
                      "@type": "Place",
                      "identifier": 123,
                      "name": "Event Venue A",
                      "image": "https://example.com/some-image.jpg",
                      "thumbnail": "https://example.com/some-thumbnail.jpg",
                      "url": "https://example-venue-a.com",
                      "sameAs": ["https://www.linkedin.com/in/event-venue-a", "https://twitter.com/event-venue-a", "https://www.facebook.com/event-venue-a"],
                      "address": {
                        "streetAddress": "789 Laughter Lane",
                        "addressLocality": "Humorville",
                        "addressRegion": "Quebec",
                        "postalCode": "G1T 4R1",
                        "addressCountry": "CA"
                      },
                      "geo": {
                        "@type": "GeoCoordinates",
                        "latitude": 37.23332,
                        "longitude": -133.43330
                      },
                      "maximumAttendeeCapacity": 1000
                    },
                    "performer": {
                      "@type": "Person",
                      "identifier": 11,
                      "name": "Jane Doe",
                      "image": "https://www.janedoecomedy.com/images/jane-doe.jpg",
                      "thumbnail": "https://example.com/jane-doe-thumbnail.jpg",
                      "url": "https://jane-doe.com",
                      "sameAs": ["https://www.linkedin.com/in/jane-doe", "https://twitter.com/jane-doe", "https://www.facebook.com/jane-doe"]
                    },
                    "offers": {
                      "url": "http://example.com/ticket-sales-club-a",
                      "priceCurrency": "CAD",
                      "price": 600.00,
                      "availability": "InStock",
                      "availabilityEnds": "2024-03-04T10:00:00",
                      "availabilityStarts": "2023-08-04T10:00:00"
                    },
                    "isAccessibleForFree": false,
                    "disciplines": [
                      {
                        "identifier": 304,
                        "code": "UI-D-Comedy",
                        "label": "Comedy",
                        "vocabularyName": "V1UITaxoDVitrine",
                        "additionalTypeIdVitrine": "V1UITaxoDVitrine_UI-D-Comedy"
                      }
                    ]
                  }
                ],
                "sameAs": [
                  "https://www.linkedin.com/in/event-venue-a",
                  "https://twitter.com/event-venue-a",
                  "https://www.facebook.com/event-venue-a"
                ],
                "lastModified": "2024-02-15T19:00:00"
              }
      '401':
        description: Authorization information is missing or invalid.
      '404':
        description: A place with specified ID not found.
      '5XX':
        description: Unexpected error.
```

## Query places
```yaml
/places:
  get:
    summary: Query places, returns list of results. Only validated places are returned. Used to gather lists of places then separate calls to the API are made to get details for each place.
    parameters:
      - name: lastModified
        in: query
        description: UNIX Timestamp (UTC)
        required: false
        schema:
          type: integer
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
      "200":
        description: OK
        content:
          application/json:
            example: >
              [
                {             
                  "@content": "http://schema.org",
                  "@type": "Place",
                  "identifier": 123,
                  "lastModified": "2024-02-15T19:00:00"
                },
                {
                  "@content": "http://schema.org",
                  "@type": "VirtualLocation",
                  "identifier": 124,
                  "lastModified": "2024-02-15T19:00:00"
                },
                {
                  "@content": "http://schema.org",
                  "@type": "Place",
                  "identifier": 125,
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
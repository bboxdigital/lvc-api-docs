# Contributors
## Get a contributor
```yaml
/contributors/{id}:
  get:
    summary: Get Contributor data
    parameters:
      - name: id
        description: id of contributor
        in: path
        required: true
        schema:
          type: string
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
                "@context": "https://schema.org",
                "@type": "Person",
                "identifier": 10,
                "name": "John Smith",
                "description": "John Smith is a comedian from Montreal.",
                "alternateName": "John Smith Funny Guy",
                "gender": "Male",
                "birthDate": "1980-01-15",
                "nationality": "Canada",
                "image": "https://www.johnsmithcomedy.com/images/john-smith.jpg",
                "thumbnail": "https://example.com/john-smith-thumbnail.jpg",
                "url": "https://john-smith.com",
                "sameAs": [
                  "https://www.linkedin.com/in/john-smith",
                  "https://twitter.com/john-smith",
                  "https://www.facebook.com/john-smith"
                ],
                "performerIn": {
                  "@type": "Event",
                  "identifier": 14,
                  "name": "John Smith Comedy Show",
                  "description": "Join us for a night of laughter with the hilarious John Smith.",
                  "startDate": "2024-02-15T19:00:00",
                  "endDate": "2024-02-15T21:00:00",
                  "eventStatus": "EventScheduled",
                  "eventAttendanceMode": "OfflineEventAttendanceMode",
                  "image": "https://example.com/john-smith.jpg",
                  "thumbnail": "https://example.com/john-smith-thumbnail.jpg",
                  "inLanguage": "en",
                  "location": {
                    "@type": "Place",
                    "identifier": 23,
                    "name": "Comedy Club A",
                    "description": "A beautiful location to host your next event",
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
                      "longitude": -133.4333
                    },
                    "maximumAttendeeCapacity": 240
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
                    "price": 10.00,
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
                "affiliation": {
                  "identifier": 6,
                  "name": "Comedy Organization",
                  "description": "Comedy Organization is a group of comedians from Montreal.",
                  "url": "https://comedy-organization.com",
                  "image": "https://example.com/comedy-organization.jpg",
                  "thumbnail": "https://example.com/comedy-organization-thumbnail.jpg",
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
                    "longitude": -133.4333
                  },
                  "sameAs": ["https://www.linkedin.com/in/comedy-organization", "https://twitter.com/comedy-organization", "https://www.facebook.com/comedy-organization"]
                }
              }
      '401':
        description: Authorization information is missing or invalid.
      '404':
        description: Not found.
      '5XX':
        description: Unexpected error.
```

## Query contributors
```yaml
/contributors:
  get:
    summary: Query Contributors. Returns list of results. Only validated contributors are returned. Used to gather lists of contributors then separate calls to the API are made to get details for each contributor.
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
      '200':
        description: OK
        content:
          application/json:
            example: >
              [
                {
                  "@context": "https://schema.org",
                  "@type": "Person",
                  "identifier": 10,
                  "lastModified": "2024-02-15T19:00:00"
                },
                {
                  "@context": "https://schema.org",
                  "@type": "Organization",
                  "identifier": 6,
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
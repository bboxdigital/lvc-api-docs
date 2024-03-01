# Event Series
```yaml
/eventSeries/{id}:
  get:
    summary: Get eventSeries data by ID
    parameters:
      - name: id
        in: path
        required: true
        schema:
          type: string
        description: The ID of the series
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
                "@context": "http://schema.org",
                "@type": "EventSeries",
                "identifier": 6,
                "name": "John Smith Comedy Festival",
                "description": "Join us for a night of laughter with the hilarious John Smith.",
                "eventAttendanceMode": "OfflineEventAttendanceMode",
                "eventStatus": "EventScheduled",
                "inLanguage": "en",
                "audience": {
                  "@type": "Audience",
                  "audienceType": "Adult"
                },
                "startDate": "2023-12-15T19:00:00",
                "endDate": "2024-03-14T19:00:00",
                "image": "https://example.com/some-image.jpg",
                "thumbnail": "https://example.com/some-thumbnail.jpg",
                "performer": {
                  "@type": "Person",
                  "identifier": 10,
                  "name": "John Smith",
                  "image": "https://www.johnsmithcomedy.com/images/john-smith.jpg",
                  "thumbnail": "https://example.com/john-smith-thumbnail.jpg",
                  "url": "https://john-smith.com",
                  "sameAs": ["https://www.linkedin.com/in/john-smith", "https://twitter.com/john-smith", "https://www.facebook.com/john-smith"]
                },
                "location": {
                  "@type": "Place",
                  "identifier": "415",
                  "name": "Example Place A",
                  "url": "https://example-place-a.com",
                  "image": "https://example.com/some-image.jpg",
                  "thumbnail": "https://example.com/some-thumbnail.jpg",
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
                  "maximumAttendeeCapacity": 240
                },
                "isAccessibleForFree": true,
                "subEvent": [
                  {
                    "@type": "Event",
                    "identifier": 14,
                    "name": "John Smith Comedy Show",
                    "image": "https://example.com/some-image.jpg",
                    "thumbnail": "https://example.com/some-thumbnail.jpg",
                    "startDate": "2024-02-15T19:00:00",
                    "endDate": "2024-02-15T21:00:00",
                    "performer": {
                      "@type": "Person",
                      "identifier": 10,
                      "name": "John Smith",
                      "image": "https://www.johnsmithcomedy.com/images/john-smith.jpg",
                      "thumbnail": "https://example.com/john-smith-thumbnail.jpg",
                      "url": "https://john-smith.com",
                      "sameAs": ["https://www.linkedin.com/in/john-smith", "https://twitter.com/john-smith", "https://www.facebook.com/john-smith"]
                    },
                    "location": {
                      "@type": "Place",
                      "identifier": "23",
                      "name": "Comedy Club A",
                      "url": "https://comedy-club-a.com"
                    }
                  },
                  {
                    "@type": "Event",
                    "identifier": 15,
                    "name": "Jane Doe Comedy Show",
                    "image": "https://example.com/some-image.jpg",
                    "thumbnail": "https://example.com/some-thumbnail.jpg",
                    "startDate": "2024-02-15T19:00:00",
                    "endDate": "2024-02-15T21:00:00",
                    "performer": {
                      "@type": "Person",
                      "identifier": 11,
                      "name": "Jane Doe",
                      "image": "https://www.janedoecomedy.com/images/jane-doe.jpg",
                      "thumbnail": "https://example.com/jane-doe-thumbnail.jpg",
                      "url": "https://jane-doe.com",
                      "sameAs": ["https://www.linkedin.com/in/jane-doe", "https://twitter.com/jane-doe", "https://www.facebook.com/jane-doe"]
                    },
                    "location": {
                      "@type": "Place",
                      "identifier": "24",
                      "name": "Comedy Club B",
                      "url": "https://comedy-club-b.com"
                    }
                  }
                ],
                "lastModified": "2024-02-15T19:00:00",
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
      '401':
        description: Authorization information is missing or invalid.
      '404':
        description: Event Series with specified ID not found.
      '5XX':
        description: Unexpected error.
```
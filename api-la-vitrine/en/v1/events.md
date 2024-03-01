# Events
```yaml
/events/{id}:
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
                "@context": "http://schema.org",
                "@type": "Event",
                "identifier": 14,
                "eventCollectionId": 1,
                "name": "John Smith Comedy Show",
                "description": "Join us for a night of laughter with the hilarious John Smith.",
                "url": "https://example.com/event-page",
                "image": "https://example.com/some-image.jpg",
                "thumbnail": "https://example.com/some-thumbnail.jpg",
                "audience": {
                  "@type": "Audience",
                  "audienceType": "Adult"
                },
                "eventStatus": "EventRescheduled",
                "eventAttendanceMode": "OfflineEventAttendanceMode",
                "previousStartDate": "2024-02-15T19:00:00",
                "startDate": "2024-02-15T19:00:00",
                "endDate": "2024-02-15T21:00:00",
                "duration": "PT2H",
                "inLanguage": "en",
                "superEvent": {
                  "@type": "EventSeries",
                  "identifier": 6,
                  "name": "Comedy Tour 2024"
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
                "location": {
                  "identifier": 23,
                  "name": "Comedy Club A",
                  "image": "https://example.com/photo.jpg",
                  "thumbnail": "https://example.com/photo-thumbnail.jpg",
                  "url": "https://comedy-club-a.com",
                  "sameAs": ["https://www.linkedin.com/in/comedy-club-a", "https://twitter.com/comedy-club-a", "https://www.facebook.com/comedy-club-a"],
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
                "offers": {
                  "url": "http://example.com/ticket-sales-club-a",
                  "priceCurrency": "CAD",
                  "priceSpecification": {
                    "price": 10.0,
                    "minPrice": 5.0
                  },
                  "availability": "InStock",
                  "availabilityEnds": "2024-03-04T10:00:00",
                  "availabilityStarts": "2023-08-04T10:00:00"
                },
                "isAccessibleForFree": false,
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
        description: An Event with specified ID not found.
      '5XX':
        description: Unexpected error.
```

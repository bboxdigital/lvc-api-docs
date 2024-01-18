# Exhibition
## Get exhibition
```yaml
/api/content/exhibition/{id}:
  get:
    summary: Get exhibition data by ID
    parameters:
      - name: id
        in: path
        required: true
        schema:
          type: string
        description: The ID of the exhibition
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
                "schema": "exhibitionEvents",
                "type": "Permanent",
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
              }
      '404':
        description: An Exhibition with specified ID was not found.
      '401':
        description: Authorization information is missing or invalid.
      '5XX':
        description: Unexpected error.
```


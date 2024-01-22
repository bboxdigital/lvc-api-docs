# Contributor API
## Get a contributor
```yaml
/api/v1/contributor/{id}:
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
                "id": 492,
                "schema": "contributor",
                "type": "Person",
                "name": "John Smith",
                "alternateName": "Johnny Funny Guy",
                "description": "Join us for a night of laughter with the hilarious John Smith.",
                "gender": "Male",
                "birthPlace": "",
                "nationality": "Canada",
                "address": "",
                "url": "https://example.com",
                "image": {
                  "name": "john-smith.jpg",
                  "contentUrl": "https://example.com/john-smith.jpg",
                  "copyrightType": "Copyright-free",
                  "encodingFormat": "image/jpeg",
                  "copyrightNotice": "© Example 2024"
                },
                "medias": [],
                "sameAs": [
                    "https://www.linkedin.com/in/john-smith",
                    "https://twitter.com/john-smith",
                    "https://www.facebook.com/john-smith"
                ],
                "affiliation": "",
                "events": [],
                "eventSeries": [],
                "exhibitionEvents": [],
                "lastModified": "2024-02-15T19:00:00"
              }
      '401':
        description: Authorization information is missing or invalid.
      '404':
        description: A contributor with specified ID not found.
      '5XX':
        description: Unexpected error.
```
## Query Contributors
```yaml
/api/v1/contributors:
  get:
    summary: Query Contributors
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
                  "id": 492,
                  "schema": "contributor",
                  "type": "Person",
                  "name": "John Smith",
                  "alternateName": "Johnny Funny Guy",
                  "description": "Join us for a night of laughter with the hilarious John Smith.",
                  "gender": "Male",
                  "birthPlace": "",
                  "nationality": "Canada",
                  "address": "",
                  "url": "https://example.com",
                  "image": {
                    "name": "john-smith.jpg",
                    "contentUrl": "https://example.com/john-smith.jpg",
                    "copyrightType": "Copyright-free",
                    "encodingFormat": "image/jpeg",
                    "copyrightNotice": "© Example 2024"
                  },
                  "medias": [],
                  "sameAs": [
                      "https://www.linkedin.com/in/john-smith",
                      "https://twitter.com/john-smith",
                      "https://www.facebook.com/john-smith"
                  ],
                  "affiliation": "",
                  "events": [],
                  "eventSeries": [],
                  "exhibitionEvents": [],
                  "lastModified": "2024-02-15T19:00:00"
                },
              ]
      '401':
        description: Authorization information is missing or invalid.
      '404':
        description: Not found.
      '5XX':
        description: Unexpected error.
```
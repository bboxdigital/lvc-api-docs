# Contributor API
## Get a 'contributor'
```yaml
openapi: 3.0.0
info:
  title: Contributor API
  version: 1.0.0
paths:
  /api/content/contributor/{id}:
    parameters:
      - name: id
        description: id of contributor
        in: path
        required: true
        schema:
          type: string
      - name: lang
        description: which language data to use
        in: query
        schema:
          type: string
          enum:
            - "fr"
            - "en"
          default: "fr"
    get:
      summary: Get Contributor data
      responses:
        "200":
          description: Successful response
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
        "404":
          description: Contributor not found
          content:
            application/json:
              example:
                error: "Contributor not found"
```
# Contributor API
## Obtenir un contributor
```yaml
/api/v1/contributors/{id}:
  get:
    summary: Obtenir les données d'un contributor
    parameters:
      - name: id
        description: id du contributor
        in: path
        required: true
        schema:
          type: string
      - name: lang
        in: query
        description: Langue préférée pour les données (fr ou en, fr par défaut)
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
        description: La clé d'API est manquante ou invalide.
      '404':
        description: Un contributor avec l'ID fourni n'a pas été trouvé.
      '5XX':
        description: Erreur inattendue.
```
## Chercher/lister les contributors
```yaml
/api/v1/contributors:
  get:
    summary: Chercher/lister les contributors
    parameters:
      - name: lastModified
        in: query
        description: UNIX Timestamp (UTC)
        required: false
        schema:
          type: integer
      - name: lang
        in: query
        description: Langue préférée pour les données (fr ou en, fr par défaut)
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
        description: La clé d'API est manquante ou invalide.
      '404':
        description: Non trouvé.
      '5XX':
        description: Erreur inattendue.
```
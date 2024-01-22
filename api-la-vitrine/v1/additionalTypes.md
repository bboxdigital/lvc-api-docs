# additionalType API
## Obtenir un additionalType
```yaml
/api/v1/additionalTypes/{id}:
  get:
    summary: Obtenir les données d'un additionalType
    parameters:
      - name: id
        description: id du additionalType
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
                "id": 2,
                "label": "Music",
                "parent": null,
                "children": [3,4,5],
                "lastModified": "2024-02-15T19:00:00"
              }
      '401':
        description: La clé d'API est manquante ou invalide.
      '404':
        description: Un additionalType avec l'ID fourni n'a pas été trouvé.
      '5XX':
        description: Erreur inattendue.
```
## Chercher/lister les additionalTypes
```yaml
/api/v1/additionalTypes:
  get:
    summary: Chercher/lister les additionalTypes
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
                  "id": 2,
                  "label": "Music",
                  "parent": null,
                  "children": [3,4,5],
                  "lastModified": "2024-02-15T19:00:00"
                },
                {
                  "id": 3,
                  "label": "Music > Rock",
                  "parent": 2,
                  "children": null,
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
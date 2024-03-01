# Disciplines
## Get a discipline
```yaml
/disciplines/{id}:
  get:
    summary: Get discipline data
    parameters:
      - name: id
        description: id of discipline
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
                "identifier": 304,
                "code": "UI-D-Comedy",
                "label": "Comedy",
                "vocabularyName": "V1UITaxoDVitrine",
                "additionalTypeIdVitrine": "V1UITaxoDVitrine_UI-D-Comedy",
                "lastModified": "2024-02-15T19:00:00"
              }
      '401':
        description: Authorization information is missing or invalid.
      '404':
        description: A additionalType with specified ID not found.
      '5XX':
        description: Unexpected error.
```

## Query disciplines
```yaml
/disciplines:
  get:
    summary: Query disciplines, returns list of results. Only validated disciplines are returned.
    parameters:
      - name: lastModified
        in: query
        description: UNIX Timestamp (UTC)
        required: false
        schema:
          type: integer
      - $ref: '#/components/parameters/lang'
    responses: 
      '200':
        description: OK
        content:
          application/json:
            example: >
              [
                {
                  "identifier": 304,
                  "code": "UI-D-Comedy",
                  "label": "Comedy",
                  "vocabularyName": "V1UITaxoDVitrine",
                  "additionalTypeIdVitrine": "V1UITaxoDVitrine_UI-D-Comedy",
                  "lastModified": "2024-02-15T19:00:00"
                },
                {
                  "identifier": 305,
                  "code": "UI-D-Drama",
                  "label": "Drama",
                  "vocabularyName": "V1UITaxoDVitrine",
                  "additionalTypeIdVitrine": "V1UITaxoDVitrine_UI-D-Drama",
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
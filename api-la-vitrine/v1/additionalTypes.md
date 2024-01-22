# Discipline API
## Get a discipline
```yaml
/api/v1/discipline/{id}:
  get:
    summary: Get Discipline data
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
                "id": 2,
                "label": "Music",
                "parent": null,
                "children": [3,4,5],
                "lastModified": "2024-02-15T19:00:00"
              }
      '401':
        description: Authorization information is missing or invalid.
      '404':
        description: A Discipline with specified ID not found.
      '5XX':
        description: Unexpected error.
```
## Query Disciplines
```yaml
/api/v1/discipline:
  get:
    summary: Query disciplines
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
        description: Authorization information is missing or invalid.
      '404':
        description: Not found.
      '5XX':
        description: Unexpected error.
```
# Search/list all events (eventCollections, events, eventSeries, exhibitionEvents)
```yaml
/searchEvents:
  get:
    summary: Retrieve events based on search parameters, returns list of results. Only active / validated events are returned. Used to gather lists of events then separate calls to the API are made to get details for each event.
    parameters:
      - name: schema
        in: query
        description: filter by specific event type only
        required: false
        schema:
          type: string
          enum:
            - EventCollection
            - Event
            - EventSeries
            - ExhibitionEvent
      - name: eventCollectionId
        in: query
        description: filter on eventCollectionId, this will only return events for a given eventCollection.
        required: false
        schema:
          type: string
      - name: contributor
        in: query
        description: filter on contributor, this will return all active events for a given contributor
        required: false
        schema:
          type: string
      - name: place
        in: query
        description: filter on place, this will return all active events for a given place
        required: false
        schema:
          type: string
      - name: startDate
        in: query
        description: filter on startDate (UNIX Timestamp), this will return all "offers" for a given startDate
        required: false
        schema:
          type: integer
      - name: endDate
        in: query
        description: filter on date range by adding endDate (UNIX Timestamp) if startDate has a value. If startDate is null, filter on endDate only.
        required: false
        schema:
          type: integer
      - name: discipline
        in: query
        description: filter on discipline code, this will return all active events for a given discipline
        required: false
        schema:
          type: string
      - name: audience
        in: query
        description: filter on audience type, this will return all active events for a given audience type
        required: false
        schema:
          type: string
      - name: limit
        in: query
        description: Limit the amount of data returned (default is 10)
        required: false
        schema:
          type: integer
          default: 10
      - name: offset
        in: query
        description: Offset for paginating results (default is 0)
        required: false
        schema:
          type: integer
          default: 0
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
                  "@context": "http://schema.org",
                  "@type": "Event",
                  "identifier": 14,
                  "eventCollectionId": 1,
                  "lastModified": "2024-02-15T19:00:00"
                },
                {
                  "@context": "http://schema.org",
                  "@type": "ExhibitionEvent",
                  "identifier": 1513,
                  "lastModified": "2024-02-15T19:00:00"
                },
                {
                  "@context": "http://schema.org",
                  "@type": "ItemList",
                  "identifier": 1,
                  "lastModified": "2024-02-15T19:00:00"
                },
                {
                  "@context": "http://schema.org",
                  "@type": "EventSeries",
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
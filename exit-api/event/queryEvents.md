## Query All Event Type(s)
I think we can use this one to also filter by event type, this one doesn't have "offers" or representations. it returns a list of all event id and types for a given filter.  From there, separate calls can be made to fetch additional information. This is useful to get list of all events within a place or artist

Similar to get_activities

Can be used to query specify types by passing parameter.

```yaml
openapi: 3.0.0
info:
  title: Query Events API
  version: 1.0.0
paths:
  "/api/content/events":
    parameters:
      - name: lang
        in: query
        schema:
          type: string
          enum:
            - fr
            - en
        default: fr
        description: "The language parameter (fr or en, default: fr)"
      - name: type
        description: Type of event (event, exhibition, series), if not applied, all types are shown.
        in: query
      - name: place
        description: Reference of ID of a place used to filter results. If present, the ids parameter won't be used.
        in: query
      - name: startDate
        description: startDate of events. ISO 8601 Format 
        in: query
      - name: endDate
        description: endDate of events
        in: query
      - name: contributor
        description: ID of contributor to fetch events
        in: query
      - name: discipline
        description: ID of discipline to fetch events
        in: query
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
    get:
      summary: "Get list of events based on filters defined in parameters"
      responses:
        "200":
          description: "Successful response"
          content:
            application/json:
              example: >
                {
                  "@context": "https://schema.org",
                  "@type": "Event",
                  "name": "Example Event",
                  "description": "This is a sample event description.",
                  "eventType": "Social Gathering",
                  "eventStatus": "Scheduled",
                  "startDate": "2024-01-01T18:00:00Z",
                  "endDate": "2024-01-01T22:00:00Z",
                  "audience": {
                    "@type": "Audience",
                    "name": "General Audience"
                  },
                  "contributor": [
                    {
                      "@type": "Organization",
                      "name": "Example Organization"
                    },
                    {
                      "@type": "Person",
                      "name": "John Doe"
                    }
                  ],
                  "image": {
                    "@type": "ImageObject",
                    "contentUrl": "https://example.com/event-image.jpg",
                    "caption": "Event Image"
                  },
                  "eventAttendanceMode": "Offline",
                  "previousStartDate": "2023-12-31T18:00:00Z",
                  "additionalType": "https://schema.org/PartyEvent",
                  "mainEntityOfPage": "https://example.com/event-page",
                  "sameAs": "https://socialmedia.com/event123"
                }
        "404":
          description: "Events not found"
          content:
            text/plain:
              example: "Events not found"
```
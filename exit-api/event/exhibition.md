# Exhibition

Similar to get_activity but now only for "exhibition" type

## Get exhibition
```yaml
openapi: 3.0.0
info:
  title: Exhibition API
  version: 1.0.0
paths:
  "/api/content/exhibition/{id}":
    parameters:
      - name: id
        in: path
        required: true
        schema:
          type: string
        description: "The ID of the event"
      - name: lang
        in: query
        schema:
          type: string
          enum:
            - fr
            - en
        default: fr
        description: "The language parameter (fr or en, default: fr)"
    get:
      summary: "Get event data by ID"
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
          description: "Event not found"
          content:
            text/plain:
              example: "Event not found"
```


# Series
**TODO Think about using "superEvent" and "subEvent" to help with eventSeries structures what info do we need to include for subEvent?**

Similar to get_activity but now only for "series" type

Think series, what information do we need to render one single series page.

TODO: include "offer" as per Schema.org standards.  Ticket + pricing info

What information should be included in the subEvent? LVCOffer type perhaps.
```json
// Example of how to use subEvent
{
  "@context": "https://schema.org",
  "@type": "Event",
  "name": "Music Festival",
  "startDate": "2024-07-01T18:00:00-07:00",
  "endDate": "2024-07-03T23:59:59-07:00",
  "location": {
    "@type": "Place",
    "name": "City Park",
    "address": "123 Main St, Cityville"
  },
  "subEvent": [
    {
      "@type": "MusicEvent",
      "name": "Opening Concert",
      "startDate": "2024-07-01T18:00:00-07:00",
      "endDate": "2024-07-01T22:00:00-07:00",
      "performer": {
        "@type": "MusicGroup",
        "name": "Awesome Band"
      }
    },
    {
      "@type": "MusicEvent",
      "name": "Day 2 Performances",
      "startDate": "2024-07-02T12:00:00-07:00",
      "endDate": "2024-07-02T23:59:59-07:00",
      "performer": {
        "@type": "MusicGroup",
        "name": "Rockin' Ensemble"
      }
    },
    {
      "@type": "MusicEvent",
      "name": "Closing Night Party",
      "startDate": "2024-07-03T19:00:00-07:00",
      "endDate": "2024-07-03T23:59:59-07:00",
      "performer": {
        "@type": "MusicGroup",
        "name": "Funky Beats Crew"
      }
    }
  ]
}

```
## Get Series
```yaml
openapi: 3.0.0
info:
  title: Series API
  version: 1.0.0
paths:
  "/api/content/series/{id}":
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
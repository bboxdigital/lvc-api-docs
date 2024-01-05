# Event
**TODO Add offers? What info is required here?**\
**TODO Think about using "superEvent" and "subEvent" to help with eventSeries structures or relationships to eventSeries**

This is used to get information about a specific "event" type. Since events themselves have basic information, this endpoint is generally used to gather basic information about a particular "event".

The Offer API should be used to query offer data and can be used to refine response data more efficently.

Think event page.  what info do we require to render one single event page.

Not sure this is needed, perhaps this api can be used to return "event" + "offer" aka representation instead.

Similar to get_activity but now only for "event" type


Think about using "subEvent" as a way to hold "showings"
Essentially, event pages are similar to series, where they hold a series of events (aka representations).  

Type would still be Event, subEvent would be a collection of events with full information (location, dates, ticket info).

This makes sense if we think about the URL strucuture used for LVC. /event/eventId/offerId

Essentially, eventOffers are subEvent of event.

For actual EventSeries, the same approach is used.  subEvent will be a list of all eventOffers for that Series.


## Get event (not representation)
todo: add list of offers?? Not really offers as per Schema.org, more like "showings" or eventSchedule that include different locations
```yaml
openapi: 3.0.0
info:
  title: Event API
  version: 1.0.0
paths:
  /api/content/event/{id}:
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
## Get event representation
Event type, includes Offer type (ticket + pricing)
```yaml
openapi: 3.0.0
info:
  title: Event API
  version: 1.0.0
paths:
  /api/content/event/{eventId}/{offerId}:
    parameters:
      - name: eventId
        in: path
        required: true
        schema:
          type: string
        description: "The identifier of the event"
      - name: offerId
        in: path
        required: true
        schema:
          type: string
        description: "The identifier of the eventOffer"
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
      summary: "Get representation data by identifier"
      responses:
        "200":
          description: "Successful response"
          content:
            application/json:
              example:
                "@context": "https://schema.org"
                "@type": "Event"
                "identifier": 123
                "name": "Sample Event"
                "description": "This is a sample event description."
                "startDate": "2024-01-01T10:00:00"
                "endDate": "2024-01-01T17:00:00"
                "previousStartDate": "2023-12-31T10:00:00"
                "url": "https://example.com/sample-event"
                "eventId": 13
                "eventType": "Event"
                "audience":
                  "@type": "Audience"
                  "audienceType": "Adult"
                "eventStatus": "https://schema.org/EventScheduled"
                "location":
                  "@type": "Place"
                  "identifier": 13
                  "name": "Event Venue"
                  "address":
                    "@type": "PostalAddress"
                    "streetAddress": "123 Main St"
                    "addressLocality": "Cityville"
                    "addressRegion": "CA"
                    "postalCode": "12345"
                    "addressCountry": "US"
                "contributor":
                  "@type": "Person"
                  "identifier": 3
                  "name": "John Doe"
                "offerContributor":
                  "@type": "Organization"
                  "identifier": 50
                  "name": "Event Organizer Inc."
                "offers":
                  "@type": "Offer"
                  "priceSpecification":
                    "@type": "PriceSpecification"
                    "minPrice": 25.00
                    "price": 50.00
                    "priceCurrency": "CAD"
                  "availabilityStart": "2023-12-15T00:00:00"
                  "availabilityEnd": "2024-01-01T09:00:00"
                  "availability": "https://schema.org/InStock"
                  "preSaleStart": "2023-12-01T12:00:00"
                "eventAttendanceMode": "https://schema.org/OfflineEventAttendanceMode"
                "isAccessibleForFree": false
                "advanceBookingRequirement": "AdvanceBookingRequired"
                "superEvent":
                  "@type": "Event"
                  "name": "Parent Event"
                  "identifier": 456
                  "url": "https://example.com/parent-event"
                "additionalType": "SpecialEvent"
                "mainEntityOfPage": "https://example.com/sample-event-details"
                "sameAs":
                  - "https://twitter.com/sampleevent"
                  - "https://facebook.com/sampleevent"
        "404":
          description: "Event not found"
          content:
            text/plain:
              example: "Event not found"
```

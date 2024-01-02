# Offer
Compiles offer data and event data, similar structure as event.
May need to create custom JSON-LD structure for this...some structure from Event, some from Offer
## Get single offer
```yaml
openapi: 3.0.0
info:
  title: Content API
  version: 1.0.0
paths:
  /api/content/{eventId}/{offerId}:
    parameters:
      - name: eventId
        in: path
        required: true
        description: The ID of the event.
        schema:
          type: string
      - name: offerId
        in: path
        required: true
        description: The ID of the offer.
        schema:
          type: string
      - name: lang
        in: query
        description: Language parameter (fr or en, default: fr)
        schema:
          type: string
          enum: [fr, en]
          default: fr
    get:
      summary: Get content for a specific event and offer
      responses:
        '200':
          description: Successful response
          content:
            application/json:
              example:
                "@context": "https://schema.org"
                "@type": "Event"
                "id": 123
                "name": "Sample Event"
                "description": "This is a sample event description."
                "startDate": "2024-01-01T10:00:00"
                "endDate": "2024-01-01T17:00:00"
                "previousStartDate": "2023-12-31T10:00:00"
                "url": "https://example.com/sample-event"
                "eventId": 13
                "eventType": "Event"
                "audience": "Adults"
                "status": "Scheduled"
                "location":
                  "@type": "Place"
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
                  "name": "John Doe"
                "offerContributor":
                  "@type": "Organization"
                  "name": "Event Organizer Inc."
                "price": 50.00
                "minimumPrice": 25.00
                "availabilityStart": "2023-12-15T00:00:00"
                "availabilityEnd": "2024-01-01T09:00:00"
                "availability": "InStock"
                "preSaleStart": "2023-12-01T12:00:00"
                "attendanceMode": "Offline"
                "isAccessibleForFree": false
                "advanceBookingRequirement": "AdvanceBookingRequired"
                "additionalType": "SpecialEvent"
                "mainEntityOfPage": "https://example.com/sample-event-details"
                "sameAs":
                  - "https://twitter.com/sampleevent"
                  - "https://facebook.com/sampleevent"
        '404':
          description: Offer Not Found
          content:
            text/plain:
              example: "Offer Not Found"
```

## Query Offers
```yaml
openapi: 3.0.0
info:
  title: Content Offer API
  version: 1.0.0
paths:
  /api/content/offer/:
    get:
      summary: Retrieve content offers
      parameters:
        - name: lang
          in: query
          description: Language code for content offers (either "fr" or "en")
          required: false
          schema:
            type: string
            enum:
              - fr
              - en
          default: fr
        - name: filter
          in: query
          description: Filtering criteria for content offers (To be determined)
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
      responses:
        '200':
          description: Successful response
          content:
            application/json:
              example:
                data:
                  - offer_id: 1
                    context: "https://schema.org"
                    type: "Event"
                    id: 123
                    name: "Sample Event 1"
                    description: "This is a sample event description for Offer 1."
                    startDate: "2024-01-01T10:00:00"
                    endDate: "2024-01-01T17:00:00"
                    url: "https://example.com/sample-event-1"
                    eventId: 13
                    eventType: "Event"
                    audience: "Adults"
                    status: "Scheduled"
                    location:
                      type: "Place"
                      name: "Event Venue 1"
                      address:
                        type: "PostalAddress"
                        streetAddress: "123 Main St"
                        addressLocality: "Cityville"
                        addressRegion: "CA"
                        postalCode: "12345"
                        addressCountry: "US"
                    contributor:
                      type: "Person"
                      name: "John Doe"
                    offerContributor:
                      type: "Organization"
                      name: "Event Organizer Inc."
                    price: 50.00
                    minimumPrice: 25.00
                    availabilityStart: "2023-12-15T00:00:00"
                    availabilityEnd: "2024-01-01T09:00:00"
                    availability: "InStock"
                    preSaleStart: "2023-12-01T12:00:00"
                    attendanceMode: "Offline"
                    isAccessibleForFree: false
                    advanceBookingRequirement: "AdvanceBookingRequired"
                    additionalType: "SpecialEvent"
                    mainEntityOfPage: "https://example.com/sample-event-details-1"
                    sameAs:
                      - "https://twitter.com/sampleevent1"
                      - "https://facebook.com/sampleevent1"
                  - offer_id: 2
                    context: "https://schema.org"
                    type: "Event"
                    id: 456
                    name: "Sample Event 2"
                    description: "This is a sample event description for Offer 2."
                    startDate: "2024-02-01T10:00:00"
                    endDate: "2024-02-01T17:00:00"
                    url: "https://example.com/sample-event-2"
                    eventId: 14
                    eventType: "Event"
                    audience: "Adults"
                    status: "Scheduled"
                    location:
                      type: "Place"
                      name: "Event Venue 2"
                      address:
                        type: "PostalAddress"
                        streetAddress: "456 Main St"
                        addressLocality: "Townsville"
                        addressRegion: "NY"
                        postalCode: "54321"
                        addressCountry: "US"
                    contributor:
                      type: "Person"
                      name: "Jane Doe"
                    offerContributor:
                      type: "Organization"
                      name: "Event Organizer Inc."
                    price: 60.00
                    minimumPrice: 30.00
                    availabilityStart: "2023-12-20T00:00:00"
                    availabilityEnd: "2024-02-01T09:00:00"
                    availability: "InStock"
                    preSaleStart: "2023-12-05T12:00:00"
                    attendanceMode: "Offline"
                    isAccessibleForFree: false
                    advanceBookingRequirement: "AdvanceBookingRequired"
                    additionalType: "SpecialEvent"
                    mainEntityOfPage: "https://example.com/sample-event-details-2"
                    sameAs:
                      - "https://twitter.com/sampleevent2"
                      - "https://facebook.com/sampleevent2"
                meta:
                  total_count: 2
                  limit: 10
                  offset: 0
        '404':
          description: Resource not found
          content:
            application/json:
              example:
                error:
                  code: 404
                  message: "Resource not found"
```
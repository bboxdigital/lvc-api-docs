# Offer (event offers, series, exhibitions)

Normalized structure so that all different types of content can be injected into frontend seemlessly, in a standard way.

Strategy is to combine all eventTypes together, then by adding filters clients can request specific data as needed (ex: only series, on this date, at this place)

Think "search"... returns all instances of "showing".

TODO: Create custom Schema for Offer

The old "Activity" / representation

The idea here is to provide an endpoint to query across all types of events, from there IDs and types can be used to retrieve specific event data from single APIs

Think about how users would want to use this, what if they want to get all eventTypes for a given filter? Similar to artist spectacles, maybe users don't want to get all offers and only have the event data.

Combines representations, exhibitions, series into one.  This endpoint could be used as a search feature where standardized data is required (ex: title, image, date, time, locaiton, url).



## Query all events as offers (all types combined)
```yaml
openapi: 3.0.0
info:
  title: Content Offer API
  version: 1.0.0
paths:
  /api/content/offers/:
    get:
      summary: Retrieve offers content, sorted chronologically by startDate
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
        - name: type
          in: query
          description: query offers by specific event type only
          required: false
          schema:
            type: string
            enum:
             - event
             - series
             - exhibition
        - name: eventId
          in: query
          description: filter on eventId, this will only return offers for a given eventId ("event" type).
          required: false
          schema:
            type: string
        - name: contributor
          in: query
          description: filter on contributor, this will return all offers for a given contributor ID
          required: false
          schema:
            type: string
        - name: place
          in: query
          description: query offers by specific place id (location)
          required: false
          schema:
            type: string
        - name: startDate
          in: query
          description: filter offers by startDate, if startDate is present, filter will return all offers on that date. A date value in ISO 8601 date format. YYYY-MM-DD.
          required: false
          schema:
            type: date
        - name: endDate
          in: query
          description: filter offers by endDate, if startDate is present, filter will return all offers within the range. If startDate is missing, filter will return all offers on or before endDate. A date value in ISO 8601 date format. YYYY-MM-DD.
          required: false
          schema:
            type: date
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
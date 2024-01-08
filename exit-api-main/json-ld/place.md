# Place API
**TODO: How to handle locationType? Place vs organization**\
**TODO: How to handle containsPlace and containedInPlace** \
**TODO: How to handle notion of "Sector"** \
**TODO: How to manage place events?**

TODO: Perhaps a query param flag to include basic offer data in response.

Think about what information is required to render one single place page.
## Get a place
```yaml
openapi: 3.0.0
info:
  title: Example API
  version: 1.0.0
paths:
  /api/content/place/{id}:
    parameters:
      - name: id
        in: path
        required: true
        schema:
          type: string
        description: The ID of the place
      - name: lang
        description: which language data to use
        in: query
        schema:
          type: string
          default: "fr"
          enum:
            - "fr"
            - "en"
    get:
      summary: Get place details by ID
      responses:
        '200':
          description: Successful response
          content:
            application/json:
              example:
                "@context": "https://schema.org"
                "@type": "Place"
                "id": 123
                "name": "Example Venue"
                "address":
                  "@type": "PostalAddress"
                  "streetAddress": "123 Main St"
                  "addressLocality": "Cityville"
                  "addressRegion": "Stateville"
                  "postalCode": "12345"
                  "addressCountry": "Countryland"
                "maximumAttendeeCapacity": 500
                "containedInPlace":
                  "@type": "Place"
                  "name": "City Convention Center"
                "containsPlace":
                  "@type": "Place"
                  "name": "Conference Room A"
                "image":
                  "@type": "ImageObject"
                  "name": "Example Venue Image"
                  "description": "A beautiful picture of Example Venue"
                  "copyrightHolder":
                    "@type": "Person"
                    "name": "Jane Doe"
                  "copyrightNotice": "© 2023 Jane Doe"
                  "contentUrl": "https://example.com/Example-venue.jpg"
                  "encodingFormat": "image/jpeg"
                "mainEntityOfPage": "https://example.com/venue-page"
                "sameAs": ["https://twitter.com/examplevenue", "https://facebook.com/examplevenue"]
                "additionalTypes": ["https://example.com/AdditionalType1", "https://example.com/AdditionalType2"]
        '404':
          description: Place not found
          content:
            text/plain:
              example: "Place not found"
```
## Query places
```yaml
openapi: 3.0.0
info:
  title: Places API
  version: 1.0.0
paths:
  /api/content/place/:
    parameters:
      - name: lang
        description: which language data to use
        in: query
        schema:
          type: string
          default: "fr"
          enum:
            - "fr"
            - "en"
      - name: ids
        description: A comma-separated list of ids. If you define this option, all filtering parameters are ignored.
        in: query
        style: form
        explode: false
        schema: 
          type: array
          items:
            type: string
      - name: withShowing
        in: query
        description: Display only locations with showings.
        schema:
          type: boolean
          default: true
    get:
      summary: Get place details by ID
      responses:
        '200':
          description: Successful response
          content:
            application/json:
              example:
                "@context": "https://schema.org"
                "@type": "Place"
                "id": 123
                "name": "Example Venue"
                "address":
                  "@type": "PostalAddress"
                  "streetAddress": "123 Main St"
                  "addressLocality": "Cityville"
                  "addressRegion": "Stateville"
                  "postalCode": "12345"
                  "addressCountry": "Countryland"
                "maximumAttendeeCapacity": 500
                "containedInPlace":
                  "@type": "Place"
                  "name": "City Convention Center"
                "containsPlace":
                  "@type": "Place"
                  "name": "Conference Room A"
                "image":
                  "@type": "ImageObject"
                  "name": "Example Venue Image"
                  "description": "A beautiful picture of Example Venue"
                  "copyrightHolder":
                    "@type": "Person"
                    "name": "Jane Doe"
                  "copyrightNotice": "© 2023 Jane Doe"
                  "contentUrl": "https://example.com/Example-venue.jpg"
                  "encodingFormat": "image/jpeg"
                "mainEntityOfPage": "https://example.com/venue-page"
                "sameAs": ["https://twitter.com/examplevenue", "https://facebook.com/examplevenue"]
                "additionalTypes": ["https://example.com/AdditionalType1", "https://example.com/AdditionalType2"]
        '404':
          description: Place not found
          content:
            text/plain:
              example: "Place not found"
```


Example on how "offers" could be injected into Place data using "event".  ** not sure if this is needed as we can run queries using queryEvents and add place param
```json
{
  "@context": {
    "@vocab": "http://schema.org/",
    "schema": "http://schema.org/"
  },
  "@type": "Place",
  "name": "Example Venue",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "123 Main Street",
    "addressLocality": "Cityville",
    "addressRegion": "Stateville",
    "postalCode": "12345",
    "addressCountry": "Countryland"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": 40.7128,
    "longitude": -74.0060
  },
  "event": [
    {
      "@type": "Event",
      "name": "Concert at Example Venue",
      "startDate": "2024-01-10T18:00:00",
      "endDate": "2024-01-10T22:00:00",
      "description": "A fantastic live music concert at Example Venue.",
      "location": {
        "@type": "Place",
        "name": "Example Venue"
      }
    },
    {
      "@type": "Event",
      "name": "Conference at Example Venue",
      "startDate": "2024-02-15T09:00:00",
      "endDate": "2024-02-16T17:00:00",
      "description": "An informative conference covering various topics.",
      "location": {
        "@type": "Place",
        "name": "Example Venue"
      }
    }
  ]
}
```
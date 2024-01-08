# Query All Events (event offers, series, exhibitions)

Normalized structure so that all different types of content can be injected into frontend seemlessly, in a standard way.

Strategy is to combine all eventTypes together, then by adding filters clients can request specific data as needed (ex: only series, on this date, at this place)

Think "search"... returns all instances of "showing".

TODO: Create custom Schema for Offer

The old "Activity" / representation

The idea here is to provide an endpoint to query across all types of events, from there IDs and types can be used to retrieve specific event data from single APIs

Think about how users would want to use this, what if they want to get all eventTypes for a given filter? Similar to artist spectacles, maybe users don't want to get all offers and only have the event data.

Combines representations, exhibitions, series into one.  This endpoint could be used as a search feature where standardized data is required (ex: title, image, date, time, locaiton, url).

## Query All Events (all types combined)
```yaml
openapi: 3.0.0
info:
  title: Query All Events API
  version: 1.0.0
paths:
  /api/content/allEvents/:
    get:
      summary: Retrieve event content, sorted chronologically by startDate
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
        - name: schema
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
          description: UNIX Timestamp (UTC)
          required: false
          schema:
            type: integer
        - name: endDate
          in: query
          description: UNIX Timestamp (UTC)
          required: false
          schema:
            type: integer
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
        "200":
          description: Successful response
          content:
            application/json:
              example: >
                [
                  {
                    "id": 140,
                    "schema": "eventOffers",
                    "eventId": 492,
                    "eventStatus": "Scheduled",
                    "name": "John Smith Comedy Show",
                    "description": "Join us for a night of laughter with the hilarious John Smith.",
                    "eventAttendanceMode": "Offline",
                    "audience": "Adult",
                    "eventStatus": "Scheduled",
                    "startDate": "2024-02-15T19:00:00",
                    "endDate": null,
                    "isAccessibleForFree": false,
                    "minPrice": 5.00,
                    "price": 40.00,
                    "availability": "http://schema.org/InStock",
                    "availabilityStarts": "2023-11-15T19:00:00",
                    "availabilityEnds": "2024-04-15T19:00:00",
                    "advanceBookingRequirement": false,
                    "image": {
                      "name": "john-smith.jpg",
                      "contentUrl": "https://example.com/john-smith.jpg",
                      "copyrightType": "Copyright-free",
                      "encodingFormat": "image/jpeg",
                      "copyrightNotice": "© Example 2024"
                    },
                    "medias": [],
                    "contributions": [
                      {
                        "id": 402,
                        "type":"Artiste sur scene",
                        "contributors": {
                          "name": "John Smith",
                          "contributorType": "Person",
                          "image": "https://www.johnsmithcomedy.com/images/john-smith.jpg",
                          "url": "https://john-smith.com"
                        }
                      },
                      {
                        "id": 401
                      }
                    ],
                    "artists": [
                      {
                        "id": 853,
                        "type": "Person",
                        "name": "John Smith",
                        "image": "https://example.com/john-smith.jpg",
                        "sameAs": [
                          "https://www.linkedin.com/in/john-smith",
                          "https://twitter.com/john-smith",
                          "https://www.facebook.com/john-smith"
                        ]
                      }
                    ],
                    "location": {
                      "id": 102,
                      "schema": "places",
                      "type": "Place",
                      "name": "Example Place A",
                      "address": {
                        "streetAddress": "789 Laughter Lane",
                        "addressLocality": "Humorville",
                        "addressRegion": "Quebec",
                        "postalCode": "G1T 4R1",
                        "addressCountry": "CA"
                      },
                      "latitude": 37.23332,
                      "longitude": -133.43330,
                      "maximumAttendeeCapacity": 240,
                      "url": "https://example-place-a.com"
                    },
                    "lastModified": "2024-02-15T19:00:00"
                  },
                  {
                    "id": 140,
                    "schema": "exhibitionEvents",
                    "type": "Temporary",
                    "eventStatus": "Scheduled",
                    "name": "The Chuckles Exhibition",
                    "description": "Get ready to burst into laughter at The Chuckles Fest featuring top comedians.",
                    "eventAttendanceMode": "Offline",
                    "audience": "Adult",
                    "startDate": "2024-02-15T19:00:00",
                    "endDate": null,
                    "isAccessibleForFree": false,
                    "minPrice": 10.00,
                    "price": 35.00,
                    "availability": "http://schema.org/InStock",
                    "availabilityStarts": "2023-12-01T10:00:00",
                    "availabilityEnds": "2024-02-15T18:00:00",
                    "advanceBookingRequirement": true,
                    "image": {
                      "name": "chuckles-fest.jpg",
                      "contentUrl": "https://example.com/chuckles-fest.jpg",
                      "copyrightType": "Copyright",
                      "encodingFormat": "image/jpeg",
                      "copyrightNotice": "© Chuckles Fest 2024"
                    },
                    "medias": [
                      {
                        "id": 601,
                        "type": "Video",
                        "url": "https://example.com/chuckles-fest-promo.mp4"
                      },
                      {
                        "id": 602,
                        "type": "Audio",
                        "url": "https://example.com/chuckles-fest-podcast.mp3"
                      }
                    ],
                    "contributions": [
                      {
                        "id": 402,
                        "type":"Artiste sur scene",
                        "contributors": {
                          "name": "Jane Doe",
                          "contributorType": "Person",
                          "image": "https://www.janedoecomedy.com/images/jane-doe.jpg",
                          "url": "https://janedoe.com"
                        }
                      },
                      {
                        "id": 401,
                        "type": "Producteur",
                        "contributors": {
                          "name": "Bob Johnson",
                          "contributorType": "Person",
                          "image": "https://www.bobjohnsoncomedy.com/images/bob-johnson.jpg",
                          "url": "https://bobjohnson.com"
                        }
                      }
                    ],
                    "artists": [
                      {
                        "id": 853,
                        "type": "Person",
                        "name": "Jane Doe",
                        "image": "https://example.com/jane-doe.jpg",
                        "sameAs": [
                          "https://www.linkedin.com/in/jane-doe",
                          "https://twitter.com/jane-doe",
                          "https://www.facebook.com/jane-doe"
                        ]
                      }
                    ],
                    "location": {
                      "id": 102,
                      "schema": "places",
                      "type": "Place",
                      "name": "Laughter Palace",
                      "address": {
                        "streetAddress": "123 Haha Street",
                        "addressLocality": "Comedy City",
                        "addressRegion": "California",
                        "postalCode": "90210",
                        "addressCountry": "US"
                      },
                      "latitude": 34.05223,
                      "longitude": -118.24368,
                      "maximumAttendeeCapacity": 300,
                      "url": "https://laughterpalace.com"
                    },
                    "lastModified": "2024-02-10T15:30:00"
                  }
                ]
        "404":
          description: Not found
          content:
            application/json:
              example:
                error:
                  code: 404
                  message: "Not found"
```
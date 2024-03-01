# Event (as per Schema.org) - JSON-LD ONLY APPROACH
The notion of "event" according to [Schema.org](https://schema.org) differs from LVC's database "event".

With that in mind, the recommended approach is to use LVC "eventOffers" (representations) as "event" type, to more accuratly represent the standard.

There is a field called "subEvent" and "superEvent" within the "event" schema, however in this context it was decided that it does not fully represent the data. These fields more accurately represent events that are part of a series or festival.

TODO: Finalize how to deal with "contributors" / "contributions" and Schema.org different fields

## JSON-LD Structure (with some comments)
```json
{
  "@context": "http://schema.org", // Always required for JSON-LD, provides context reference for the crawlers.
  "@type": "Event",  // Could also be more specific (ex: MusicEvent) - "https://schema.org/Event" crawlers will then know what to look for.
  "@id": "", // URI of the event page on the injected website.
  "url": "https://example.com/event-page", // Official website
  "identifier": 23,  // Not useful for JSON-LD, for database reference
  "name": "John Smith Comedy Show",
  "description": "Join us for a night of laughter with the hilarious John Smith.",
  "superEvent": { // If part of series
    "@type": "EventSeries",
    "@id": "https://la-vitrine.com/series/comedy-tour-2024/6",
    "identifier": 6,
    "name": "Comedy Tour 2024"
  },
  "image": {
    "@type": "ImageObject",
    "contentUrl": "https://example.com/some-image.jpg",
    "description": "An example image",
    "encodingFormat": "image/jpeg",
    "creditText": "Jane Doe"
  },
  "audience": {
    "@type": "Audience",
    "audienceType": "Adult"
  },
  "eventStatus": "https://schema.org/EventScheduled", // Enum value, Plain Text not recommended
  "eventAttendanceMode": "https://schema.org/OfflineEventAttendanceMode", // Enum
  "performer": {
    "@type": "Person",
    "@id": "https://la-vitrine.com/artist/john-smith/10", // Only for LVC website injection
    "identifier": 10, // database reference
    "name": "John Smith",
    "image": "https://www.johnsmithcomedy.com/images/john-smith.jpg", // or full ImageObject
    "url": "https://john-smith.com", // Official website
    "sameAs": [
      // Add LVC website link here if for external consumption
      "https://www.linkedin.com/in/john-smith",
      "https://twitter.com/john-smith",
      "https://www.facebook.com/john-smith"
    ]
  },
  "startDate": "2024-02-15T19:00:00",
  "endDate": "2024-02-15T21:00:00",
  "location": {
    "@type": "Place",
    "@id": "https://la-vitrine.com/place/comedy-club-a/23",
    "name": "Comedy Club A",
    "image": "https://example.com/photo.jpg",
    "url": "https://comedy-club-a.com",
    "sameAs": [
      "https://www.linkedin.com/in/comedy-club-a",
      "https://twitter.com/comedy-club-a",
      "https://www.facebook.com/comedy-club-a"
    ],
    "address": {
      "@type": "PostalAddress",
      "streetAddress": "789 Laughter Lane",
      "addressLocality": "Humorville",
      "addressRegion": "Quebec",
      "postalCode": "G1T 4R1",
      "addressCountry": {
        "@type": "Country",
        "name": "CA"
      }
    },
    "geo": {
      "@type": "GeoCoordinates",
      "latitude": 37.23332,
      "longitude": -133.43330,
    },
    "maximumAttendeeCapacity": 240
  },
  "offers": {
    "@type": "Offer",
    "url": "http://example.com/ticket-sales-club-a",
    "priceSpecification": {
      "@type": "PriceSpecification",
      "price": 10.00,
      "minPrice": 5.00,
      "priceCurrency": "CAD"
    },
    "isAccessibleForFree": false,
    "availability": "http://schema.org/InStock",
    "availabilityEnds": "2024-03-04T10:00:00",
    "availabilityStarts": "2023-08-04T10:00:00",
    "advanceBookingRequirement": false,
  },
}
```
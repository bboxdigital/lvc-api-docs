## LVC Event Representation JSON-LD Schema.org structure
TODO: Clean up, think about what information and data will be required from this.
Look at old API + LVC APP

TODO: How to include "other events / other dates"  perhaps ItemList...maybe separate API call.

Notes: 
- @type could be more specific (ex: MusicEvent)
- @id, probably not useful for external API, maybe add to sameAs
```json
// Example of event (representation) data
{
  "@context": "http://schema.org",
  "@type": "Event",
  "@id": "https://la-vitrine.com/event/john-smith-show/492/23", //sameAs?
  "url": "https://example.com/event-page",
  "identifier": 23,  //Not useful for JSON-LD
  "name": "John Smith Comedy Show",
  "description": "Join us for a night of laughter with the hilarious John Smith.",
  "superEvent": {
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
  "eventStatus": "https://schema.org/EventScheduled",
  "eventAttendanceMode": "https://schema.org/OfflineEventAttendanceMode",
  "performer": {
    "@type": "Person",
    "@id": "https://la-vitrine.com/artist/john-smith/10", // sameAs instead?
    "identifier": 10, // Not useful for JSON-LD
    "name": "John Smith",
    "image": "https://www.johnsmithcomedy.com/images/john-smith.jpg",
    "url": "https://john-smith.com",
    "sameAs": [
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
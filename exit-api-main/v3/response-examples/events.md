# Example of Event JSON Response
review:

- how deep to resolve? (ex: images, performer etc)
- what to do with contributors

query params

- id
- lang

```json
{
  "@context": "http://schema.org",
  "@type": "Event",
  "@id": "https://la-vitrine.com/fr/evenement/john-smith-comedy-show/123/14",
  "url": "https://example.com/event-page",
  "identifier": 14,
  "name": "John Smith Comedy Show",
  "description": "Join us for a night of laughter with the hilarious John Smith.",
  "superEvent": {
    "@type": "EventSeries",
    "@id": "https://la-vitrine.com/fr/series/comedy-tour-2024/6",
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
  "eventStatus": "EventScheduled",
  "eventAttendanceMode": "OfflineEventAttendanceMode",
  "startDate": "2024-02-15T19:00:00",
  "endDate": "2024-02-15T21:00:00",
  "performer": {
    "@type": "Person",
    "@id": "https://la-vitrine.com/artist/john-smith/10",
    "identifier": 10,
    "name": "John Smith",
    "image": "https://www.johnsmithcomedy.com/images/john-smith.jpg",
    "url": "https://john-smith.com",
    "sameAs": ["https://www.linkedin.com/in/john-smith", "https://twitter.com/john-smith", "https://www.facebook.com/john-smith"]
  },
  "location": {
    "@type": "Place",
    "@id": "https://la-vitrine.com/fr/lieu/comedy-club-a/23",
    "identifier": 23,
    "name": "Comedy Club A",
    "image": "https://example.com/photo.jpg",
    "url": "https://comedy-club-a.com",
    "sameAs": ["https://www.linkedin.com/in/comedy-club-a", "https://twitter.com/comedy-club-a", "https://www.facebook.com/comedy-club-a"],
    "address": {
      "@type": "PostalAddress",
      "streetAddress": "789 Laughter Lane",
      "addressLocality": "Humorville",
      "addressRegion": "Quebec",
      "postalCode": "G1T 4R1",
      "addressCountry": "CA"
    },
    "geo": {
      "@type": "GeoCoordinates",
      "latitude": 37.23332,
      "longitude": -133.4333
    },
    "maximumAttendeeCapacity": 240
  },
  "offers": {
    "@type": "Offer",
    "url": "http://example.com/ticket-sales-club-a",
    "priceCurrency": "CAD",
    "priceSpecification": {
      "@type": "PriceSpecification",
      "price": 10.0,
      "minPrice": 5.0
    },
    "availability": "InStock",
    "availabilityEnds": "2024-03-04T10:00:00",
    "availabilityStarts": "2023-08-04T10:00:00"
  },
  "isAccessibleForFree": false
}
```

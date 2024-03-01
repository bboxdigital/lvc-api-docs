# Place
Google doesn't accept "Place" type yet.
They have "Organization", "LocalBusiness"

```json
{
  "@context": "https://schema.org",
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
  "containedInPlace": {
    "@type": "Place",
    "@id": "https://la-vitrine.com/fr/lieu/city-park/23",
    "identifier": 23,
    "name": "City Park"
  },
  "events": [
    {
      "@type": "Event",
      "@id": "https://la-vitrine.com/fr/evenement/john-smith-comedy-show/123/14",
      "identifier": 14,
      "name": "John Smith Comedy Show",
      "startDate": "2024-02-15T19:00:00",
      "endDate": "2024-02-15T21:00:00",
      "image": "https://example.com/john-smith.jpg",
      "location": {
        "@type": "Place",
        "@id": "https://la-vitrine.com/fr/lieu/comedy-club-a/23",
        "identifier": 23,
        "name": "Comedy Club A"
      }
    },
    {
      "@type": "Event",
      "@id": "https://la-vitrine.com/fr/evenement/jane-doe-comedy-show/123/15",
      "identifier": 15,
      "name": "Jane Doe Comedy Show",
      "startDate": "2024-02-16T19:00:00",
      "endDate": "2024-02-16T21:00:00",
      "image": "https://example.com/jane-doe.jpg",
      "location": {
        "@type": "Place",
        "@id": "https://la-vitrine.com/fr/lieu/comedy-club-a/23",
        "identifier": 23,
        "name": "Comedy Club A"
      }
    }
  ],
  "maximumAttendeeCapacity": 240
}
```

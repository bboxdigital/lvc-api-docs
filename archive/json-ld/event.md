## LVC Event JSON-LD Schema.org structure
TODO: Clean up, think about what information and data will be required from this.
Look at old API + LVC APP
```json
// Example of event data
{
  "@context": "http://schema.org",
  "@type": "Event",
  "@id": "https://la-vitrine.com/event/john-smith-show/492",
  "identifier": 492,
  "name": "John Smith Comedy Show",
  "description": "Join us for a night of laughter with the hilarious John Smith.",
  "performer": {
    "@type": "Person",
    "@id": "https://la-vitrine.com/artist/john-smith/10",
    "identifier": 10,
    "name": "John Smith",
    "image": "https://www.johnsmithcomedy.com/images/john-smith.jpg",
    "url": "https://john-smith.com",
    "sameAs": [
      "https://www.linkedin.com/in/john-smith",
      "https://twitter.com/john-smith",
      "https://www.facebook.com/john-smith"
    ]
  },
  "subEvent": [
    {
      "@type": "Event",
      "@id": "https://la-vitrine.com/event/john-smith-show/492/23",
      "identifier": 23,
      "name": "John Smith Comedy Show",
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
          "addressCountry": "Canada"
        },
        "latitude": 37.23332,
        "longitude": -133.43330,
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
        "availability": "http://schema.org/InStock",
        "availabilityEnds": "ISO 8601",
        "availabilityStarts": "ISO 8601",
        "advanceBookingRequirement": false,
      },
    },
    {
      "@type": "Event",
      "@id": "https://la-vitrine.com/event/john-smith-show/492/23",      
      "identifier": 24,
      "name": "John Smith Comedy Show",
      "startDate": "2024-02-15T22:00:00",
      "endDate": "2024-02-16T00:00:00",
      "location": {
        "@type": "Place",
        "@id": "https://la-vitrine.com/place/comedy-club-a/23",
        "name": "Comedy Lounge B",
        "image": "https://example.com/photo-b.jpg",
        "url": "https://comedy-lounge-b.com",
        "sameAs": "https://www.facebook.com/comedy-club-a",
        "address": {
          "@type": "PostalAddress",
          "identifier": 145,
          "streetAddress": "456 Chuckles Street",
          "addressLocality": "Joketown",
          "addressRegion": "Quebec",
          "postalCode": "G1R 3D7",
          "addressCountry": "Canada"
        },
        "latitude": 42.24442,
        "longitude": -124.44555,
        "maximumAttendeeCapacity": 140
      },
      "offers": {
        "@type": "Offer",
        "url": "http://example.com/ticket-sales-lounge-b",
        "price": "25.00",
        "priceCurrency": "USD",
        "availability": "http://schema.org/InStock"
      }
    }
  ]
}
```
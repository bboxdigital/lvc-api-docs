# Series

Does Google Support EventSeries?

```json
{
  "@context": "https://schema.org",
  "@type": "EventSeries",
  "@id": "https://la-vitrine.com/fr/series/comedy-festival-2024/9",
  "identifier": 9,
  "name": "Comedy Festival 2024",
  "startDate": "2024-07-01T18:00:00-07:00",
  "endDate": "2024-07-03T23:59:59-07:00",
  "location": {
    "@type": "Place",
    "@id": "https://la-vitrine.com/fr/lieu/city-park/23",
    "identifier": 23,
    "name": "City Park",
    "image": "https://example.com/photo.jpg",
    "url": "https://example.com",
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
  "subEvent": [
    {
      "@type": "Event",
      "@id": "https://la-vitrine.com/fr/evenement/opening-concert/12324/10",
      "identifier": 10,
      "name": "Opening Concert",
      "description": "Join us for the opening concert of the Comedy Festival 2024.",
      "startDate": "2024-07-01T18:00:00-07:00",
      "endDate": "2024-07-01T21:00:00-07:00",
      "eventStatus": "EventScheduled",
      "location": {
        "@type": "Place",
        "@id": "https://la-vitrine.com/fr/lieu/city-park/23",
        "identifier": 23,
        "name": "City Park",
        "image": "https://example.com/photo.jpg",
        "url": "https://example.com",
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
      "performer": {
        "@type": "Organization",
        "@id": "https://la-vitrine.com/fr/organisation/awesome-band/23",
        "identifier": 23,
        "name": "Awesome Band"
      },
      "image": "https://example.com/some-image.jpg"
    },
    {
      "@type": "Event",
      "@id": "https://la-vitrine.com/fr/evenement/day-2-performances/135/11",
      "identifier": 11,
      "name": "Day 2 Performances",
      "startDate": "2024-07-02T12:00:00-07:00",
      "endDate": "2024-07-02T23:59:59-07:00",
      "eventStatus": "EventScheduled",
      "location": {
        "@type": "Place",
        "@id": "https://la-vitrine.com/fr/lieu/city-park/23",
        "identifier": 23,
        "name": "City Park",
        "image": "https://example.com/photo.jpg",
        "url": "https://example.com",
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
      "performer": {
        "@type": "Organization",
        "@id": "https://la-vitrine.com/fr/artist/rockin-ensemble/24",
        "identifier": 24,
        "name": "Rockin' Ensemble"
      },
      "image": "https://example.com/some-image2.jpg"
    },
    {
      "@type": "Event",
      "@id": "https://la-vitrine.com/fr/evenement/closing-night-party/123/12",
      "identifier": 12,
      "name": "Closing Night Party",
      "startDate": "2024-07-03T19:00:00-07:00",
      "endDate": "2024-07-03T23:59:59-07:00",
      "eventStatus": "EventScheduled",
      "location": {
        "@type": "Place",
        "@id": "https://la-vitrine.com/fr/lieu/city-park/23",
        "identifier": 23,
        "name": "City Park",
        "image": "https://example.com/photo.jpg",
        "url": "https://example.com",
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
      "performer": {
        "@type": "Organization",
        "@id": "https://la-vitrine.com/fr/artist/funky-beats-crew/25",
        "identifier": 25,
        "name": "Funky Beats Crew"
      },
      "image": "https://example.com/some-image3.jpg"
    }
  ]
}
```

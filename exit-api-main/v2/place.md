# Place
```/content/place/{id}```

## Content

```json
{
  "id": 492,
  "type": "Place",
  "name": "Event Venue A",
  "url": "https://example-venue-a.com",
  "description": "A beautiful place to host your next event",
  "address": {
    "streetAddress": "789 Laughter Lane",
    "addressLocality": "Humorville",
    "addressRegion": "Quebec",
    "postalCode": "G1T 4R1",
    "addressCountry": "CA"
  },
  "geo": {
    "latitude": 37.23332,
    "longitude": -133.43330,
  },
  "maximumAttendeeCapacity": 240,
  "photo": {
    "name": "event-venue-a.jpg",
    "contentUrl": "https://example.com/event-venue-a.jpg",
    "copyrightType": "Copyright-free",
    "encodingFormat": "image/jpeg",
    "copyrightNotice": "© Example 2024"
  },
  "sameAs": [
    "https://www.linkedin.com/in/event-venue-a",
    "https://twitter.com/event-venue-a",
    "https://www.facebook.com/event-venue-a"
  ],
  "containedInPlace": null,
  "containsPlace": [ // List of places contained in this place (children)
    {
      "id": 23,
      "type": "Place",
      "name": "Comedy Club A",
      "url": "https://comedy-club-a.com",
      "sameAs": [
        "https://www.linkedin.com/in/comedy-club-a",
        "https://twitter.com/comedy-club-a",
        "https://www.facebook.com/comedy-club-a"
      ],
      "address": {
        "streetAddress": "789 Laughter Lane",
        "addressLocality": "Humorville",
        "addressRegion": "Quebec",
        "postalCode": "G1T 4R1",
        "addressCountry": "CA"
      },
      "geo": {
        "latitude": 37.23332,
        "longitude": -133.43330,
      },
      "maximumAttendeeCapacity": 240
    }
  ],
  "event": [ // List of events at this place
    {
      "id": 23,
      "type": "Event",
      "name": "John Smith Comedy Show",
      "startDate": "2024-02-15T19:00:00",
      "endDate": "2024-02-15T21:00:00",
      "image": "https://example.com/john-smith.jpg",
      "url": "https://example.com/event-page",
      "audience": "Adult",
      "eventStatus": "Scheduled",
      "eventAttendanceMode": "OfflineEventAttendanceMode",
      "contributions": {
        "id": 450, 
        "type": "Artiste Sur Scene",
        "contributor": {
          "id": 10,
          "type": "Person", // Person or Organization
          "name": "John Smith",
          "image": "https://www.johnsmithcomedy.com/images/john-smith.jpg",
          "url": "https://john-smith.com",
          "sameAs": [
            "https://www.linkedin.com/in/john-smith",
            "https://twitter.com/john-smith",
            "https://www.facebook.com/john-smith"
          ]
        },
      },
      "lastModified": "2024-02-15T19:00:00"
    },
    {
      "id": 45,
      "type": "ExhibitionEvent",
      "name": "Jane Doe Comedy Exhibition Show",
      "startDate": "2024-02-15T19:00:00",
      "endDate": "2024-02-15T21:00:00",
      "image": "https://example.com/jane-doe.jpg",
      "url": "https://example.com/event-page",
      "audience": "Adult",
      "eventStatus": "Scheduled",
      "eventAttendanceMode": "OfflineEventAttendanceMode"
    }
  ],
  "lastModified": "2024-02-15T19:00:00"
}
```

## JSON-LD
```/json-ld/place/{id}```
```json
{
  "@context": "https://schema.org",
  "@type": "Place",
  "@id": "https://la-vitrine.com/place/comedy-club-a/23",
  "identifier": 492,
  "name": "Comedy Club A",
  "image": {
    "@type": "ImageObject",
    "contentUrl": "https://example.com/photo.jpg",
    "description": "An example image",
    "encodingFormat": "image/jpeg",
    "creditText": "Jane Doe"
  },
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
  "maximumAttendeeCapacity": 240,
  "event": [ // List of events at this place
    {
      "type": "Event",
      "identifier": 23,
      "name": "John Smith Comedy Show",
      "startDate": "2024-02-15T19:00:00",
      "endDate": "2024-02-15T21:00:00",
      "image": "https://example.com/john-smith.jpg",
      "url": "https://example.com/event-page",
      "audience": "Adult",
      "eventStatus": "Scheduled",
      "eventAttendanceMode": "OfflineEventAttendanceMode",
      "contributions": {
        "id": 450, 
        "type": "Artiste Sur Scene",
        "contributor": {
          "id": 10,
          "type": "Person", // Person or Organization
          "name": "John Smith",
          "image": "https://www.johnsmithcomedy.com/images/john-smith.jpg",
          "url": "https://john-smith.com",
          "sameAs": [
            "https://www.linkedin.com/in/john-smith",
            "https://twitter.com/john-smith",
            "https://www.facebook.com/john-smith"
          ]
        },
      },
      "lastModified": "2024-02-15T19:00:00"
    },
    {
      "type": "ExhibitionEvent",
      "identifier": 45,
      "name": "Jane Doe Comedy Exhibition Show",
      "startDate": "2024-02-15T19:00:00",
      "endDate": "2024-02-15T21:00:00",
      "image": "https://example.com/jane-doe.jpg",
      "url": "https://example.com/event-page",
      "audience": "Adult",
      "eventStatus": "Scheduled",
      "eventAttendanceMode": "OfflineEventAttendanceMode"
    }
  ],
}

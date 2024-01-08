# Place
Notes: using "places_full" view or similar
```json
// Example of event data
// Similar to old "get_activity"
{
  "id": 492,
  "schema": "places",
  "type": "Place", // Place | Sector | Virtual Location
  "name": "Event Venue A",
  "description": "A beautiful location to host your next event",
  "address": { // Could combined to String instead, but more difficult for users to parse into JSON-LD
    "streetAddress": "789 Laughter Lane",
    "addressLocality": "Humorville",
    "addressRegion": "Quebec",
    "postalCode": "G1T 4R1",
    "addressCountry": "CA"
  },
  "latitude": 37.23332,
  "longitude": -133.43330,
  "maximumAttendeeCapacity": 240,
  "url": "https://example-venue-a.com",  // Offical Website
  "image": {
    "name": "event-venue-a.jpg",
    "contentUrl": "https://example.com/event-venue-a.jpg",
    "copyrightType": "Copyright-free", // Copyright-free | Copyright
    "encodingFormat": "image/jpeg",
    "copyrightNotice": "© Example 2024", // or creditText
  },
  "medias": [
    // Raw list of all medias
  ],
  "sameAs": [
    "https://www.linkedin.com/in/event-venue-a",
    "https://twitter.com/event-venue-a",
    "https://www.facebook.com/event-venue-a"
  ],
  "touristRegion": "Québec",
  "organismes": [], // List of organsmes as text.
  "containedInPlace": null, // Place object or id?
  "containsPlace": null, // Place object or id?
  "childrenIds": null, // List of children place ids
  "grandchildrenIds": null, // List if grandchildren place ids
  "offerIds": [53, 24, 99], // List of event offers
  "seriesIds": [9], // List of series
  "exhibitionIds": [11, 82], // List of exhibitions
  "lastModified": "2024-02-15T19:00:00"
}
```